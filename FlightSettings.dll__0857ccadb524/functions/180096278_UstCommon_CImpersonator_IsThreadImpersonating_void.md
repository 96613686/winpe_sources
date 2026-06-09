# UstCommon::CImpersonator::_IsThreadImpersonating(void)

- ea: `0x180096278`
- end: `0x1800963a1`
- name: `?_IsThreadImpersonating@CImpersonator@UstCommon@@AEAA_NXZ`
- size: `297`
- prototype: `bool __fastcall(UstCommon::CImpersonator *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180096140`

## callees

- `0x180010e9c`
- `0x180017870`
- `0x180096278`
- `0x1800963d8`
- `0x18009641c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009631e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009633d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009631e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009633d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800962b4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800962b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009629d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009629d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800962f3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800962f3`

## pseudocode

```c
bool __fastcall UstCommon::CImpersonator::_IsThreadImpersonating(UstCommon::CImpersonator *this)
{
  bool v1; // bl
  HANDLE CurrentThread; // rax
  __int64 v3; // rdx
  __int64 v4; // r8
  BOOL v5; // eax
  _QWORD *v6; // rcx
  DWORD LastError; // eax
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  const wchar_t *v11; // r9
  UstCommon::CImpersonator *TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  TokenInformation = this;
  TokenHandle = 0;
  v1 = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_16;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_11;
    LastError = GetLastError();
    v9 = 15;
    goto LABEL_10;
  }
  LODWORD(TokenInformation) = 0;
  ReturnLength = 0;
  v5 = GetTokenInformation(TokenHandle, TokenImpersonationLevel, &TokenInformation, 4u, &ReturnLength);
  v6 = WPP_GLOBAL_Control;
  if ( v5 )
  {
    v1 = (unsigned int)((_DWORD)TokenInformation - 2) <= 1;
    goto LABEL_11;
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_16;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    LastError = GetLastError();
    v9 = 14;
LABEL_10:
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v8, LastError);
    v6 = WPP_GLOBAL_Control;
  }
LABEL_11:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
  {
    v10 = v6[2];
    v11 = L"YES";
    if ( !v1 )
      v11 = L"NO";
    WPP_SF_S(v10, v3, v4, v11);
  }
LABEL_16:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return v1;
}

```

## disassembly

```asm
0x180096278  mov     rax, rsp
0x18009627b  mov     [rax+20h], rbx
0x18009627f  mov     [rax+8], rcx
0x180096283  push    rbp
0x180096284  sub     rsp, 30h
0x180096288  xor     edx, edx
0x18009628a  mov     qword ptr [rax+18h], 0
0x180096292  lea     rcx, [rax+18h]
0x180096296  xor     bl, bl
0x180096298  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18009629d  call    cs:__imp_GetCurrentThread
0x1800962a3  mov     edx, 8; DesiredAccess
0x1800962a8  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800962ad  mov     rcx, rax; ThreadHandle
0x1800962b0  lea     r8d, [rdx-7]; OpenAsSelf
0x1800962b4  call    cs:__imp_OpenThreadToken
0x1800962ba  lea     rbp, WPP_GLOBAL_Control
0x1800962c1  test    eax, eax
0x1800962c3  jz      short loc_18009632B
0x1800962c5  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800962ca  lea     rax, [rsp+38h+arg_8]
0x1800962cf  mov     r9d, 4; TokenInformationLength
0x1800962d5  mov     dword ptr [rsp+38h+TokenInformation], 0
0x1800962dd  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800962e2  mov     [rsp+38h+arg_8], 0
0x1800962ea  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800962ef  lea     edx, [r9+5]; TokenInformationClass
0x1800962f3  call    cs:__imp_GetTokenInformation
0x1800962f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180096300  test    eax, eax
0x180096302  jz      short loc_180096313
0x180096304  mov     eax, dword ptr [rsp+38h+TokenInformation]
0x180096308  add     eax, 0FFFFFFFEh
0x18009630b  cmp     eax, 1
0x18009630e  setbe   bl
0x180096311  jmp     short loc_180096362
0x180096313  cmp     rcx, rbp
0x180096316  jz      short loc_18009638A
0x180096318  test    byte ptr [rcx+1Ch], 2
0x18009631c  jz      short loc_180096362
0x18009631e  call    cs:__imp_GetLastError
0x180096324  mov     edx, 0Eh
0x180096329  jmp     short loc_180096348
0x18009632b  mov     rcx, cs:WPP_GLOBAL_Control
0x180096332  cmp     rcx, rbp
0x180096335  jz      short loc_18009638A
0x180096337  test    byte ptr [rcx+1Ch], 2
0x18009633b  jz      short loc_180096362
0x18009633d  call    cs:__imp_GetLastError
0x180096343  mov     edx, 0Fh
0x180096348  mov     rcx, cs:WPP_GLOBAL_Control
0x18009634f  mov     r9d, eax
0x180096352  mov     rcx, [rcx+10h]
0x180096356  call    WPP_SF_D
0x18009635b  mov     rcx, cs:WPP_GLOBAL_Control
0x180096362  cmp     rcx, rbp
0x180096365  jz      short loc_18009638A
0x180096367  test    byte ptr [rcx+1Ch], 2
0x18009636b  jz      short loc_18009638A
0x18009636d  mov     rcx, [rcx+10h]
0x180096371  lea     rax, aNo; "NO"
0x180096378  test    bl, bl
0x18009637a  lea     r9, aYes; "YES"
0x180096381  cmovz   r9, rax
0x180096385  call    WPP_SF_S
0x18009638a  lea     rcx, [rsp+38h+TokenHandle]
0x18009638f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180096394  mov     al, bl
0x180096396  mov     rbx, [rsp+38h+arg_18]
0x18009639b  add     rsp, 30h
0x18009639f  pop     rbp
0x1800963a0  retn
```
