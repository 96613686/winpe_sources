# WinStoreAuth::AuthenticationInternal::ExtractTicketsFromTokenResult(Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult> const &,WinStoreAuth::TicketHolder *,unsigned __int64,unsigned __int64 *,Windows::System::IUser *)

- ea: `0x1800620e8`
- end: `0x1800626e5`
- name: `?ExtractTicketsFromTokenResult@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@PEAUTicketHolder@2@_KPEA_KPEAUIUser@System@Windows@@@Z`
- size: `1533`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180060810`

## callees

- `0x180003b5c`
- `0x180004738`
- `0x18002cce0`
- `0x1800401e0`
- `0x180042090`
- `0x180046f88`
- `0x180061c04`
- `0x1800620e8`
- `0x1800680dc`
- `0x18006c124`
- `0x18006e9e0`
- `0x1800a52ec`
- `0x1800a7508`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006221e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006240d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062559`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062571`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800625a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006221e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006240d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062559`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062571`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800625a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800621ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800622e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800622f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800623da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062455`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800621ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800622e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800622f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800623da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062455`

## string_xrefs

- `0x180062231`: `WebTokenRequestStatus: ProviderError\nHR: 0x%x\nResponseErrorMessage: %ws`
- `0x180062425`: `WebTokenRequestStatus: UserInteractionRequired\nHR: 0x%x\nWAM HR: 0x%x\nResponseErrorMessage: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WinStoreAuth::AuthenticationInternal::ExtractTicketsFromTokenResult(
        _QWORD *a1,
        __int64 a2,
        unsigned __int64 a3,
        unsigned __int64 *a4,
        unsigned int a5)
{
  __int64 v6; // r12
  unsigned int v8; // r14d
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rdi
  int (__fastcall *v12)(__int64, HSTRING *); // rbx
  HSTRING v13; // rdi
  int (__fastcall *v14)(HSTRING, HSTRING *); // rbx
  unsigned int v15; // ebx
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  unsigned int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64 *); // rbx
  int v22; // eax
  __int64 v23; // rdx
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // rdi
  int (__fastcall *v28)(__int64, HSTRING *); // rbx
  HSTRING v29; // rdi
  int (__fastcall *v30)(HSTRING, HSTRING *); // rbx
  unsigned int v31; // ebx
  PCWSTR v32; // rax
  __int64 v34; // r9
  int v35; // eax
  __int64 v36; // rdi
  __int64 (__fastcall *v37)(__int64, _QWORD, char **); // rbx
  int v38; // eax
  int v39; // eax
  char v40; // di
  unsigned __int64 v41; // rax
  unsigned __int64 v42; // rbx
  PCWSTR StringRawBuffer; // r15
  PCWSTR v44; // rax
  signed __int64 v45; // r15
  int v46; // ecx
  int v47; // edx
  enum WinStoreAuth::AccountProviderType *v48; // rdx
  const char *v49; // rax
  __int64 v50; // rdx
  __int64 v51; // rdx
  int v52; // [rsp+28h] [rbp-51h]
  char *v53; // [rsp+38h] [rbp-41h]
  int v54; // [rsp+58h] [rbp-21h] BYREF
  int v55; // [rsp+5Ch] [rbp-1Dh] BYREF
  __int64 v56; // [rsp+60h] [rbp-19h] BYREF
  HSTRING v57; // [rsp+68h] [rbp-11h] BYREF
  HSTRING string; // [rsp+70h] [rbp-9h] BYREF
  int v59; // [rsp+78h] [rbp-1h] BYREF
  HSTRING v60[2]; // [rsp+80h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+57h]
  char *v62; // [rsp+D8h] [rbp+5Fh] BYREF
  __int64 v63; // [rsp+E0h] [rbp+67h]
  unsigned __int64 v64; // [rsp+E8h] [rbp+6Fh]

  v64 = a3;
  v63 = a2;
  v6 = a2;
  v8 = 0;
  v54 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a1 + 56LL))(*a1, &v54);
  if ( (v9 & 0x80000000) != 0 )
  {
    v10 = 2135;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)v9,
      v52);
    return v9;
  }
  v9 = -2147467259;
  if ( !v54 )
  {
LABEL_27:
    v56 = 0;
    v20 = *a1;
    v21 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a1 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
    v22 = v21(v20, &v56);
    v9 = v22;
    if ( v22 >= 0 )
    {
      v22 = WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v56);
      v9 = v22;
      if ( v22 >= 0 )
      {
        a5 = 0;
        v35 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v56 + 56LL))(v56, &a5);
        v9 = v35;
        if ( v35 >= 0 )
        {
          if ( a5 )
          {
            while ( 1 )
            {
              v62 = 0;
              v36 = v56;
              v37 = *(__int64 (__fastcall **)(__int64, _QWORD, char **))(*(_QWORD *)v56 + 48LL);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v62);
              v38 = v37(v36, v8, &v62);
              v9 = v38;
              if ( v38 < 0 )
                break;
              v38 = WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v62);
              v9 = v38;
              if ( v38 < 0 )
              {
                v51 = 2218;
                goto LABEL_71;
              }
              v59 = 0;
              *(_OWORD *)v60 = 0;
              v39 = WinStoreAuth::AuthenticationInternal::ExtractTicketFromTokenResponse(&v62, &v59);
              v9 = v39;
              if ( v39 < 0 )
              {
                v50 = 2221;
                goto LABEL_67;
              }
              v40 = 0;
              v41 = *a4;
              if ( *a4 )
              {
                v42 = 0;
                do
                {
                  if ( v40 )
                    break;
                  StringRawBuffer = WindowsGetStringRawBuffer(v60[1], 0);
                  v44 = WindowsGetStringRawBuffer(*(HSTRING *)(v63 + 24 * v42 + 16), 0);
                  v45 = (char *)StringRawBuffer - (char *)v44;
                  do
                  {
                    v46 = *(PCWSTR)((char *)v44 + v45);
                    v47 = *v44 - v46;
                    if ( v47 )
                      break;
                    ++v44;
                  }
                  while ( v46 );
                  if ( !v47 && *(_DWORD *)(v63 + 24 * v42) == v59 )
                  {
                    v40 = 1;
                    WindowsGetStringRawBuffer(v60[1], 0);
                    v49 = (const char *)WinStoreAuth::ConvertProviderTypeToString((WinStoreAuth *)&v59, v48);
                    wil::details::in1diag3::Log_HrMsg(
                      retaddr,
                      (void *)0x8B5,
                      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
                      (const char *)0x80004005LL,
                      (int)"Duplicate ticket detected. Ticket providerType: %ws web: %ws ",
                      v49);
                  }
                  ++v42;
                  v41 = *a4;
                }
                while ( v42 < *a4 );
                v6 = v63;
              }
              if ( v41 < v64 && !v40 )
              {
                WinStoreAuth::TicketHolder::operator=(v6 + 24 * v41, &v59);
                ++*a4;
              }
              v39 = WinStoreAuth::AuthenticationInternal::ManagePropertiesFromTokenResponse(&v62);
              v9 = v39;
              if ( v39 < 0 )
              {
                v50 = 2239;
LABEL_67:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v50,
                  (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
                  (const char *)(unsigned int)v39,
                  v52);
                WinStoreAuth::TicketHolder::~TicketHolder((WinStoreAuth::TicketHolder *)&v59);
                goto LABEL_72;
              }
              WinStoreAuth::TicketHolder::~TicketHolder((WinStoreAuth::TicketHolder *)&v59);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v62);
              if ( ++v8 >= a5 )
              {
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
                return 0;
              }
            }
            v51 = 2217;
LABEL_71:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v51,
              (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
              (const char *)(unsigned int)v38,
              v52);
LABEL_72:
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v62);
            goto LABEL_75;
          }
          v9 = -2147023728;
          v34 = 2147943568LL;
          v23 = 2244;
        }
        else
        {
          v34 = (unsigned int)v35;
          v23 = 2210;
        }
LABEL_74:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)v34,
          v52);
LABEL_75:
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
        return v9;
      }
      v23 = 2207;
    }
    else
    {
      v23 = 2206;
    }
    v34 = (unsigned int)v22;
    goto LABEL_74;
  }
  if ( v54 == 1 )
  {
    v9 = -2147023673;
    v10 = 2144;
    goto LABEL_3;
  }
  if ( v54 != 3 )
  {
    if ( v54 != 5 )
    {
      v10 = 2200;
      goto LABEL_3;
    }
    LODWORD(v62) = 0;
    string = 0;
    v57 = 0;
    v11 = *a1;
    v12 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)*a1 + 64LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v57);
    if ( v12(v11, &v57) >= 0 )
    {
      (*(void (__fastcall **)(HSTRING, char **))(*(_QWORD *)v57 + 48LL))(v57, &v62);
      v13 = v57;
      v14 = *(int (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v57 + 56LL);
      WindowsDeleteString(string);
      string = 0;
      if ( v14(v13, &string) >= 0 )
      {
        v15 = (unsigned int)v62;
        if ( (int)v62 > 0 )
          v15 = (unsigned __int16)v62 | 0x80070000;
        WindowsGetStringRawBuffer(string, 0);
        LODWORD(v53) = v15;
        LOBYTE(v52) = 1;
        wil::details::in1diag3::Log_HrIfMsg(
          retaddr,
          (void *)0x888,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)v15,
          v52,
          (bool)"WebTokenRequestStatus: ProviderError\nHR: 0x%x\nResponseErrorMessage: %ws",
          v53);
      }
    }
    if ( WinStoreAuth::g_hTelemetry
      && **(_DWORD **)WinStoreAuth::g_hTelemetry > 5u
      && (unsigned __int8)tlgKeywordOn(*WinStoreAuth::g_hTelemetry, 0x400000000000LL) )
    {
      v19 = (unsigned int)v62;
      if ( (_DWORD)v62 )
      {
        if ( (int)v62 > 0 )
          v19 = (unsigned __int16)v62 | 0x80070000;
      }
      else
      {
        v19 = -2147467259;
      }
      v55 = v19;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v16,
        (unsigned int)byte_1800D8719,
        v17,
        v18,
        (__int64)&v55);
    }
    v9 = (unsigned int)v62;
    if ( (int)v62 > 0 )
      v9 = (unsigned __int16)v62 | 0x80070000;
    v8 = 0;
    if ( (v9 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x893,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)v9,
        v52);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v57);
      WindowsDeleteString(string);
      return v9;
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v57);
    WindowsDeleteString(string);
    goto LABEL_27;
  }
  if ( WinStoreAuth::g_hTelemetry
    && **(_DWORD **)WinStoreAuth::g_hTelemetry > 5u
    && (unsigned __int8)tlgKeywordOn(*WinStoreAuth::g_hTelemetry, 0x400000000000LL) )
  {
    v55 = -2147023579;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v24,
      (unsigned int)byte_1800D8791,
      v25,
      v26,
      (__int64)&v55);
  }
  LODWORD(v62) = 0;
  v57 = 0;
  string = 0;
  v27 = *a1;
  v28 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)*a1 + 64LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&string);
  if ( v28(v27, &string) >= 0 )
  {
    (*(void (__fastcall **)(HSTRING, char **))(*(_QWORD *)string + 48LL))(string, &v62);
    v29 = string;
    v30 = *(int (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)string + 56LL);
    WindowsDeleteString(v57);
    v57 = 0;
    if ( v30(v29, &v57) >= 0 )
    {
      v31 = (unsigned int)v62;
      if ( (int)v62 > 0 )
        v31 = (unsigned __int16)v62 | 0x80070000;
      v32 = WindowsGetStringRawBuffer(v57, 0);
      LODWORD(v53) = -2147023579;
      LOBYTE(v52) = 1;
      wil::details::in1diag3::Log_HrIfMsg(
        retaddr,
        (void *)0x875,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)v31,
        v52,
        (bool)"WebTokenRequestStatus: UserInteractionRequired\nHR: 0x%x\nWAM HR: 0x%x\nResponseErrorMessage: %ws",
        v53,
        v31,
        v32);
    }
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&string);
  WindowsDeleteString(v57);
  return 2147943717LL;
}

```

## disassembly

```asm
0x1800620e8  mov     rax, rsp
0x1800620eb  mov     [rax+20h], rbx
0x1800620ef  mov     [rax+18h], r8
0x1800620f3  mov     [rax+10h], rdx
0x1800620f7  push    rbp
0x1800620f8  push    rsi
0x1800620f9  push    rdi
0x1800620fa  push    r12
0x1800620fc  push    r13
0x1800620fe  push    r14
0x180062100  push    r15
0x180062102  lea     rbp, [rax-57h]
0x180062106  sub     rsp, 90h
0x18006210d  mov     r13, r9
0x180062110  mov     r12, rdx
0x180062113  mov     r15, rcx
0x180062116  xor     r14d, r14d
0x180062119  mov     [rbp+4Fh+var_70], r14d
0x18006211d  mov     rcx, [rcx]
0x180062120  mov     rax, [rcx]
0x180062123  lea     rdx, [rbp+4Fh+var_70]
0x180062127  mov     rax, [rax+38h]
0x18006212b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062130  mov     ebx, eax
0x180062132  test    eax, eax
0x180062134  jns     short loc_180062153
0x180062136  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18006213d  mov     edx, 857h; void *
0x180062142  mov     rcx, [rbp+57h]; this
0x180062146  mov     r9d, ebx; char *
0x180062149  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006214e  jmp     loc_1800626C8
0x180062153  mov     ecx, [rbp+4Fh+var_70]
0x180062156  lea     rsi, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18006215d  mov     ebx, 80004005h
0x180062162  test    ecx, ecx
0x180062164  jz      loc_1800622FF
0x18006216a  sub     ecx, 1
0x18006216d  jz      loc_180062463
0x180062173  sub     ecx, 2
0x180062176  jz      loc_180062339
0x18006217c  cmp     ecx, 2
0x18006217f  jz      short loc_18006218B
0x180062181  mov     r8, rsi
0x180062184  mov     edx, 898h
0x180062189  jmp     short loc_180062142
0x18006218b  mov     dword ptr [rbp+4Fh+arg_0], r14d
0x18006218f  mov     [rbp+4Fh+string], r14
0x180062193  mov     [rbp+4Fh+var_60], r14
0x180062197  mov     rdi, [r15]
0x18006219a  mov     rax, [rdi]
0x18006219d  mov     rbx, [rax+40h]
0x1800621a1  lea     rcx, [rbp+4Fh+var_60]
0x1800621a5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800621aa  lea     rdx, [rbp+4Fh+var_60]
0x1800621ae  mov     rcx, rdi
0x1800621b1  mov     rax, rbx
0x1800621b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800621b9  mov     r14d, 80070000h
0x1800621bf  test    eax, eax
0x1800621c1  js      loc_180062252
0x1800621c7  mov     rcx, [rbp+4Fh+var_60]
0x1800621cb  mov     rax, [rcx]
0x1800621ce  lea     rdx, [rbp+4Fh+arg_0]
0x1800621d2  mov     rax, [rax+30h]
0x1800621d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800621db  mov     rdi, [rbp+4Fh+var_60]
0x1800621df  mov     rax, [rdi]
0x1800621e2  mov     rbx, [rax+38h]
0x1800621e6  mov     rcx, [rbp+4Fh+string]; string
0x1800621ea  call    cs:__imp_WindowsDeleteString
0x1800621f0  mov     [rbp+4Fh+string], 0
0x1800621f8  lea     rdx, [rbp+4Fh+string]
0x1800621fc  mov     rcx, rdi
0x1800621ff  mov     rax, rbx
0x180062202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062207  test    eax, eax
0x180062209  js      short loc_180062252
0x18006220b  mov     ebx, dword ptr [rbp+4Fh+arg_0]
0x18006220e  test    ebx, ebx
0x180062210  jle     short loc_180062218
0x180062212  movzx   ebx, bx
0x180062215  or      ebx, r14d
0x180062218  xor     edx, edx; length
0x18006221a  mov     rcx, [rbp+4Fh+string]; string
0x18006221e  call    cs:__imp_WindowsGetStringRawBuffer
0x180062224  mov     rcx, [rbp+57h]; this
0x180062228  mov     [rsp+0C0h+var_88], rax
0x18006222d  mov     dword ptr [rsp+0C0h+var_90], ebx; char *
0x180062231  lea     rax, aWebtokenreques; "WebTokenRequestStatus: ProviderError\nH"...
0x180062238  mov     [rsp+0C0h+var_98], rax; bool
0x18006223d  mov     byte ptr [rsp+0C0h+var_A0], 1; int
0x180062242  mov     r9d, ebx; char *
0x180062245  mov     r8, rsi; unsigned int
0x180062248  mov     edx, 888h; void *
0x18006224d  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180062252  mov     rcx, cs:?g_hTelemetry@WinStoreAuth@@3PEBQEBU_tlgProvider_t@@EB; _tlgProvider_t const * const * const WinStoreAuth::g_hTelemetry
0x180062259  test    rcx, rcx
0x18006225c  jz      short loc_1800622A9
0x18006225e  mov     rcx, [rcx]
0x180062261  mov     eax, [rcx]
0x180062263  cmp     eax, 5
0x180062266  jbe     short loc_1800622A9
0x180062268  mov     rdx, 400000000000h
0x180062272  call    _tlgKeywordOn
0x180062277  test    al, al
0x180062279  jz      short loc_1800622A9
0x18006227b  mov     eax, dword ptr [rbp+4Fh+arg_0]
0x18006227e  test    eax, eax
0x180062280  jz      short loc_18006228C
0x180062282  jle     short loc_180062291
0x180062284  movzx   eax, ax
0x180062287  or      eax, r14d
0x18006228a  jmp     short loc_180062291
0x18006228c  mov     eax, 80004005h
0x180062291  mov     [rbp+4Fh+var_6C], eax
0x180062294  lea     rax, [rbp+4Fh+var_6C]
0x180062298  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18006229d  lea     rdx, byte_1800D8719
0x1800622a4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800622a9  mov     ebx, dword ptr [rbp+4Fh+arg_0]
0x1800622ac  test    ebx, ebx
0x1800622ae  jle     short loc_1800622B6
0x1800622b0  movzx   ebx, bx
0x1800622b3  or      ebx, r14d
0x1800622b6  xor     r14d, r14d
0x1800622b9  test    ebx, ebx
0x1800622bb  jns     short loc_1800622EB
0x1800622bd  mov     rcx, [rbp+57h]; this
0x1800622c1  mov     r9d, ebx; char *
0x1800622c4  mov     r8, rsi; unsigned int
0x1800622c7  mov     edx, 893h; void *
0x1800622cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800622d1  nop
0x1800622d2  lea     rcx, [rbp+4Fh+var_60]
0x1800622d6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800622db  nop
0x1800622dc  mov     rcx, [rbp+4Fh+string]; string
0x1800622e0  call    cs:__imp_WindowsDeleteString
0x1800622e6  jmp     loc_1800626C8
0x1800622eb  lea     rcx, [rbp+4Fh+var_60]
0x1800622ef  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800622f4  nop
0x1800622f5  mov     rcx, [rbp+4Fh+string]; string
0x1800622f9  call    cs:__imp_WindowsDeleteString
0x1800622ff  mov     [rbp+4Fh+var_68], r14
0x180062303  mov     rdi, [r15]
0x180062306  mov     rax, [rdi]
0x180062309  mov     rbx, [rax+30h]
0x18006230d  lea     rcx, [rbp+4Fh+var_68]
0x180062311  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180062316  lea     rdx, [rbp+4Fh+var_68]
0x18006231a  mov     rcx, rdi
0x18006231d  mov     rax, rbx
0x180062320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062325  mov     ebx, eax
0x180062327  test    eax, eax
0x180062329  jns     loc_180062475
0x18006232f  mov     edx, 89Eh
0x180062334  jmp     loc_180062489
0x180062339  mov     r12d, 80070525h
0x18006233f  mov     rcx, cs:?g_hTelemetry@WinStoreAuth@@3PEBQEBU_tlgProvider_t@@EB; _tlgProvider_t const * const * const WinStoreAuth::g_hTelemetry
0x180062346  test    rcx, rcx
0x180062349  jz      short loc_180062381
0x18006234b  mov     rcx, [rcx]
0x18006234e  mov     eax, [rcx]
0x180062350  cmp     eax, 5
0x180062353  jbe     short loc_180062381
0x180062355  mov     rdx, 400000000000h
0x18006235f  call    _tlgKeywordOn
0x180062364  test    al, al
0x180062366  jz      short loc_180062381
0x180062368  mov     [rbp+4Fh+var_6C], r12d
0x18006236c  lea     rax, [rbp+4Fh+var_6C]
0x180062370  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180062375  lea     rdx, byte_1800D8791
0x18006237c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180062381  mov     dword ptr [rbp+4Fh+arg_0], r14d
0x180062385  mov     [rbp+4Fh+var_60], r14
0x180062389  mov     [rbp+4Fh+string], r14
0x18006238d  mov     rdi, [r15]
0x180062390  mov     rax, [rdi]
0x180062393  mov     rbx, [rax+40h]
0x180062397  lea     rcx, [rbp+4Fh+string]
0x18006239b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800623a0  lea     rdx, [rbp+4Fh+string]
0x1800623a4  mov     rcx, rdi
0x1800623a7  mov     rax, rbx
0x1800623aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800623af  test    eax, eax
0x1800623b1  js      loc_180062447
0x1800623b7  mov     rcx, [rbp+4Fh+string]
0x1800623bb  mov     rax, [rcx]
0x1800623be  lea     rdx, [rbp+4Fh+arg_0]
0x1800623c2  mov     rax, [rax+30h]
0x1800623c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800623cb  mov     rdi, [rbp+4Fh+string]
0x1800623cf  mov     rax, [rdi]
0x1800623d2  mov     rbx, [rax+38h]
0x1800623d6  mov     rcx, [rbp+4Fh+var_60]; string
0x1800623da  call    cs:__imp_WindowsDeleteString
0x1800623e0  mov     [rbp+4Fh+var_60], r14
0x1800623e4  lea     rdx, [rbp+4Fh+var_60]
0x1800623e8  mov     rcx, rdi
0x1800623eb  mov     rax, rbx
0x1800623ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800623f3  test    eax, eax
0x1800623f5  js      short loc_180062447
0x1800623f7  mov     ebx, dword ptr [rbp+4Fh+arg_0]
0x1800623fa  test    ebx, ebx
0x1800623fc  jle     short loc_180062407
0x1800623fe  movzx   ebx, bx
0x180062401  or      ebx, 80070000h
0x180062407  xor     edx, edx; length
0x180062409  mov     rcx, [rbp+4Fh+var_60]; string
0x18006240d  call    cs:__imp_WindowsGetStringRawBuffer
0x180062413  mov     rcx, [rbp+57h]; this
0x180062417  mov     [rsp+40h], rax
0x18006241c  mov     dword ptr [rsp+0C0h+var_88], ebx
0x180062420  mov     dword ptr [rsp+0C0h+var_90], r12d; char *
0x180062425  lea     rdx, aWebtokenreques_0; "WebTokenRequestStatus: UserInteractionR"...
0x18006242c  mov     [rsp+0C0h+var_98], rdx; bool
0x180062431  mov     byte ptr [rsp+0C0h+var_A0], 1; int
0x180062436  mov     r9d, ebx; char *
0x180062439  mov     r8, rsi; unsigned int
0x18006243c  mov     edx, 875h; void *
0x180062441  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180062446  nop
0x180062447  lea     rcx, [rbp+4Fh+string]
0x18006244b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180062450  nop
0x180062451  mov     rcx, [rbp+4Fh+var_60]; string
0x180062455  call    cs:__imp_WindowsDeleteString
0x18006245b  mov     eax, r12d
0x18006245e  jmp     loc_1800626CA
0x180062463  mov     ebx, 800704C7h
0x180062468  mov     r8, rsi
0x18006246b  mov     edx, 860h
0x180062470  jmp     loc_180062142
0x180062475  mov     rcx, [rbp+4Fh+var_68]
0x180062479  call    ??$SetProxyBlanket@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@WinStoreAuth@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Z; WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *)
0x18006247e  mov     ebx, eax
0x180062480  test    eax, eax
0x180062482  jns     short loc_180062491
0x180062484  mov     edx, 89Fh
0x180062489  mov     r9d, eax
0x18006248c  jmp     loc_1800626B2
0x180062491  mov     [rbp+4Fh+arg_20], r14d
0x180062495  mov     rcx, [rbp+4Fh+var_68]
0x180062499  mov     rax, [rcx]
0x18006249c  lea     rdx, [rbp+4Fh+arg_20]
0x1800624a0  mov     rax, [rax+38h]
0x1800624a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800624a9  mov     ebx, eax
0x1800624ab  test    eax, eax
0x1800624ad  jns     short loc_1800624BC
0x1800624af  mov     r9d, eax
0x1800624b2  mov     edx, 8A2h
0x1800624b7  jmp     loc_1800626B2
0x1800624bc  mov     eax, [rbp+4Fh+arg_20]
0x1800624bf  test    eax, eax
0x1800624c1  jz      loc_1800626A5
0x1800624c7  mov     [rbp+4Fh+arg_0], 0
0x1800624cf  mov     rdi, [rbp+4Fh+var_68]
0x1800624d3  mov     rax, [rdi]
0x1800624d6  mov     rbx, [rax+30h]
0x1800624da  lea     rcx, [rbp+4Fh+arg_0]
0x1800624de  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800624e3  lea     r8, [rbp+4Fh+arg_0]
0x1800624e7  mov     edx, r14d
0x1800624ea  mov     rcx, rdi
0x1800624ed  mov     rax, rbx
0x1800624f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800624f5  mov     ebx, eax
0x1800624f7  test    eax, eax
0x1800624f9  js      loc_180062685
0x1800624ff  mov     rcx, [rbp+4Fh+arg_0]
0x180062503  call    ??$SetProxyBlanket@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@WinStoreAuth@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Z; WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *)
0x180062508  mov     ebx, eax
0x18006250a  test    eax, eax
0x18006250c  js      loc_18006267E
0x180062512  mov     [rbp+4Fh+var_50], 0
0x180062519  xorps   xmm0, xmm0
0x18006251c  movdqu  xmmword ptr [rbp+4Fh+var_48], xmm0
0x180062521  lea     rdx, [rbp+4Fh+var_50]
0x180062525  lea     rcx, [rbp+4Fh+arg_0]
0x180062529  call    ?ExtractTicketFromTokenResponse@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@AEAUTicketHolder@2@@Z; WinStoreAuth::AuthenticationInternal::ExtractTicketFromTokenResponse(Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenResponse> const &,WinStoreAuth::TicketHolder &)
0x18006252e  mov     ebx, eax
0x180062530  test    eax, eax
0x180062532  js      loc_180062677
0x180062538  xor     dil, dil
0x18006253b  mov     rax, [r13+0]
0x18006253f  test    rax, rax
0x180062542  jz      loc_1800625FB
0x180062548  xor     ebx, ebx
0x18006254a  test    dil, dil
0x18006254d  jnz     loc_1800625F7
0x180062553  xor     edx, edx; length
0x180062555  mov     rcx, [rbp+4Fh+var_48+8]; string
0x180062559  call    cs:__imp_WindowsGetStringRawBuffer
  ... truncated ...
```
