# CExec::ConnectStdDevicePipe(void *,bool,bool)

- ea: `0x1400162fc`
- end: `0x14001647a`
- name: `?ConnectStdDevicePipe@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX_N1@Z`
- size: `382`
- prototype: `LPHANDLE __fastcall(LPHANDLE lpTargetHandle, HANDLE hSourceHandle, unsigned __int8, unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x140016cc0`

## callees

- `0x140002310`
- `0x14000e828`
- `0x1400162fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400163fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400163fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140016411`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140016411`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001634a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140016353`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001634a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140016353`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14001637d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14001637d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016409`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016409`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400163e8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400163e8`

## string_xrefs

- `0x14001644e`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140016468`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c
LPHANDLE __fastcall CExec::ConnectStdDevicePipe(
        LPHANDLE lpTargetHandle,
        HANDLE hSourceHandle,
        unsigned __int8 a3,
        unsigned __int8 a4)
{
  DWORD v6; // esi
  HANDLE CurrentProcess; // rbx
  HANDLE v8; // rax
  const char *v9; // r9
  HANDLE v10; // rsi
  const char *v11; // r9
  HANDLE v12; // rbp
  DWORD LastError; // ebx
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *lpTargetHandle = (HANDLE)-1LL;
  v6 = (a3 + 1) << 30;
  if ( hSourceHandle )
  {
    *lpTargetHandle = (HANDLE)-1LL;
    CurrentProcess = GetCurrentProcess();
    v8 = GetCurrentProcess();
    if ( !DuplicateHandle(v8, hSourceHandle, CurrentProcess, lpTargetHandle, v6 | 0x100000, 1, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        v9);
  }
  else
  {
    *(_OWORD *)&SecurityAttributes.nLength = 0;
    *(&SecurityAttributes.bInheritHandle + 1) = 0;
    SecurityAttributes.nLength = 24;
    SecurityAttributes.bInheritHandle = 1;
    v10 = CreateFileW(L"nul", v6, 0, &SecurityAttributes, 3u, (a4 << 30) | ((a3 ^ 1u) << 31), 0);
    v12 = *lpTargetHandle;
    if ( (char *)*lpTargetHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(v12);
      SetLastError(LastError);
    }
    *lpTargetHandle = v10;
    if ( (((unsigned __int64)v10 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x86,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        v11);
  }
  return lpTargetHandle;
}

```

## disassembly

```asm
0x1400162fc  mov     [rsp+arg_10], rbx
0x140016301  push    rbp
0x140016302  push    rsi
0x140016303  push    rdi
0x140016304  sub     rsp, 70h
0x140016308  mov     rax, cs:__security_cookie
0x14001630f  xor     rax, rsp
0x140016312  mov     [rsp+88h+var_20], rax
0x140016317  mov     rbp, rdx
0x14001631a  mov     rdi, rcx
0x14001631d  mov     [rsp+88h+var_40], rcx
0x140016322  mov     [rsp+88h+var_48], 0
0x14001632a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001632e  mov     [rcx], rax
0x140016331  mov     [rsp+88h+var_48], 1
0x140016339  movzx   esi, r8b
0x14001633d  inc     esi
0x14001633f  shl     esi, 1Eh
0x140016342  test    rdx, rdx
0x140016345  jz      short loc_140016390
0x140016347  mov     [rcx], rax
0x14001634a  call    cs:__imp_GetCurrentProcess
0x140016350  mov     rbx, rax
0x140016353  call    cs:__imp_GetCurrentProcess
0x140016359  bts     esi, 14h
0x14001635d  mov     [rsp+88h+dwOptions], 0; dwOptions
0x140016365  mov     [rsp+88h+bInheritHandle], 1; bInheritHandle
0x14001636d  mov     [rsp+88h+dwDesiredAccess], esi; dwDesiredAccess
0x140016371  mov     r9, rdi; lpTargetHandle
0x140016374  mov     r8, rbx; hTargetProcessHandle
0x140016377  mov     rdx, rbp; hSourceHandle
0x14001637a  mov     rcx, rax; hSourceProcessHandle
0x14001637d  call    cs:__imp_DuplicateHandle
0x140016383  test    eax, eax
0x140016385  jz      loc_140016460
0x14001638b  jmp     loc_140016426
0x140016390  xorps   xmm0, xmm0
0x140016393  xor     eax, eax
0x140016395  movups  xmmword ptr [rsp+88h+SecurityAttributes.nLength], xmm0
0x14001639a  mov     qword ptr [rsp+88h+SecurityAttributes.bInheritHandle], rax
0x14001639f  mov     [rsp+88h+SecurityAttributes.nLength], 18h
0x1400163a7  mov     [rsp+88h+SecurityAttributes.bInheritHandle], 1
0x1400163af  movzx   ecx, r8b
0x1400163b3  xor     ecx, 1
0x1400163b6  shl     ecx, 1Fh
0x1400163b9  movzx   eax, r9b
0x1400163bd  shl     eax, 1Eh
0x1400163c0  or      ecx, eax
0x1400163c2  mov     qword ptr [rsp+88h+dwOptions], 0; hTemplateFile
0x1400163cb  mov     [rsp+88h+bInheritHandle], ecx; dwFlagsAndAttributes
0x1400163cf  mov     [rsp+88h+dwDesiredAccess], 3; dwCreationDisposition
0x1400163d7  lea     r9, [rsp+88h+SecurityAttributes]; lpSecurityAttributes
0x1400163dc  xor     r8d, r8d; dwShareMode
0x1400163df  mov     edx, esi; dwDesiredAccess
0x1400163e1  lea     rcx, FileName; "nul"
0x1400163e8  call    cs:__imp_CreateFileW
0x1400163ee  mov     rsi, rax
0x1400163f1  mov     rbp, [rdi]
0x1400163f4  lea     rax, [rbp-1]
0x1400163f8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400163fc  ja      short loc_140016417
0x1400163fe  call    cs:__imp_GetLastError
0x140016404  mov     ebx, eax
0x140016406  mov     rcx, rbp; hObject
0x140016409  call    cs:__imp_CloseHandle
0x14001640f  mov     ecx, ebx; dwErrCode
0x140016411  call    cs:__imp_SetLastError
0x140016417  mov     [rdi], rsi
0x14001641a  lea     rax, [rsi+1]
0x14001641e  test    rax, 0FFFFFFFFFFFFFFFEh
0x140016424  jz      short loc_140016446
0x140016426  mov     rax, rdi
0x140016429  mov     rcx, [rsp+88h+var_20]
0x14001642e  xor     rcx, rsp; StackCookie
0x140016431  call    __security_check_cookie
0x140016436  mov     rbx, [rsp+88h+arg_10]
0x14001643e  add     rsp, 70h
0x140016442  pop     rdi
0x140016443  pop     rsi
0x140016444  pop     rbp
0x140016445  retn
0x140016446  mov     rcx, [rsp+88h]; this
0x14001644e  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\service\\cexec\\l"...
0x140016455  mov     edx, 86h; void *
0x14001645a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140016460  mov     rcx, [rsp+88h]; this
0x140016468  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\service\\cexec\\l"...
0x14001646f  mov     edx, 71h ; 'q'; void *
0x140016474  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
