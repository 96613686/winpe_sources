# std::_Associated_state<AppInstallResult>::_Get_value(bool)

- ea: `0x180019e60`
- end: `0x180019ff0`
- name: `?_Get_value@?$_Associated_state@UAppInstallResult@@@std@@UEAAAEAUAppInstallResult@@_N@Z`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18001afb0`

## callees

- `0x180019e60`
- `0x18002cc80`
- `0x18002ccb4`
- `0x18002eab4`
- `0x180036d78`
- `0x180036ed8`
- `0x1800563c8`
- `0x180056500`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019f6d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019f6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019f32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019f32`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180019f28`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180019f28`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Associated_state<AppInstallResult>::_Get_value(__int64 a1, char a2)
{
  __int64 v4; // rdi
  __int64 v5; // rdi
  __int64 v6; // rdx
  __int64 v9; // rax
  __int64 v10; // rax
  _BYTE v11[16]; // [rsp+20h] [rbp-30h] BYREF
  __int128 v12; // [rsp+30h] [rbp-20h] BYREF

  v4 = a1 + 56;
  v12 = (unsigned __int64)(a1 + 56);
  if ( (unsigned int)mtx_do_lock(a1 + 56) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(v4 + 76) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v4 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  BYTE8(v12) = 1;
  if ( a2 && *(_BYTE *)(a1 + 208) )
    std::_Throw_future_error2(2);
  if ( *(_QWORD *)(a1 + 40) )
  {
    v9 = std::exception_ptr::exception_ptr((std::exception_ptr *)v11, (const struct std::exception_ptr *)(a1 + 40));
    std::rethrow_exception(v9);
  }
  *(_BYTE *)(a1 + 208) = 1;
  if ( !*(_BYTE *)(a1 + 218) )
  {
    *(_BYTE *)(a1 + 218) = 1;
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 32LL))(a1, &v12);
  }
  while ( !*(_DWORD *)(a1 + 212) )
  {
    v5 = v12;
    *(_DWORD *)(v12 + 72) = -1;
    --*(_DWORD *)(v5 + 76);
    if ( !SleepConditionVariableSRW((PCONDITION_VARIABLE)(a1 + 144), (PSRWLOCK)(v5 + 16), 0xFFFFFFFF, 0) )
      abort();
    *(_DWORD *)(v5 + 72) = GetCurrentThreadId();
    ++*(_DWORD *)(v5 + 76);
  }
  if ( *(_QWORD *)(a1 + 40) )
  {
    v10 = std::exception_ptr::exception_ptr((std::exception_ptr *)v11, (const struct std::exception_ptr *)(a1 + 40));
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
  return a1 + 16;
}

```

## disassembly

```asm
0x180019e60  mov     [rsp-18h+arg_8], rbx
0x180019e65  mov     [rsp-18h+arg_10], rsi
0x180019e6a  push    rbp
0x180019e6b  push    rdi
0x180019e6c  push    r14
0x180019e6e  mov     rbp, rsp
0x180019e71  sub     rsp, 50h
0x180019e75  mov     rax, cs:__security_cookie
0x180019e7c  xor     rax, rsp
0x180019e7f  mov     [rbp+var_10], rax
0x180019e83  mov     sil, dl
0x180019e86  mov     rbx, rcx
0x180019e89  xorps   xmm0, xmm0
0x180019e8c  movups  [rbp+var_20], xmm0
0x180019e90  lea     rdi, [rcx+38h]
0x180019e94  mov     qword ptr [rbp+var_20], rdi
0x180019e98  mov     byte ptr [rbp+var_20+8], 0
0x180019e9c  mov     rcx, rdi
0x180019e9f  call    mtx_do_lock
0x180019ea4  test    eax, eax
0x180019ea6  jnz     loc_180019F9E
0x180019eac  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x180019eb3  jz      loc_180019FA9
0x180019eb9  mov     byte ptr [rbp+var_20+8], 1
0x180019ebd  test    sil, sil
0x180019ec0  jz      short loc_180019ECE
0x180019ec2  cmp     [rbx+0D0h], al
0x180019ec8  jnz     loc_180019FBB
0x180019ece  lea     rsi, [rbx+28h]
0x180019ed2  cmp     qword ptr [rsi], 0
0x180019ed6  jnz     loc_180019FC6
0x180019edc  mov     byte ptr [rbx+0D0h], 1
0x180019ee3  cmp     byte ptr [rbx+0DAh], 0
0x180019eea  jnz     short loc_180019F3E
0x180019eec  mov     byte ptr [rbx+0DAh], 1
0x180019ef3  mov     rax, [rbx]
0x180019ef6  lea     rdx, [rbp+var_20]
0x180019efa  mov     rcx, rbx
0x180019efd  mov     rax, [rax+20h]
0x180019f01  call    _guard_dispatch_icall
0x180019f06  jmp     short loc_180019F3E
0x180019f08  mov     rdi, qword ptr [rbp+var_20]
0x180019f0c  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x180019f13  dec     dword ptr [rdi+4Ch]
0x180019f16  lea     rdx, [rdi+10h]; SRWLock
0x180019f1a  xor     r9d, r9d; Flags
0x180019f1d  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180019f21  lea     rcx, [rbx+90h]; ConditionVariable
0x180019f28  call    cs:__imp_SleepConditionVariableSRW
0x180019f2e  test    eax, eax
0x180019f30  jz      short loc_180019F98
0x180019f32  call    cs:__imp_GetCurrentThreadId
0x180019f38  mov     [rdi+48h], eax
0x180019f3b  inc     dword ptr [rdi+4Ch]
0x180019f3e  cmp     dword ptr [rbx+0D4h], 0
0x180019f45  jz      short loc_180019F08
0x180019f47  cmp     qword ptr [rbx+28h], 0
0x180019f4c  jnz     loc_180019FDB
0x180019f52  cmp     byte ptr [rbp+var_20+8], 0
0x180019f56  jz      short loc_180019F73
0x180019f58  mov     rdx, qword ptr [rbp+var_20]
0x180019f5c  sub     dword ptr [rdx+4Ch], 1
0x180019f60  jnz     short loc_180019F73
0x180019f62  mov     dword ptr [rdx+48h], 0FFFFFFFFh
0x180019f69  lea     rcx, [rdx+10h]; SRWLock
0x180019f6d  call    cs:__imp_ReleaseSRWLockExclusive
0x180019f73  lea     rax, [rbx+10h]
0x180019f77  mov     rcx, [rbp+var_10]
0x180019f7b  xor     rcx, rsp; StackCookie
0x180019f7e  call    __security_check_cookie
0x180019f83  lea     r11, [rsp+50h+var_s0]
0x180019f88  mov     rbx, [r11+28h]
0x180019f8c  mov     rsi, [r11+30h]
0x180019f90  mov     rsp, r11
0x180019f93  pop     r14
0x180019f95  pop     rdi
0x180019f96  pop     rbp
0x180019f97  retn
0x180019f98  call    abort
0x180019f9e  mov     ecx, 5; int
0x180019fa3  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180019fa9  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x180019fb0  mov     ecx, 6; int
0x180019fb5  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180019fbb  mov     ecx, 2
0x180019fc0  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x180019fc6  mov     rdx, rsi; struct std::exception_ptr *
0x180019fc9  lea     rcx, [rbp+var_30]; this
0x180019fcd  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x180019fd2  mov     rcx, rax
0x180019fd5  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x180019fdb  mov     rdx, rsi; struct std::exception_ptr *
0x180019fde  lea     rcx, [rbp+var_30]; this
0x180019fe2  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x180019fe7  mov     rcx, rax
0x180019fea  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
```
