# SecUtils::TraceAuthenticationPackageInfo(void *)

- ea: `0x180161624`
- end: `0x180161989`
- name: `?TraceAuthenticationPackageInfo@SecUtils@@YAJPEAX@Z`
- size: `869`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18015a980`

## callees

- `0x1800012dc`
- `0x18000964c`
- `0x18004d52c`
- `0x180076090`
- `0x18007e9e0`
- `0x1801615f4`
- `0x180161624`
- `0x18019b2f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180161713`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180161713`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801616a8`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180161757`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180161912`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801616a8`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180161757`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180161912`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18016194c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18016194c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180161709`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180161709`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1801616e8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1801616e8`
- `SspiCli!LsaFreeReturnBuffer` at `0x180161965`
- `SspiCli!LsaFreeReturnBuffer` at `0x180161965`
- `SspiCli!LsaGetLogonSessionData` at `0x18016178f`
- `SspiCli!LsaGetLogonSessionData` at `0x18016178f`

## string_xrefs

- `0x180161766`: `GetTokenInformation failed on token`
- `0x1801616ae`: `Invalid token handle`

## pseudocode

```c
__int64 __fastcall SecUtils::TraceAuthenticationPackageInfo(HANDLE TokenHandle, void *a2)
{
  signed int v3; // ebx
  int ActivityIdPrefix; // eax
  BOOL v5; // r15d
  signed int LastError; // eax
  int v7; // eax
  NTSTATUS LogonSessionData; // edi
  int v9; // edi
  const wchar_t *v10; // rsi
  unsigned int v11; // edi
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // r14d
  __int128 v15; // xmm0
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  int v19; // eax
  PVOID v20; // rcx
  PVOID Buffer; // [rsp+60h] [rbp-A0h] BYREF
  DWORD ReturnLength; // [rsp+68h] [rbp-98h] BYREF
  int v24; // [rsp+6Ch] [rbp-94h] BYREF
  int v25; // [rsp+70h] [rbp-90h] BYREF
  __int128 *v26; // [rsp+78h] [rbp-88h] BYREF
  char *v27; // [rsp+80h] [rbp-80h] BYREF
  const char *v28; // [rsp+88h] [rbp-78h] BYREF
  const char *v29; // [rsp+90h] [rbp-70h] BYREF
  __int64 v30; // [rsp+98h] [rbp-68h] BYREF
  const char *v31; // [rsp+A0h] [rbp-60h] BYREF
  GUID ActivityId; // [rsp+A8h] [rbp-58h] BYREF
  char v33; // [rsp+B8h] [rbp-48h]
  __int128 v34; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD TokenInformation[3]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v36; // [rsp+100h] [rbp+0h]

  Buffer = 0;
  v36 = 0;
  ReturnLength = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  if ( (((unsigned __int64)TokenHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v3 = 0;
    v5 = ImpersonateLoggedOnUser(TokenHandle);
    if ( GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
      goto LABEL_14;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_14:
      *(_QWORD *)ActivityId.Data4 = 0;
      *(_QWORD *)&ActivityId.Data1 = &Buffer;
      v33 = 1;
      LogonSessionData = LsaGetLogonSessionData(
                           (PLUID)TokenInformation + 1,
                           (PSECURITY_LOGON_SESSION_DATA *)ActivityId.Data4);
      wil::details::out_param_t<wistd::unique_ptr<_SECURITY_LOGON_SESSION_DATA,wil::function_deleter<long (*)(void *),&long LsaFreeReturnBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<_SECURITY_LOGON_SESSION_DATA,wil::function_deleter<long (*)(void *),&long LsaFreeReturnBuffer(void *)>>>(&ActivityId);
      v9 = LogonSessionData | 0x10000000;
      if ( v9 < 0 )
      {
        v3 = v9;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = ((__int64 (*)(void))RdpX_GetActivityIdPrefix)();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            (unsigned int)WPP_f5b992e9d455330a647a66dd3f03467f_Traceguids,
            v19,
            (__int64)"LsaGetLogonSessionData failed",
            v9);
        }
      }
      else if ( Buffer )
      {
        v10 = (const wchar_t *)*((_QWORD *)Buffer + 7);
        v11 = *((unsigned __int16 *)Buffer + 24) >> 1;
        if ( !wcsncmp_0(v10, L"NTLM", v11)
          || !wcsncmp_0(v10, L"MICROSOFT_AUTHENTICATION_PACKAGE_V1_0", v11)
          || (v14 = 0, !wcsncmp_0(v10, L"MSV1_0", v11)) )
        {
          v14 = 1;
        }
        if ( (unsigned int)CallbackContext > 4
          && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, v12, v13) )
        {
          v15 = (__int128)*RdpActivityId::GetCurrentActivityId(&ActivityId);
          v24 = v14;
          v26 = &v34;
          v34 = v15;
          v16 = *((_DWORD *)Buffer + 16);
          v27 = (char *)Buffer + 48;
          v28 = "Authentication";
          v29 = "Stack";
          v31 = "Checkpoint";
          v25 = v16;
          v30 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
            v16,
            (unsigned int)word_1802A06BA,
            v17,
            v18,
            (__int64)&v31,
            (__int64)&v30,
            (__int64)&v29,
            (__int64)&v28,
            (__int64)&v27,
            (__int64)&v25,
            (__int64)&v24,
            (__int64)&v26);
        }
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = ((__int64 (*)(void))RdpX_GetActivityIdPrefix)();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)WPP_f5b992e9d455330a647a66dd3f03467f_Traceguids,
        v7,
        (__int64)"GetTokenInformation failed on token",
        v3);
    }
    if ( v5 )
      RevertToSelf();
  }
  else
  {
    v3 = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, a2);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_f5b992e9d455330a647a66dd3f03467f_Traceguids,
        ActivityIdPrefix,
        (__int64)"Invalid token handle",
        87);
    }
  }
  v20 = Buffer;
  Buffer = 0;
  if ( v20 )
    LsaFreeReturnBuffer(v20);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180161624  push    rbp
0x180161626  push    rbx
0x180161627  push    rsi
0x180161628  push    rdi
0x180161629  push    r14
0x18016162b  push    r15
0x18016162d  lea     rbp, [rsp-18h]
0x180161632  sub     rsp, 118h
0x180161639  mov     rax, cs:__security_cookie
0x180161640  xor     rax, rsp
0x180161643  mov     [rbp+40h+var_38], rax
0x180161647  xor     eax, eax
0x180161649  mov     [rsp+140h+Buffer], 0
0x180161652  xorps   xmm0, xmm0
0x180161655  mov     [rbp+40h+var_40], rax
0x180161659  mov     [rsp+140h+var_D8], eax
0x18016165d  mov     rdi, rcx
0x180161660  lea     rax, [rcx+1]
0x180161664  movups  [rbp+40h+TokenInformation], xmm0
0x180161668  movups  [rbp+40h+var_60], xmm0
0x18016166c  movups  [rbp+40h+var_50], xmm0
0x180161670  test    rax, 0FFFFFFFFFFFFFFFEh
0x180161676  jnz     short loc_1801616E6
0x180161678  mov     ebx, 80070057h
0x18016167d  mov     rcx, cs:WPP_GLOBAL_Control
0x180161684  lea     rax, WPP_GLOBAL_Control
0x18016168b  cmp     rcx, rax
0x18016168e  jz      loc_180161952
0x180161694  test    byte ptr [rcx+1Ch], 8
0x180161698  jz      loc_180161952
0x18016169e  cmp     byte ptr [rcx+19h], 2
0x1801616a2  jb      loc_180161952
0x1801616a8  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1801616ae  lea     rcx, aInvalidTokenHa; "Invalid token handle"
0x1801616b5  mov     dword ptr [rsp+140h+var_118], 80070057h
0x1801616bd  mov     [rsp+140h+ReturnLength], rcx
0x1801616c2  lea     r8, WPP_f5b992e9d455330a647a66dd3f03467f_Traceguids
0x1801616c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801616d0  mov     edx, 0Ch
0x1801616d5  mov     r9d, eax
0x1801616d8  mov     rcx, [rcx+10h]
0x1801616dc  call    WPP_SF_DsD
0x1801616e1  jmp     loc_180161952
0x1801616e6  xor     ebx, ebx
0x1801616e8  call    cs:__imp_ImpersonateLoggedOnUser
0x1801616ee  lea     r9d, [rbx+38h]; TokenInformationLength
0x1801616f2  mov     rcx, rdi; TokenHandle
0x1801616f5  mov     r15d, eax
0x1801616f8  lea     r8, [rbp+40h+TokenInformation]; TokenInformation
0x1801616fc  lea     rax, [rsp+140h+var_D8]
0x180161701  lea     edx, [rbx+0Ah]; TokenInformationClass
0x180161704  mov     [rsp+140h+ReturnLength], rax; ReturnLength
0x180161709  call    cs:__imp_GetTokenInformation
0x18016170f  test    eax, eax
0x180161711  jnz     short loc_180161772
0x180161713  call    cs:__imp_GetLastError
0x180161719  mov     ebx, eax
0x18016171b  test    eax, eax
0x18016171d  jle     short loc_180161728
0x18016171f  movzx   ebx, ax
0x180161722  or      ebx, 80070000h
0x180161728  test    ebx, ebx
0x18016172a  jns     short loc_180161772
0x18016172c  mov     rcx, cs:WPP_GLOBAL_Control
0x180161733  lea     rax, WPP_GLOBAL_Control
0x18016173a  cmp     rcx, rax
0x18016173d  jz      loc_180161947
0x180161743  test    byte ptr [rcx+1Ch], 8
0x180161747  jz      loc_180161947
0x18016174d  cmp     byte ptr [rcx+19h], 2
0x180161751  jb      loc_180161947
0x180161757  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18016175d  mov     edx, 0Dh
0x180161762  mov     dword ptr [rsp+140h+var_118], ebx
0x180161766  lea     rcx, aGettokeninform; "GetTokenInformation failed on token"
0x18016176d  jmp     loc_180161928
0x180161772  lea     rax, [rsp+140h+Buffer]
0x180161777  mov     qword ptr [rbp+40h+ActivityId.Data4], 0
0x18016177f  lea     rdx, [rbp+40h+ActivityId.Data4]; ppLogonSessionData
0x180161783  mov     qword ptr [rbp+40h+ActivityId.Data1], rax
0x180161787  lea     rcx, [rbp+40h+TokenInformation+8]; LogonId
0x18016178b  mov     [rbp+40h+var_88], 1
0x18016178f  call    cs:__imp_LsaGetLogonSessionData
0x180161795  lea     rcx, [rbp+40h+ActivityId]
0x180161799  mov     edi, eax
0x18016179b  call    ??1?$out_param_t@V?$unique_ptr@U_SECURITY_LOGON_SESSION_DATA@@U?$function_deleter@P6AJPEAX@Z$1?LsaFreeReturnBuffer@@YAJ0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_SECURITY_LOGON_SESSION_DATA,wil::function_deleter<long (*)(void *),&LsaFreeReturnBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<_SECURITY_LOGON_SESSION_DATA,wil::function_deleter<long (*)(void *),&LsaFreeReturnBuffer(void *)>>>(void)
0x1801617a0  or      edi, 10000000h
0x1801617a6  jl      loc_1801618F1
0x1801617ac  mov     rax, [rsp+140h+Buffer]
0x1801617b1  test    rax, rax
0x1801617b4  jz      loc_180161947
0x1801617ba  movzx   edi, word ptr [rax+30h]
0x1801617be  lea     rdx, aNtlm; "NTLM"
0x1801617c5  mov     rsi, [rax+38h]
0x1801617c9  shr     edi, 1
0x1801617cb  mov     rcx, rsi; String1
0x1801617ce  mov     r8d, edi; MaxCount
0x1801617d1  call    wcsncmp_0
0x1801617d6  test    eax, eax
0x1801617d8  jz      short loc_180161809
0x1801617da  mov     r8d, edi; MaxCount
0x1801617dd  lea     rdx, aMicrosoftAuthe; "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0"
0x1801617e4  mov     rcx, rsi; String1
0x1801617e7  call    wcsncmp_0
0x1801617ec  test    eax, eax
0x1801617ee  jz      short loc_180161809
0x1801617f0  mov     r8d, edi; MaxCount
0x1801617f3  lea     rdx, aMsv10; "MSV1_0"
0x1801617fa  mov     rcx, rsi; String1
0x1801617fd  xor     r14d, r14d
0x180161800  call    wcsncmp_0
0x180161805  test    eax, eax
0x180161807  jnz     short loc_18016180F
0x180161809  mov     r14d, 1
0x18016180f  mov     eax, cs:CallbackContext
0x180161815  cmp     eax, 4
0x180161818  jbe     loc_180161947
0x18016181e  mov     rdx, 470000000000h
0x180161828  lea     rcx, CallbackContext
0x18016182f  call    _tlgKeywordOn
0x180161834  test    al, al
0x180161836  jz      loc_180161947
0x18016183c  lea     rcx, [rbp+40h+ActivityId]; ActivityId
0x180161840  call    ?GetCurrentActivityId@RdpActivityId@@SA?AU_GUID@@XZ; RdpActivityId::GetCurrentActivityId(void)
0x180161845  lea     rdx, word_1802A06BA
0x18016184c  movups  xmm0, xmmword ptr [rax]
0x18016184f  lea     rax, [rbp+40h+var_80]
0x180161853  mov     [rsp+140h+var_D4], r14d
0x180161858  mov     [rsp+140h+var_C8], rax
0x18016185d  mov     rax, [rsp+140h+Buffer]
0x180161862  movdqu  [rbp+40h+var_80], xmm0
0x180161867  mov     ecx, [rax+40h]
0x18016186a  add     rax, 30h ; '0'
0x18016186e  mov     [rbp+40h+var_C0], rax
0x180161872  lea     rax, aAuthentication_2; "Authentication"
0x180161879  mov     [rbp+40h+var_B8], rax
0x18016187d  lea     rax, aStack; "Stack"
0x180161884  mov     [rbp+40h+var_B0], rax
0x180161888  lea     rax, aCheckpoint; "Checkpoint"
0x18016188f  mov     [rbp+40h+var_A0], rax
0x180161893  lea     rax, [rsp+140h+var_C8]
0x180161898  mov     [rsp+140h+var_E8], rax
0x18016189d  lea     rax, [rsp+140h+var_D4]
0x1801618a2  mov     [rsp+140h+var_F0], rax
0x1801618a7  lea     rax, [rsp+140h+var_D0]
0x1801618ac  mov     [rsp+140h+var_F8], rax
0x1801618b1  lea     rax, [rbp+40h+var_C0]
0x1801618b5  mov     [rsp+140h+var_100], rax
0x1801618ba  lea     rax, [rbp+40h+var_B8]
0x1801618be  mov     [rsp+140h+var_108], rax
0x1801618c3  lea     rax, [rbp+40h+var_B0]
0x1801618c7  mov     [rsp+140h+var_110], rax
0x1801618cc  lea     rax, [rbp+40h+var_A8]
0x1801618d0  mov     [rsp+140h+var_118], rax
0x1801618d5  lea     rax, [rbp+40h+var_A0]
0x1801618d9  mov     [rsp+140h+ReturnLength], rax
0x1801618de  mov     [rsp+140h+var_D0], ecx
0x1801618e2  mov     [rbp+40h+var_A8], 1000000h
0x1801618ea  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U?$_tlgWrapperByVal@$03@@U4@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@AEBU?$_tlgWrapperByVal@$03@@6AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x1801618ef  jmp     short loc_180161947
0x1801618f1  mov     ebx, edi
0x1801618f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801618fa  lea     rax, WPP_GLOBAL_Control
0x180161901  cmp     rcx, rax
0x180161904  jz      short loc_180161947
0x180161906  test    byte ptr [rcx+1Ch], 8
0x18016190a  jz      short loc_180161947
0x18016190c  cmp     byte ptr [rcx+19h], 2
0x180161910  jb      short loc_180161947
0x180161912  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180161918  mov     edx, 0Eh
0x18016191d  mov     dword ptr [rsp+140h+var_118], edi
0x180161921  lea     rcx, aLsagetlogonses_0; "LsaGetLogonSessionData failed"
0x180161928  mov     [rsp+140h+ReturnLength], rcx
0x18016192d  lea     r8, WPP_f5b992e9d455330a647a66dd3f03467f_Traceguids
0x180161934  mov     rcx, cs:WPP_GLOBAL_Control
0x18016193b  mov     r9d, eax
0x18016193e  mov     rcx, [rcx+10h]
0x180161942  call    WPP_SF_DsD
0x180161947  test    r15d, r15d
0x18016194a  jz      short loc_180161952
0x18016194c  call    cs:__imp_RevertToSelf
0x180161952  mov     rcx, [rsp+140h+Buffer]; Buffer
0x180161957  mov     [rsp+140h+Buffer], 0
0x180161960  test    rcx, rcx
0x180161963  jz      short loc_18016196B
0x180161965  call    cs:__imp_LsaFreeReturnBuffer
0x18016196b  mov     eax, ebx
0x18016196d  mov     rcx, [rbp+40h+var_38]
0x180161971  xor     rcx, rsp; StackCookie
0x180161974  call    __security_check_cookie
0x180161979  add     rsp, 118h
0x180161980  pop     r15
0x180161982  pop     r14
0x180161984  pop     rdi
0x180161985  pop     rsi
0x180161986  pop     rbx
0x180161987  pop     rbp
0x180161988  retn
```
