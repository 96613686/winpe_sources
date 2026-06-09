# CStackDlg::SwitchToInteractiveDesktop(void)

- ea: `0x18001071c`
- end: `0x1800108b4`
- name: `?SwitchToInteractiveDesktop@CStackDlg@@AEAAHXZ`
- size: `408`
- prototype: `__int64 __fastcall(CStackDlg *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010364`

## callees

- `0x18001071c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180010745`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180010745`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010732`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010732`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800107d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010844`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800107d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010844`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010789`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001079c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010789`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001079c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001077a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001077a`

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
  v4 = (*(__int64 (**)(void))(qword_18001FA80 + 72))();
  *((_QWORD *)this + 5) = v4;
  if ( !v4 )
    return 0;
  v5 = *(__int64 (__fastcall **)(_QWORD))(qword_18001FA80 + 104);
  CurrentThreadId = GetCurrentThreadId();
  v7 = v5(CurrentThreadId);
  *((_QWORD *)this + 2) = v7;
  if ( !v7 )
    return 0;
  v8 = (*(__int64 (__fastcall **)(const wchar_t *, _QWORD, __int64))(qword_18001FA80 + 88))(L"winsta0", 0, 895);
  *((_QWORD *)this + 6) = v8;
  if ( !v8 )
    return 0;
  if ( !(*(unsigned int (__fastcall **)(__int64))(qword_18001FA80 + 80))(v8) )
    return 0;
  v9 = *(__int64 (__fastcall **)(_QWORD))(qword_18001FA80 + 104);
  v10 = GetCurrentThreadId();
  v11 = v9(v10);
  *((_QWORD *)this + 3) = v11;
  if ( !v11 )
    return 0;
  v12 = (*(__int64 (__fastcall **)(const wchar_t *, _QWORD, _QWORD, __int64))(qword_18001FA80 + 120))(
          L"default",
          0,
          0,
          386);
  *((_QWORD *)this + 4) = v12;
  if ( !v12 )
    return 0;
  return (*(unsigned int (__fastcall **)(__int64))(qword_18001FA80 + 112))(v12) != 0;
}

```

## disassembly

```asm
0x18001071c  mov     [rsp+arg_0], rbx
0x180010721  push    rdi
0x180010722  sub     rsp, 30h
0x180010726  mov     rdi, rcx
0x180010729  mov     [rsp+38h+TokenHandle], 0
0x180010732  call    cs:__imp_GetCurrentProcess
0x180010738  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18001073d  mov     edx, 8; DesiredAccess
0x180010742  mov     rcx, rax; ProcessHandle
0x180010745  call    cs:__imp_OpenProcessToken
0x18001074b  test    eax, eax
0x18001074d  jz      short loc_18001078F
0x18001074f  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180010754  lea     rax, [rsp+38h+arg_10]
0x180010759  mov     r9d, 4; TokenInformationLength
0x18001075f  mov     [rsp+38h+TokenInformation], 0
0x180010767  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18001076c  mov     [rsp+38h+arg_10], r9d
0x180010771  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180010776  lea     edx, [r9+8]; TokenInformationClass
0x18001077a  call    cs:__imp_GetTokenInformation
0x180010780  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180010785  test    eax, eax
0x180010787  jnz     short loc_18001079C
0x180010789  call    cs:__imp_CloseHandle
0x18001078f  xor     eax, eax
0x180010791  mov     rbx, [rsp+38h+arg_0]
0x180010796  add     rsp, 30h
0x18001079a  pop     rdi
0x18001079b  retn
0x18001079c  call    cs:__imp_CloseHandle
0x1800107a2  cmp     [rsp+38h+TokenInformation], 0
0x1800107a7  mov     [rsp+38h+TokenHandle], 0
0x1800107b0  jz      short loc_18001078F
0x1800107b2  mov     rax, cs:qword_18001FA80
0x1800107b9  mov     rax, [rax+48h]
0x1800107bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107c2  mov     [rdi+28h], rax
0x1800107c6  test    rax, rax
0x1800107c9  jz      short loc_18001078F
0x1800107cb  mov     rax, cs:qword_18001FA80
0x1800107d2  mov     rbx, [rax+68h]
0x1800107d6  call    cs:__imp_GetCurrentThreadId
0x1800107dc  mov     ecx, eax
0x1800107de  mov     rax, rbx
0x1800107e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107e6  mov     [rdi+10h], rax
0x1800107ea  test    rax, rax
0x1800107ed  jz      short loc_18001078F
0x1800107ef  mov     rax, cs:qword_18001FA80
0x1800107f6  lea     rcx, aWinsta0; "winsta0"
0x1800107fd  xor     edx, edx
0x1800107ff  mov     r8d, 37Fh
0x180010805  mov     rax, [rax+58h]
0x180010809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001080e  mov     [rdi+30h], rax
0x180010812  mov     rdx, rax
0x180010815  test    rax, rax
0x180010818  jz      loc_18001078F
0x18001081e  mov     rcx, cs:qword_18001FA80
0x180010825  mov     rax, [rcx+50h]
0x180010829  mov     rcx, rdx
0x18001082c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010831  test    eax, eax
0x180010833  jz      loc_18001078F
0x180010839  mov     rax, cs:qword_18001FA80
0x180010840  mov     rbx, [rax+68h]
0x180010844  call    cs:__imp_GetCurrentThreadId
0x18001084a  mov     ecx, eax
0x18001084c  mov     rax, rbx
0x18001084f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010854  mov     [rdi+18h], rax
0x180010858  test    rax, rax
0x18001085b  jz      loc_18001078F
0x180010861  mov     rax, cs:qword_18001FA80
0x180010868  lea     rcx, aDefault; "default"
0x18001086f  mov     r9d, 182h
0x180010875  xor     r8d, r8d
0x180010878  xor     edx, edx
0x18001087a  mov     rax, [rax+78h]
0x18001087e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010883  mov     [rdi+20h], rax
0x180010887  mov     rdx, rax
0x18001088a  test    rax, rax
0x18001088d  jz      loc_18001078F
0x180010893  mov     rcx, cs:qword_18001FA80
0x18001089a  mov     rax, [rcx+70h]
0x18001089e  mov     rcx, rdx
0x1800108a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108a6  xor     ecx, ecx
0x1800108a8  test    eax, eax
0x1800108aa  setnz   cl
0x1800108ad  mov     eax, ecx
0x1800108af  jmp     loc_180010791
```
