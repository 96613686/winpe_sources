# CStackDlg::SwitchToInteractiveDesktop(void)

- ea: `0x180089f1c`
- end: `0x18008a0b4`
- name: `?SwitchToInteractiveDesktop@CStackDlg@@AEAAHXZ`
- size: `408`
- prototype: `__int64 __fastcall(CStackDlg *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180089b60`

## callees

- `0x180089f1c`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089fd6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008a044`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089fd6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008a044`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180089f45`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180089f45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180089f32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180089f32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089f89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089f9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089f89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089f9c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180089f7a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180089f7a`

## pseudocode

```c
_BOOL8 __fastcall CStackDlg::SwitchToInteractiveDesktop(CStackDlg *this)
{
  HANDLE CurrentProcess; // rax
  __int64 v4; // rax
  __int64 (__fastcall *v5)(_QWORD); // rbx
  DWORD CurrentThreadId; // eax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 (__fastcall *v9)(_QWORD); // rbx
  DWORD v10; // eax
  __int64 v11; // rax
  __int64 v12; // rax
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    return 0;
  TokenInformation = 0;
  ReturnLength = 4;
  if ( !GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
  {
    CloseHandle(TokenHandle);
    return 0;
  }
  CloseHandle(TokenHandle);
  TokenHandle = 0;
  if ( !TokenInformation )
    return 0;
  v4 = (*(__int64 (**)(void))(qword_18015DBA8 + 72))();
  *((_QWORD *)this + 5) = v4;
  if ( !v4 )
    return 0;
  v5 = *(__int64 (__fastcall **)(_QWORD))(qword_18015DBA8 + 104);
  CurrentThreadId = GetCurrentThreadId();
  v7 = v5(CurrentThreadId);
  *((_QWORD *)this + 2) = v7;
  if ( !v7 )
    return 0;
  v8 = (*(__int64 (__fastcall **)(const wchar_t *, _QWORD, __int64))(qword_18015DBA8 + 88))(L"winsta0", 0, 895);
  *((_QWORD *)this + 6) = v8;
  if ( !v8 )
    return 0;
  if ( !(*(unsigned int (__fastcall **)(__int64))(qword_18015DBA8 + 80))(v8) )
    return 0;
  v9 = *(__int64 (__fastcall **)(_QWORD))(qword_18015DBA8 + 104);
  v10 = GetCurrentThreadId();
  v11 = v9(v10);
  *((_QWORD *)this + 3) = v11;
  if ( !v11 )
    return 0;
  v12 = (*(__int64 (__fastcall **)(const wchar_t *, _QWORD, _QWORD, __int64))(qword_18015DBA8 + 120))(
          L"default",
          0,
          0,
          386);
  *((_QWORD *)this + 4) = v12;
  if ( !v12 )
    return 0;
  return (*(unsigned int (__fastcall **)(__int64))(qword_18015DBA8 + 112))(v12) != 0;
}

```

## disassembly

```asm
0x180089f1c  mov     [rsp+arg_0], rbx
0x180089f21  push    rdi
0x180089f22  sub     rsp, 30h
0x180089f26  mov     rdi, rcx
0x180089f29  mov     [rsp+38h+TokenHandle], 0
0x180089f32  call    cs:__imp_GetCurrentProcess
0x180089f38  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180089f3d  mov     edx, 8; DesiredAccess
0x180089f42  mov     rcx, rax; ProcessHandle
0x180089f45  call    cs:__imp_OpenProcessToken
0x180089f4b  test    eax, eax
0x180089f4d  jz      short loc_180089F8F
0x180089f4f  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180089f54  lea     rax, [rsp+38h+arg_10]
0x180089f59  mov     r9d, 4; TokenInformationLength
0x180089f5f  mov     [rsp+38h+TokenInformation], 0
0x180089f67  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180089f6c  mov     [rsp+38h+arg_10], r9d
0x180089f71  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180089f76  lea     edx, [r9+8]; TokenInformationClass
0x180089f7a  call    cs:__imp_GetTokenInformation
0x180089f80  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180089f85  test    eax, eax
0x180089f87  jnz     short loc_180089F9C
0x180089f89  call    cs:__imp_CloseHandle
0x180089f8f  xor     eax, eax
0x180089f91  mov     rbx, [rsp+38h+arg_0]
0x180089f96  add     rsp, 30h
0x180089f9a  pop     rdi
0x180089f9b  retn
0x180089f9c  call    cs:__imp_CloseHandle
0x180089fa2  cmp     [rsp+38h+TokenInformation], 0
0x180089fa7  mov     [rsp+38h+TokenHandle], 0
0x180089fb0  jz      short loc_180089F8F
0x180089fb2  mov     rax, cs:qword_18015DBA8
0x180089fb9  mov     rax, [rax+48h]
0x180089fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089fc2  mov     [rdi+28h], rax
0x180089fc6  test    rax, rax
0x180089fc9  jz      short loc_180089F8F
0x180089fcb  mov     rax, cs:qword_18015DBA8
0x180089fd2  mov     rbx, [rax+68h]
0x180089fd6  call    cs:__imp_GetCurrentThreadId
0x180089fdc  mov     ecx, eax
0x180089fde  mov     rax, rbx
0x180089fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089fe6  mov     [rdi+10h], rax
0x180089fea  test    rax, rax
0x180089fed  jz      short loc_180089F8F
0x180089fef  mov     rax, cs:qword_18015DBA8
0x180089ff6  lea     rcx, aWinsta0; "winsta0"
0x180089ffd  xor     edx, edx
0x180089fff  mov     r8d, 37Fh
0x18008a005  mov     rax, [rax+58h]
0x18008a009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a00e  mov     [rdi+30h], rax
0x18008a012  mov     rdx, rax
0x18008a015  test    rax, rax
0x18008a018  jz      loc_180089F8F
0x18008a01e  mov     rcx, cs:qword_18015DBA8
0x18008a025  mov     rax, [rcx+50h]
0x18008a029  mov     rcx, rdx
0x18008a02c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a031  test    eax, eax
0x18008a033  jz      loc_180089F8F
0x18008a039  mov     rax, cs:qword_18015DBA8
0x18008a040  mov     rbx, [rax+68h]
0x18008a044  call    cs:__imp_GetCurrentThreadId
0x18008a04a  mov     ecx, eax
0x18008a04c  mov     rax, rbx
0x18008a04f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a054  mov     [rdi+18h], rax
0x18008a058  test    rax, rax
0x18008a05b  jz      loc_180089F8F
0x18008a061  mov     rax, cs:qword_18015DBA8
0x18008a068  lea     rcx, aDefault; "default"
0x18008a06f  mov     r9d, 182h
0x18008a075  xor     r8d, r8d
0x18008a078  xor     edx, edx
0x18008a07a  mov     rax, [rax+78h]
0x18008a07e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a083  mov     [rdi+20h], rax
0x18008a087  mov     rdx, rax
0x18008a08a  test    rax, rax
0x18008a08d  jz      loc_180089F8F
0x18008a093  mov     rcx, cs:qword_18015DBA8
0x18008a09a  mov     rax, [rcx+70h]
0x18008a09e  mov     rcx, rdx
0x18008a0a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a0a6  xor     ecx, ecx
0x18008a0a8  test    eax, eax
0x18008a0aa  setnz   cl
0x18008a0ad  mov     eax, ecx
0x18008a0af  jmp     loc_180089F91
```
