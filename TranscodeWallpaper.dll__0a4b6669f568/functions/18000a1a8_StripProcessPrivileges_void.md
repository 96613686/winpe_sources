# StripProcessPrivileges(void)

- ea: `0x18000a1a8`
- end: `0x18000a34f`
- name: `?StripProcessPrivileges@@YAJXZ`
- size: `423`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000ceb0`

## callees

- `0x180002540`
- `0x18000257c`
- `0x180005ab4`
- `0x180005ad4`
- `0x18000a1a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a21c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a21c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000a1d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000a1d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a1c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a1c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a2c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a2f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a337`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a2c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a2f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a337`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a20e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a25f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a20e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a25f`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000a29c`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000a29c`

## string_xrefs

- `0x18000a1e1`: `shell\themes\wallpapertranscodecontainer\dll\transcodewallpaper.cpp`
- `0x18000a2d4`: `shell\themes\wallpapertranscodecontainer\dll\transcodewallpaper.cpp`
- `0x18000a310`: `shell\themes\wallpapertranscodecontainer\dll\transcodewallpaper.cpp`

## pseudocode

```c
__int64 StripProcessPrivileges(void)
{
  HANDLE CurrentProcess; // rax
  const char *v1; // r9
  __int64 v2; // rdx
  unsigned int LastError; // ebx
  struct _TOKEN_PRIVILEGES *v4; // rbx
  const char *v5; // r9
  DWORD i; // ecx
  __int64 v7; // rax
  unsigned __int64 v8; // rdx
  __int64 v9; // rdx
  unsigned int v11; // edi
  unsigned __int64 v12; // rdx
  int ReturnLength; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  DWORD TokenInformationLength; // [rsp+40h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    v2 = 17;
LABEL_3:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v2,
                  (unsigned int)"shell\\themes\\wallpapertranscodecontainer\\dll\\transcodewallpaper.cpp",
                  v1);
LABEL_21:
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return LastError;
  }
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenPrivileges, 0, 0, &TokenInformationLength) )
    goto LABEL_20;
  if ( GetLastError() != 122 )
  {
    v2 = 29;
    goto LABEL_3;
  }
  v4 = (struct _TOKEN_PRIVILEGES *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
LABEL_20:
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"shell\\themes\\wallpapertranscodecontainer\\dll\\transcodewallpaper.cpp",
      (const char *)0x8007000ELL,
      ReturnLength);
    goto LABEL_21;
  }
  if ( !GetTokenInformation(TokenHandle, TokenPrivileges, v4, TokenInformationLength, &TokenInformationLength) )
  {
    v9 = 34;
    goto LABEL_16;
  }
  for ( i = 0; i < v4->PrivilegeCount; v4->Privileges[v7].Attributes = 4 )
    v7 = i++;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, v4, TokenInformationLength, 0, 0) )
  {
    v9 = 43;
LABEL_16:
    v11 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v9,
            (unsigned int)"shell\\themes\\wallpapertranscodecontainer\\dll\\transcodewallpaper.cpp",
            v5);
    operator delete(v4, v12);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return v11;
  }
  operator delete(v4, v8);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x18000a1a8  mov     [rsp-8+arg_10], rbx
0x18000a1ad  mov     [rsp-8+arg_18], rdi
0x18000a1b2  push    rbp
0x18000a1b3  mov     rbp, rsp
0x18000a1b6  sub     rsp, 30h
0x18000a1ba  xor     edi, edi
0x18000a1bc  mov     [rbp+TokenHandle], rdi
0x18000a1c0  call    cs:__imp_GetCurrentProcess
0x18000a1c6  mov     rcx, rax; ProcessHandle
0x18000a1c9  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000a1cd  lea     edx, [rdi+28h]; DesiredAccess
0x18000a1d0  call    cs:__imp_OpenProcessToken
0x18000a1d6  test    eax, eax
0x18000a1d8  jnz     short loc_18000A1F4
0x18000a1da  lea     edx, [rdi+11h]; void *
0x18000a1dd  mov     rcx, [rbp+8]; this
0x18000a1e1  lea     r8, aShellThemesWal; "shell\\themes\\wallpapertranscodecontai"...
0x18000a1e8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a1ed  mov     ebx, eax
0x18000a1ef  jmp     loc_18000A329
0x18000a1f4  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000a1f8  lea     rax, [rbp+TokenInformationLength]
0x18000a1fc  xor     r9d, r9d; TokenInformationLength
0x18000a1ff  mov     [rbp+TokenInformationLength], edi
0x18000a202  xor     r8d, r8d; TokenInformation
0x18000a205  mov     [rsp+30h+ReturnLength], rax; int
0x18000a20a  lea     edx, [r9+3]; TokenInformationClass
0x18000a20e  call    cs:__imp_GetTokenInformation
0x18000a214  test    eax, eax
0x18000a216  jnz     loc_18000A30C
0x18000a21c  call    cs:__imp_GetLastError
0x18000a222  cmp     eax, 7Ah ; 'z'
0x18000a225  jnz     loc_18000A302
0x18000a22b  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x18000a22e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a235  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000a23a  mov     rbx, rax
0x18000a23d  test    rax, rax
0x18000a240  jz      loc_18000A30C
0x18000a246  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18000a24a  lea     rax, [rbp+TokenInformationLength]
0x18000a24e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000a252  mov     r8, rbx; TokenInformation
0x18000a255  mov     edx, 3; TokenInformationClass
0x18000a25a  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18000a25f  call    cs:__imp_GetTokenInformation
0x18000a265  test    eax, eax
0x18000a267  jz      short loc_18000A2CB
0x18000a269  mov     ecx, edi
0x18000a26b  cmp     [rbx], edi
0x18000a26d  jbe     short loc_18000A285
0x18000a26f  mov     eax, ecx
0x18000a271  inc     ecx
0x18000a273  inc     rax
0x18000a276  lea     rax, [rax+rax*2]
0x18000a27a  mov     dword ptr [rbx+rax*4], 4
0x18000a281  cmp     ecx, [rbx]
0x18000a283  jb      short loc_18000A26F
0x18000a285  mov     r9d, [rbp+TokenInformationLength]; BufferLength
0x18000a289  mov     r8, rbx; NewState
0x18000a28c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000a290  xor     edx, edx; DisableAllPrivileges
0x18000a292  mov     [rsp+30h+var_8], rdi; ReturnLength
0x18000a297  mov     [rsp+30h+ReturnLength], rdi; PreviousState
0x18000a29c  call    cs:__imp_AdjustTokenPrivileges
0x18000a2a2  test    eax, eax
0x18000a2a4  jnz     short loc_18000A2AB
0x18000a2a6  lea     edx, [rax+2Bh]
0x18000a2a9  jmp     short loc_18000A2D0
0x18000a2ab  mov     rcx, rbx; void *
0x18000a2ae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a2b3  mov     rcx, [rbp+TokenHandle]; hObject
0x18000a2b7  lea     rax, [rcx-1]
0x18000a2bb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a2bf  ja      short loc_18000A2C7
0x18000a2c1  call    cs:__imp_CloseHandle
0x18000a2c7  xor     eax, eax
0x18000a2c9  jmp     short loc_18000A33F
0x18000a2cb  mov     edx, 22h ; '"'; void *
0x18000a2d0  mov     rcx, [rbp+8]; this
0x18000a2d4  lea     r8, aShellThemesWal; "shell\\themes\\wallpapertranscodecontai"...
0x18000a2db  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a2e0  mov     rcx, rbx; void *
0x18000a2e3  mov     edi, eax
0x18000a2e5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a2ea  mov     rcx, [rbp+TokenHandle]; hObject
0x18000a2ee  lea     rdx, [rcx-1]
0x18000a2f2  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000a2f6  ja      short loc_18000A2FE
0x18000a2f8  call    cs:__imp_CloseHandle
0x18000a2fe  mov     eax, edi
0x18000a300  jmp     short loc_18000A33F
0x18000a302  mov     edx, 1Dh
0x18000a307  jmp     loc_18000A1DD
0x18000a30c  mov     rcx, [rbp+8]; this
0x18000a310  lea     r8, aShellThemesWal; "shell\\themes\\wallpapertranscodecontai"...
0x18000a317  mov     ebx, 8007000Eh
0x18000a31c  mov     edx, 20h ; ' '; void *
0x18000a321  mov     r9d, ebx; char *
0x18000a324  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a329  mov     rcx, [rbp+TokenHandle]; hObject
0x18000a32d  lea     rdx, [rcx-1]
0x18000a331  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000a335  ja      short loc_18000A33D
0x18000a337  call    cs:__imp_CloseHandle
0x18000a33d  mov     eax, ebx
0x18000a33f  mov     rbx, [rsp+30h+arg_10]
0x18000a344  mov     rdi, [rsp+30h+arg_18]
0x18000a349  add     rsp, 30h
0x18000a34d  pop     rbp
0x18000a34e  retn
```
