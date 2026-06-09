# IsClientAllowed(void)

- ea: `0x18000e284`
- end: `0x18000e42a`
- name: `?IsClientAllowed@@YA_NXZ`
- size: `422`
- prototype: `char(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000faa4`

## callees

- `0x180002250`
- `0x180002cf8`
- `0x18000c13c`
- `0x18000c37c`
- `0x18000e284`
- `0x18000f148`
- `0x18000f190`
- `0x18000f1b8`
- `0x18000f1d8`
- `0x18000fe30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e2e1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e2e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e2cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e2cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e37e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e37e`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000e2af`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000e2af`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000e2f6`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000e2f6`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18000e325`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18000e325`

## string_xrefs

- `0x18000e412`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000e3d1`: `Disallowed client attempted to access AggregatedDataPlatform APIs.`

## pseudocode

```c
char IsClientAllowed(void)
{
  HRESULT v0; // eax
  char v1; // di
  HANDLE CurrentThread; // rax
  void *v3; // rdx
  unsigned int v4; // r8d
  const char *v5; // r9
  unsigned int ApplicationUserModelIdFromToken; // eax
  void *v7; // rdx
  unsigned int v8; // r8d
  __int64 v9; // r8
  const wchar_t *v10; // rsi
  __int64 v11; // r14
  wchar_t **v12; // rbx
  size_t v13; // r8
  unsigned int v15; // [rsp+20h] [rbp-E0h]
  UINT32 applicationUserModelIdLength; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE TokenHandle; // [rsp+28h] [rbp-D8h] BYREF
  wchar_t *S2[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v20; // [rsp+48h] [rbp-B8h]
  WCHAR applicationUserModelId[136]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  TokenHandle = 0;
  v0 = CoImpersonateClient();
  if ( v0 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x14B1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v0,
      v15);
  v1 = 1;
  LOBYTE(v15) = 1;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, v3, v4, v5);
  CoRevertToSelf();
  memset_0(applicationUserModelId, 0, 0x104u);
  applicationUserModelIdLength = 130;
  ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(
                                      TokenHandle,
                                      &applicationUserModelIdLength,
                                      applicationUserModelId);
  if ( ApplicationUserModelIdFromToken )
    wil::details::in1diag3::_Throw_Win32(retaddr, v7, v8, (const char *)ApplicationUserModelIdFromToken, v15);
  *(_OWORD *)S2 = 0;
  v19 = 0;
  v20 = 0;
  v9 = -1;
  do
    ++v9;
  while ( applicationUserModelId[v9] );
  std::wstring::_Construct<1,wchar_t const *>(S2, applicationUserModelId);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  v10 = (const wchar_t *)S2;
  if ( v20 > 7 )
    v10 = S2[0];
  v11 = v19;
  v12 = &off_1800CC690;
  while ( 1 )
  {
    v13 = (size_t)v12[1];
    if ( v13 == v11 && (!v13 || !wmemcmp(*v12, v10, v13)) )
      break;
    v12 += 2;
    if ( v12 == (wchar_t **)&lpSubKey )
    {
      v1 = 0;
      ADPTraceLoggingProvider::TraceLoggingInfo("Disallowed client attempted to access AggregatedDataPlatform APIs.");
      break;
    }
  }
  std::wstring::~wstring(S2);
  return v1;
}

```

## disassembly

```asm
0x18000e284  push    rbp
0x18000e286  push    rbx
0x18000e287  push    rsi
0x18000e288  push    rdi
0x18000e289  push    r14
0x18000e28b  push    r15
0x18000e28d  lea     rbp, [rsp-78h]
0x18000e292  sub     rsp, 178h
0x18000e299  mov     rax, cs:__security_cookie
0x18000e2a0  xor     rax, rsp
0x18000e2a3  mov     [rbp+0A0h+var_40], rax
0x18000e2a7  xor     r15d, r15d
0x18000e2aa  mov     [rsp+1A0h+TokenHandle], r15
0x18000e2af  call    cs:__imp_CoImpersonateClient
0x18000e2b5  mov     rcx, [rbp+0A8h]; this
0x18000e2bc  test    eax, eax
0x18000e2be  js      loc_18000E40F
0x18000e2c4  lea     edi, [r15+1]
0x18000e2c8  mov     byte ptr [rsp+1A0h+var_180], dil; unsigned int
0x18000e2cd  call    cs:__imp_GetCurrentThread
0x18000e2d3  lea     r9, [rsp+1A0h+TokenHandle]; TokenHandle
0x18000e2d8  mov     r8d, edi; OpenAsSelf
0x18000e2db  lea     edx, [rdi+7]; DesiredAccess
0x18000e2de  mov     rcx, rax; ThreadHandle
0x18000e2e1  call    cs:__imp_OpenThreadToken
0x18000e2e7  mov     rcx, [rbp+0A8h]; this
0x18000e2ee  test    eax, eax
0x18000e2f0  jz      loc_18000E424
0x18000e2f6  call    cs:__imp_CoRevertToSelf
0x18000e2fc  xor     edx, edx; Val
0x18000e2fe  mov     r8d, 104h; Size
0x18000e304  lea     rcx, [rsp+1A0h+applicationUserModelId]; void *
0x18000e309  call    memset_0
0x18000e30e  mov     [rsp+1A0h+applicationUserModelIdLength], 82h
0x18000e316  lea     r8, [rsp+1A0h+applicationUserModelId]; applicationUserModelId
0x18000e31b  lea     rdx, [rsp+1A0h+applicationUserModelIdLength]; applicationUserModelIdLength
0x18000e320  mov     rcx, [rsp+1A0h+TokenHandle]; token
0x18000e325  call    cs:__imp_GetApplicationUserModelIdFromToken
0x18000e32b  mov     rcx, [rbp+0A8h]; this
0x18000e332  test    eax, eax
0x18000e334  jnz     loc_18000E406
0x18000e33a  xorps   xmm0, xmm0
0x18000e33d  movups  xmmword ptr [rsp+1A0h+S2], xmm0
0x18000e342  mov     [rsp+1A0h+var_160], r15
0x18000e347  mov     [rsp+1A0h+var_158], r15
0x18000e34c  lea     rax, [rsp+1A0h+applicationUserModelId]
0x18000e351  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000e355  inc     r8
0x18000e358  cmp     [rax+r8*2], r15w
0x18000e35d  jnz     short loc_18000E355
0x18000e35f  lea     rdx, [rsp+1A0h+applicationUserModelId]
0x18000e364  lea     rcx, [rsp+1A0h+S2]
0x18000e369  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000e36e  nop
0x18000e36f  mov     rcx, [rsp+1A0h+TokenHandle]; hObject
0x18000e374  lea     rax, [rcx-1]
0x18000e378  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e37c  ja      short loc_18000E384
0x18000e37e  call    cs:__imp_CloseHandle
0x18000e384  lea     rsi, [rsp+1A0h+S2]
0x18000e389  cmp     [rsp+1A0h+var_158], 7
0x18000e38f  cmova   rsi, [rsp+1A0h+S2]
0x18000e395  mov     r14, [rsp+1A0h+var_160]
0x18000e39a  lea     rbx, off_1800CC690; "MicrosoftWindows.Client.CBS_cw5n1h2txye"...
0x18000e3a1  mov     r8, [rbx+8]; N
0x18000e3a5  cmp     r8, r14
0x18000e3a8  jnz     short loc_18000E3BE
0x18000e3aa  test    r8, r8
0x18000e3ad  jz      short loc_18000E3DD
0x18000e3af  mov     rdx, rsi; S2
0x18000e3b2  mov     rcx, [rbx]; S1
0x18000e3b5  call    wmemcmp
0x18000e3ba  test    eax, eax
0x18000e3bc  jz      short loc_18000E3DD
0x18000e3be  add     rbx, 10h
0x18000e3c2  lea     rax, lpSubKey
0x18000e3c9  cmp     rbx, rax
0x18000e3cc  jnz     short loc_18000E3A1
0x18000e3ce  mov     dil, r15b
0x18000e3d1  lea     rcx, aDisallowedClie; "Disallowed client attempted to access A"...
0x18000e3d8  call    ?TraceLoggingInfo@ADPTraceLoggingProvider@@SAXPEBDZZ; ADPTraceLoggingProvider::TraceLoggingInfo(char const *,...)
0x18000e3dd  lea     rcx, [rsp+1A0h+S2]
0x18000e3e2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e3e7  mov     al, dil
0x18000e3ea  mov     rcx, [rbp+0A0h+var_40]
0x18000e3ee  xor     rcx, rsp; StackCookie
0x18000e3f1  call    __security_check_cookie
0x18000e3f6  add     rsp, 178h
0x18000e3fd  pop     r15
0x18000e3ff  pop     r14
0x18000e401  pop     rdi
0x18000e402  pop     rsi
0x18000e403  pop     rbx
0x18000e404  pop     rbp
0x18000e405  retn
0x18000e406  mov     r9d, eax; char *
0x18000e409  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000e40f  mov     r9d, eax; char *
0x18000e412  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e419  mov     edx, 14B1h; void *
0x18000e41e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000e424  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
