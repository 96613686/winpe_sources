# DloadReleaseSectionWriteAccess(void)

- ea: `0x180014bd0`
- end: `0x180014c79`
- name: `?DloadReleaseSectionWriteAccess@@YAXXZ`
- size: `169`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014c80`

## callees

- `0x1800148ec`
- `0x180014ad0`
- `0x180014bd0`
- `0x180015450`

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
0x180014bd0  sub     rsp, 28h
0x180014bd4  test    cs:dword_180017AB0, 1000h
0x180014bde  jz      loc_180014C74
0x180014be4  cmp     cs:__bChangeProtectionOfWholeDloadSection, 0
0x180014beb  jz      loc_180014C74
0x180014bf1  call    ?DloadGetSRWLockFunctionPointers@@YAEXZ; DloadGetSRWLockFunctionPointers(void)
0x180014bf6  test    al, al
0x180014bf8  jz      short loc_180014C12
0x180014bfa  mov     rax, cs:?DloadAcquireSRWLockExclusive@@3P6AXPEA_K@ZEA; void (*DloadAcquireSRWLockExclusive)(unsigned __int64 *)
0x180014c01  lea     rcx, ?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x180014c08  call    cs:__guard_dispatch_icall_fptr
0x180014c0e  jmp     short loc_180014C2C
0x180014c10  pause
0x180014c12  mov     rax, cs:?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x180014c19  test    rax, rax
0x180014c1c  jnz     short loc_180014C10
0x180014c1e  lea     ecx, [rax+1]
0x180014c21  lock cmpxchg cs:?DloadSrwLock@@3_KA, rcx; unsigned __int64 DloadSrwLock
0x180014c2a  jnz     short loc_180014C12
0x180014c2c  add     cs:?DloadSectionLockCount@@3KA, 0FFFFFFFFh; ulong DloadSectionLockCount
0x180014c33  jnz     short loc_180014C4A
0x180014c35  mov     r8d, cs:?DloadSectionOldProtection@@3KA; flNewProtect
0x180014c3c  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x180014c41  xor     edx, edx; dwSize
0x180014c43  xor     ecx, ecx; lpAddress
0x180014c45  call    ?DloadProtectSection@@YAXPEAX_KKPEAK@Z; DloadProtectSection(void *,unsigned __int64,ulong,ulong *)
0x180014c4a  call    ?DloadGetSRWLockFunctionPointers@@YAEXZ; DloadGetSRWLockFunctionPointers(void)
0x180014c4f  test    al, al
0x180014c51  jz      short loc_180014C69
0x180014c53  mov     rax, cs:?DloadReleaseSRWLockExclusive@@3P6AXPEA_K@ZEA; void (*DloadReleaseSRWLockExclusive)(unsigned __int64 *)
0x180014c5a  lea     rcx, ?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x180014c61  call    cs:__guard_dispatch_icall_fptr
0x180014c67  jmp     short loc_180014C74
0x180014c69  mov     cs:?DloadSrwLock@@3_KA, 0; unsigned __int64 DloadSrwLock
0x180014c74  add     rsp, 28h
0x180014c78  retn
```
