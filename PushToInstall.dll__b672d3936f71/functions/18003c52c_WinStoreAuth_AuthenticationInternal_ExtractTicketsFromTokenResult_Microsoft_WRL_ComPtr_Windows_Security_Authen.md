# WinStoreAuth::AuthenticationInternal::ExtractTicketsFromTokenResult(Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult> const &,WinStoreAuth::TicketHolder *,unsigned __int64,unsigned __int64 *,Windows::System::IUser *)

- ea: `0x18003c52c`
- end: `0x18003ceb0`
- name: `?ExtractTicketsFromTokenResult@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@PEAUTicketHolder@2@_KPEA_KPEAUIUser@System@Windows@@@Z`
- size: `2436`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180043f90`

## callees

- `0x180001300`
- `0x1800026b0`
- `0x180010b84`
- `0x180038550`
- `0x180039b30`
- `0x18003c128`
- `0x18003c52c`
- `0x180042680`
- `0x1800426d8`
- `0x180042768`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c672`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c8f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cb72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cb8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cbc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c672`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c8f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cb72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cb8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cbc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c63e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c775`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c79e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c8bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c94a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cc8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cc99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cd02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cd10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cd6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cd7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c63e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c775`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c79e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c8bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c94a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cc8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cc99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cd02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cd10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cd6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cd7a`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003c999`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003c9f5`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003c999`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003c9f5`

## string_xrefs

- `0x18003c685`: `WebTokenRequestStatus: ProviderError\nHR: 0x%x\nResponseErrorMessage: %ws`
- `0x18003c90a`: `WebTokenRequestStatus: UserInteractionRequired\nHR: 0x%x\nWAM HR: 0x%x\nResponseErrorMessage: %ws`

## pseudocode

```c
__int64 __fastcall WinStoreAuth::AuthenticationInternal::ExtractTicketsFromTokenResult(
        _QWORD *a1,
        __int64 a2,
        unsigned __int64 a3,
        unsigned __int64 *a4)
{
  __int64 v5; // r12
  char v7; // r14
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v11; // rdx
  HSTRING v12; // rdi
  int (__fastcall *v13)(HSTRING, HSTRING *); // rbx
  unsigned int v14; // ebx
  __int64 v15; // r10
  unsigned int v16; // eax
  HSTRING v17; // rcx
  HSTRING v18; // rcx
  int v19; // eax
  IUnknown *v20; // rcx
  __int64 v21; // r10
  HSTRING v22; // rdi
  int (__fastcall *v23)(HSTRING, HSTRING *); // rbx
  unsigned int v24; // ebx
  PCWSTR v25; // rax
  HSTRING v26; // rcx
  IUnknown *v27; // rbx
  HRESULT v28; // edi
  HRESULT v29; // eax
  HSTRING v30; // rcx
  HSTRING v31; // rcx
  IUnknown *v32; // rcx
  int v33; // eax
  IUnknown *v34; // rcx
  unsigned int v35; // edi
  int v36; // eax
  int v37; // eax
  int v38; // eax
  unsigned __int64 v39; // rax
  unsigned __int64 v40; // rbx
  PCWSTR StringRawBuffer; // r15
  PCWSTR v42; // rax
  signed __int64 v43; // r15
  int v44; // ecx
  int v45; // edx
  PCWSTR v46; // r8
  int v47; // eax
  IUnknown *v48; // rcx
  IUnknown *v49; // rcx
  IUnknown *v50; // rcx
  IUnknown *v51; // rcx
  IUnknown *v52; // rcx
  IUnknown *v53; // rcx
  IUnknown *v54; // rcx
  IUnknown *v55; // rcx
  IUnknown *v56; // rcx
  IUnknown *v57; // rcx
  IUnknown *v58; // rcx
  int dwAuthnLevel; // [rsp+20h] [rbp-91h]
  int dwAuthnLevela; // [rsp+20h] [rbp-91h]
  int dwAuthnLevelb; // [rsp+20h] [rbp-91h]
  const char *pAuthInfo; // [rsp+30h] [rbp-81h]
  IUnknown *pProxy; // [rsp+50h] [rbp-61h] BYREF
  HSTRING string; // [rsp+58h] [rbp-59h] BYREF
  IUnknown *v65; // [rsp+60h] [rbp-51h] BYREF
  char *v66; // [rsp+68h] [rbp-49h] BYREF
  HSTRING v67; // [rsp+70h] [rbp-41h] BYREF
  unsigned int v68; // [rsp+78h] [rbp-39h] BYREF
  int v69; // [rsp+7Ch] [rbp-35h] BYREF
  __int64 v70; // [rsp+80h] [rbp-31h]
  unsigned __int64 v71; // [rsp+88h] [rbp-29h]
  int v72; // [rsp+90h] [rbp-21h] BYREF
  HSTRING v73[3]; // [rsp+98h] [rbp-19h]
  IUnknown **v74; // [rsp+B0h] [rbp-1h]
  __int64 v75; // [rsp+B8h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]

  v71 = a3;
  v5 = a2;
  v70 = a2;
  v7 = 0;
  v69 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a1 + 56LL))(*a1, &v69);
  if ( (v8 & 0x80000000) != 0 )
  {
    v9 = 2135;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)v8,
      dwAuthnLevel);
    return v8;
  }
  if ( !v69 )
  {
LABEL_32:
    pProxy = 0;
    v19 = (*(__int64 (__fastcall **)(_QWORD, IUnknown **))(*(_QWORD *)*a1 + 48LL))(*a1, &pProxy);
    v8 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x89E,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v19,
        dwAuthnLevel);
      v20 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v20->lpVtbl->Release)(v20);
      }
      return v8;
    }
    v27 = pProxy;
    v28 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
    if ( v28 != -2147467262 )
    {
      string = 0;
      if ( ((__int64 (__fastcall *)(IUnknown *, GUID *, HSTRING *))v27->lpVtbl->QueryInterface)(
             v27,
             &GUID_00000000_0000_0000_c000_000000000046,
             &string) >= 0 )
      {
        v29 = CoSetProxyBlanket(
                (IUnknown *)string,
                0xFFFFFFFF,
                0xFFFFFFFF,
                (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                0,
                3u,
                0,
                0x40u);
        v8 = v29;
        if ( v29 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xF0,
            (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
            (const char *)(unsigned int)v29,
            dwAuthnLevela);
          v30 = string;
          if ( string )
          {
            string = 0;
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v30 + 16LL))(v30);
          }
          goto LABEL_60;
        }
      }
      v31 = string;
      if ( string )
      {
        string = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v31 + 16LL))(v31);
      }
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF3,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v28,
          dwAuthnLevela);
        v8 = v28;
LABEL_60:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x89F,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)v8,
          dwAuthnLevelb);
        v32 = pProxy;
        if ( pProxy )
        {
          pProxy = 0;
          ((void (__fastcall *)(IUnknown *))v32->lpVtbl->Release)(v32);
        }
        return v8;
      }
    }
    v68 = 0;
    v33 = ((__int64 (__fastcall *)(IUnknown *, unsigned int *))pProxy->lpVtbl[2].AddRef)(pProxy, &v68);
    v8 = v33;
    if ( v33 >= 0 )
    {
      if ( v68 )
      {
        v35 = 0;
        while ( 1 )
        {
          v65 = 0;
          v36 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, IUnknown **))pProxy->lpVtbl[2].QueryInterface)(
                  pProxy,
                  v35,
                  &v65);
          v8 = v36;
          if ( v36 < 0 )
            break;
          v37 = WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v65);
          v8 = v37;
          if ( v37 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x8AA,
              (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
              (const char *)(unsigned int)v37,
              dwAuthnLevela);
            v54 = v65;
            if ( v65 )
            {
              v65 = 0;
              ((void (__fastcall *)(IUnknown *))v54->lpVtbl->Release)(v54);
            }
            v55 = pProxy;
            if ( pProxy )
            {
              pProxy = 0;
              ((void (__fastcall *)(IUnknown *))v55->lpVtbl->Release)(v55);
            }
            return v8;
          }
          v72 = 0;
          *(_OWORD *)v73 = 0;
          v38 = WinStoreAuth::AuthenticationInternal::ExtractTicketFromTokenResponse(&v65, (__int64)&v72);
          v8 = v38;
          if ( v38 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x8AD,
              (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
              (const char *)(unsigned int)v38,
              dwAuthnLevela);
            WindowsDeleteString(v73[1]);
            v73[1] = 0;
            WindowsDeleteString(v73[0]);
            v73[0] = 0;
            v52 = v65;
            if ( v65 )
            {
              v65 = 0;
              ((void (__fastcall *)(IUnknown *))v52->lpVtbl->Release)(v52);
            }
            v53 = pProxy;
            if ( pProxy )
            {
              pProxy = 0;
              ((void (__fastcall *)(IUnknown *))v53->lpVtbl->Release)(v53);
            }
            return v8;
          }
          v39 = *a4;
          if ( *a4 )
          {
            v40 = 0;
            do
            {
              if ( v7 )
                break;
              StringRawBuffer = WindowsGetStringRawBuffer(v73[1], 0);
              v42 = WindowsGetStringRawBuffer(*(HSTRING *)(v70 + 24 * v40 + 16), 0);
              v43 = (char *)StringRawBuffer - (char *)v42;
              do
              {
                v44 = *(PCWSTR)((char *)v42 + v43);
                v45 = *v42 - v44;
                if ( v45 )
                  break;
                ++v42;
              }
              while ( v44 );
              if ( !v45 && *(_DWORD *)(v70 + 24 * v40) == v72 )
              {
                v7 = 1;
                v46 = WindowsGetStringRawBuffer(v73[1], 0);
                switch ( v72 )
                {
                  case 1:
                    wil::details::in1diag3::Log_HrMsg(
                      retaddr,
                      (void *)0x8B5,
                      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
                      (const char *)0x80004005LL,
                      (int)"Duplicate ticket detected. Ticket providerType: %ws web: %ws ",
                      (const char *)L"MSA",
                      v46);
                    break;
                  case 2:
                    wil::details::in1diag3::Log_HrMsg(
                      retaddr,
                      (void *)0x8B5,
                      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
                      (const char *)0x80004005LL,
                      (int)"Duplicate ticket detected. Ticket providerType: %ws web: %ws ",
                      (const char *)L"AAD",
                      v46);
                    break;
                  case 4:
                    wil::details::in1diag3::Log_HrMsg(
                      retaddr,
                      (void *)0x8B5,
                      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
                      (const char *)0x80004005LL,
                      (int)"Duplicate ticket detected. Ticket providerType: %ws web: %ws ",
                      (const char *)L"Device",
                      v46);
                    break;
                  case 8:
                    wil::details::in1diag3::Log_HrMsg(
                      retaddr,
                      (void *)0x8B5,
                      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
                      (const char *)0x80004005LL,
                      (int)"Duplicate ticket detected. Ticket providerType: %ws web: %ws ",
                      (const char *)L"Xbox",
                      v46);
                    break;
                  default:
                    wil::details::in1diag3::Log_HrMsg(
                      retaddr,
                      (void *)0x8B5,
                      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
                      (const char *)0x80004005LL,
                      (int)"Duplicate ticket detected. Ticket providerType: %ws web: %ws ",
                      L"None",
                      v46);
                    break;
                }
              }
              ++v40;
              v39 = *a4;
            }
            while ( v40 < *a4 );
            v5 = v70;
          }
          if ( v39 < v71 && !v7 )
          {
            WinStoreAuth::TicketHolder::operator=(v5 + 24 * v39, (__int64)&v72);
            ++*a4;
          }
          v47 = WinStoreAuth::AuthenticationInternal::ManagePropertiesFromTokenResponse(&v65);
          v8 = v47;
          v7 = 0;
          if ( v47 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x8BF,
              (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
              (const char *)(unsigned int)v47,
              dwAuthnLevela);
            WindowsDeleteString(v73[1]);
            v73[1] = 0;
            WindowsDeleteString(v73[0]);
            v73[0] = 0;
            v50 = v65;
            if ( v65 )
            {
              v65 = 0;
              ((void (__fastcall *)(IUnknown *))v50->lpVtbl->Release)(v50);
            }
            v51 = pProxy;
            if ( pProxy )
            {
              pProxy = 0;
              ((void (__fastcall *)(IUnknown *))v51->lpVtbl->Release)(v51);
            }
            return v8;
          }
          WindowsDeleteString(v73[1]);
          v73[1] = 0;
          WindowsDeleteString(v73[0]);
          v73[0] = 0;
          v48 = v65;
          if ( v65 )
          {
            v65 = 0;
            ((void (__fastcall *)(IUnknown *))v48->lpVtbl->Release)(v48);
          }
          if ( ++v35 >= v68 )
          {
            v49 = pProxy;
            if ( pProxy )
            {
              pProxy = 0;
              ((void (__fastcall *)(IUnknown *))v49->lpVtbl->Release)(v49);
            }
            return 0;
          }
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8A9,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v36,
          dwAuthnLevela);
        v56 = v65;
        if ( v65 )
        {
          v65 = 0;
          ((void (__fastcall *)(IUnknown *))v56->lpVtbl->Release)(v56);
        }
        v57 = pProxy;
        if ( pProxy )
        {
          pProxy = 0;
          ((void (__fastcall *)(IUnknown *))v57->lpVtbl->Release)(v57);
        }
      }
      else
      {
        v8 = -2147023728;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8C4,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)0x80070490LL,
          dwAuthnLevela);
        v58 = pProxy;
        if ( pProxy )
        {
          pProxy = 0;
          ((void (__fastcall *)(IUnknown *))v58->lpVtbl->Release)(v58);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8A2,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v33,
        dwAuthnLevela);
      v34 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v34->lpVtbl->Release)(v34);
      }
    }
    return v8;
  }
  if ( v69 == 1 )
  {
    v8 = -2147023673;
    v9 = 2144;
    goto LABEL_3;
  }
  if ( v69 != 3 )
  {
    if ( v69 != 5 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x898,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)0x80004005LL,
        dwAuthnLevel);
      return 2147500037LL;
    }
    LODWORD(v66) = 0;
    string = 0;
    v67 = 0;
    if ( (*(int (__fastcall **)(_QWORD, HSTRING *))(*(_QWORD *)*a1 + 64LL))(*a1, &v67) >= 0 )
    {
      (*(void (__fastcall **)(HSTRING, char **))(*(_QWORD *)v67 + 48LL))(v67, &v66);
      v12 = v67;
      v13 = *(int (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v67 + 56LL);
      WindowsDeleteString(string);
      string = 0;
      if ( v13(v12, &string) >= 0 )
      {
        v14 = (unsigned int)v66;
        if ( (int)v66 > 0 )
          v14 = (unsigned __int16)v66 | 0x80070000;
        WindowsGetStringRawBuffer(string, 0);
        LODWORD(pAuthInfo) = v14;
        LOBYTE(dwAuthnLevel) = 1;
        wil::details::in1diag3::Log_HrIfMsg(
          retaddr,
          (void *)0x888,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)v14,
          dwAuthnLevel,
          (bool)"WebTokenRequestStatus: ProviderError\nHR: 0x%x\nResponseErrorMessage: %ws",
          pAuthInfo);
      }
    }
    if ( WinStoreAuth::g_hTelemetry )
    {
      v15 = (__int64)*WinStoreAuth::g_hTelemetry;
      if ( **(_DWORD **)WinStoreAuth::g_hTelemetry > 5u )
      {
        v11 = *(_QWORD *)(v15 + 24);
        if ( (*(_QWORD *)(v15 + 16) & 0x400000000000LL) != 0 && (v11 & 0x400000000000LL) == v11 )
        {
          v16 = (unsigned int)v66;
          if ( (_DWORD)v66 )
          {
            if ( (int)v66 > 0 )
              v16 = (unsigned __int16)v66 | 0x80070000;
          }
          else
          {
            v16 = -2147467259;
          }
          LODWORD(v65) = v16;
          v74 = &v65;
          v75 = 4;
          dwAuthnLevel = 3;
          tlgWriteTransfer_EventWriteTransfer(v15, &dword_18005B33C, 0);
        }
      }
    }
    v8 = (unsigned int)v66;
    if ( (int)v66 > 0 )
      v8 = (unsigned __int16)v66 | 0x80070000;
    v7 = 0;
    if ( (v8 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x893,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)v8,
        dwAuthnLevel);
      v17 = v67;
      if ( v67 )
      {
        v67 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v17 + 16LL))(v17);
      }
      WindowsDeleteString(string);
      return v8;
    }
    v18 = v67;
    if ( v67 )
    {
      v67 = 0;
      (*(void (__fastcall **)(HSTRING, __int64))(*(_QWORD *)v18 + 16LL))(v18, v11);
    }
    WindowsDeleteString(string);
    goto LABEL_32;
  }
  if ( WinStoreAuth::g_hTelemetry )
  {
    v21 = (__int64)*WinStoreAuth::g_hTelemetry;
    if ( **(_DWORD **)WinStoreAuth::g_hTelemetry > 5u
      && (*(_QWORD *)(v21 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v21 + 24) & 0x400000000000LL) == *(_QWORD *)(v21 + 24) )
    {
      LODWORD(v65) = -2147023579;
      v74 = &v65;
      v75 = 4;
      dwAuthnLevel = 3;
      tlgWriteTransfer_EventWriteTransfer(v21, &dword_18005B3B4, 0);
    }
  }
  LODWORD(v66) = 0;
  v67 = 0;
  string = 0;
  if ( (*(int (__fastcall **)(_QWORD, HSTRING *))(*(_QWORD *)*a1 + 64LL))(*a1, &string) >= 0 )
  {
    (*(void (__fastcall **)(HSTRING, char **))(*(_QWORD *)string + 48LL))(string, &v66);
    v22 = string;
    v23 = *(int (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)string + 56LL);
    WindowsDeleteString(v67);
    v67 = 0;
    if ( v23(v22, &v67) >= 0 )
    {
      v24 = (unsigned int)v66;
      if ( (int)v66 > 0 )
        v24 = (unsigned __int16)v66 | 0x80070000;
      v25 = WindowsGetStringRawBuffer(v67, 0);
      LODWORD(pAuthInfo) = -2147023579;
      LOBYTE(dwAuthnLevel) = 1;
      wil::details::in1diag3::Log_HrIfMsg(
        retaddr,
        (void *)0x875,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)v24,
        dwAuthnLevel,
        (bool)"WebTokenRequestStatus: UserInteractionRequired\nHR: 0x%x\nWAM HR: 0x%x\nResponseErrorMessage: %ws",
        pAuthInfo,
        v24,
        v25);
    }
  }
  v26 = string;
  if ( string )
  {
    string = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v26 + 16LL))(v26);
  }
  WindowsDeleteString(v67);
  return 2147943717LL;
}

```

## disassembly

```asm
0x18003c52c  mov     [rsp-8+arg_10], rbx
0x18003c531  push    rbp
0x18003c532  push    rsi
0x18003c533  push    rdi
0x18003c534  push    r12
0x18003c536  push    r13
0x18003c538  push    r14
0x18003c53a  push    r15
0x18003c53c  lea     rbp, [rsp-1Fh]
0x18003c541  sub     rsp, 0D0h
0x18003c548  mov     rax, cs:__security_cookie
0x18003c54f  xor     rax, rsp
0x18003c552  mov     [rbp+4Fh+var_40], rax
0x18003c556  mov     r13, r9
0x18003c559  mov     [rbp+4Fh+var_78], r8
0x18003c55d  mov     r12, rdx
0x18003c560  mov     [rbp+4Fh+var_80], rdx
0x18003c564  mov     r15, rcx
0x18003c567  xor     r14d, r14d
0x18003c56a  mov     [rbp+4Fh+var_84], r14d
0x18003c56e  mov     rcx, [rcx]
0x18003c571  mov     rax, [rcx]
0x18003c574  lea     rdx, [rbp+4Fh+var_84]
0x18003c578  mov     rax, [rax+38h]
0x18003c57c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c581  mov     ebx, eax
0x18003c583  test    eax, eax
0x18003c585  jns     short loc_18003C5A4
0x18003c587  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003c58e  mov     edx, 857h; void *
0x18003c593  mov     r9d, ebx; char *
0x18003c596  mov     rcx, [rbp+57h]; this
0x18003c59a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c59f  jmp     loc_18003CE87
0x18003c5a4  mov     ecx, [rbp+4Fh+var_84]
0x18003c5a7  lea     rsi, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003c5ae  test    ecx, ecx
0x18003c5b0  jz      loc_18003C7A4
0x18003c5b6  sub     ecx, 1
0x18003c5b9  jz      loc_18003C958
0x18003c5bf  sub     ecx, 2
0x18003c5c2  jz      loc_18003C7F9
0x18003c5c8  cmp     ecx, 2
0x18003c5cb  jz      short loc_18003C5EE
0x18003c5cd  mov     rcx, [rbp+57h]; this
0x18003c5d1  mov     r9d, 80004005h; char *
0x18003c5d7  mov     r8, rsi; unsigned int
0x18003c5da  mov     edx, 898h; void *
0x18003c5df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c5e4  mov     eax, 80004005h
0x18003c5e9  jmp     loc_18003CE89
0x18003c5ee  mov     dword ptr [rbp+4Fh+var_98], r14d
0x18003c5f2  mov     [rbp+4Fh+string], r14
0x18003c5f6  mov     [rbp+4Fh+var_90], r14
0x18003c5fa  mov     rcx, [r15]
0x18003c5fd  mov     rax, [rcx]
0x18003c600  lea     rdx, [rbp+4Fh+var_90]
0x18003c604  mov     rax, [rax+40h]
0x18003c608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c60d  mov     r14d, 80070000h
0x18003c613  test    eax, eax
0x18003c615  js      loc_18003C6A6
0x18003c61b  mov     rcx, [rbp+4Fh+var_90]
0x18003c61f  mov     rax, [rcx]
0x18003c622  lea     rdx, [rbp+4Fh+var_98]
0x18003c626  mov     rax, [rax+30h]
0x18003c62a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c62f  mov     rdi, [rbp+4Fh+var_90]
0x18003c633  mov     rax, [rdi]
0x18003c636  mov     rbx, [rax+38h]
0x18003c63a  mov     rcx, [rbp+4Fh+string]; string
0x18003c63e  call    cs:__imp_WindowsDeleteString
0x18003c644  mov     [rbp+4Fh+string], 0
0x18003c64c  lea     rdx, [rbp+4Fh+string]
0x18003c650  mov     rcx, rdi
0x18003c653  mov     rax, rbx
0x18003c656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c65b  test    eax, eax
0x18003c65d  js      short loc_18003C6A6
0x18003c65f  mov     ebx, dword ptr [rbp+4Fh+var_98]
0x18003c662  test    ebx, ebx
0x18003c664  jle     short loc_18003C66C
0x18003c666  movzx   ebx, bx
0x18003c669  or      ebx, r14d
0x18003c66c  xor     edx, edx; length
0x18003c66e  mov     rcx, [rbp+4Fh+string]; string
0x18003c672  call    cs:__imp_WindowsGetStringRawBuffer
0x18003c678  mov     rcx, [rbp+57h]; this
0x18003c67c  mov     qword ptr [rsp+100h+dwCapabilities], rax
0x18003c681  mov     dword ptr [rsp+100h+pAuthInfo], ebx; char *
0x18003c685  lea     rax, aWebtokenreques; "WebTokenRequestStatus: ProviderError\nH"...
0x18003c68c  mov     qword ptr [rsp+100h+dwImpLevel], rax; bool
0x18003c691  mov     byte ptr [rsp+100h+dwAuthnLevel], 1; int
0x18003c696  mov     r9d, ebx; char *
0x18003c699  mov     r8, rsi; unsigned int
0x18003c69c  mov     edx, 888h; void *
0x18003c6a1  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18003c6a6  mov     r10, cs:?g_hTelemetry@WinStoreAuth@@3PEBQEBU_tlgProvider_t@@EB; _tlgProvider_t const * const * const WinStoreAuth::g_hTelemetry
0x18003c6ad  test    r10, r10
0x18003c6b0  jz      short loc_18003C72E
0x18003c6b2  mov     r10, [r10]
0x18003c6b5  mov     eax, [r10]
0x18003c6b8  cmp     eax, 5
0x18003c6bb  jbe     short loc_18003C72E
0x18003c6bd  mov     rdx, [r10+18h]
0x18003c6c1  mov     rax, [r10+10h]
0x18003c6c5  mov     rcx, 400000000000h
0x18003c6cf  test    rcx, rax
0x18003c6d2  jz      short loc_18003C72E
0x18003c6d4  mov     rax, rdx
0x18003c6d7  and     rax, rcx
0x18003c6da  cmp     rax, rdx
0x18003c6dd  jnz     short loc_18003C72E
0x18003c6df  mov     eax, dword ptr [rbp+4Fh+var_98]
0x18003c6e2  test    eax, eax
0x18003c6e4  jz      short loc_18003C6F0
0x18003c6e6  jle     short loc_18003C6F5
0x18003c6e8  movzx   eax, ax
0x18003c6eb  or      eax, r14d
0x18003c6ee  jmp     short loc_18003C6F5
0x18003c6f0  mov     eax, 80004005h
0x18003c6f5  mov     dword ptr [rbp+4Fh+var_A0], eax
0x18003c6f8  lea     rax, [rbp+4Fh+var_A0]
0x18003c6fc  mov     [rbp+4Fh+var_50], rax
0x18003c700  mov     [rbp+4Fh+var_48], 4
0x18003c708  lea     rax, [rbp+4Fh+var_70]
0x18003c70c  mov     qword ptr [rsp+100h+dwImpLevel], rax
0x18003c711  mov     [rsp+100h+dwAuthnLevel], 3; int
0x18003c719  xor     r9d, r9d
0x18003c71c  xor     r8d, r8d
0x18003c71f  lea     rdx, dword_18005B33C
0x18003c726  mov     rcx, r10
0x18003c729  call    _tlgWriteTransfer_EventWriteTransfer
0x18003c72e  mov     ebx, dword ptr [rbp+4Fh+var_98]
0x18003c731  test    ebx, ebx
0x18003c733  jle     short loc_18003C73B
0x18003c735  movzx   ebx, bx
0x18003c738  or      ebx, r14d
0x18003c73b  xor     r14d, r14d
0x18003c73e  test    ebx, ebx
0x18003c740  jns     short loc_18003C780
0x18003c742  mov     rcx, [rbp+57h]; this
0x18003c746  mov     r9d, ebx; char *
0x18003c749  mov     r8, rsi; unsigned int
0x18003c74c  mov     edx, 893h; void *
0x18003c751  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c756  nop
0x18003c757  mov     rcx, [rbp+4Fh+var_90]
0x18003c75b  test    rcx, rcx
0x18003c75e  jz      short loc_18003C771
0x18003c760  mov     [rbp+4Fh+var_90], r14
0x18003c764  mov     rdx, [rcx]
0x18003c767  mov     rax, [rdx+10h]
0x18003c76b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c770  nop
0x18003c771  mov     rcx, [rbp+4Fh+string]; string
0x18003c775  call    cs:__imp_WindowsDeleteString
0x18003c77b  jmp     loc_18003CE87
0x18003c780  mov     rcx, [rbp+4Fh+var_90]
0x18003c784  test    rcx, rcx
0x18003c787  jz      short loc_18003C79A
0x18003c789  mov     [rbp+4Fh+var_90], r14
0x18003c78d  mov     rax, [rcx]
0x18003c790  mov     rax, [rax+10h]
0x18003c794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c799  nop
0x18003c79a  mov     rcx, [rbp+4Fh+string]; string
0x18003c79e  call    cs:__imp_WindowsDeleteString
0x18003c7a4  mov     [rbp+4Fh+pProxy], r14
0x18003c7a8  mov     rcx, [r15]
0x18003c7ab  mov     rax, [rcx]
0x18003c7ae  lea     rdx, [rbp+4Fh+pProxy]
0x18003c7b2  mov     rax, [rax+30h]
0x18003c7b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c7bb  mov     ebx, eax
0x18003c7bd  test    eax, eax
0x18003c7bf  jns     loc_18003C96A
0x18003c7c5  mov     rcx, [rbp+57h]; this
0x18003c7c9  mov     r9d, eax; char *
0x18003c7cc  mov     r8, rsi; unsigned int
0x18003c7cf  mov     edx, 89Eh; void *
0x18003c7d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c7d9  nop
0x18003c7da  mov     rcx, [rbp+4Fh+pProxy]
0x18003c7de  test    rcx, rcx
0x18003c7e1  jz      short loc_18003C7F4
0x18003c7e3  mov     [rbp+4Fh+pProxy], r14
0x18003c7e7  mov     rax, [rcx]
0x18003c7ea  mov     rax, [rax+10h]
0x18003c7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c7f3  nop
0x18003c7f4  jmp     loc_18003CE87
0x18003c7f9  mov     r12d, 80070525h
0x18003c7ff  mov     r10, cs:?g_hTelemetry@WinStoreAuth@@3PEBQEBU_tlgProvider_t@@EB; _tlgProvider_t const * const * const WinStoreAuth::g_hTelemetry
0x18003c806  test    r10, r10
0x18003c809  jz      short loc_18003C872
0x18003c80b  mov     r10, [r10]
0x18003c80e  mov     eax, [r10]
0x18003c811  cmp     eax, 5
0x18003c814  jbe     short loc_18003C872
0x18003c816  mov     rdx, [r10+18h]
0x18003c81a  mov     rax, [r10+10h]
0x18003c81e  mov     rcx, 400000000000h
0x18003c828  test    rcx, rax
0x18003c82b  jz      short loc_18003C872
0x18003c82d  mov     rax, rdx
0x18003c830  and     rax, rcx
0x18003c833  cmp     rax, rdx
0x18003c836  jnz     short loc_18003C872
0x18003c838  mov     dword ptr [rbp+4Fh+var_A0], r12d
0x18003c83c  lea     rax, [rbp+4Fh+var_A0]
0x18003c840  mov     [rbp+4Fh+var_50], rax
0x18003c844  mov     [rbp+4Fh+var_48], 4
0x18003c84c  lea     rax, [rbp+4Fh+var_70]
0x18003c850  mov     qword ptr [rsp+100h+dwImpLevel], rax
0x18003c855  mov     [rsp+100h+dwAuthnLevel], 3
0x18003c85d  xor     r9d, r9d
0x18003c860  xor     r8d, r8d
0x18003c863  lea     rdx, dword_18005B3B4
0x18003c86a  mov     rcx, r10
0x18003c86d  call    _tlgWriteTransfer_EventWriteTransfer
0x18003c872  mov     dword ptr [rbp+4Fh+var_98], r14d
0x18003c876  mov     [rbp+4Fh+var_90], r14
0x18003c87a  mov     [rbp+4Fh+string], r14
0x18003c87e  mov     rcx, [r15]
0x18003c881  mov     rax, [rcx]
0x18003c884  lea     rdx, [rbp+4Fh+string]
0x18003c888  mov     rax, [rax+40h]
0x18003c88c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c891  test    eax, eax
0x18003c893  js      loc_18003C92C
0x18003c899  mov     rcx, [rbp+4Fh+string]
0x18003c89d  mov     rax, [rcx]
0x18003c8a0  lea     rdx, [rbp+4Fh+var_98]
0x18003c8a4  mov     rax, [rax+30h]
0x18003c8a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8ad  mov     rdi, [rbp+4Fh+string]
0x18003c8b1  mov     rax, [rdi]
0x18003c8b4  mov     rbx, [rax+38h]
0x18003c8b8  mov     rcx, [rbp+4Fh+var_90]; string
0x18003c8bc  call    cs:__imp_WindowsDeleteString
0x18003c8c2  mov     [rbp+4Fh+var_90], r14
0x18003c8c6  lea     rdx, [rbp+4Fh+var_90]
0x18003c8ca  mov     rcx, rdi
0x18003c8cd  mov     rax, rbx
0x18003c8d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8d5  test    eax, eax
0x18003c8d7  js      short loc_18003C92C
0x18003c8d9  mov     ebx, dword ptr [rbp+4Fh+var_98]
0x18003c8dc  test    ebx, ebx
0x18003c8de  jle     short loc_18003C8EC
0x18003c8e0  movzx   ebx, bx
0x18003c8e3  or      ebx, 80070000h
0x18003c8e9  xor     r14d, r14d
0x18003c8ec  xor     edx, edx; length
0x18003c8ee  mov     rcx, [rbp+4Fh+var_90]; string
0x18003c8f2  call    cs:__imp_WindowsGetStringRawBuffer
0x18003c8f8  mov     rcx, [rbp+57h]; this
0x18003c8fc  mov     [rsp+100h+var_C0], rax
0x18003c901  mov     [rsp+100h+dwCapabilities], ebx
0x18003c905  mov     dword ptr [rsp+100h+pAuthInfo], r12d; char *
0x18003c90a  lea     rax, aWebtokenreques_0; "WebTokenRequestStatus: UserInteractionR"...
0x18003c911  mov     qword ptr [rsp+100h+dwImpLevel], rax; bool
0x18003c916  mov     byte ptr [rsp+100h+dwAuthnLevel], 1; int
0x18003c91b  mov     r9d, ebx; char *
0x18003c91e  mov     r8, rsi; unsigned int
0x18003c921  mov     edx, 875h; void *
0x18003c926  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18003c92b  nop
0x18003c92c  mov     rcx, [rbp+4Fh+string]
0x18003c930  test    rcx, rcx
0x18003c933  jz      short loc_18003C946
0x18003c935  mov     [rbp+4Fh+string], r14
0x18003c939  mov     rdx, [rcx]
0x18003c93c  mov     rax, [rdx+10h]
0x18003c940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c945  nop
0x18003c946  mov     rcx, [rbp+4Fh+var_90]; string
0x18003c94a  call    cs:__imp_WindowsDeleteString
0x18003c950  mov     eax, r12d
0x18003c953  jmp     loc_18003CE89
0x18003c958  mov     ebx, 800704C7h
0x18003c95d  mov     r8, rsi
0x18003c960  mov     edx, 860h
0x18003c965  jmp     loc_18003C593
0x18003c96a  mov     rbx, [rbp+4Fh+pProxy]
0x18003c96e  mov     [rsp+100h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18003c976  mov     [rsp+100h+pAuthInfo], r14; pAuthInfo
0x18003c97b  mov     [rsp+100h+dwImpLevel], 3; dwImpLevel
0x18003c983  mov     [rsp+100h+dwAuthnLevel], r14d; int
0x18003c988  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18003c98c  or      r15d, 0FFFFFFFFh
0x18003c990  mov     r8d, r15d; dwAuthzSvc
0x18003c993  mov     edx, r15d; dwAuthnSvc
0x18003c996  mov     rcx, rbx; pProxy
0x18003c999  call    cs:__imp_CoSetProxyBlanket
0x18003c99f  mov     edi, eax
0x18003c9a1  cmp     eax, 80004002h
0x18003c9a6  jz      loc_18003CA9A
0x18003c9ac  mov     [rbp+4Fh+string], r14
  ... truncated ...
```
