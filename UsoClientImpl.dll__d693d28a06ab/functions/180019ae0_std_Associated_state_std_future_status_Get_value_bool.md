# std::_Associated_state<std::future_status>::_Get_value(bool)

- ea: `0x180019ae0`
- end: `0x180019c6d`
- name: `?_Get_value@?$_Associated_state@W4future_status@std@@@std@@UEAAAEAW4future_status@2@_N@Z`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001acd0`

## callees

- `0x180019ae0`
- `0x18002cc80`
- `0x18002ccb4`
- `0x18002eab4`
- `0x180036d78`
- `0x180036ed8`
- `0x1800563c8`
- `0x180056500`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019bea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019bea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019baf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019baf`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180019ba5`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180019ba5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Associated_state<enum std::future_status>::_Get_value(__int64 a1, char a2)
{
  __int64 v4; // rdi
  __int64 v5; // rdi
  __int64 v6; // rdx
  __int64 v9; // rax
  __int64 v10; // rax
  _BYTE v11[16]; // [rsp+20h] [rbp-30h] BYREF
  __int128 v12; // [rsp+30h] [rbp-20h] BYREF

  v4 = a1 + 32;
  v12 = (unsigned __int64)(a1 + 32);
  if ( (unsigned int)mtx_do_lock(a1 + 32) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(v4 + 76) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v4 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  BYTE8(v12) = 1;
  if ( a2 && *(_BYTE *)(a1 + 184) )
    std::_Throw_future_error2(2);
  if ( *(_QWORD *)(a1 + 16) )
  {
    v9 = std::exception_ptr::exception_ptr((std::exception_ptr *)v11, (const struct std::exception_ptr *)(a1 + 16));
    std::rethrow_exception(v9);
  }
  *(_BYTE *)(a1 + 184) = 1;
  if ( !*(_BYTE *)(a1 + 194) )
  {
    *(_BYTE *)(a1 + 194) = 1;
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 32LL))(a1, &v12);
  }
  while ( !*(_DWORD *)(a1 + 188) )
  {
    v5 = v12;
    *(_DWORD *)(v12 + 72) = -1;
    --*(_DWORD *)(v5 + 76);
    if ( !SleepConditionVariableSRW((PCONDITION_VARIABLE)(a1 + 120), (PSRWLOCK)(v5 + 16), 0xFFFFFFFF, 0) )
      abort();
    *(_DWORD *)(v5 + 72) = GetCurrentThreadId();
    ++*(_DWORD *)(v5 + 76);
  }
  if ( *(_QWORD *)(a1 + 16) )
  {
    v10 = std::exception_ptr::exception_ptr((std::exception_ptr *)v11, (const struct std::exception_ptr *)(a1 + 16));
    std::rethrow_exception(v10);
  }
  if ( BYTE8(v12) )
  {
    v6 = v12;
    if ( (*(_DWORD *)(v12 + 76))-- == 1 )
    {
      *(_DWORD *)(v6 + 72) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)(v6 + 16));
    }
  }
  return a1 + 12;
}

```

## disassembly

```asm
0x180019ae0  mov     [rsp-18h+arg_8], rbx
0x180019ae5  mov     [rsp-18h+arg_10], rsi
0x180019aea  push    rbp
0x180019aeb  push    rdi
0x180019aec  push    r14
0x180019aee  mov     rbp, rsp
0x180019af1  sub     rsp, 50h
0x180019af5  mov     rax, cs:__security_cookie
0x180019afc  xor     rax, rsp
0x180019aff  mov     [rbp+var_10], rax
0x180019b03  mov     sil, dl
0x180019b06  mov     rbx, rcx
0x180019b09  xorps   xmm0, xmm0
0x180019b0c  movups  [rbp+var_20], xmm0
0x180019b10  lea     rdi, [rcx+20h]
0x180019b14  mov     qword ptr [rbp+var_20], rdi
0x180019b18  mov     byte ptr [rbp+var_20+8], 0
0x180019b1c  mov     rcx, rdi
0x180019b1f  call    mtx_do_lock
0x180019b24  test    eax, eax
0x180019b26  jnz     loc_180019C1B
0x180019b2c  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x180019b33  jz      loc_180019C26
0x180019b39  mov     byte ptr [rbp+var_20+8], 1
0x180019b3d  test    sil, sil
0x180019b40  jz      short loc_180019B4E
0x180019b42  cmp     [rbx+0B8h], al
0x180019b48  jnz     loc_180019C38
0x180019b4e  lea     rsi, [rbx+10h]
0x180019b52  cmp     qword ptr [rsi], 0
0x180019b56  jnz     loc_180019C43
0x180019b5c  mov     byte ptr [rbx+0B8h], 1
0x180019b63  cmp     byte ptr [rbx+0C2h], 0
0x180019b6a  jnz     short loc_180019BBB
0x180019b6c  mov     byte ptr [rbx+0C2h], 1
0x180019b73  mov     rax, [rbx]
0x180019b76  lea     rdx, [rbp+var_20]
0x180019b7a  mov     rcx, rbx
0x180019b7d  mov     rax, [rax+20h]
0x180019b81  call    _guard_dispatch_icall
0x180019b86  jmp     short loc_180019BBB
0x180019b88  mov     rdi, qword ptr [rbp+var_20]
0x180019b8c  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x180019b93  dec     dword ptr [rdi+4Ch]
0x180019b96  lea     rdx, [rdi+10h]; SRWLock
0x180019b9a  xor     r9d, r9d; Flags
0x180019b9d  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180019ba1  lea     rcx, [rbx+78h]; ConditionVariable
0x180019ba5  call    cs:__imp_SleepConditionVariableSRW
0x180019bab  test    eax, eax
0x180019bad  jz      short loc_180019C15
0x180019baf  call    cs:__imp_GetCurrentThreadId
0x180019bb5  mov     [rdi+48h], eax
0x180019bb8  inc     dword ptr [rdi+4Ch]
0x180019bbb  cmp     dword ptr [rbx+0BCh], 0
0x180019bc2  jz      short loc_180019B88
0x180019bc4  cmp     qword ptr [rbx+10h], 0
0x180019bc9  jnz     loc_180019C58
0x180019bcf  cmp     byte ptr [rbp+var_20+8], 0
0x180019bd3  jz      short loc_180019BF0
0x180019bd5  mov     rdx, qword ptr [rbp+var_20]
0x180019bd9  sub     dword ptr [rdx+4Ch], 1
0x180019bdd  jnz     short loc_180019BF0
0x180019bdf  mov     dword ptr [rdx+48h], 0FFFFFFFFh
0x180019be6  lea     rcx, [rdx+10h]; SRWLock
0x180019bea  call    cs:__imp_ReleaseSRWLockExclusive
0x180019bf0  lea     rax, [rbx+0Ch]
0x180019bf4  mov     rcx, [rbp+var_10]
0x180019bf8  xor     rcx, rsp; StackCookie
0x180019bfb  call    __security_check_cookie
0x180019c00  lea     r11, [rsp+50h+var_s0]
0x180019c05  mov     rbx, [r11+28h]
0x180019c09  mov     rsi, [r11+30h]
0x180019c0d  mov     rsp, r11
0x180019c10  pop     r14
0x180019c12  pop     rdi
0x180019c13  pop     rbp
0x180019c14  retn
0x180019c15  call    abort
0x180019c1b  mov     ecx, 5; int
0x180019c20  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180019c26  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x180019c2d  mov     ecx, 6; int
0x180019c32  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180019c38  mov     ecx, 2
0x180019c3d  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x180019c43  mov     rdx, rsi; struct std::exception_ptr *
0x180019c46  lea     rcx, [rbp+var_30]; this
0x180019c4a  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x180019c4f  mov     rcx, rax
0x180019c52  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x180019c58  mov     rdx, rsi; struct std::exception_ptr *
0x180019c5b  lea     rcx, [rbp+var_30]; this
0x180019c5f  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x180019c64  mov     rcx, rax
0x180019c67  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
```
