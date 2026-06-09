# UstCommon::CImpersonator::_IsThreadImpersonating(void)

- ea: `0x1800500ac`
- end: `0x1800501d5`
- name: `?_IsThreadImpersonating@CImpersonator@UstCommon@@AEAA_NXZ`
- size: `297`
- prototype: `bool __fastcall(UstCommon::CImpersonator *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005000c`

## callees

- `0x180019ecc`
- `0x180024518`
- `0x1800500ac`
- `0x18005020c`
- `0x180050250`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050171`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050171`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800500d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800500d1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800500e8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800500e8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180050127`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180050127`

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
0x1800500ac  mov     rax, rsp
0x1800500af  mov     [rax+20h], rbx
0x1800500b3  mov     [rax+8], rcx
0x1800500b7  push    rbp
0x1800500b8  sub     rsp, 30h
0x1800500bc  xor     edx, edx
0x1800500be  mov     qword ptr [rax+18h], 0
0x1800500c6  lea     rcx, [rax+18h]
0x1800500ca  xor     bl, bl
0x1800500cc  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800500d1  call    cs:__imp_GetCurrentThread
0x1800500d7  mov     edx, 8; DesiredAccess
0x1800500dc  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800500e1  mov     rcx, rax; ThreadHandle
0x1800500e4  lea     r8d, [rdx-7]; OpenAsSelf
0x1800500e8  call    cs:__imp_OpenThreadToken
0x1800500ee  lea     rbp, WPP_GLOBAL_Control
0x1800500f5  test    eax, eax
0x1800500f7  jz      short loc_18005015F
0x1800500f9  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800500fe  lea     rax, [rsp+38h+arg_8]
0x180050103  mov     r9d, 4; TokenInformationLength
0x180050109  mov     dword ptr [rsp+38h+TokenInformation], 0
0x180050111  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180050116  mov     [rsp+38h+arg_8], 0
0x18005011e  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180050123  lea     edx, [r9+5]; TokenInformationClass
0x180050127  call    cs:__imp_GetTokenInformation
0x18005012d  mov     rcx, cs:WPP_GLOBAL_Control
0x180050134  test    eax, eax
0x180050136  jz      short loc_180050147
0x180050138  mov     eax, dword ptr [rsp+38h+TokenInformation]
0x18005013c  add     eax, 0FFFFFFFEh
0x18005013f  cmp     eax, 1
0x180050142  setbe   bl
0x180050145  jmp     short loc_180050196
0x180050147  cmp     rcx, rbp
0x18005014a  jz      short loc_1800501BE
0x18005014c  test    byte ptr [rcx+1Ch], 2
0x180050150  jz      short loc_180050196
0x180050152  call    cs:__imp_GetLastError
0x180050158  mov     edx, 0Eh
0x18005015d  jmp     short loc_18005017C
0x18005015f  mov     rcx, cs:WPP_GLOBAL_Control
0x180050166  cmp     rcx, rbp
0x180050169  jz      short loc_1800501BE
0x18005016b  test    byte ptr [rcx+1Ch], 2
0x18005016f  jz      short loc_180050196
0x180050171  call    cs:__imp_GetLastError
0x180050177  mov     edx, 0Fh
0x18005017c  mov     rcx, cs:WPP_GLOBAL_Control
0x180050183  mov     r9d, eax
0x180050186  mov     rcx, [rcx+10h]
0x18005018a  call    WPP_SF_D
0x18005018f  mov     rcx, cs:WPP_GLOBAL_Control
0x180050196  cmp     rcx, rbp
0x180050199  jz      short loc_1800501BE
0x18005019b  test    byte ptr [rcx+1Ch], 2
0x18005019f  jz      short loc_1800501BE
0x1800501a1  mov     rcx, [rcx+10h]
0x1800501a5  lea     rax, aNo; "NO"
0x1800501ac  test    bl, bl
0x1800501ae  lea     r9, aYes; "YES"
0x1800501b5  cmovz   r9, rax
0x1800501b9  call    WPP_SF_S
0x1800501be  lea     rcx, [rsp+38h+TokenHandle]
0x1800501c3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800501c8  mov     al, bl
0x1800501ca  mov     rbx, [rsp+38h+arg_18]
0x1800501cf  add     rsp, 30h
0x1800501d3  pop     rbp
0x1800501d4  retn
```
