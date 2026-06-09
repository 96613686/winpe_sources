# CheckServicePrivilege(ushort const *)

- ea: `0x1800aa264`
- end: `0x1800aa395`
- name: `?CheckServicePrivilege@@YAHPEBG@Z`
- size: `305`
- prototype: `__int64 __fastcall(LPCWSTR StringSid)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180062970`
- `0x1800aa63c`

## callees

- `0x1800119f0`
- `0x1800137a0`
- `0x1800355b4`
- `0x18003a540`
- `0x180071b7c`
- `0x180084f50`
- `0x1800aa264`
- `0x1800abdc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa2f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa33e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa2f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa33e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800aa315`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800aa315`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800aa2cc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800aa2cc`

## pseudocode

```c
__int64 __fastcall CheckServicePrivilege(LPCWSTR StringSid)
{
  DWORD LastError; // eax
  __int64 v4; // rdx
  unsigned int v5; // ebx
  HANDLE TokenHandle; // [rsp+20h] [rbp-20h] BYREF
  WINBOOL IsMember; // [rsp+28h] [rbp-18h] BYREF
  PSID Sid; // [rsp+30h] [rbp-10h] BYREF

  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  if ( LocalQueryRpcClientToken(&TokenHandle) )
  {
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return 0;
  }
  Sid = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &Sid,
    0);
  if ( !ConvertStringSidToSidW(StringSid, &Sid) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
      || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
    {
      goto LABEL_14;
    }
    LastError = GetLastError();
    v4 = 89;
    goto LABEL_13;
  }
  IsMember = 0;
  if ( CheckTokenMembership(TokenHandle, Sid, &IsMember) )
  {
    v5 = IsMember;
    goto LABEL_16;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    LastError = GetLastError();
    v4 = 90;
LABEL_13:
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v4, WPP_59cb1c30c417333f98d499625c161da5_Traceguids, LastError);
  }
LABEL_14:
  v5 = 0;
LABEL_16:
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x1800aa264  mov     [rsp-8+arg_8], rbx
0x1800aa269  push    rbp
0x1800aa26a  mov     rbp, rsp
0x1800aa26d  sub     rsp, 40h
0x1800aa271  mov     rax, cs:__security_cookie
0x1800aa278  xor     rax, rsp
0x1800aa27b  mov     [rbp+var_8], rax
0x1800aa27f  mov     rbx, rcx
0x1800aa282  mov     [rbp+TokenHandle], 0
0x1800aa28a  lea     rcx, [rbp+TokenHandle]
0x1800aa28e  xor     edx, edx
0x1800aa290  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800aa295  lea     rcx, [rbp+TokenHandle]; void **
0x1800aa299  call    ?LocalQueryRpcClientToken@@YAKPEAPEAX@Z; LocalQueryRpcClientToken(void * *)
0x1800aa29e  test    eax, eax
0x1800aa2a0  jz      short loc_1800AA2B2
0x1800aa2a2  lea     rcx, [rbp+TokenHandle]
0x1800aa2a6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800aa2ab  xor     eax, eax
0x1800aa2ad  jmp     loc_1800AA37E
0x1800aa2b2  xor     edx, edx
0x1800aa2b4  mov     [rbp+Sid], 0
0x1800aa2bc  lea     rcx, [rbp+Sid]
0x1800aa2c0  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800aa2c5  lea     rdx, [rbp+Sid]; Sid
0x1800aa2c9  mov     rcx, rbx; StringSid
0x1800aa2cc  call    cs:__imp_ConvertStringSidToSidW
0x1800aa2d2  test    eax, eax
0x1800aa2d4  jnz     short loc_1800AA302
0x1800aa2d6  mov     rax, cs:WPP_GLOBAL_Control
0x1800aa2dd  lea     rcx, WPP_GLOBAL_Control
0x1800aa2e4  cmp     rax, rcx
0x1800aa2e7  jz      short loc_1800AA363
0x1800aa2e9  cmp     byte ptr [rax+19h], 1
0x1800aa2ed  jb      short loc_1800AA363
0x1800aa2ef  test    byte ptr [rax+1Ch], 1
0x1800aa2f3  jz      short loc_1800AA363
0x1800aa2f5  call    cs:__imp_GetLastError
0x1800aa2fb  mov     edx, 59h ; 'Y'
0x1800aa300  jmp     short loc_1800AA349
0x1800aa302  mov     rdx, [rbp+Sid]; SidToCheck
0x1800aa306  lea     r8, [rbp+IsMember]; IsMember
0x1800aa30a  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800aa30e  mov     [rbp+IsMember], 0
0x1800aa315  call    cs:__imp_CheckTokenMembership
0x1800aa31b  test    eax, eax
0x1800aa31d  jnz     short loc_1800AA367
0x1800aa31f  mov     rax, cs:WPP_GLOBAL_Control
0x1800aa326  lea     rcx, WPP_GLOBAL_Control
0x1800aa32d  cmp     rax, rcx
0x1800aa330  jz      short loc_1800AA363
0x1800aa332  cmp     byte ptr [rax+19h], 1
0x1800aa336  jb      short loc_1800AA363
0x1800aa338  test    byte ptr [rax+1Ch], 1
0x1800aa33c  jz      short loc_1800AA363
0x1800aa33e  call    cs:__imp_GetLastError
0x1800aa344  mov     edx, 5Ah ; 'Z'
0x1800aa349  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa350  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x1800aa357  mov     r9d, eax
0x1800aa35a  mov     rcx, [rcx+10h]
0x1800aa35e  call    WPP_SF_d
0x1800aa363  xor     ebx, ebx
0x1800aa365  jmp     short loc_1800AA36A
0x1800aa367  mov     ebx, [rbp+IsMember]
0x1800aa36a  lea     rcx, [rbp+Sid]
0x1800aa36e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800aa373  lea     rcx, [rbp+TokenHandle]
0x1800aa377  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800aa37c  mov     eax, ebx
0x1800aa37e  mov     rcx, [rbp+var_8]
0x1800aa382  xor     rcx, rsp; StackCookie
0x1800aa385  call    __security_check_cookie
0x1800aa38a  mov     rbx, [rsp+40h+arg_8]
0x1800aa38f  add     rsp, 40h
0x1800aa393  pop     rbp
0x1800aa394  retn
```
