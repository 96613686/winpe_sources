# AdjustPrivilegesToLoadNewUserRegHive(void)

- ea: `0x18005aac4`
- end: `0x18005ac21`
- name: `?AdjustPrivilegesToLoadNewUserRegHive@@YAJXZ`
- size: `349`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180042460`
- `0x18005c350`

## callees

- `0x180003ea0`
- `0x180005df8`
- `0x180009064`
- `0x180009084`
- `0x18005aac4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005aadc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005aadc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005aaf1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005aaf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005aba9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005abe7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005aba9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005abe7`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18005ab7e`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18005ab7e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18005ab44`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18005ab44`

## string_xrefs

- `0x18005ab00`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemutils.cpp`
- `0x18005abb8`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemutils.cpp`
- `0x18005abfa`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 AdjustPrivilegesToLoadNewUserRegHive(void)
{
  HANDLE CurrentThread; // rax
  const char *v1; // r9
  int LastError; // ebx
  struct _TOKEN_PRIVILEGES *v3; // rdi
  __int64 v4; // rbx
  char *v5; // rsi
  const char *v6; // r9
  __int64 v7; // rdx
  int PreviousState; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *TokenHandle; // [rsp+40h] [rbp+8h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x28u, 0, &TokenHandle) )
  {
    v3 = (struct _TOKEN_PRIVILEGES *)operator new[](0x1Cu);
    v3->PrivilegeCount = 2;
    v4 = 0;
    do
    {
      v5 = (char *)v3 + 12 * v4;
      if ( !LookupPrivilegeValueW(0, off_18006CED0[v4], (PLUID)(v5 + 4)) )
      {
        v7 = 43;
        goto LABEL_12;
      }
      *((_DWORD *)v5 + 3) = 2;
      v4 = (unsigned int)(v4 + 1);
    }
    while ( (unsigned int)v4 < 2 );
    if ( !AdjustTokenPrivileges(TokenHandle, 0, v3, 0x1Cu, 0, 0) )
    {
      v7 = 53;
LABEL_12:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v7,
                    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemutils.cpp",
                    v6);
      operator delete(v3);
      goto LABEL_13;
    }
    operator delete(v3);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    LastError = 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1B,
                  (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemutils.cpp",
                  v1);
LABEL_13:
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
  }
  if ( LastError >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3F,
    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemutils.cpp",
    (const char *)(unsigned int)LastError,
    PreviousState);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18005aac4  mov     [rsp+arg_8], rbx
0x18005aac9  mov     [rsp+arg_10], rsi
0x18005aace  push    rdi
0x18005aacf  sub     rsp, 30h
0x18005aad3  mov     [rsp+38h+TokenHandle], 0
0x18005aadc  call    cs:__imp_GetCurrentThread
0x18005aae2  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x18005aae7  xor     r8d, r8d; OpenAsSelf
0x18005aaea  lea     edx, [r8+28h]; DesiredAccess
0x18005aaee  mov     rcx, rax; ThreadHandle
0x18005aaf1  call    cs:__imp_OpenThreadToken
0x18005aaf7  test    eax, eax
0x18005aaf9  jnz     short loc_18005AB16
0x18005aafb  mov     rcx, [rsp+38h]; this
0x18005ab00  lea     r8, aOnecoreBaseLan_0; "onecore\\base\\languageoverlay\\service"...
0x18005ab07  lea     edx, [rax+1Bh]; void *
0x18005ab0a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005ab0f  mov     ebx, eax
0x18005ab11  jmp     loc_18005ABD8
0x18005ab16  mov     ecx, 1Ch; unsigned __int64
0x18005ab1b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005ab20  mov     rdi, rax
0x18005ab23  mov     dword ptr [rax], 2
0x18005ab29  xor     ebx, ebx
0x18005ab2b  lea     rcx, [rbx+rbx*2]
0x18005ab2f  lea     rsi, [rdi+rcx*4]
0x18005ab33  lea     rax, off_18006CED0; "SeRestorePrivilege"
0x18005ab3a  lea     r8, [rsi+4]; lpLuid
0x18005ab3e  mov     rdx, [rax+rbx*8]; lpName
0x18005ab42  xor     ecx, ecx; lpSystemName
0x18005ab44  call    cs:__imp_LookupPrivilegeValueW
0x18005ab4a  test    eax, eax
0x18005ab4c  jz      short loc_18005ABB3
0x18005ab4e  mov     dword ptr [rsi+0Ch], 2
0x18005ab55  inc     ebx
0x18005ab57  cmp     ebx, 2
0x18005ab5a  jb      short loc_18005AB2B
0x18005ab5c  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x18005ab65  mov     [rsp+38h+PreviousState], 0; PreviousState
0x18005ab6e  mov     r9d, 1Ch; BufferLength
0x18005ab74  mov     r8, rdi; NewState
0x18005ab77  xor     edx, edx; DisableAllPrivileges
0x18005ab79  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18005ab7e  call    cs:__imp_AdjustTokenPrivileges
0x18005ab84  test    eax, eax
0x18005ab86  jnz     short loc_18005AB8D
0x18005ab88  lea     edx, [rax+35h]
0x18005ab8b  jmp     short loc_18005ABB8
0x18005ab8d  mov     edx, 10h; unsigned __int64
0x18005ab92  mov     rcx, rdi; void *
0x18005ab95  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005ab9a  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18005ab9f  lea     rax, [rcx-1]
0x18005aba3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005aba7  ja      short loc_18005ABAF
0x18005aba9  call    cs:__imp_CloseHandle
0x18005abaf  xor     ebx, ebx
0x18005abb1  jmp     short loc_18005ABEE
0x18005abb3  mov     edx, 2Bh ; '+'; void *
0x18005abb8  lea     r8, aOnecoreBaseLan_0; "onecore\\base\\languageoverlay\\service"...
0x18005abbf  mov     rcx, [rsp+38h]; this
0x18005abc4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005abc9  mov     ebx, eax
0x18005abcb  mov     edx, 10h; unsigned __int64
0x18005abd0  mov     rcx, rdi; void *
0x18005abd3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005abd8  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18005abdd  lea     rax, [rcx-1]
0x18005abe1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005abe5  ja      short loc_18005ABEE
0x18005abe7  call    cs:__imp_CloseHandle
0x18005abed  nop
0x18005abee  test    ebx, ebx
0x18005abf0  jns     short loc_18005AC0F
0x18005abf2  mov     rcx, [rsp+38h]; this
0x18005abf7  mov     r9d, ebx; char *
0x18005abfa  lea     r8, aOnecoreBaseLan_0; "onecore\\base\\languageoverlay\\service"...
0x18005ac01  mov     edx, 3Fh ; '?'; void *
0x18005ac06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ac0b  mov     eax, ebx
0x18005ac0d  jmp     short loc_18005AC11
0x18005ac0f  xor     eax, eax
0x18005ac11  mov     rbx, [rsp+38h+arg_8]
0x18005ac16  mov     rsi, [rsp+38h+arg_10]
0x18005ac1b  add     rsp, 30h
0x18005ac1f  pop     rdi
0x18005ac20  retn
```
