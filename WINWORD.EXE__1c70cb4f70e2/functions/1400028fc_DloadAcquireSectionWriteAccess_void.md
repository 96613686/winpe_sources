# DloadAcquireSectionWriteAccess(void)

- ea: `0x1400028fc`
- end: `0x1400029b6`
- name: `?DloadAcquireSectionWriteAccess@@YAXXZ`
- size: `186`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140002d30`

## callees

- `0x140001020`
- `0x1400028fc`
- `0x1400029b8`
- `0x140002b8c`

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
0x1400028fc  push    rbx
0x1400028fe  sub     rsp, 20h
0x140002902  test    cs:dword_140006660, 1000h
0x14000290c  jz      loc_1400029B0
0x140002912  cmp     cs:__bChangeProtectionOfWholeDloadSection, 0
0x140002919  jz      loc_1400029B0
0x14000291f  call    ?DloadGetSRWLockFunctionPointers@@YAEXZ; DloadGetSRWLockFunctionPointers(void)
0x140002924  mov     ebx, 1
0x140002929  test    al, al
0x14000292b  jz      short loc_140002945
0x14000292d  mov     rax, cs:?DloadAcquireSRWLockExclusive@@3P6AXPEA_K@ZEA; void (*DloadAcquireSRWLockExclusive)(unsigned __int64 *)
0x140002934  lea     rcx, ?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x14000293b  call    cs:__guard_dispatch_icall_fptr
0x140002941  jmp     short loc_14000295C
0x140002943  pause
0x140002945  mov     rax, cs:?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x14000294c  test    rax, rax
0x14000294f  jnz     short loc_140002943
0x140002951  lock cmpxchg cs:?DloadSrwLock@@3_KA, rbx; unsigned __int64 DloadSrwLock
0x14000295a  jnz     short loc_140002945
0x14000295c  mov     eax, cs:?DloadSectionLockCount@@3KA; ulong DloadSectionLockCount
0x140002962  add     eax, ebx
0x140002964  mov     cs:?DloadSectionLockCount@@3KA, eax; ulong DloadSectionLockCount
0x14000296a  cmp     eax, ebx
0x14000296c  jnz     short loc_140002982
0x14000296e  xor     edx, edx; dwSize
0x140002970  lea     r9, ?DloadSectionOldProtection@@3KA; lpflOldProtect
0x140002977  xor     ecx, ecx; lpAddress
0x140002979  lea     r8d, [rdx+4]; flNewProtect
0x14000297d  call    ?DloadProtectSection@@YAXPEAX_KKPEAK@Z; DloadProtectSection(void *,unsigned __int64,ulong,ulong *)
0x140002982  call    ?DloadGetSRWLockFunctionPointers@@YAEXZ; DloadGetSRWLockFunctionPointers(void)
0x140002987  test    al, al
0x140002989  jz      short loc_1400029A5
0x14000298b  mov     rax, cs:?DloadReleaseSRWLockExclusive@@3P6AXPEA_K@ZEA; void (*DloadReleaseSRWLockExclusive)(unsigned __int64 *)
0x140002992  lea     rcx, ?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x140002999  add     rsp, 20h
0x14000299d  pop     rbx
0x14000299e  jmp     cs:__guard_dispatch_icall_fptr
0x1400029a5  mov     cs:?DloadSrwLock@@3_KA, 0; unsigned __int64 DloadSrwLock
0x1400029b0  add     rsp, 20h
0x1400029b4  pop     rbx
0x1400029b5  retn
```
