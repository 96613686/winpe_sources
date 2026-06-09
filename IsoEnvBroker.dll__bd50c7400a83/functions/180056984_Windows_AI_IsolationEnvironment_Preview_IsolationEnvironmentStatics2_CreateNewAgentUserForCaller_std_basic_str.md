# Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::CreateNewAgentUserForCaller(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180056984`
- end: `0x180056d87`
- name: `?CreateNewAgentUserForCaller@IsolationEnvironmentStatics2@Preview@IsolationEnvironment@AI@Windows@@AEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00000@Z`
- size: `1027`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800564f0`

## callees

- `0x180002520`
- `0x180002a54`
- `0x1800030d0`
- `0x1800050cd`
- `0x18000a464`
- `0x180010148`
- `0x180010240`
- `0x18001045c`
- `0x180013270`
- `0x180014c04`
- `0x180021564`
- `0x180056984`
- `0x180059200`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056afb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056b2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056afb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056b2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056b0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056b0e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180056aba`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180056aba`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180056a76`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180056a76`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180056add`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180056add`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056b06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056b4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056c94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056d1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056b06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056b4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056c94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056d1d`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180056bc1`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180056bc1`

## string_xrefs

- `0x180056d75`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180056d60`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`
- `0x180056c6e`: `onecoreuap\windows\core\isoenvbroker\lib\v2\isolationenvironmentstatics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::CreateNewAgentUserForCaller(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  _QWORD *v7; // rsi
  __int64 v8; // r14
  __int64 v9; // r15
  int v10; // r12d
  _WORD *v11; // rcx
  _WORD *v12; // rcx
  _WORD *v13; // rcx
  _WORD *v14; // rcx
  _WORD *v15; // rcx
  _WORD *v16; // rcx
  HRESULT v17; // eax
  int token_information; // eax
  PSID *v19; // rdi
  BOOL v20; // r13d
  LPWSTR v21; // r12
  LPWSTR v22; // r14
  void *v23; // r15
  DWORD LastError; // ebx
  signed int v25; // eax
  unsigned int v26; // ebx
  unsigned __int64 v28; // rbx
  __int64 v29; // r8
  __int64 v30; // r8
  int AgentAccount; // r14d
  __int64 v32; // r8
  HLOCAL v33; // r9
  size_t v34; // rbx
  int cchReferencedDomainName; // [rsp+20h] [rbp-E0h]
  int cchReferencedDomainNamea; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+38h] [rbp-C8h] BYREF
  DWORD v39; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  void *Block; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B0h]
  __int64 v43; // [rsp+58h] [rbp-A8h]
  __int64 v44; // [rsp+60h] [rbp-A0h]
  __int64 v45; // [rsp+68h] [rbp-98h]
  unsigned __int64 *v46; // [rsp+70h] [rbp-90h]
  __int64 v47; // [rsp+78h] [rbp-88h]
  LPWSTR StringSid[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v49; // [rsp+90h] [rbp-70h]
  _OWORD v50[2]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ReferencedDomainName[8]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v52; // [rsp+D0h] [rbp-30h]
  __int16 v53; // [rsp+E0h] [rbp-20h]
  WCHAR Name[264]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+248h]

  v45 = a4;
  v47 = a3;
  v7 = a2;
  v8 = a7;
  v43 = a7;
  v9 = a6;
  v44 = a6;
  v10 = a5;
  v42 = a5;
  if ( a2[3] <= 7u )
    v11 = a2;
  else
    v11 = (_WORD *)*a2;
  v46 = a2 + 2;
  a2[2] = 0;
  *v11 = 0;
  if ( *(_QWORD *)(a3 + 24) <= 7u )
    v12 = (_WORD *)a3;
  else
    v12 = *(_WORD **)a3;
  *(_QWORD *)(a3 + 16) = 0;
  *v12 = 0;
  if ( *(_QWORD *)(a4 + 24) <= 7u )
    v13 = (_WORD *)a4;
  else
    v13 = *(_WORD **)a4;
  *(_QWORD *)(a4 + 16) = 0;
  *v13 = 0;
  if ( *(_QWORD *)(a5 + 24) <= 7u )
    v14 = (_WORD *)a5;
  else
    v14 = *(_WORD **)a5;
  *(_QWORD *)(a5 + 16) = 0;
  *v14 = 0;
  if ( *(_QWORD *)(a6 + 24) <= 7u )
    v15 = (_WORD *)a6;
  else
    v15 = *(_WORD **)a6;
  *(_QWORD *)(a6 + 16) = 0;
  *v15 = 0;
  if ( *(_QWORD *)(a7 + 24) <= 7u )
    v16 = (_WORD *)a7;
  else
    v16 = *(_WORD **)a7;
  *(_QWORD *)(a7 + 16) = 0;
  *v16 = 0;
  v17 = CoImpersonateClient();
  if ( v17 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x14AA,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      (const char *)(unsigned int)v17,
      cchReferencedDomainName);
  Block = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, -5);
  if ( token_information < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1C9B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
      (const char *)(unsigned int)token_information,
      cchReferencedDomainName);
  v19 = (PSID *)Block;
  CoRevertToSelf();
  hMem = 0;
  StringSid[0] = (LPWSTR)&hMem;
  StringSid[1] = 0;
  LOBYTE(v49) = 1;
  v20 = ConvertSidToStringSidW(*v19, &StringSid[1]);
  if ( (_BYTE)v49 )
  {
    v21 = StringSid[1];
    v22 = StringSid[0];
    v23 = *(void **)StringSid[0];
    if ( *(_QWORD *)StringSid[0] )
    {
      LastError = GetLastError();
      LocalFree(v23);
      SetLastError(LastError);
    }
    *(_QWORD *)v22 = v21;
    v8 = v43;
    v9 = v44;
    v10 = v42;
  }
  if ( v20
    && (memset_0(Name, 0, 0x204u),
        cchName = 257,
        *(_OWORD *)ReferencedDomainName = 0,
        v52 = 0,
        v53 = 0,
        v39 = 16,
        peUse = 0,
        LookupAccountSidLocalW(*v19, Name, &cchName, ReferencedDomainName, &v39, &peUse)) )
  {
    memset(v50, 0, sizeof(v50));
    v28 = -1;
    v29 = -1;
    do
      ++v29;
    while ( Name[v29] );
    std::wstring::_Construct<1,wchar_t const *>(v50, Name);
    v42 = 0;
    *(_OWORD *)StringSid = 0;
    v49 = 0;
    v30 = -1;
    do
      ++v30;
    while ( *((_WORD *)hMem + v30) );
    std::wstring::_Construct<1,wchar_t const *>(StringSid, hMem);
    AgentAccount = AgentAccountHelpers2::CreateAgentAccount(
                     (unsigned int)v50,
                     (unsigned int)StringSid,
                     v45,
                     v10,
                     v9,
                     v8);
    std::wstring::~wstring(StringSid);
    if ( AgentAccount >= 0 )
    {
      v33 = hMem;
      do
        ++v28;
      while ( *((_WORD *)hMem + v28) );
      if ( v28 > v7[3] )
      {
        ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
          v7,
          v28,
          v32,
          hMem);
      }
      else
      {
        if ( v7[3] > 7u )
          v7 = (_QWORD *)*v7;
        *v46 = v28;
        v34 = 2 * v28;
        memmove_0(v7, v33, v34);
        *(_WORD *)((char *)v7 + v34) = 0;
      }
      std::wstring::operator=(v47, v50);
      std::wstring::~wstring(v50);
      if ( hMem )
        LocalFree(hMem);
      if ( v19 )
        operator delete(v19);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16A,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\isolationenvironmentstatics.cpp",
        (const char *)(unsigned int)AgentAccount,
        cchReferencedDomainNamea);
      std::wstring::~wstring(v50);
      if ( hMem )
        LocalFree(hMem);
      if ( v19 )
        operator delete(v19);
      return (unsigned int)AgentAccount;
    }
  }
  else
  {
    v25 = GetLastError();
    v26 = v25;
    if ( v25 > 0 )
      v26 = (unsigned __int16)v25 | 0x80070000;
    if ( hMem )
      LocalFree(hMem);
    if ( v19 )
      operator delete(v19);
    return v26;
  }
}

```

## disassembly

```asm
0x180056984  mov     [rsp-8+arg_0], rbx
0x180056989  push    rbp
0x18005698a  push    rsi
0x18005698b  push    rdi
0x18005698c  push    r12
0x18005698e  push    r13
0x180056990  push    r14
0x180056992  push    r15
0x180056994  lea     rbp, [rsp-210h]
0x18005699c  sub     rsp, 310h
0x1800569a3  mov     rax, cs:__security_cookie
0x1800569aa  xor     rax, rsp
0x1800569ad  mov     [rbp+240h+var_40], rax
0x1800569b4  mov     [rsp+340h+var_2D8], r9
0x1800569b9  mov     [rsp+340h+var_2C8], r8
0x1800569be  mov     rsi, rdx
0x1800569c1  mov     r14, [rbp+240h+arg_30]
0x1800569c8  mov     [rsp+340h+var_2E8], r14
0x1800569cd  mov     r15, [rbp+240h+arg_28]
0x1800569d4  mov     [rsp+340h+var_2E0], r15
0x1800569d9  mov     r12, [rbp+240h+arg_20]
0x1800569e0  mov     [rsp+340h+var_2F0], r12
0x1800569e5  cmp     qword ptr [rdx+18h], 7
0x1800569ea  jbe     short loc_1800569F1
0x1800569ec  mov     rcx, [rdx]
0x1800569ef  jmp     short loc_1800569F4
0x1800569f1  mov     rcx, rsi
0x1800569f4  lea     rax, [rdx+10h]
0x1800569f8  mov     [rsp+340h+var_2D0], rax
0x1800569fd  xor     ebx, ebx
0x1800569ff  mov     [rax], rbx
0x180056a02  mov     [rcx], bx
0x180056a05  cmp     qword ptr [r8+18h], 7
0x180056a0a  jbe     short loc_180056A11
0x180056a0c  mov     rcx, [r8]
0x180056a0f  jmp     short loc_180056A14
0x180056a11  mov     rcx, r8
0x180056a14  mov     [r8+10h], rbx
0x180056a18  mov     [rcx], bx
0x180056a1b  cmp     qword ptr [r9+18h], 7
0x180056a20  jbe     short loc_180056A27
0x180056a22  mov     rcx, [r9]
0x180056a25  jmp     short loc_180056A2A
0x180056a27  mov     rcx, r9
0x180056a2a  mov     [r9+10h], rbx
0x180056a2e  mov     [rcx], bx
0x180056a31  cmp     qword ptr [r12+18h], 7
0x180056a37  jbe     short loc_180056A3F
0x180056a39  mov     rcx, [r12]
0x180056a3d  jmp     short loc_180056A42
0x180056a3f  mov     rcx, r12
0x180056a42  mov     [r12+10h], rbx
0x180056a47  mov     [rcx], bx
0x180056a4a  cmp     qword ptr [r15+18h], 7
0x180056a4f  jbe     short loc_180056A56
0x180056a51  mov     rcx, [r15]
0x180056a54  jmp     short loc_180056A59
0x180056a56  mov     rcx, r15
0x180056a59  mov     [r15+10h], rbx
0x180056a5d  mov     [rcx], bx
0x180056a60  cmp     qword ptr [r14+18h], 7
0x180056a65  jbe     short loc_180056A6C
0x180056a67  mov     rcx, [r14]
0x180056a6a  jmp     short loc_180056A6F
0x180056a6c  mov     rcx, r14
0x180056a6f  mov     [r14+10h], rbx
0x180056a73  mov     [rcx], bx
0x180056a76  call    cs:__imp_CoImpersonateClient
0x180056a7c  mov     rcx, [rbp+248h]; this
0x180056a83  test    eax, eax
0x180056a85  js      loc_180056D72
0x180056a8b  mov     [rsp+340h+Block], rbx
0x180056a90  mov     rdx, 0FFFFFFFFFFFFFFFBh
0x180056a97  lea     rcx, [rsp+340h+Block]
0x180056a9c  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180056aa1  mov     rcx, [rbp+248h]; this
0x180056aa8  test    eax, eax
0x180056aaa  js      loc_180056D5D
0x180056ab0  mov     rdi, [rsp+340h+Block]
0x180056ab5  mov     [rsp+340h+Block], rdi
0x180056aba  call    cs:__imp_CoRevertToSelf
0x180056ac0  mov     [rsp+340h+hMem], rbx
0x180056ac5  lea     rax, [rsp+340h+hMem]
0x180056aca  mov     [rbp+240h+StringSid], rax
0x180056ace  mov     [rbp+240h+StringSid+8], rbx
0x180056ad2  mov     byte ptr [rbp+240h+var_2B0], 1
0x180056ad6  lea     rdx, [rbp+240h+StringSid+8]; StringSid
0x180056ada  mov     rcx, [rdi]; Sid
0x180056add  call    cs:__imp_ConvertSidToStringSidW
0x180056ae3  mov     r13d, eax
0x180056ae6  cmp     byte ptr [rbp+240h+var_2B0], bl
0x180056ae9  jz      short loc_180056B28
0x180056aeb  mov     r12, [rbp+240h+StringSid+8]
0x180056aef  mov     r14, [rbp+240h+StringSid]
0x180056af3  mov     r15, [r14]
0x180056af6  test    r15, r15
0x180056af9  jz      short loc_180056B16
0x180056afb  call    cs:__imp_GetLastError
0x180056b01  mov     ebx, eax
0x180056b03  mov     rcx, r15; hMem
0x180056b06  call    cs:__imp_LocalFree
0x180056b0c  mov     ecx, ebx; dwErrCode
0x180056b0e  call    cs:__imp_SetLastError
0x180056b14  xor     ebx, ebx
0x180056b16  mov     [r14], r12
0x180056b19  mov     r14, [rsp+340h+var_2E8]
0x180056b1e  mov     r15, [rsp+340h+var_2E0]
0x180056b23  mov     r12, [rsp+340h+var_2F0]
0x180056b28  test    r13d, r13d
0x180056b2b  jnz     short loc_180056B67
0x180056b2d  call    cs:__imp_GetLastError
0x180056b33  test    eax, eax
0x180056b35  mov     ebx, eax
0x180056b37  jle     short loc_180056B42
0x180056b39  movzx   ebx, ax
0x180056b3c  or      ebx, 80070000h
0x180056b42  mov     rcx, [rsp+340h+hMem]; hMem
0x180056b47  test    rcx, rcx
0x180056b4a  jz      short loc_180056B53
0x180056b4c  call    cs:__imp_LocalFree
0x180056b52  nop
0x180056b53  test    rdi, rdi
0x180056b56  jz      short loc_180056B60
0x180056b58  mov     rcx, rdi; Block
0x180056b5b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180056b60  mov     eax, ebx
0x180056b62  jmp     loc_180056D33
0x180056b67  xor     edx, edx; Val
0x180056b69  mov     r8d, 204h; Size
0x180056b6f  lea     rcx, [rbp+240h+Name]; void *
0x180056b73  call    memset_0
0x180056b78  mov     [rsp+340h+cchName], 101h
0x180056b80  xorps   xmm0, xmm0
0x180056b83  xor     eax, eax
0x180056b85  movups  xmmword ptr [rbp+240h+ReferencedDomainName], xmm0
0x180056b89  movups  [rbp+240h+var_270], xmm0
0x180056b8d  mov     [rbp+240h+var_260], ax
0x180056b91  mov     [rsp+340h+var_304], 10h
0x180056b99  mov     [rsp+340h+var_308], ebx
0x180056b9d  lea     rax, [rsp+340h+var_308]
0x180056ba2  mov     [rsp+340h+peUse], rax; peUse
0x180056ba7  lea     rax, [rsp+340h+var_304]
0x180056bac  mov     [rsp+340h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180056bb1  lea     r9, [rbp+240h+ReferencedDomainName]; ReferencedDomainName
0x180056bb5  lea     r8, [rsp+340h+cchName]; cchName
0x180056bba  lea     rdx, [rbp+240h+Name]; Name
0x180056bbe  mov     rcx, [rdi]; Sid
0x180056bc1  call    cs:__imp_LookupAccountSidLocalW
0x180056bc7  test    eax, eax
0x180056bc9  jz      loc_180056B2D
0x180056bcf  xorps   xmm0, xmm0
0x180056bd2  movups  [rbp+240h+var_2A0], xmm0
0x180056bd6  xorps   xmm1, xmm1
0x180056bd9  movdqu  [rbp+240h+var_290], xmm1
0x180056bde  lea     rax, [rbp+240h+Name]
0x180056be2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180056be6  mov     r8, rbx
0x180056be9  xor     r13d, r13d
0x180056bec  inc     r8
0x180056bef  cmp     [rax+r8*2], r13w
0x180056bf4  jnz     short loc_180056BEC
0x180056bf6  lea     rdx, [rbp+240h+Name]
0x180056bfa  lea     rcx, [rbp+240h+var_2A0]
0x180056bfe  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180056c03  nop
0x180056c04  mov     [rsp+340h+var_2F0], r13
0x180056c09  mov     rdx, [rsp+340h+hMem]
0x180056c0e  xorps   xmm0, xmm0
0x180056c11  movups  xmmword ptr [rbp+240h+StringSid], xmm0
0x180056c15  xorps   xmm1, xmm1
0x180056c18  movdqu  [rbp+240h+var_2B0], xmm1
0x180056c1d  mov     r8, rbx
0x180056c20  inc     r8
0x180056c23  cmp     [rdx+r8*2], r13w
0x180056c28  jnz     short loc_180056C20
0x180056c2a  lea     rcx, [rbp+240h+StringSid]
0x180056c2e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180056c33  nop
0x180056c34  mov     [rsp+340h+peUse], r14
0x180056c39  mov     [rsp+340h+cchReferencedDomainName], r15; int
0x180056c3e  mov     r9, r12
0x180056c41  mov     r8, [rsp+340h+var_2D8]
0x180056c46  lea     rdx, [rbp+240h+StringSid]
0x180056c4a  lea     rcx, [rbp+240h+var_2A0]
0x180056c4e  call    ?CreateAgentAccount@AgentAccountHelpers2@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEAV23@111@Z; AgentAccountHelpers2::CreateAgentAccount(std::wstring const &,std::wstring const &,std::wstring &,std::wstring &,std::wstring &,std::wstring &)
0x180056c53  mov     r14d, eax
0x180056c56  lea     rcx, [rbp+240h+StringSid]
0x180056c5a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056c5f  test    r14d, r14d
0x180056c62  jns     short loc_180056CB0
0x180056c64  mov     rcx, [rbp+248h]; this
0x180056c6b  mov     r9d, r14d; char *
0x180056c6e  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180056c75  mov     edx, 16Ah; void *
0x180056c7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056c7f  nop
0x180056c80  lea     rcx, [rbp+240h+var_2A0]
0x180056c84  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056c89  nop
0x180056c8a  mov     rcx, [rsp+340h+hMem]; hMem
0x180056c8f  test    rcx, rcx
0x180056c92  jz      short loc_180056C9B
0x180056c94  call    cs:__imp_LocalFree
0x180056c9a  nop
0x180056c9b  test    rdi, rdi
0x180056c9e  jz      short loc_180056CA8
0x180056ca0  mov     rcx, rdi; Block
0x180056ca3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180056ca8  mov     eax, r14d
0x180056cab  jmp     loc_180056D33
0x180056cb0  mov     r9, [rsp+340h+hMem]
0x180056cb5  inc     rbx
0x180056cb8  cmp     [r9+rbx*2], r13w
0x180056cbd  jnz     short loc_180056CB5
0x180056cbf  cmp     rbx, [rsi+18h]
0x180056cc3  ja      short loc_180056CEF
0x180056cc5  cmp     qword ptr [rsi+18h], 7
0x180056cca  jbe     short loc_180056CCF
0x180056ccc  mov     rsi, [rsi]
0x180056ccf  mov     rax, [rsp+340h+var_2D0]
0x180056cd4  mov     [rax], rbx
0x180056cd7  add     rbx, rbx
0x180056cda  mov     r8, rbx; Size
0x180056cdd  mov     rdx, r9; Src
0x180056ce0  mov     rcx, rsi; void *
0x180056ce3  call    memmove_0
0x180056ce8  mov     [rbx+rsi], r13w
0x180056ced  jmp     short loc_180056CFA
0x180056cef  mov     rdx, rbx
0x180056cf2  mov     rcx, rsi
0x180056cf5  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *>(unsigned __int64,`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *)
0x180056cfa  lea     rdx, [rbp+240h+var_2A0]
0x180056cfe  mov     rcx, [rsp+340h+var_2C8]
0x180056d03  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180056d08  nop
0x180056d09  lea     rcx, [rbp+240h+var_2A0]
0x180056d0d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056d12  nop
0x180056d13  mov     rcx, [rsp+340h+hMem]; hMem
0x180056d18  test    rcx, rcx
0x180056d1b  jz      short loc_180056D24
0x180056d1d  call    cs:__imp_LocalFree
0x180056d23  nop
0x180056d24  test    rdi, rdi
0x180056d27  jz      short loc_180056D31
0x180056d29  mov     rcx, rdi; Block
0x180056d2c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180056d31  xor     eax, eax
0x180056d33  mov     rcx, [rbp+240h+var_40]
0x180056d3a  xor     rcx, rsp; StackCookie
0x180056d3d  call    __security_check_cookie
0x180056d42  mov     rbx, [rsp+340h+arg_0]
0x180056d4a  add     rsp, 310h
0x180056d51  pop     r15
0x180056d53  pop     r14
0x180056d55  pop     r13
0x180056d57  pop     r12
0x180056d59  pop     rdi
0x180056d5a  pop     rsi
0x180056d5b  pop     rbp
0x180056d5c  retn
0x180056d5d  mov     r9d, eax; char *
0x180056d60  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180056d67  mov     edx, 1C9Bh; void *
0x180056d6c  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180056d72  mov     r9d, eax; char *
0x180056d75  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180056d7c  mov     edx, 14AAh; void *
0x180056d81  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
