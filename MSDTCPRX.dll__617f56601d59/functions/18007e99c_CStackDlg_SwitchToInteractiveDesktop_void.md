# CStackDlg::SwitchToInteractiveDesktop(void)

- ea: `0x18007e99c`
- end: `0x18007eb34`
- name: `?SwitchToInteractiveDesktop@CStackDlg@@AEAAHXZ`
- size: `408`
- prototype: `__int64 __fastcall(CStackDlg *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007e5ec`

## callees

- `0x18007e99c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007e9b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007e9b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007ea56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007eac4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007ea56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007eac4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007e9c5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007e9c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ea09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ea1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ea09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ea1c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007e9fa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007e9fa`

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
  v4 = (*(__int64 (**)(void))(qword_1800D7100 + 72))();
  *((_QWORD *)this + 5) = v4;
  if ( !v4 )
    return 0;
  v5 = *(__int64 (__fastcall **)(_QWORD))(qword_1800D7100 + 104);
  CurrentThreadId = GetCurrentThreadId();
  v7 = v5(CurrentThreadId);
  *((_QWORD *)this + 2) = v7;
  if ( !v7 )
    return 0;
  v8 = (*(__int64 (__fastcall **)(const wchar_t *, _QWORD, __int64))(qword_1800D7100 + 88))(L"winsta0", 0, 895);
  *((_QWORD *)this + 6) = v8;
  if ( !v8 )
    return 0;
  if ( !(*(unsigned int (__fastcall **)(__int64))(qword_1800D7100 + 80))(v8) )
    return 0;
  v9 = *(__int64 (__fastcall **)(_QWORD))(qword_1800D7100 + 104);
  v10 = GetCurrentThreadId();
  v11 = v9(v10);
  *((_QWORD *)this + 3) = v11;
  if ( !v11 )
    return 0;
  v12 = (*(__int64 (__fastcall **)(const wchar_t *, _QWORD, _QWORD, __int64))(qword_1800D7100 + 120))(
          L"default",
          0,
          0,
          386);
  *((_QWORD *)this + 4) = v12;
  if ( !v12 )
    return 0;
  return (*(unsigned int (__fastcall **)(__int64))(qword_1800D7100 + 112))(v12) != 0;
}

```

## disassembly

```asm
0x18007e99c  mov     [rsp+arg_0], rbx
0x18007e9a1  push    rdi
0x18007e9a2  sub     rsp, 30h
0x18007e9a6  mov     rdi, rcx
0x18007e9a9  mov     [rsp+38h+TokenHandle], 0
0x18007e9b2  call    cs:__imp_GetCurrentProcess
0x18007e9b8  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18007e9bd  mov     edx, 8; DesiredAccess
0x18007e9c2  mov     rcx, rax; ProcessHandle
0x18007e9c5  call    cs:__imp_OpenProcessToken
0x18007e9cb  test    eax, eax
0x18007e9cd  jz      short loc_18007EA0F
0x18007e9cf  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18007e9d4  lea     rax, [rsp+38h+arg_10]
0x18007e9d9  mov     r9d, 4; TokenInformationLength
0x18007e9df  mov     [rsp+38h+TokenInformation], 0
0x18007e9e7  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18007e9ec  mov     [rsp+38h+arg_10], r9d
0x18007e9f1  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18007e9f6  lea     edx, [r9+8]; TokenInformationClass
0x18007e9fa  call    cs:__imp_GetTokenInformation
0x18007ea00  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18007ea05  test    eax, eax
0x18007ea07  jnz     short loc_18007EA1C
0x18007ea09  call    cs:__imp_CloseHandle
0x18007ea0f  xor     eax, eax
0x18007ea11  mov     rbx, [rsp+38h+arg_0]
0x18007ea16  add     rsp, 30h
0x18007ea1a  pop     rdi
0x18007ea1b  retn
0x18007ea1c  call    cs:__imp_CloseHandle
0x18007ea22  cmp     [rsp+38h+TokenInformation], 0
0x18007ea27  mov     [rsp+38h+TokenHandle], 0
0x18007ea30  jz      short loc_18007EA0F
0x18007ea32  mov     rax, cs:qword_1800D7100
0x18007ea39  mov     rax, [rax+48h]
0x18007ea3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ea42  mov     [rdi+28h], rax
0x18007ea46  test    rax, rax
0x18007ea49  jz      short loc_18007EA0F
0x18007ea4b  mov     rax, cs:qword_1800D7100
0x18007ea52  mov     rbx, [rax+68h]
0x18007ea56  call    cs:__imp_GetCurrentThreadId
0x18007ea5c  mov     ecx, eax
0x18007ea5e  mov     rax, rbx
0x18007ea61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ea66  mov     [rdi+10h], rax
0x18007ea6a  test    rax, rax
0x18007ea6d  jz      short loc_18007EA0F
0x18007ea6f  mov     rax, cs:qword_1800D7100
0x18007ea76  lea     rcx, aWinsta0; "winsta0"
0x18007ea7d  xor     edx, edx
0x18007ea7f  mov     r8d, 37Fh
0x18007ea85  mov     rax, [rax+58h]
0x18007ea89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ea8e  mov     [rdi+30h], rax
0x18007ea92  mov     rdx, rax
0x18007ea95  test    rax, rax
0x18007ea98  jz      loc_18007EA0F
0x18007ea9e  mov     rcx, cs:qword_1800D7100
0x18007eaa5  mov     rax, [rcx+50h]
0x18007eaa9  mov     rcx, rdx
0x18007eaac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eab1  test    eax, eax
0x18007eab3  jz      loc_18007EA0F
0x18007eab9  mov     rax, cs:qword_1800D7100
0x18007eac0  mov     rbx, [rax+68h]
0x18007eac4  call    cs:__imp_GetCurrentThreadId
0x18007eaca  mov     ecx, eax
0x18007eacc  mov     rax, rbx
0x18007eacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ead4  mov     [rdi+18h], rax
0x18007ead8  test    rax, rax
0x18007eadb  jz      loc_18007EA0F
0x18007eae1  mov     rax, cs:qword_1800D7100
0x18007eae8  lea     rcx, aDefault; "default"
0x18007eaef  mov     r9d, 182h
0x18007eaf5  xor     r8d, r8d
0x18007eaf8  xor     edx, edx
0x18007eafa  mov     rax, [rax+78h]
0x18007eafe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb03  mov     [rdi+20h], rax
0x18007eb07  mov     rdx, rax
0x18007eb0a  test    rax, rax
0x18007eb0d  jz      loc_18007EA0F
0x18007eb13  mov     rcx, cs:qword_1800D7100
0x18007eb1a  mov     rax, [rcx+70h]
0x18007eb1e  mov     rcx, rdx
0x18007eb21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb26  xor     ecx, ecx
0x18007eb28  test    eax, eax
0x18007eb2a  setnz   cl
0x18007eb2d  mov     eax, ecx
0x18007eb2f  jmp     loc_18007EA11
```
