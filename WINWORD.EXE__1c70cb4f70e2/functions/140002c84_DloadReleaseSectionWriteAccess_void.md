# DloadReleaseSectionWriteAccess(void)

- ea: `0x140002c84`
- end: `0x140002d2d`
- name: `?DloadReleaseSectionWriteAccess@@YAXXZ`
- size: `169`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140002d30`

## callees

- `0x140001020`
- `0x1400029b8`
- `0x140002b8c`
- `0x140002c84`

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
0x140002c84  sub     rsp, 28h
0x140002c88  test    cs:dword_140006660, 1000h
0x140002c92  jz      loc_140002D28
0x140002c98  cmp     cs:__bChangeProtectionOfWholeDloadSection, 0
0x140002c9f  jz      loc_140002D28
0x140002ca5  call    ?DloadGetSRWLockFunctionPointers@@YAEXZ; DloadGetSRWLockFunctionPointers(void)
0x140002caa  test    al, al
0x140002cac  jz      short loc_140002CC6
0x140002cae  mov     rax, cs:?DloadAcquireSRWLockExclusive@@3P6AXPEA_K@ZEA; void (*DloadAcquireSRWLockExclusive)(unsigned __int64 *)
0x140002cb5  lea     rcx, ?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x140002cbc  call    cs:__guard_dispatch_icall_fptr
0x140002cc2  jmp     short loc_140002CE0
0x140002cc4  pause
0x140002cc6  mov     rax, cs:?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x140002ccd  test    rax, rax
0x140002cd0  jnz     short loc_140002CC4
0x140002cd2  lea     ecx, [rax+1]
0x140002cd5  lock cmpxchg cs:?DloadSrwLock@@3_KA, rcx; unsigned __int64 DloadSrwLock
0x140002cde  jnz     short loc_140002CC6
0x140002ce0  add     cs:?DloadSectionLockCount@@3KA, 0FFFFFFFFh; ulong DloadSectionLockCount
0x140002ce7  jnz     short loc_140002CFE
0x140002ce9  mov     r8d, cs:?DloadSectionOldProtection@@3KA; flNewProtect
0x140002cf0  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x140002cf5  xor     edx, edx; dwSize
0x140002cf7  xor     ecx, ecx; lpAddress
0x140002cf9  call    ?DloadProtectSection@@YAXPEAX_KKPEAK@Z; DloadProtectSection(void *,unsigned __int64,ulong,ulong *)
0x140002cfe  call    ?DloadGetSRWLockFunctionPointers@@YAEXZ; DloadGetSRWLockFunctionPointers(void)
0x140002d03  test    al, al
0x140002d05  jz      short loc_140002D1D
0x140002d07  mov     rax, cs:?DloadReleaseSRWLockExclusive@@3P6AXPEA_K@ZEA; void (*DloadReleaseSRWLockExclusive)(unsigned __int64 *)
0x140002d0e  lea     rcx, ?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x140002d15  call    cs:__guard_dispatch_icall_fptr
0x140002d1b  jmp     short loc_140002D28
0x140002d1d  mov     cs:?DloadSrwLock@@3_KA, 0; unsigned __int64 DloadSrwLock
0x140002d28  add     rsp, 28h
0x140002d2c  retn
```
