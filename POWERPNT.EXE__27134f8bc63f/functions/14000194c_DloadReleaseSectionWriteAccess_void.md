# DloadReleaseSectionWriteAccess(void)

- ea: `0x14000194c`
- end: `0x1400019f5`
- name: `?DloadReleaseSectionWriteAccess@@YAXXZ`
- size: `169`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140001650`

## callees

- `0x140001540`
- `0x14000194c`
- `0x140001f00`
- `0x140002150`

## pseudocode

```c
void DloadReleaseSectionWriteAccess(void)
{
  DWORD flOldProtect; // [rsp+38h] [rbp+10h] BYREF

  if ( _bChangeProtectionOfWholeDloadSection )
  {
    if ( DloadGetSRWLockFunctionPointers() )
    {
      ((void (__fastcall *)(unsigned __int64 *))DloadAcquireSRWLockExclusive)(&DloadSrwLock);
    }
    else
    {
      do
      {
        while ( DloadSrwLock )
          _mm_pause();
      }
      while ( _InterlockedCompareExchange64((volatile signed __int64 *)&DloadSrwLock, 1, 0) );
    }
    if ( !--DloadSectionLockCount )
      DloadProtectSection(0, 0, DloadSectionOldProtection, &flOldProtect);
    if ( DloadGetSRWLockFunctionPointers() )
      ((void (__fastcall *)(unsigned __int64 *))DloadReleaseSRWLockExclusive)(&DloadSrwLock);
    else
      DloadSrwLock = 0;
  }
}

```

## disassembly

```asm
0x14000194c  sub     rsp, 28h
0x140001950  test    cs:dword_140003400, 1000h
0x14000195a  jz      loc_1400019F0
0x140001960  cmp     cs:__bChangeProtectionOfWholeDloadSection, 0
0x140001967  jz      loc_1400019F0
0x14000196d  call    ?DloadGetSRWLockFunctionPointers@@YAEXZ; DloadGetSRWLockFunctionPointers(void)
0x140001972  test    al, al
0x140001974  jz      short loc_14000198E
0x140001976  mov     rax, cs:?DloadAcquireSRWLockExclusive@@3P6AXPEA_K@ZEA; void (*DloadAcquireSRWLockExclusive)(unsigned __int64 *)
0x14000197d  lea     rcx, ?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x140001984  call    cs:__guard_dispatch_icall_fptr
0x14000198a  jmp     short loc_1400019A8
0x14000198c  pause
0x14000198e  mov     rax, cs:?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x140001995  test    rax, rax
0x140001998  jnz     short loc_14000198C
0x14000199a  lea     ecx, [rax+1]
0x14000199d  lock cmpxchg cs:?DloadSrwLock@@3_KA, rcx; unsigned __int64 DloadSrwLock
0x1400019a6  jnz     short loc_14000198E
0x1400019a8  add     cs:?DloadSectionLockCount@@3KA, 0FFFFFFFFh; ulong DloadSectionLockCount
0x1400019af  jnz     short loc_1400019C6
0x1400019b1  mov     r8d, cs:?DloadSectionOldProtection@@3KA; flNewProtect
0x1400019b8  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x1400019bd  xor     edx, edx; dwSize
0x1400019bf  xor     ecx, ecx; lpAddress
0x1400019c1  call    ?DloadProtectSection@@YAXPEAX_KKPEAK@Z; DloadProtectSection(void *,unsigned __int64,ulong,ulong *)
0x1400019c6  call    ?DloadGetSRWLockFunctionPointers@@YAEXZ; DloadGetSRWLockFunctionPointers(void)
0x1400019cb  test    al, al
0x1400019cd  jz      short loc_1400019E5
0x1400019cf  mov     rax, cs:?DloadReleaseSRWLockExclusive@@3P6AXPEA_K@ZEA; void (*DloadReleaseSRWLockExclusive)(unsigned __int64 *)
0x1400019d6  lea     rcx, ?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x1400019dd  call    cs:__guard_dispatch_icall_fptr
0x1400019e3  jmp     short loc_1400019F0
0x1400019e5  mov     cs:?DloadSrwLock@@3_KA, 0; unsigned __int64 DloadSrwLock
0x1400019f0  add     rsp, 28h
0x1400019f4  retn
```
