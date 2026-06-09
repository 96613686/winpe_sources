# DloadAcquireSectionWriteAccess(void)

- ea: `0x18001482c`
- end: `0x1800148e6`
- name: `?DloadAcquireSectionWriteAccess@@YAXXZ`
- size: `186`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014c80`

## callees

- `0x18001482c`
- `0x1800148ec`
- `0x180014ad0`
- `0x180015450`

## pseudocode

```c
void DloadAcquireSectionWriteAccess(void)
{
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
    if ( ++DloadSectionLockCount == 1 )
      DloadProtectSection(0, 0, 4u, &DloadSectionOldProtection);
    if ( DloadGetSRWLockFunctionPointers() )
      ((void (__fastcall *)(unsigned __int64 *))DloadReleaseSRWLockExclusive)(&DloadSrwLock);
    else
      DloadSrwLock = 0;
  }
}

```

## disassembly

```asm
0x18001482c  push    rbx
0x18001482e  sub     rsp, 20h
0x180014832  test    cs:dword_180017AB0, 1000h
0x18001483c  jz      loc_1800148E0
0x180014842  cmp     cs:__bChangeProtectionOfWholeDloadSection, 0
0x180014849  jz      loc_1800148E0
0x18001484f  call    ?DloadGetSRWLockFunctionPointers@@YAEXZ; DloadGetSRWLockFunctionPointers(void)
0x180014854  mov     ebx, 1
0x180014859  test    al, al
0x18001485b  jz      short loc_180014875
0x18001485d  mov     rax, cs:?DloadAcquireSRWLockExclusive@@3P6AXPEA_K@ZEA; void (*DloadAcquireSRWLockExclusive)(unsigned __int64 *)
0x180014864  lea     rcx, ?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x18001486b  call    cs:__guard_dispatch_icall_fptr
0x180014871  jmp     short loc_18001488C
0x180014873  pause
0x180014875  mov     rax, cs:?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x18001487c  test    rax, rax
0x18001487f  jnz     short loc_180014873
0x180014881  lock cmpxchg cs:?DloadSrwLock@@3_KA, rbx; unsigned __int64 DloadSrwLock
0x18001488a  jnz     short loc_180014875
0x18001488c  mov     eax, cs:?DloadSectionLockCount@@3KA; ulong DloadSectionLockCount
0x180014892  add     eax, ebx
0x180014894  mov     cs:?DloadSectionLockCount@@3KA, eax; ulong DloadSectionLockCount
0x18001489a  cmp     eax, ebx
0x18001489c  jnz     short loc_1800148B2
0x18001489e  xor     edx, edx; dwSize
0x1800148a0  lea     r9, ?DloadSectionOldProtection@@3KA; lpflOldProtect
0x1800148a7  xor     ecx, ecx; lpAddress
0x1800148a9  lea     r8d, [rdx+4]; flNewProtect
0x1800148ad  call    ?DloadProtectSection@@YAXPEAX_KKPEAK@Z; DloadProtectSection(void *,unsigned __int64,ulong,ulong *)
0x1800148b2  call    ?DloadGetSRWLockFunctionPointers@@YAEXZ; DloadGetSRWLockFunctionPointers(void)
0x1800148b7  test    al, al
0x1800148b9  jz      short loc_1800148D5
0x1800148bb  mov     rax, cs:?DloadReleaseSRWLockExclusive@@3P6AXPEA_K@ZEA; void (*DloadReleaseSRWLockExclusive)(unsigned __int64 *)
0x1800148c2  lea     rcx, ?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x1800148c9  add     rsp, 20h
0x1800148cd  pop     rbx
0x1800148ce  jmp     cs:__guard_dispatch_icall_fptr
0x1800148d5  mov     cs:?DloadSrwLock@@3_KA, 0; unsigned __int64 DloadSrwLock
0x1800148e0  add     rsp, 20h
0x1800148e4  pop     rbx
0x1800148e5  retn
```
