# WinStoreAuth::AuthenticationInternal::GetXToken(HWND__ *,WinStoreAuth::PromptType,HSTRING__ *,HSTRING__ *,Windows::System::IUser *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x1800a6df0`
- end: `0x1800a7311`
- name: `?GetXToken@AuthenticationInternal@WinStoreAuth@@YAJPEAUHWND__@@W4PromptType@2@PEAUHSTRING__@@2PEAUIUser@System@Windows@@PEAPEAU5@4@Z`
- size: `1313`
- prototype: `int __high(HWND, enum WinStoreAuth::PromptType, HSTRING, HSTRING, struct Windows::System::IUser *, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003bf58`

## callees

- `0x180004738`
- `0x18000aba8`
- `0x18002aae8`
- `0x180042044`
- `0x180044dcc`
- `0x180061c04`
- `0x1800629dc`
- `0x180062a40`
- `0x18006ea74`
- `0x1800a3a88`
- `0x1800a6df0`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a725c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a72a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a725c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a72a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a6ffc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a700b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a70b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a70c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a70f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a6ffc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a700b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a70b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a70c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a70f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a6e34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a6e90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a72d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a72de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a6e34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a6e90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a72d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a72de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a6fbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a6fe3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a71a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a71ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a6fbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a6fe3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a71a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a71ef`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a6ed6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a6ed6`

## string_xrefs

- `0x1800a7049`: `x-xbl-contract-version:2\nAccept:application/json`
- `0x1800a710e`: `x-xbl-contract-version:2\nAccept:application/json`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall WinStoreAuth::AuthenticationInternal::GetXToken(
        __int64 a1,
        __int64 a2,
        HSTRING a3,
        __int64 a4,
        __int64 a5,
        HSTRING *a6,
        HSTRING *a7)
{
  int SlsValue; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  HRESULT Instance; // eax
  HRESULT v12; // eax
  __int64 v13; // rdx
  LPVOID v14; // rsi
  __int64 (__fastcall *v15)(LPVOID, const wchar_t *, PCWSTR, const wchar_t *); // r14
  void *v16; // rbx
  WCHAR *v17; // rbx
  PCWSTR StringRawBuffer; // rdi
  WinStoreAuth::AuthenticationInternal *v19; // rcx
  bool IsPlatformXbox; // al
  const wchar_t *v21; // rcx
  LPVOID v22; // r14
  __int64 (__fastcall *v23)(LPVOID, _QWORD, PCWSTR, _QWORD); // rsi
  unsigned int v24; // edi
  WinStoreAuth::AuthenticationInternal *v25; // rcx
  bool v26; // al
  const wchar_t *v27; // rcx
  PCWSTR v28; // rax
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, PCNZWCH *); // rsi
  WCHAR *v33; // rbx
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, LPVOID *); // rsi
  void *v36; // rbx
  int ppv; // [rsp+20h] [rbp-A1h]
  LPVOID *ppva; // [rsp+20h] [rbp-A1h]
  LPVOID v40[2]; // [rsp+70h] [rbp-51h] BYREF
  UINT32 length[2]; // [rsp+80h] [rbp-41h] BYREF
  __int64 v42; // [rsp+90h] [rbp-31h] BYREF
  LPVOID pv; // [rsp+98h] [rbp-29h] BYREF
  PCNZWCH sourceString; // [rsp+A0h] [rbp-21h] BYREF
  __int64 v45; // [rsp+A8h] [rbp-19h] BYREF
  HSTRING string; // [rsp+B0h] [rbp-11h] BYREF
  HSTRING v47[9]; // [rsp+B8h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+47h]

  *(_QWORD *)length = 0;
  sourceString = 0;
  pv = 0;
  *a6 = 0;
  *a7 = 0;
  string = 0;
  WindowsDeleteString(0);
  v47[0] = 0;
  SlsValue = WinStoreAuth::GetSlsValue(5, v47);
  v9 = SlsValue;
  if ( SlsValue >= 0 )
  {
    SlsValue = Microsoft::WRL::Wrappers::HString::Set(&string, (HSTRING *)length);
    v9 = SlsValue;
    if ( SlsValue < 0 )
    {
      v10 = 977;
      goto LABEL_5;
    }
    if ( !string )
    {
      WindowsDeleteString(0);
      string = 0;
      SlsValue = WinStoreAuth::GetSlsValue(6, &string);
      v9 = SlsValue;
      if ( SlsValue < 0 )
      {
        v10 = 980;
        goto LABEL_5;
      }
    }
    v40[0] = 0;
    Instance = CoCreateInstance(
                 &GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc,
                 0,
                 0x17u,
                 &GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5,
                 v40);
    v9 = Instance;
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D8,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)Instance,
        (int)ppva);
LABEL_11:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v40);
      goto LABEL_50;
    }
    v42 = 0;
    v12 = Microsoft::WRL::ComPtr<IXblAuthManager>::As<IClientSecurity>(v40, &v42);
    v9 = v12;
    if ( v12 < 0 )
    {
      v13 = 1021;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v12,
        (int)ppva);
LABEL_15:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
      goto LABEL_11;
    }
    LODWORD(ppva) = -1;
    v12 = (*(__int64 (__fastcall **)(__int64, LPVOID, __int64, __int64))(*(_QWORD *)v42 + 32LL))(
            v42,
            v40[0],
            0xFFFFFFFFLL,
            0xFFFFFFFFLL);
    v9 = v12;
    if ( v12 < 0 )
    {
      v13 = 1022;
      goto LABEL_14;
    }
    if ( !a3 )
    {
      v14 = v40[0];
      v15 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, PCWSTR, const wchar_t *))(*(_QWORD *)v40[0] + 504LL);
      v16 = pv;
      if ( pv )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)length);
        CoTaskMemFree(v16);
        wil::last_error_context::~last_error_context((wil::last_error_context *)length);
      }
      pv = 0;
      v17 = (WCHAR *)sourceString;
      if ( sourceString )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)length);
        CoTaskMemFree(v17);
        wil::last_error_context::~last_error_context((wil::last_error_context *)length);
      }
      sourceString = 0;
      WindowsGetStringRawBuffer(string, 0);
      StringRawBuffer = WindowsGetStringRawBuffer(v47[0], 0);
      IsPlatformXbox = WinStoreAuth::AuthenticationInternal::IsPlatformXbox(v19);
      v21 = L"S-1-15-2-903380885-3144618533-3326689759-1293738580-1356288723-3824823557-3342340653";
      if ( !IsPlatformXbox )
        v21 = L"S-1-15-2-1609473798-1231923017-684268153-4268514328-882773646-2760585773-1760938157";
      ppva = (LPVOID *)L"GET";
      v12 = v15(v14, v21, StringRawBuffer, L"MBI_SSL");
      v9 = v12;
      if ( v12 < 0 )
      {
        v13 = 1039;
        goto LABEL_14;
      }
LABEL_41:
      *(_QWORD *)length = 0;
      v12 = StringCchLengthW(sourceString, 0x7FFFFFFFu, (unsigned __int64 *)length);
      v9 = v12;
      if ( v12 >= 0 )
      {
        v12 = WindowsCreateString(sourceString, length[0], a6);
        v9 = v12;
        if ( v12 >= 0 )
        {
          *(_QWORD *)length = 0;
          v12 = StringCchLengthW((const unsigned __int16 *)pv, 0x7FFFFFFFu, (unsigned __int64 *)length);
          v9 = v12;
          if ( v12 >= 0 )
          {
            v12 = WindowsCreateString((PCNZWCH)pv, length[0], a7);
            v9 = v12;
            if ( v12 >= 0 )
            {
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v40);
              v9 = 0;
              goto LABEL_50;
            }
            v13 = 1124;
          }
          else
          {
            v13 = 1123;
          }
        }
        else
        {
          v13 = 1120;
        }
      }
      else
      {
        v13 = 1119;
      }
      goto LABEL_14;
    }
    v45 = 0;
    v22 = v40[0];
    v23 = *(__int64 (__fastcall **)(LPVOID, _QWORD, PCWSTR, _QWORD))(*(_QWORD *)v40[0] + 456LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
    WindowsGetStringRawBuffer(string, 0);
    v24 = (unsigned int)WindowsGetStringRawBuffer(v47[0], 0);
    v26 = WinStoreAuth::AuthenticationInternal::IsPlatformXbox(v25);
    v27 = L"S-1-15-2-903380885-3144618533-3326689759-1293738580-1356288723-3824823557-3342340653";
    if ( !v26 )
      v27 = L"S-1-15-2-1609473798-1231923017-684268153-4268514328-882773646-2760585773-1760938157";
    *(_QWORD *)length = v27;
    v28 = WindowsGetStringRawBuffer(a3, 0);
    LODWORD(ppva) = v24;
    v29 = v23(v22, 0, v28, *(_QWORD *)length);
    v9 = v29;
    if ( v29 >= 0 )
    {
      v31 = v45;
      v32 = *(__int64 (__fastcall **)(__int64, PCNZWCH *))(*(_QWORD *)v45 + 40LL);
      v33 = (WCHAR *)sourceString;
      if ( sourceString )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)length);
        CoTaskMemFree(v33);
        wil::last_error_context::~last_error_context((wil::last_error_context *)length);
      }
      sourceString = 0;
      v29 = v32(v31, &sourceString);
      v9 = v29;
      if ( v29 >= 0 )
      {
        v34 = v45;
        v35 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v45 + 48LL);
        v36 = pv;
        if ( pv )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)length);
          CoTaskMemFree(v36);
          wil::last_error_context::~last_error_context((wil::last_error_context *)length);
        }
        pv = 0;
        v29 = v35(v34, &pv);
        v9 = v29;
        if ( v29 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
          goto LABEL_41;
        }
        v30 = 1115;
      }
      else
      {
        v30 = 1114;
      }
    }
    else
    {
      v30 = 1112;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v29,
      (int)ppva);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
    goto LABEL_15;
  }
  v10 = 975;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
    (const char *)(unsigned int)SlsValue,
    ppv);
LABEL_50:
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v47[0]);
  v47[0] = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&sourceString);
  return v9;
}

```

## disassembly

```asm
0x1800a6df0  push    rbp
0x1800a6df2  push    rbx
0x1800a6df3  push    rsi
0x1800a6df4  push    rdi
0x1800a6df5  push    r12
0x1800a6df7  push    r13
0x1800a6df9  push    r14
0x1800a6dfb  push    r15
0x1800a6dfd  lea     rbp, [rsp-7]
0x1800a6e02  sub     rsp, 0C8h
0x1800a6e09  mov     r13, r8
0x1800a6e0c  mov     r15, [rbp+3Fh+arg_28]
0x1800a6e10  mov     r12, [rbp+3Fh+arg_30]
0x1800a6e14  xor     r14d, r14d
0x1800a6e17  mov     qword ptr [rbp+3Fh+length], r14
0x1800a6e1b  mov     [rbp+3Fh+sourceString], r14
0x1800a6e1f  mov     [rbp+3Fh+pv], r14
0x1800a6e23  mov     [r15], r14
0x1800a6e26  mov     [r12], r14
0x1800a6e2a  mov     [rbp+3Fh+var_48], r14
0x1800a6e2e  mov     [rbp+3Fh+string], r14
0x1800a6e32  xor     ecx, ecx; string
0x1800a6e34  call    cs:__imp_WindowsDeleteString
0x1800a6e3a  mov     [rbp+3Fh+var_48], r14
0x1800a6e3e  lea     rdx, [rbp+3Fh+var_48]
0x1800a6e42  lea     ecx, [r14+5]
0x1800a6e46  call    ?GetSlsValue@WinStoreAuth@@YAJW4SlsIndex@1@PEAPEAUHSTRING__@@@Z; WinStoreAuth::GetSlsValue(WinStoreAuth::SlsIndex,HSTRING__ * *)
0x1800a6e4b  mov     ebx, eax
0x1800a6e4d  test    eax, eax
0x1800a6e4f  jns     short loc_1800A6E58
0x1800a6e51  mov     edx, 3CFh
0x1800a6e56  jmp     short loc_1800A6E70
0x1800a6e58  lea     rdx, [rbp+3Fh+length]; HSTRING *
0x1800a6e5c  lea     rcx, [rbp+3Fh+string]; newString
0x1800a6e60  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800a6e65  mov     ebx, eax
0x1800a6e67  test    eax, eax
0x1800a6e69  jns     short loc_1800A6E88
0x1800a6e6b  mov     edx, 3D1h; void *
0x1800a6e70  mov     rcx, [rbp+47h]; this
0x1800a6e74  mov     r9d, eax; char *
0x1800a6e77  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800a6e7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6e83  jmp     loc_1800A72CC
0x1800a6e88  cmp     [rbp+3Fh+string], r14
0x1800a6e8c  jnz     short loc_1800A6EB5
0x1800a6e8e  xor     ecx, ecx; string
0x1800a6e90  call    cs:__imp_WindowsDeleteString
0x1800a6e96  mov     [rbp+3Fh+string], r14
0x1800a6e9a  lea     rdx, [rbp+3Fh+string]
0x1800a6e9e  mov     ecx, 6
0x1800a6ea3  call    ?GetSlsValue@WinStoreAuth@@YAJW4SlsIndex@1@PEAPEAUHSTRING__@@@Z; WinStoreAuth::GetSlsValue(WinStoreAuth::SlsIndex,HSTRING__ * *)
0x1800a6ea8  mov     ebx, eax
0x1800a6eaa  test    eax, eax
0x1800a6eac  jns     short loc_1800A6EB5
0x1800a6eae  mov     edx, 3D4h
0x1800a6eb3  jmp     short loc_1800A6E70
0x1800a6eb5  mov     [rbp+3Fh+var_90], r14
0x1800a6eb9  lea     rax, [rbp+3Fh+var_90]
0x1800a6ebd  mov     [rsp+100h+ppv], rax; int
0x1800a6ec2  lea     r9, _GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5; riid
0x1800a6ec9  xor     edx, edx; pUnkOuter
0x1800a6ecb  lea     r8d, [rdx+17h]; dwClsContext
0x1800a6ecf  lea     rcx, _GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc; rclsid
0x1800a6ed6  call    cs:__imp_CoCreateInstance
0x1800a6edc  mov     ebx, eax
0x1800a6ede  test    eax, eax
0x1800a6ee0  jns     short loc_1800A6F09
0x1800a6ee2  mov     rcx, [rbp+47h]; this
0x1800a6ee6  mov     r9d, eax; char *
0x1800a6ee9  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800a6ef0  mov     edx, 3D8h; void *
0x1800a6ef5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6efa  nop
0x1800a6efb  lea     rcx, [rbp+3Fh+var_90]
0x1800a6eff  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a6f04  jmp     loc_1800A72CC
0x1800a6f09  mov     [rbp+3Fh+var_70], r14
0x1800a6f0d  lea     rdx, [rbp+3Fh+var_70]
0x1800a6f11  lea     rcx, [rbp+3Fh+var_90]
0x1800a6f15  call    ??$As@UIClientSecurity@@@?$ComPtr@UIXblAuthManager@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIClientSecurity@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IXblAuthManager>::As<IClientSecurity>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IClientSecurity>>)
0x1800a6f1a  mov     ebx, eax
0x1800a6f1c  test    eax, eax
0x1800a6f1e  jns     short loc_1800A6F44
0x1800a6f20  mov     edx, 3FDh; void *
0x1800a6f25  mov     rcx, [rbp+47h]; this
0x1800a6f29  mov     r9d, eax; char *
0x1800a6f2c  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800a6f33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6f38  nop
0x1800a6f39  lea     rcx, [rbp+3Fh+var_70]
0x1800a6f3d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a6f42  jmp     short loc_1800A6EFB
0x1800a6f44  mov     rcx, [rbp+3Fh+var_70]
0x1800a6f48  mov     rax, [rcx]
0x1800a6f4b  mov     dword ptr [rsp+100h+var_C0], 40h ; '@'
0x1800a6f53  mov     [rsp+100h+var_C8], r14
0x1800a6f58  mov     dword ptr [rsp+100h+var_D0], 3
0x1800a6f60  mov     dword ptr [rsp+100h+var_D8], r14d
0x1800a6f65  mov     [rsp+100h+ppv], 0FFFFFFFFFFFFFFFFh
0x1800a6f6e  or      r8d, 0FFFFFFFFh
0x1800a6f72  mov     r9d, r8d
0x1800a6f75  mov     rdx, [rbp+3Fh+var_90]
0x1800a6f79  mov     rax, [rax+20h]
0x1800a6f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6f82  mov     ebx, eax
0x1800a6f84  test    eax, eax
0x1800a6f86  jns     short loc_1800A6F8F
0x1800a6f88  mov     edx, 3FEh
0x1800a6f8d  jmp     short loc_1800A6F25
0x1800a6f8f  test    r13, r13
0x1800a6f92  jnz     loc_1800A7095
0x1800a6f98  mov     rsi, [rbp+3Fh+var_90]
0x1800a6f9c  mov     rax, [rsi]
0x1800a6f9f  mov     r14, [rax+1F8h]
0x1800a6fa6  mov     rbx, [rbp+3Fh+pv]
0x1800a6faa  test    rbx, rbx
0x1800a6fad  jz      short loc_1800A6FCA
0x1800a6faf  lea     rcx, [rbp+3Fh+length]; this
0x1800a6fb3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800a6fb8  mov     rcx, rbx; pv
0x1800a6fbb  call    cs:__imp_CoTaskMemFree
0x1800a6fc1  lea     rcx, [rbp+3Fh+length]; this
0x1800a6fc5  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800a6fca  mov     [rbp+3Fh+pv], r13
0x1800a6fce  mov     rbx, [rbp+3Fh+sourceString]
0x1800a6fd2  test    rbx, rbx
0x1800a6fd5  jz      short loc_1800A6FF2
0x1800a6fd7  lea     rcx, [rbp+3Fh+length]; this
0x1800a6fdb  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800a6fe0  mov     rcx, rbx; pv
0x1800a6fe3  call    cs:__imp_CoTaskMemFree
0x1800a6fe9  lea     rcx, [rbp+3Fh+length]; this
0x1800a6fed  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800a6ff2  mov     [rbp+3Fh+sourceString], r13
0x1800a6ff6  xor     edx, edx; length
0x1800a6ff8  mov     rcx, [rbp+3Fh+string]; string
0x1800a6ffc  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a7002  mov     rbx, rax
0x1800a7005  xor     edx, edx; length
0x1800a7007  mov     rcx, [rbp+3Fh+var_48]; string
0x1800a700b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a7011  mov     rdi, rax
0x1800a7014  call    ?IsPlatformXbox@AuthenticationInternal@WinStoreAuth@@YA_NXZ; WinStoreAuth::AuthenticationInternal::IsPlatformXbox(void)
0x1800a7019  lea     rdx, aS1152160947379; "S-1-15-2-1609473798-1231923017-68426815"...
0x1800a7020  lea     rcx, aS1152903380885; "S-1-15-2-903380885-3144618533-332668975"...
0x1800a7027  test    al, al
0x1800a7029  cmovz   rcx, rdx
0x1800a702d  lea     rax, [rbp+3Fh+pv]
0x1800a7031  mov     [rsp+100h+var_B0], rax
0x1800a7036  lea     rax, [rbp+3Fh+sourceString]
0x1800a703a  mov     [rsp+100h+var_B8], rax
0x1800a703f  mov     dword ptr [rsp+100h+var_C0], r13d
0x1800a7044  mov     [rsp+100h+var_C8], r13
0x1800a7049  lea     rdx, aXXblContractVe; "x-xbl-contract-version:2\r\nAccept:appl"...
0x1800a7050  mov     [rsp+100h+var_D0], rdx
0x1800a7055  mov     [rsp+100h+var_D8], rbx
0x1800a705a  lea     rdx, aGet; "GET"
0x1800a7061  mov     [rsp+100h+ppv], rdx
0x1800a7066  lea     r9, aMbiSsl; "MBI_SSL"
0x1800a706d  mov     r8, rdi
0x1800a7070  mov     rdx, rcx
0x1800a7073  mov     rcx, rsi
0x1800a7076  mov     rax, r14
0x1800a7079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a707e  mov     ebx, eax
0x1800a7080  xor     r14d, r14d
0x1800a7083  test    eax, eax
0x1800a7085  jns     loc_1800A722A
0x1800a708b  mov     edx, 40Fh
0x1800a7090  jmp     loc_1800A6F25
0x1800a7095  mov     [rbp+3Fh+var_58], r14
0x1800a7099  mov     r14, [rbp+3Fh+var_90]
0x1800a709d  mov     rax, [r14]
0x1800a70a0  mov     rsi, [rax+1C8h]
0x1800a70a7  lea     rcx, [rbp+3Fh+var_58]
0x1800a70ab  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a70b0  xor     edx, edx; length
0x1800a70b2  mov     rcx, [rbp+3Fh+string]; string
0x1800a70b6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a70bc  mov     rbx, rax
0x1800a70bf  xor     edx, edx; length
0x1800a70c1  mov     rcx, [rbp+3Fh+var_48]; string
0x1800a70c5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a70cb  mov     rdi, rax
0x1800a70ce  call    ?IsPlatformXbox@AuthenticationInternal@WinStoreAuth@@YA_NXZ; WinStoreAuth::AuthenticationInternal::IsPlatformXbox(void)
0x1800a70d3  lea     rdx, aS1152160947379; "S-1-15-2-1609473798-1231923017-68426815"...
0x1800a70da  lea     rcx, aS1152903380885; "S-1-15-2-903380885-3144618533-332668975"...
0x1800a70e1  test    al, al
0x1800a70e3  cmovz   rcx, rdx
0x1800a70e7  mov     qword ptr [rbp+3Fh+length], rcx
0x1800a70eb  xor     edx, edx; length
0x1800a70ed  mov     rcx, r13; string
0x1800a70f0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a70f6  lea     rcx, [rbp+3Fh+var_58]
0x1800a70fa  mov     [rsp+100h+var_A0], rcx
0x1800a70ff  xor     ecx, ecx
0x1800a7101  mov     [rsp+100h+var_A8], ecx
0x1800a7105  mov     dword ptr [rsp+100h+var_B0], ecx
0x1800a7109  mov     [rsp+100h+var_B8], rcx
0x1800a710e  lea     rdx, aXXblContractVe; "x-xbl-contract-version:2\r\nAccept:appl"...
0x1800a7115  mov     [rsp+100h+var_C0], rdx
0x1800a711a  mov     [rsp+100h+var_C8], rbx
0x1800a711f  lea     rdx, aGet; "GET"
0x1800a7126  mov     [rsp+100h+var_D0], rdx
0x1800a712b  lea     rdx, aMbiSsl; "MBI_SSL"
0x1800a7132  mov     [rsp+100h+var_D8], rdx
0x1800a7137  mov     [rsp+100h+ppv], rdi; int
0x1800a713c  mov     r9, qword ptr [rbp+3Fh+length]
0x1800a7140  mov     r8, rax
0x1800a7143  xor     edx, edx
0x1800a7145  mov     rcx, r14
0x1800a7148  mov     rax, rsi
0x1800a714b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7150  mov     ebx, eax
0x1800a7152  xor     r14d, r14d
0x1800a7155  test    eax, eax
0x1800a7157  jns     short loc_1800A7180
0x1800a7159  mov     edx, 458h; void *
0x1800a715e  mov     rcx, [rbp+47h]; this
0x1800a7162  mov     r9d, eax; char *
0x1800a7165  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800a716c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7171  nop
0x1800a7172  lea     rcx, [rbp+3Fh+var_58]
0x1800a7176  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a717b  jmp     loc_1800A6F39
0x1800a7180  mov     rdi, [rbp+3Fh+var_58]
0x1800a7184  mov     rax, [rdi]
0x1800a7187  mov     rsi, [rax+28h]
0x1800a718b  mov     rbx, [rbp+3Fh+sourceString]
0x1800a718f  test    rbx, rbx
0x1800a7192  jz      short loc_1800A71AF
0x1800a7194  lea     rcx, [rbp+3Fh+length]; this
0x1800a7198  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800a719d  mov     rcx, rbx; pv
0x1800a71a0  call    cs:__imp_CoTaskMemFree
0x1800a71a6  lea     rcx, [rbp+3Fh+length]; this
0x1800a71aa  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800a71af  mov     [rbp+3Fh+sourceString], r14
0x1800a71b3  lea     rdx, [rbp+3Fh+sourceString]
0x1800a71b7  mov     rcx, rdi
0x1800a71ba  mov     rax, rsi
0x1800a71bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a71c2  mov     ebx, eax
0x1800a71c4  test    eax, eax
0x1800a71c6  jns     short loc_1800A71CF
0x1800a71c8  mov     edx, 45Ah
0x1800a71cd  jmp     short loc_1800A715E
0x1800a71cf  mov     rdi, [rbp+3Fh+var_58]
0x1800a71d3  mov     rax, [rdi]
0x1800a71d6  mov     rsi, [rax+30h]
0x1800a71da  mov     rbx, [rbp+3Fh+pv]
0x1800a71de  test    rbx, rbx
0x1800a71e1  jz      short loc_1800A71FE
0x1800a71e3  lea     rcx, [rbp+3Fh+length]; this
0x1800a71e7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800a71ec  mov     rcx, rbx; pv
0x1800a71ef  call    cs:__imp_CoTaskMemFree
0x1800a71f5  lea     rcx, [rbp+3Fh+length]; this
0x1800a71f9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800a71fe  mov     [rbp+3Fh+pv], r14
0x1800a7202  lea     rdx, [rbp+3Fh+pv]
0x1800a7206  mov     rcx, rdi
0x1800a7209  mov     rax, rsi
0x1800a720c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7211  mov     ebx, eax
0x1800a7213  test    eax, eax
0x1800a7215  jns     short loc_1800A7221
0x1800a7217  mov     edx, 45Bh
0x1800a721c  jmp     loc_1800A715E
0x1800a7221  lea     rcx, [rbp+3Fh+var_58]
0x1800a7225  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a722a  mov     qword ptr [rbp+3Fh+length], r14
0x1800a722e  lea     r8, [rbp+3Fh+length]; unsigned __int64 *
0x1800a7232  mov     edi, 7FFFFFFFh
0x1800a7237  mov     edx, edi; unsigned __int64
0x1800a7239  mov     rcx, [rbp+3Fh+sourceString]; unsigned __int16 *
0x1800a723d  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800a7242  mov     ebx, eax
0x1800a7244  test    eax, eax
0x1800a7246  jns     short loc_1800A7252
0x1800a7248  mov     edx, 45Fh
0x1800a724d  jmp     loc_1800A6F25
0x1800a7252  mov     r8, r15; string
0x1800a7255  mov     edx, [rbp+3Fh+length]; length
0x1800a7258  mov     rcx, [rbp+3Fh+sourceString]; sourceString
0x1800a725c  call    cs:__imp_WindowsCreateString
0x1800a7262  mov     ebx, eax
0x1800a7264  test    eax, eax
0x1800a7266  jns     short loc_1800A7272
0x1800a7268  mov     edx, 460h
0x1800a726d  jmp     loc_1800A6F25
0x1800a7272  mov     qword ptr [rbp+3Fh+length], r14
0x1800a7276  lea     r8, [rbp+3Fh+length]; unsigned __int64 *
0x1800a727a  mov     rdx, rdi; unsigned __int64
0x1800a727d  mov     rcx, [rbp+3Fh+pv]; unsigned __int16 *
0x1800a7281  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800a7286  mov     ebx, eax
0x1800a7288  test    eax, eax
  ... truncated ...
```
