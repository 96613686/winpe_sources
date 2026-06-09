# WinStoreAuth::AuthenticationInternal::ExtractTicketsFromTokenResult(Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult> const &,WinStoreAuth::TicketHolder *,unsigned __int64,unsigned __int64 *,Windows::System::IUser *)

- ea: `0x1801e4528`
- end: `0x1801e4b37`
- name: `?ExtractTicketsFromTokenResult@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@PEAUTicketHolder@2@_KPEA_KPEAUIUser@System@Windows@@@Z`
- size: `1551`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1801ec82c`

## callees

- `0x180001b88`
- `0x180007c8c`
- `0x1800101f4`
- `0x180010b74`
- `0x180056cc8`
- `0x180056d20`
- `0x1801e0834`
- `0x1801e21a4`
- `0x1801e2268`
- `0x1801e322c`
- `0x1801e4328`
- `0x1801e4528`
- `0x1801eb030`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e462a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e4727`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e4740`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e4828`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e48a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e462a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e4727`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e4740`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e4828`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e48a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e465e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e485b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e49a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e49bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e49f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e465e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e485b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e49a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e49bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e49f6`

## string_xrefs

- `0x1801e4873`: `WebTokenRequestStatus: UserInteractionRequired\nHR: 0x%x\nWAM HR: 0x%x\nResponseErrorMessage: %ws`
- `0x1801e4671`: `WebTokenRequestStatus: ProviderError\nHR: 0x%x\nResponseErrorMessage: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WinStoreAuth::AuthenticationInternal::ExtractTicketsFromTokenResult(
        _QWORD *a1,
        __int64 a2,
        unsigned __int64 a3,
        unsigned __int64 *a4,
        __int64 a5)
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
  int v16; // r8d
  int v17; // r9d
  unsigned int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64 *); // rbx
  int v21; // eax
  __int64 v22; // rdx
  int v23; // r8d
  int v24; // r9d
  __int64 v25; // rdi
  int (__fastcall *v26)(__int64, HSTRING *); // rbx
  HSTRING v27; // rdi
  int (__fastcall *v28)(HSTRING, HSTRING *); // rbx
  unsigned int v29; // ebx
  PCWSTR v30; // rax
  __int64 v32; // r9
  int v33; // eax
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, _QWORD, char **); // rbx
  int v36; // eax
  int v37; // eax
  char v38; // di
  unsigned __int64 v39; // rax
  unsigned __int64 v40; // rbx
  PCWSTR StringRawBuffer; // r15
  PCWSTR v42; // rax
  signed __int64 v43; // r15
  int v44; // ecx
  int v45; // edx
  enum WinStoreAuth::AccountProviderType *v46; // rdx
  const char *v47; // rax
  __int64 v48; // rdx
  __int64 v49; // rdx
  int v50; // [rsp+28h] [rbp-51h]
  char *v51; // [rsp+38h] [rbp-41h]
  unsigned int v52; // [rsp+58h] [rbp-21h] BYREF
  int v53; // [rsp+5Ch] [rbp-1Dh] BYREF
  int v54; // [rsp+60h] [rbp-19h] BYREF
  __int64 v55; // [rsp+68h] [rbp-11h] BYREF
  HSTRING v56; // [rsp+70h] [rbp-9h] BYREF
  HSTRING string; // [rsp+78h] [rbp-1h] BYREF
  int v58; // [rsp+80h] [rbp+7h] BYREF
  HSTRING v59[2]; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+57h]
  char *v61; // [rsp+D8h] [rbp+5Fh] BYREF
  __int64 v62; // [rsp+E0h] [rbp+67h]
  unsigned __int64 v63; // [rsp+E8h] [rbp+6Fh]

  v63 = a3;
  v62 = a2;
  v6 = a2;
  v8 = 0;
  v53 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a1 + 56LL))(*a1, &v53);
  if ( (v9 & 0x80000000) != 0 )
  {
    v10 = 2135;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)v9,
      v50);
    return v9;
  }
  v9 = -2147467259;
  if ( !v53 )
  {
LABEL_27:
    v55 = 0;
    v19 = *a1;
    v20 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a1 + 48LL);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v55);
    v21 = v20(v19, &v55);
    v9 = v21;
    if ( v21 >= 0 )
    {
      v21 = WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v55);
      v9 = v21;
      if ( v21 >= 0 )
      {
        v52 = 0;
        v33 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v55 + 56LL))(v55, &v52);
        v9 = v33;
        if ( v33 >= 0 )
        {
          if ( v52 )
          {
            while ( 1 )
            {
              v61 = 0;
              v34 = v55;
              v35 = *(__int64 (__fastcall **)(__int64, _QWORD, char **))(*(_QWORD *)v55 + 48LL);
              Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v61);
              v36 = v35(v34, v8, &v61);
              v9 = v36;
              if ( v36 < 0 )
                break;
              v36 = WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v61);
              v9 = v36;
              if ( v36 < 0 )
              {
                v49 = 2218;
                goto LABEL_71;
              }
              v58 = 0;
              *(_OWORD *)v59 = 0;
              v37 = WinStoreAuth::AuthenticationInternal::ExtractTicketFromTokenResponse(&v61, &v58);
              v9 = v37;
              if ( v37 < 0 )
              {
                v48 = 2221;
                goto LABEL_67;
              }
              v38 = 0;
              v39 = *a4;
              if ( *a4 )
              {
                v40 = 0;
                do
                {
                  if ( v38 )
                    break;
                  StringRawBuffer = WindowsGetStringRawBuffer(v59[1], 0);
                  v42 = WindowsGetStringRawBuffer(*(HSTRING *)(v62 + 24 * v40 + 16), 0);
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
                  if ( !v45 && *(_DWORD *)(v62 + 24 * v40) == v58 )
                  {
                    v38 = 1;
                    WindowsGetStringRawBuffer(v59[1], 0);
                    v47 = (const char *)WinStoreAuth::ConvertProviderTypeToString((WinStoreAuth *)&v58, v46);
                    wil::details::in1diag3::Log_HrMsg(
                      retaddr,
                      (void *)0x8B5,
                      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
                      (const char *)0x80004005LL,
                      (int)"Duplicate ticket detected. Ticket providerType: %ws web: %ws ",
                      v47);
                  }
                  ++v40;
                  v39 = *a4;
                }
                while ( v40 < *a4 );
                v6 = v62;
              }
              if ( v39 < v63 && !v38 )
              {
                WinStoreAuth::TicketHolder::operator=(v6 + 24 * v39, &v58);
                ++*a4;
              }
              v37 = WinStoreAuth::AuthenticationInternal::ManagePropertiesFromTokenResponse(&v61, a5);
              v9 = v37;
              if ( v37 < 0 )
              {
                v48 = 2239;
LABEL_67:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v48,
                  (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
                  (const char *)(unsigned int)v37,
                  v50);
                WinStoreAuth::TicketHolder::~TicketHolder((WinStoreAuth::TicketHolder *)&v58);
                goto LABEL_72;
              }
              WinStoreAuth::TicketHolder::~TicketHolder((WinStoreAuth::TicketHolder *)&v58);
              Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v61);
              if ( ++v8 >= v52 )
              {
                Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v55);
                return 0;
              }
            }
            v49 = 2217;
LABEL_71:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v49,
              (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
              (const char *)(unsigned int)v36,
              v50);
LABEL_72:
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v61);
            goto LABEL_75;
          }
          v9 = -2147023728;
          v32 = 2147943568LL;
          v22 = 2244;
        }
        else
        {
          v32 = (unsigned int)v33;
          v22 = 2210;
        }
LABEL_74:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)v32,
          v50);
LABEL_75:
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v55);
        return v9;
      }
      v22 = 2207;
    }
    else
    {
      v22 = 2206;
    }
    v32 = (unsigned int)v21;
    goto LABEL_74;
  }
  if ( v53 == 1 )
  {
    v9 = -2147023673;
    v10 = 2144;
    goto LABEL_3;
  }
  if ( v53 != 3 )
  {
    if ( v53 != 5 )
    {
      v10 = 2200;
      goto LABEL_3;
    }
    LODWORD(v61) = 0;
    string = 0;
    v56 = 0;
    v11 = *a1;
    v12 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)*a1 + 64LL);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v56);
    if ( v12(v11, &v56) >= 0 )
    {
      (*(void (__fastcall **)(HSTRING, char **))(*(_QWORD *)v56 + 48LL))(v56, &v61);
      v13 = v56;
      v14 = *(int (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v56 + 56LL);
      WindowsDeleteString(string);
      string = 0;
      if ( v14(v13, &string) >= 0 )
      {
        v15 = (unsigned int)v61;
        if ( (int)v61 > 0 )
          v15 = (unsigned __int16)v61 | 0x80070000;
        WindowsGetStringRawBuffer(string, 0);
        LODWORD(v51) = v15;
        LOBYTE(v50) = 1;
        wil::details::in1diag3::Log_HrIfMsg(
          retaddr,
          (void *)0x888,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)v15,
          v50,
          (bool)"WebTokenRequestStatus: ProviderError\nHR: 0x%x\nResponseErrorMessage: %ws",
          v51);
      }
    }
    if ( WinStoreAuth::g_hTelemetry
      && **(_DWORD **)WinStoreAuth::g_hTelemetry > 5u
      && (unsigned __int8)tlgKeywordOn(*WinStoreAuth::g_hTelemetry, 0x400000000000LL) )
    {
      v18 = (unsigned int)v61;
      if ( (_DWORD)v61 )
      {
        if ( (int)v61 > 0 )
          v18 = (unsigned __int16)v61 | 0x80070000;
      }
      else
      {
        v18 = -2147467259;
      }
      v54 = v18;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v16,
        (unsigned int)&byte_18028D7DF,
        v16,
        v17,
        (__int64)&v54);
    }
    v9 = (unsigned int)v61;
    if ( (int)v61 > 0 )
      v9 = (unsigned __int16)v61 | 0x80070000;
    v8 = 0;
    if ( (v9 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x893,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)v9,
        v50);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v56);
      WindowsDeleteString(string);
      return v9;
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v56);
    WindowsDeleteString(string);
    goto LABEL_27;
  }
  if ( WinStoreAuth::g_hTelemetry
    && **(_DWORD **)WinStoreAuth::g_hTelemetry > 5u
    && (unsigned __int8)tlgKeywordOn(*WinStoreAuth::g_hTelemetry, 0x400000000000LL) )
  {
    v54 = -2147023579;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v23,
      (unsigned int)&byte_18028D857,
      v23,
      v24,
      (__int64)&v54);
  }
  LODWORD(v61) = 0;
  v56 = 0;
  string = 0;
  v25 = *a1;
  v26 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)*a1 + 64LL);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&string);
  if ( v26(v25, &string) >= 0 )
  {
    (*(void (__fastcall **)(HSTRING, char **))(*(_QWORD *)string + 48LL))(string, &v61);
    v27 = string;
    v28 = *(int (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)string + 56LL);
    WindowsDeleteString(v56);
    v56 = 0;
    if ( v28(v27, &v56) >= 0 )
    {
      v29 = (unsigned int)v61;
      if ( (int)v61 > 0 )
        v29 = (unsigned __int16)v61 | 0x80070000;
      v30 = WindowsGetStringRawBuffer(v56, 0);
      LODWORD(v51) = -2147023579;
      LOBYTE(v50) = 1;
      wil::details::in1diag3::Log_HrIfMsg(
        retaddr,
        (void *)0x875,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)v29,
        v50,
        (bool)"WebTokenRequestStatus: UserInteractionRequired\nHR: 0x%x\nWAM HR: 0x%x\nResponseErrorMessage: %ws",
        v51,
        v29,
        v30);
    }
  }
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&string);
  WindowsDeleteString(v56);
  return 2147943717LL;
}

```

## disassembly

```asm
0x1801e4528  mov     rax, rsp
0x1801e452b  mov     [rax+20h], rbx
0x1801e452f  mov     [rax+18h], r8
0x1801e4533  mov     [rax+10h], rdx
0x1801e4537  push    rbp
0x1801e4538  push    rsi
0x1801e4539  push    rdi
0x1801e453a  push    r12
0x1801e453c  push    r13
0x1801e453e  push    r14
0x1801e4540  push    r15
0x1801e4542  lea     rbp, [rax-57h]
0x1801e4546  sub     rsp, 90h
0x1801e454d  mov     r13, r9
0x1801e4550  mov     r12, rdx
0x1801e4553  mov     r15, rcx
0x1801e4556  xor     r14d, r14d
0x1801e4559  mov     [rbp+4Fh+var_6C], r14d
0x1801e455d  mov     rcx, [rcx]
0x1801e4560  mov     rax, [rcx]
0x1801e4563  lea     rdx, [rbp+4Fh+var_6C]
0x1801e4567  mov     rax, [rax+38h]
0x1801e456b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e4570  mov     ebx, eax
0x1801e4572  test    eax, eax
0x1801e4574  jns     short loc_1801E4593
0x1801e4576  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e457d  mov     edx, 857h; void *
0x1801e4582  mov     rcx, [rbp+57h]; this
0x1801e4586  mov     r9d, ebx; char *
0x1801e4589  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e458e  jmp     loc_1801E4B1A
0x1801e4593  mov     ecx, [rbp+4Fh+var_6C]
0x1801e4596  lea     rsi, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e459d  mov     ebx, 80004005h
0x1801e45a2  test    ecx, ecx
0x1801e45a4  jz      loc_1801E4746
0x1801e45aa  sub     ecx, 1
0x1801e45ad  jz      loc_1801E48B1
0x1801e45b3  sub     ecx, 2
0x1801e45b6  jz      loc_1801E4780
0x1801e45bc  cmp     ecx, 2
0x1801e45bf  jz      short loc_1801E45CB
0x1801e45c1  mov     r8, rsi
0x1801e45c4  mov     edx, 898h
0x1801e45c9  jmp     short loc_1801E4582
0x1801e45cb  mov     dword ptr [rbp+4Fh+arg_0], r14d
0x1801e45cf  mov     [rbp+4Fh+string], r14
0x1801e45d3  mov     [rbp+4Fh+var_58], r14
0x1801e45d7  mov     rdi, [r15]
0x1801e45da  mov     rax, [rdi]
0x1801e45dd  mov     rbx, [rax+40h]
0x1801e45e1  lea     rcx, [rbp+4Fh+var_58]
0x1801e45e5  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e45ea  lea     rdx, [rbp+4Fh+var_58]
0x1801e45ee  mov     rcx, rdi
0x1801e45f1  mov     rax, rbx
0x1801e45f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e45f9  mov     r14d, 80070000h
0x1801e45ff  test    eax, eax
0x1801e4601  js      loc_1801E4692
0x1801e4607  mov     rcx, [rbp+4Fh+var_58]
0x1801e460b  mov     rax, [rcx]
0x1801e460e  lea     rdx, [rbp+4Fh+arg_0]
0x1801e4612  mov     rax, [rax+30h]
0x1801e4616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e461b  mov     rdi, [rbp+4Fh+var_58]
0x1801e461f  mov     rax, [rdi]
0x1801e4622  mov     rbx, [rax+38h]
0x1801e4626  mov     rcx, [rbp+4Fh+string]; string
0x1801e462a  call    cs:__imp_WindowsDeleteString
0x1801e4630  mov     [rbp+4Fh+string], 0
0x1801e4638  lea     rdx, [rbp+4Fh+string]
0x1801e463c  mov     rcx, rdi
0x1801e463f  mov     rax, rbx
0x1801e4642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e4647  test    eax, eax
0x1801e4649  js      short loc_1801E4692
0x1801e464b  mov     ebx, dword ptr [rbp+4Fh+arg_0]
0x1801e464e  test    ebx, ebx
0x1801e4650  jle     short loc_1801E4658
0x1801e4652  movzx   ebx, bx
0x1801e4655  or      ebx, r14d
0x1801e4658  xor     edx, edx; length
0x1801e465a  mov     rcx, [rbp+4Fh+string]; string
0x1801e465e  call    cs:__imp_WindowsGetStringRawBuffer
0x1801e4664  mov     rcx, [rbp+57h]; this
0x1801e4668  mov     [rsp+0C0h+var_88], rax
0x1801e466d  mov     dword ptr [rsp+0C0h+var_90], ebx; char *
0x1801e4671  lea     rax, aWebtokenreques; "WebTokenRequestStatus: ProviderError\nH"...
0x1801e4678  mov     [rsp+0C0h+var_98], rax; bool
0x1801e467d  mov     byte ptr [rsp+0C0h+var_A0], 1; int
0x1801e4682  mov     r9d, ebx; char *
0x1801e4685  mov     r8, rsi; unsigned int
0x1801e4688  mov     edx, 888h; void *
0x1801e468d  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1801e4692  mov     r8, cs:?g_hTelemetry@WinStoreAuth@@3PEBQEBU_tlgProvider_t@@EB; _tlgProvider_t const * const * const WinStoreAuth::g_hTelemetry
0x1801e4699  test    r8, r8
0x1801e469c  jz      short loc_1801E46F0
0x1801e469e  mov     r8, [r8]
0x1801e46a1  mov     eax, [r8]
0x1801e46a4  cmp     eax, 5
0x1801e46a7  jbe     short loc_1801E46F0
0x1801e46a9  mov     rdx, 400000000000h
0x1801e46b3  mov     rcx, r8
0x1801e46b6  call    _tlgKeywordOn
0x1801e46bb  test    al, al
0x1801e46bd  jz      short loc_1801E46F0
0x1801e46bf  mov     eax, dword ptr [rbp+4Fh+arg_0]
0x1801e46c2  test    eax, eax
0x1801e46c4  jz      short loc_1801E46D0
0x1801e46c6  jle     short loc_1801E46D5
0x1801e46c8  movzx   eax, ax
0x1801e46cb  or      eax, r14d
0x1801e46ce  jmp     short loc_1801E46D5
0x1801e46d0  mov     eax, 80004005h
0x1801e46d5  mov     [rbp+4Fh+var_68], eax
0x1801e46d8  lea     rax, [rbp+4Fh+var_68]
0x1801e46dc  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x1801e46e1  lea     rdx, byte_18028D7DF
0x1801e46e8  mov     rcx, r8
0x1801e46eb  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1801e46f0  mov     ebx, dword ptr [rbp+4Fh+arg_0]
0x1801e46f3  test    ebx, ebx
0x1801e46f5  jle     short loc_1801E46FD
0x1801e46f7  movzx   ebx, bx
0x1801e46fa  or      ebx, r14d
0x1801e46fd  xor     r14d, r14d
0x1801e4700  test    ebx, ebx
0x1801e4702  jns     short loc_1801E4732
0x1801e4704  mov     rcx, [rbp+57h]; this
0x1801e4708  mov     r9d, ebx; char *
0x1801e470b  mov     r8, rsi; unsigned int
0x1801e470e  mov     edx, 893h; void *
0x1801e4713  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e4718  nop
0x1801e4719  lea     rcx, [rbp+4Fh+var_58]
0x1801e471d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e4722  nop
0x1801e4723  mov     rcx, [rbp+4Fh+string]; string
0x1801e4727  call    cs:__imp_WindowsDeleteString
0x1801e472d  jmp     loc_1801E4B1A
0x1801e4732  lea     rcx, [rbp+4Fh+var_58]
0x1801e4736  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e473b  nop
0x1801e473c  mov     rcx, [rbp+4Fh+string]; string
0x1801e4740  call    cs:__imp_WindowsDeleteString
0x1801e4746  mov     [rbp+4Fh+var_60], r14
0x1801e474a  mov     rdi, [r15]
0x1801e474d  mov     rax, [rdi]
0x1801e4750  mov     rbx, [rax+30h]
0x1801e4754  lea     rcx, [rbp+4Fh+var_60]
0x1801e4758  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e475d  lea     rdx, [rbp+4Fh+var_60]
0x1801e4761  mov     rcx, rdi
0x1801e4764  mov     rax, rbx
0x1801e4767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e476c  mov     ebx, eax
0x1801e476e  test    eax, eax
0x1801e4770  jns     loc_1801E48C3
0x1801e4776  mov     edx, 89Eh
0x1801e477b  jmp     loc_1801E48D7
0x1801e4780  mov     r12d, 80070525h
0x1801e4786  mov     r8, cs:?g_hTelemetry@WinStoreAuth@@3PEBQEBU_tlgProvider_t@@EB; _tlgProvider_t const * const * const WinStoreAuth::g_hTelemetry
0x1801e478d  test    r8, r8
0x1801e4790  jz      short loc_1801E47CF
0x1801e4792  mov     r8, [r8]
0x1801e4795  mov     eax, [r8]
0x1801e4798  cmp     eax, 5
0x1801e479b  jbe     short loc_1801E47CF
0x1801e479d  mov     rdx, 400000000000h
0x1801e47a7  mov     rcx, r8
0x1801e47aa  call    _tlgKeywordOn
0x1801e47af  test    al, al
0x1801e47b1  jz      short loc_1801E47CF
0x1801e47b3  mov     [rbp+4Fh+var_68], r12d
0x1801e47b7  lea     rax, [rbp+4Fh+var_68]
0x1801e47bb  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1801e47c0  lea     rdx, byte_18028D857
0x1801e47c7  mov     rcx, r8
0x1801e47ca  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1801e47cf  mov     dword ptr [rbp+4Fh+arg_0], r14d
0x1801e47d3  mov     [rbp+4Fh+var_58], r14
0x1801e47d7  mov     [rbp+4Fh+string], r14
0x1801e47db  mov     rdi, [r15]
0x1801e47de  mov     rax, [rdi]
0x1801e47e1  mov     rbx, [rax+40h]
0x1801e47e5  lea     rcx, [rbp+4Fh+string]
0x1801e47e9  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e47ee  lea     rdx, [rbp+4Fh+string]
0x1801e47f2  mov     rcx, rdi
0x1801e47f5  mov     rax, rbx
0x1801e47f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e47fd  test    eax, eax
0x1801e47ff  js      loc_1801E4895
0x1801e4805  mov     rcx, [rbp+4Fh+string]
0x1801e4809  mov     rax, [rcx]
0x1801e480c  lea     rdx, [rbp+4Fh+arg_0]
0x1801e4810  mov     rax, [rax+30h]
0x1801e4814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e4819  mov     rdi, [rbp+4Fh+string]
0x1801e481d  mov     rax, [rdi]
0x1801e4820  mov     rbx, [rax+38h]
0x1801e4824  mov     rcx, [rbp+4Fh+var_58]; string
0x1801e4828  call    cs:__imp_WindowsDeleteString
0x1801e482e  mov     [rbp+4Fh+var_58], r14
0x1801e4832  lea     rdx, [rbp+4Fh+var_58]
0x1801e4836  mov     rcx, rdi
0x1801e4839  mov     rax, rbx
0x1801e483c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e4841  test    eax, eax
0x1801e4843  js      short loc_1801E4895
0x1801e4845  mov     ebx, dword ptr [rbp+4Fh+arg_0]
0x1801e4848  test    ebx, ebx
0x1801e484a  jle     short loc_1801E4855
0x1801e484c  movzx   ebx, bx
0x1801e484f  or      ebx, 80070000h
0x1801e4855  xor     edx, edx; length
0x1801e4857  mov     rcx, [rbp+4Fh+var_58]; string
0x1801e485b  call    cs:__imp_WindowsGetStringRawBuffer
0x1801e4861  mov     rcx, [rbp+57h]; this
0x1801e4865  mov     [rsp+40h], rax
0x1801e486a  mov     dword ptr [rsp+0C0h+var_88], ebx
0x1801e486e  mov     dword ptr [rsp+0C0h+var_90], r12d; char *
0x1801e4873  lea     rdx, aWebtokenreques_0; "WebTokenRequestStatus: UserInteractionR"...
0x1801e487a  mov     [rsp+0C0h+var_98], rdx; bool
0x1801e487f  mov     byte ptr [rsp+0C0h+var_A0], 1; int
0x1801e4884  mov     r9d, ebx; char *
0x1801e4887  mov     r8, rsi; unsigned int
0x1801e488a  mov     edx, 875h; void *
0x1801e488f  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1801e4894  nop
0x1801e4895  lea     rcx, [rbp+4Fh+string]
0x1801e4899  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e489e  nop
0x1801e489f  mov     rcx, [rbp+4Fh+var_58]; string
0x1801e48a3  call    cs:__imp_WindowsDeleteString
0x1801e48a9  mov     eax, r12d
0x1801e48ac  jmp     loc_1801E4B1C
0x1801e48b1  mov     ebx, 800704C7h
0x1801e48b6  mov     r8, rsi
0x1801e48b9  mov     edx, 860h
0x1801e48be  jmp     loc_1801E4582
0x1801e48c3  mov     rcx, [rbp+4Fh+var_60]
0x1801e48c7  call    ??$SetProxyBlanket@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@WinStoreAuth@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Z; WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *)
0x1801e48cc  mov     ebx, eax
0x1801e48ce  test    eax, eax
0x1801e48d0  jns     short loc_1801E48DF
0x1801e48d2  mov     edx, 89Fh
0x1801e48d7  mov     r9d, eax
0x1801e48da  jmp     loc_1801E4B04
0x1801e48df  mov     [rbp+4Fh+var_70], r14d
0x1801e48e3  mov     rcx, [rbp+4Fh+var_60]
0x1801e48e7  mov     rax, [rcx]
0x1801e48ea  lea     rdx, [rbp+4Fh+var_70]
0x1801e48ee  mov     rax, [rax+38h]
0x1801e48f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e48f7  mov     ebx, eax
0x1801e48f9  test    eax, eax
0x1801e48fb  jns     short loc_1801E490A
0x1801e48fd  mov     r9d, eax
0x1801e4900  mov     edx, 8A2h
0x1801e4905  jmp     loc_1801E4B04
0x1801e490a  mov     eax, [rbp+4Fh+var_70]
0x1801e490d  test    eax, eax
0x1801e490f  jz      loc_1801E4AF7
0x1801e4915  mov     [rbp+4Fh+arg_0], 0
0x1801e491d  mov     rdi, [rbp+4Fh+var_60]
0x1801e4921  mov     rax, [rdi]
0x1801e4924  mov     rbx, [rax+30h]
0x1801e4928  lea     rcx, [rbp+4Fh+arg_0]
0x1801e492c  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e4931  lea     r8, [rbp+4Fh+arg_0]
0x1801e4935  mov     edx, r14d
0x1801e4938  mov     rcx, rdi
0x1801e493b  mov     rax, rbx
0x1801e493e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e4943  mov     ebx, eax
0x1801e4945  test    eax, eax
0x1801e4947  js      loc_1801E4AD7
0x1801e494d  mov     rcx, [rbp+4Fh+arg_0]
0x1801e4951  call    ??$SetProxyBlanket@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@WinStoreAuth@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Z; WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *)
0x1801e4956  mov     ebx, eax
0x1801e4958  test    eax, eax
0x1801e495a  js      loc_1801E4AD0
0x1801e4960  mov     [rbp+4Fh+var_48], 0
0x1801e4967  xorps   xmm0, xmm0
0x1801e496a  movdqu  xmmword ptr [rbp+4Fh+var_40], xmm0
0x1801e496f  lea     rdx, [rbp+4Fh+var_48]
0x1801e4973  lea     rcx, [rbp+4Fh+arg_0]
0x1801e4977  call    ?ExtractTicketFromTokenResponse@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@AEAUTicketHolder@2@@Z; WinStoreAuth::AuthenticationInternal::ExtractTicketFromTokenResponse(Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenResponse> const &,WinStoreAuth::TicketHolder &)
0x1801e497c  mov     ebx, eax
0x1801e497e  test    eax, eax
0x1801e4980  js      loc_1801E4AC9
0x1801e4986  xor     dil, dil
0x1801e4989  mov     rax, [r13+0]
0x1801e498d  test    rax, rax
0x1801e4990  jz      loc_1801E4A49
0x1801e4996  xor     ebx, ebx
0x1801e4998  test    dil, dil
  ... truncated ...
```
