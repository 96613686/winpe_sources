# Windows::CallerToken::Get(bool)

- ea: `0x140268990`
- end: `0x140268ba9`
- name: `?Get@CallerToken@Windows@@SA?AV?$unique_ptr@VCallerToken@Windows@@U?$default_delete@VCallerToken@Windows@@@std@@@std@@_N@Z`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14029a4d0`

## callees

- `0x14003c578`
- `0x14018b0dc`
- `0x140268574`
- `0x140268990`
- `0x140379070`
- `0x1403790d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140268a1c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140268a1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140268a05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140268a05`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140268a3f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140268a3f`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1402689ca`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1402689ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1402689f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140268a92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1402689f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140268a92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1402689e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140268a7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1402689e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140268a7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1402689ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140268a8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140268ab3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140268b42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1402689ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140268a8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140268ab3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140268b42`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140268af1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140268af1`

## string_xrefs

- `0x140268a2e`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\CallerToken.cpp`
- `0x140268b96`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\CallerToken.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
_QWORD *__fastcall Windows::CallerToken::Get(_QWORD *a1, char a2)
{
  char *v3; // rcx
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  const char *v6; // r9
  HANDLE *MostPreferredLoggedOnSessionToken; // r14
  HANDLE v8; // r12
  HANDLE v9; // r15
  DWORD v10; // ebx
  const char *v11; // r9
  _QWORD *v12; // rax
  _QWORD *v14; // rax
  HANDLE hObject; // [rsp+48h] [rbp-40h] BYREF
  int TokenInformation; // [rsp+50h] [rbp-38h] BYREF
  HANDLE ReturnLength; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v3 = 0;
  hObject = 0;
  if ( a2 )
  {
    if ( CoImpersonateClient() >= 0 )
    {
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        LastError = GetLastError();
        CloseHandle(hObject);
        SetLastError(LastError);
      }
      hObject = 0;
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &hObject) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0xA6,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\CallerToken.cpp",
          v6);
      CoRevertToSelf();
    }
    v3 = (char *)hObject;
  }
  if ( ((unsigned __int64)(v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    MostPreferredLoggedOnSessionToken = (HANDLE *)Windows::CallerToken::GetMostPreferredLoggedOnSessionToken(&ReturnLength);
    if ( &hObject != MostPreferredLoggedOnSessionToken )
    {
      v8 = *MostPreferredLoggedOnSessionToken;
      v9 = hObject;
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        v10 = GetLastError();
        CloseHandle(v9);
        SetLastError(v10);
      }
      hObject = v8;
      *MostPreferredLoggedOnSessionToken = 0;
    }
    if ( (char *)ReturnLength - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(ReturnLength);
    v3 = (char *)hObject;
  }
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LODWORD(ReturnLength) = 0;
    TokenInformation = 0;
    if ( !GetTokenInformation(v3, TokenSessionId, &TokenInformation, 4u, (PDWORD)&ReturnLength) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xB2,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\CallerToken.cpp",
        v11);
    if ( TokenInformation )
    {
      v12 = operator new(0x10u);
      *v12 = &Windows::CallerToken::`vftable';
      v12[1] = hObject;
      *a1 = v12;
      return a1;
    }
    v3 = (char *)hObject;
  }
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v3);
  v14 = operator new(0x10u);
  *v14 = &Windows::CallerToken::`vftable';
  v14[1] = 0;
  *a1 = v14;
  return a1;
}

```

## disassembly

```asm
0x140268990  mov     [rsp+arg_8], rbx
0x140268995  mov     [rsp+arg_10], rsi
0x14026899a  push    r12
0x14026899c  push    r14
0x14026899e  push    r15
0x1402689a0  sub     rsp, 70h
0x1402689a4  mov     rax, cs:__security_cookie
0x1402689ab  xor     rax, rsp
0x1402689ae  mov     [rsp+88h+var_28], rax
0x1402689b3  mov     rsi, rcx
0x1402689b6  mov     [rsp+88h+var_50], rcx
0x1402689bb  xor     ecx, ecx
0x1402689bd  mov     [rsp+88h+hObject], rcx
0x1402689c2  test    dl, dl
0x1402689c4  jz      loc_140268A4A
0x1402689ca  call    cs:__imp_CoImpersonateClient
0x1402689d0  test    eax, eax
0x1402689d2  js      short loc_140268A45
0x1402689d4  mov     r14, [rsp+88h+hObject]
0x1402689d9  lea     rax, [r14-1]
0x1402689dd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1402689e1  ja      short loc_1402689FC
0x1402689e3  call    cs:__imp_GetLastError
0x1402689e9  mov     ebx, eax
0x1402689eb  mov     rcx, r14; hObject
0x1402689ee  call    cs:__imp_CloseHandle
0x1402689f4  mov     ecx, ebx; dwErrCode
0x1402689f6  call    cs:__imp_SetLastError
0x1402689fc  mov     [rsp+88h+hObject], 0
0x140268a05  call    cs:__imp_GetCurrentThread
0x140268a0b  lea     r9, [rsp+88h+hObject]; TokenHandle
0x140268a10  mov     edx, 0Eh; DesiredAccess
0x140268a15  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x140268a19  mov     rcx, rax; ThreadHandle
0x140268a1c  call    cs:__imp_OpenThreadToken
0x140268a22  mov     rcx, [rsp+88h]; this
0x140268a2a  test    eax, eax
0x140268a2c  jnz     short loc_140268A3F
0x140268a2e  lea     r8, aCW1SSrcOrchest_54; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140268a35  mov     edx, 0A6h; void *
0x140268a3a  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x140268a3f  call    cs:__imp_CoRevertToSelf
0x140268a45  mov     rcx, [rsp+88h+hObject]
0x140268a4a  lea     rax, [rcx+1]
0x140268a4e  test    rax, 0FFFFFFFFFFFFFFFEh
0x140268a54  jnz     short loc_140268ABE
0x140268a56  lea     rcx, [rsp+88h+var_30]
0x140268a5b  call    ?GetMostPreferredLoggedOnSessionToken@CallerToken@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; Windows::CallerToken::GetMostPreferredLoggedOnSessionToken(void)
0x140268a60  mov     r14, rax
0x140268a63  lea     rax, [rsp+88h+hObject]
0x140268a68  cmp     rax, r14
0x140268a6b  jz      short loc_140268AA4
0x140268a6d  mov     r12, [r14]
0x140268a70  mov     r15, [rsp+88h+hObject]
0x140268a75  lea     rcx, [r15-1]
0x140268a79  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140268a7d  ja      short loc_140268A98
0x140268a7f  call    cs:__imp_GetLastError
0x140268a85  mov     ebx, eax
0x140268a87  mov     rcx, r15; hObject
0x140268a8a  call    cs:__imp_CloseHandle
0x140268a90  mov     ecx, ebx; dwErrCode
0x140268a92  call    cs:__imp_SetLastError
0x140268a98  mov     [rsp+88h+hObject], r12
0x140268a9d  mov     qword ptr [r14], 0
0x140268aa4  mov     rcx, [rsp+88h+var_30]; hObject
0x140268aa9  lea     rax, [rcx-1]
0x140268aad  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140268ab1  ja      short loc_140268AB9
0x140268ab3  call    cs:__imp_CloseHandle
0x140268ab9  mov     rcx, [rsp+88h+hObject]; TokenHandle
0x140268abe  lea     rax, [rcx-1]
0x140268ac2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140268ac6  ja      short loc_140268B38
0x140268ac8  mov     dword ptr [rsp+88h+var_30], 0
0x140268ad0  mov     [rsp+88h+TokenInformation], 0
0x140268ad8  lea     rax, [rsp+88h+var_30]
0x140268add  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x140268ae2  mov     r9d, 4; TokenInformationLength
0x140268ae8  lea     r8, [rsp+88h+TokenInformation]; TokenInformation
0x140268aed  lea     edx, [r9+8]; TokenInformationClass
0x140268af1  call    cs:__imp_GetTokenInformation
0x140268af7  mov     rcx, [rsp+88h]; this
0x140268aff  test    eax, eax
0x140268b01  jz      loc_140268B96
0x140268b07  cmp     [rsp+88h+TokenInformation], 0
0x140268b0c  jz      short loc_140268B33
0x140268b0e  mov     ecx, 10h; Size
0x140268b13  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140268b18  lea     rcx, ??_7CallerToken@Windows@@6B@; const Windows::CallerToken::`vftable'
0x140268b1f  mov     [rax], rcx
0x140268b22  mov     rcx, [rsp+88h+hObject]
0x140268b27  mov     [rax+8], rcx
0x140268b2b  mov     [rsi], rax
0x140268b2e  mov     rax, rsi
0x140268b31  jmp     short loc_140268B72
0x140268b33  mov     rcx, [rsp+88h+hObject]; hObject
0x140268b38  lea     rax, [rcx-1]
0x140268b3c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140268b40  ja      short loc_140268B49
0x140268b42  call    cs:__imp_CloseHandle
0x140268b48  nop
0x140268b49  jmp     short loc_140268B50
0x140268b4b  mov     rsi, [rsp+88h+var_50]
0x140268b50  mov     ecx, 10h; Size
0x140268b55  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140268b5a  lea     rcx, ??_7CallerToken@Windows@@6B@; const Windows::CallerToken::`vftable'
0x140268b61  mov     [rax], rcx
0x140268b64  mov     qword ptr [rax+8], 0
0x140268b6c  mov     [rsi], rax
0x140268b6f  mov     rax, rsi
0x140268b72  mov     rcx, [rsp+88h+var_28]
0x140268b77  xor     rcx, rsp; StackCookie
0x140268b7a  call    __security_check_cookie
0x140268b7f  lea     r11, [rsp+88h+var_18]
0x140268b84  mov     rbx, [r11+28h]
0x140268b88  mov     rsi, [r11+30h]
0x140268b8c  mov     rsp, r11
0x140268b8f  pop     r15
0x140268b91  pop     r14
0x140268b93  pop     r12
0x140268b95  retn
0x140268b96  lea     r8, aCW1SSrcOrchest_54; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140268b9d  mov     edx, 0B2h; void *
0x140268ba2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
