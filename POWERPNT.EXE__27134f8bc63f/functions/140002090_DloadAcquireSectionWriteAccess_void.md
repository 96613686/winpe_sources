# DloadAcquireSectionWriteAccess(void)

- ea: `0x140002090`
- end: `0x14000214a`
- name: `?DloadAcquireSectionWriteAccess@@YAXXZ`
- size: `186`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140001650`

## callees

- `0x140001540`
- `0x140001f00`
- `0x140002090`
- `0x140002150`

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
0x140002090  push    rbx
0x140002092  sub     rsp, 20h
0x140002096  test    cs:dword_140003400, 1000h
0x1400020a0  jz      loc_140002144
0x1400020a6  cmp     cs:__bChangeProtectionOfWholeDloadSection, 0
0x1400020ad  jz      loc_140002144
0x1400020b3  call    ?DloadGetSRWLockFunctionPointers@@YAEXZ; DloadGetSRWLockFunctionPointers(void)
0x1400020b8  mov     ebx, 1
0x1400020bd  test    al, al
0x1400020bf  jz      short loc_1400020D9
0x1400020c1  mov     rax, cs:?DloadAcquireSRWLockExclusive@@3P6AXPEA_K@ZEA; void (*DloadAcquireSRWLockExclusive)(unsigned __int64 *)
0x1400020c8  lea     rcx, ?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x1400020cf  call    cs:__guard_dispatch_icall_fptr
0x1400020d5  jmp     short loc_1400020F0
0x1400020d7  pause
0x1400020d9  mov     rax, cs:?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x1400020e0  test    rax, rax
0x1400020e3  jnz     short loc_1400020D7
0x1400020e5  lock cmpxchg cs:?DloadSrwLock@@3_KA, rbx; unsigned __int64 DloadSrwLock
0x1400020ee  jnz     short loc_1400020D9
0x1400020f0  mov     eax, cs:?DloadSectionLockCount@@3KA; ulong DloadSectionLockCount
0x1400020f6  add     eax, ebx
0x1400020f8  mov     cs:?DloadSectionLockCount@@3KA, eax; ulong DloadSectionLockCount
0x1400020fe  cmp     eax, ebx
0x140002100  jnz     short loc_140002116
0x140002102  xor     edx, edx; dwSize
0x140002104  lea     r9, ?DloadSectionOldProtection@@3KA; lpflOldProtect
0x14000210b  xor     ecx, ecx; lpAddress
0x14000210d  lea     r8d, [rdx+4]; flNewProtect
0x140002111  call    ?DloadProtectSection@@YAXPEAX_KKPEAK@Z; DloadProtectSection(void *,unsigned __int64,ulong,ulong *)
0x140002116  call    ?DloadGetSRWLockFunctionPointers@@YAEXZ; DloadGetSRWLockFunctionPointers(void)
0x14000211b  test    al, al
0x14000211d  jz      short loc_140002139
0x14000211f  mov     rax, cs:?DloadReleaseSRWLockExclusive@@3P6AXPEA_K@ZEA; void (*DloadReleaseSRWLockExclusive)(unsigned __int64 *)
0x140002126  lea     rcx, ?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x14000212d  add     rsp, 20h
0x140002131  pop     rbx
0x140002132  jmp     cs:__guard_dispatch_icall_fptr
0x140002139  mov     cs:?DloadSrwLock@@3_KA, 0; unsigned __int64 DloadSrwLock
0x140002144  add     rsp, 20h
0x140002148  pop     rbx
0x140002149  retn
```
