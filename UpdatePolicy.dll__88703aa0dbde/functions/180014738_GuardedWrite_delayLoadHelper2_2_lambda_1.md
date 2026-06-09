# GuardedWrite____delayLoadHelper2_::_2_::_lambda_1___

- ea: `0x180014738`
- end: `0x180014823`
- name: `GuardedWrite____delayLoadHelper2_::_2_::_lambda_1___`
- size: `235`
- prototype: `__int64 __fastcall(void *lpAddress, SIZE_T dwSize)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014c80`

## callees

- `0x180014738`
- `0x1800148ec`
- `0x180014ad0`
- `0x180015450`

## pseudocode

```c
char __fastcall GuardedWrite____delayLoadHelper2_::_2_::_lambda_1___(void *lpAddress, SIZE_T dwSize, __int64 a3)
{
  int v6; // ebx
  __int64 v7; // rax
  DWORD flOldProtect; // [rsp+40h] [rbp+18h] BYREF

  if ( _bChangeProtectionOfWholeDloadSection )
  {
    v6 = 0;
  }
  else
  {
    v6 = 1;
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
    DloadProtectSection(lpAddress, dwSize, 4u, &flOldProtect);
  }
  v7 = *(_QWORD *)(a3 + 8);
  **(_QWORD **)a3 = v7;
  if ( v6 )
  {
    DloadProtectSection(lpAddress, dwSize, flOldProtect, &flOldProtect);
    LOBYTE(v7) = DloadGetSRWLockFunctionPointers();
    if ( (_BYTE)v7 )
      LOBYTE(v7) = ((__int64 (__fastcall *)(unsigned __int64 *))DloadReleaseSRWLockExclusive)(&DloadSrwLock);
    else
      DloadSrwLock = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180014738  mov     [rsp+arg_0], rbx
0x18001473d  mov     [rsp+arg_8], rbp
0x180014742  mov     [rsp+arg_18], rsi
0x180014747  push    rdi
0x180014748  sub     rsp, 20h
0x18001474c  test    cs:dword_180017AB0, 1000h
0x180014756  mov     rdi, r8
0x180014759  mov     rsi, rdx
0x18001475c  mov     rbp, rcx
0x18001475f  jz      short loc_1800147BF
0x180014761  cmp     cs:__bChangeProtectionOfWholeDloadSection, 0
0x180014768  jnz     short loc_1800147BF
0x18001476a  mov     ebx, 1
0x18001476f  call    ?DloadGetSRWLockFunctionPointers@@YAEXZ; DloadGetSRWLockFunctionPointers(void)
0x180014774  test    al, al
0x180014776  jz      short loc_180014790
0x180014778  mov     rax, cs:?DloadAcquireSRWLockExclusive@@3P6AXPEA_K@ZEA; void (*DloadAcquireSRWLockExclusive)(unsigned __int64 *)
0x18001477f  lea     rcx, ?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x180014786  call    cs:__guard_dispatch_icall_fptr
0x18001478c  jmp     short loc_1800147A7
0x18001478e  pause
0x180014790  mov     rax, cs:?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x180014797  test    rax, rax
0x18001479a  jnz     short loc_18001478E
0x18001479c  lock cmpxchg cs:?DloadSrwLock@@3_KA, rbx; unsigned __int64 DloadSrwLock
0x1800147a5  jnz     short loc_180014790
0x1800147a7  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x1800147ac  mov     r8d, 4; flNewProtect
0x1800147b2  mov     rdx, rsi; dwSize
0x1800147b5  mov     rcx, rbp; lpAddress
0x1800147b8  call    ?DloadProtectSection@@YAXPEAX_KKPEAK@Z; DloadProtectSection(void *,unsigned __int64,ulong,ulong *)
0x1800147bd  jmp     short loc_1800147C1
0x1800147bf  xor     ebx, ebx
0x1800147c1  mov     rcx, [rdi]
0x1800147c4  mov     rax, [rdi+8]
0x1800147c8  mov     [rcx], rax
0x1800147cb  test    ebx, ebx
0x1800147cd  jz      short loc_18001480E
0x1800147cf  mov     r8d, [rsp+28h+flOldProtect]; flNewProtect
0x1800147d4  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x1800147d9  mov     rdx, rsi; dwSize
0x1800147dc  mov     rcx, rbp; lpAddress
0x1800147df  call    ?DloadProtectSection@@YAXPEAX_KKPEAK@Z; DloadProtectSection(void *,unsigned __int64,ulong,ulong *)
0x1800147e4  call    ?DloadGetSRWLockFunctionPointers@@YAEXZ; DloadGetSRWLockFunctionPointers(void)
0x1800147e9  test    al, al
0x1800147eb  jz      short loc_180014803
0x1800147ed  mov     rax, cs:?DloadReleaseSRWLockExclusive@@3P6AXPEA_K@ZEA; void (*DloadReleaseSRWLockExclusive)(unsigned __int64 *)
0x1800147f4  lea     rcx, ?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x1800147fb  call    cs:__guard_dispatch_icall_fptr
0x180014801  jmp     short loc_18001480E
0x180014803  mov     cs:?DloadSrwLock@@3_KA, 0; unsigned __int64 DloadSrwLock
0x18001480e  mov     rbx, [rsp+28h+arg_0]
0x180014813  mov     rbp, [rsp+28h+arg_8]
0x180014818  mov     rsi, [rsp+28h+arg_18]
0x18001481d  add     rsp, 20h
0x180014821  pop     rdi
0x180014822  retn
```
