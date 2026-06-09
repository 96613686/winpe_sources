# CDPComAppControlHandler::CallAppServiceInternal(unsigned __int64,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::vector<uchar,std::allocator<uchar>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,CDPComAppServiceDataFormat,unsigned __int64)

- ea: `0x18004bdac`
- end: `0x18004c42e`
- name: `?CallAppServiceInternal@CDPComAppControlHandler@@AEAAX_KAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEBV?$vector@EV?$allocator@E@std@@@3@11W4CDPComAppServiceDataFormat@@0@Z`
- size: `1666`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004b600`

## callees

- `0x180001008`
- `0x180001130`
- `0x180002a4c`
- `0x180003678`
- `0x180004a58`
- `0x180004a98`
- `0x180005028`
- `0x1800198bc`
- `0x18001b1f0`
- `0x18001b92c`
- `0x18001c284`
- `0x18001e0f0`
- `0x180026bbc`
- `0x1800283a8`
- `0x18002862c`
- `0x1800289cc`
- `0x180029304`
- `0x18002c570`
- `0x18003eecc`
- `0x180041054`
- `0x18004bdac`
- `0x18004d5bc`
- `0x18005c0fc`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c053`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c0fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c111`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c121`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c134`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c3b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c053`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c0fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c111`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c121`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c134`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c3b0`

## string_xrefs

- `0x18004c2b2`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004c406`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004c41b`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004c2bc`: `{"hr":"0x%08x","file":"%s","line":%d,"text":"Failure calling OnCallAppServiceComplete"}`
- `0x18004bf5c`: `Starting request to Call App Service. PFN = %s, App Service Name = %s and Input Message JSON = '%s'.`
- `0x18004c377`: `Invocation of App Service complete. Name = %s, PFN = %s, Result = 0x%08x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CDPComAppControlHandler::CallAppServiceInternal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        __int64 a6,
        __int64 a7,
        unsigned int a8,
        __int64 a9)
{
  __int64 v9; // r12
  __int64 v10; // r13
  __int64 v11; // r8
  _DWORD *v12; // r9
  const char *v13; // rdi
  const char *v14; // rbx
  const char *v15; // r8
  __int64 v16; // r8
  int v17; // r14d
  HSTRING v18; // rbx
  int v19; // eax
  int v20; // eax
  AppServiceHelper *v21; // r15
  HSTRING v22; // r14
  HSTRING v23; // rdi
  HSTRING v24; // rbx
  HSTRING *v25; // rax
  __int64 v26; // rbx
  wil *v27; // rcx
  int v28; // edi
  __int64 v29; // r15
  __int64 v30; // rdx
  int v31; // eax
  const char *v32; // rdi
  const char *v33; // r8
  int v35; // [rsp+20h] [rbp-198h]
  struct Windows::Foundation::Collections::IPropertySet *v36; // [rsp+48h] [rbp-170h] BYREF
  HSTRING v37; // [rsp+50h] [rbp-168h] BYREF
  HSTRING v38; // [rsp+58h] [rbp-160h] BYREF
  HSTRING v39; // [rsp+60h] [rbp-158h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v40; // [rsp+68h] [rbp-150h] BYREF
  AppServiceHelper *v41; // [rsp+70h] [rbp-148h] BYREF
  __int64 v42; // [rsp+78h] [rbp-140h]
  __int128 v43; // [rsp+80h] [rbp-138h] BYREF
  __int64 v44; // [rsp+90h] [rbp-128h]
  HSTRING string; // [rsp+98h] [rbp-120h] BYREF
  __int64 v46; // [rsp+A0h] [rbp-118h]
  __int64 v47; // [rsp+A8h] [rbp-110h]
  __int64 v48; // [rsp+B0h] [rbp-108h]
  struct Windows::Foundation::Collections::IPropertySet *v49; // [rsp+B8h] [rbp-100h]
  HSTRING v50; // [rsp+C0h] [rbp-F8h] BYREF
  __int64 v51; // [rsp+C8h] [rbp-F0h]
  __int64 v52; // [rsp+D0h] [rbp-E8h]
  __int64 v53; // [rsp+D8h] [rbp-E0h]
  __int64 v54; // [rsp+E0h] [rbp-D8h]
  HSTRING_HEADER hstringHeader; // [rsp+E8h] [rbp-D0h] BYREF
  __int64 v56; // [rsp+100h] [rbp-B8h]
  int v57; // [rsp+108h] [rbp-B0h] BYREF
  char v58; // [rsp+10Ch] [rbp-ACh]
  _BYTE v59[16]; // [rsp+110h] [rbp-A8h] BYREF
  _DWORD v60[4]; // [rsp+120h] [rbp-98h] BYREF
  _BYTE v61[32]; // [rsp+130h] [rbp-88h] BYREF
  _BYTE v62[32]; // [rsp+150h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v9 = a4;
  v10 = a3;
  v46 = a2;
  v42 = a1;
  v51 = a1;
  v52 = a2;
  v53 = a3;
  v54 = a4;
  v48 = a6;
  v47 = a7;
  v57 = 0;
  v58 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v57);
  if ( (unsigned int)dword_180094048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180094048, 0x400000000000LL, v11) )
  {
    v40 = (struct Windows::Foundation::Collections::IPropertySet *)std::_String_val<std::_Simple_types<char>>::_Myptr(v9);
    v39 = (HSTRING)std::_String_val<std::_Simple_types<char>>::_Myptr(v10);
    v38 = (HSTRING)0x1000000;
    if ( v58 && (v60[0] || v60[1] || v60[2] || v60[3]) )
      v12 = v60;
    else
      v12 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (__int64)&dword_180094048,
      (__int64)&word_18008379E,
      (__int64)v59,
      (__int64)v12,
      (__int64)&v38,
      &v39,
      &v40);
  }
  std::string::string(v62, *a5, a5[1]);
  v13 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v62);
  v14 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v9);
  v15 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v10);
  cdp::detail::StringFormat(
    &hstringHeader,
    "Starting request to Call App Service. PFN = %s, App Service Name = %s and Input Message JSON = '%s'.",
    v15,
    v14,
    v13);
  shared::LogMessage(4, &hstringHeader);
  std::string::_Tidy_deallocate(&hstringHeader);
  if ( !*(_QWORD *)(v10 + 16) || (v17 = 0, !*(_QWORD *)(v9 + 16)) )
    v17 = -2147024809;
  v43 = 0;
  v44 = 0;
  v18 = 0;
  v37 = 0;
  if ( v17 >= 0 )
  {
    v41 = 0;
    v19 = Microsoft::WRL::Details::MakeAndInitialize<AppServiceHelper,AppServiceHelper,>(&v41);
    try
    {
      if ( v19 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x177,
          (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
          (const char *)(unsigned int)v19,
          v35);
      CDPComAppControlHandler::DeserializeAppServiceData(&v40, a5, a8);
      v36 = 0;
      v56 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Foundation.Collections.ValueSet",
        0x28u,
        0x27u);
      v20 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
              v56,
              &v36);
      if ( v20 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x17E,
          (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
          (const char *)(unsigned int)v20,
          v35);
      v21 = v41;
      WindowsDeleteString(0);
      v37 = 0;
      v49 = v40;
      v22 = *(HSTRING *)cdp::UTF8toHSTRING(&v50, v47);
      v23 = *(HSTRING *)cdp::UTF8toHSTRING(&v39, v48);
      v24 = *(HSTRING *)cdp::UTF8toHSTRING(&v38, v9);
      v25 = (HSTRING *)cdp::UTF8toHSTRING(&string, v10);
      v17 = AppServiceHelper::OpenAppServiceAndSendMessageAsync(v21, *v25, v24, v23, v22, v49, &v36, &v37);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v38);
      v38 = 0;
      WindowsDeleteString(v39);
      v39 = 0;
      WindowsDeleteString(v50);
      if ( v17 >= 0 )
      {
        v26 = CDPComAppControlHandler::SerializeAppServiceData(&hstringHeader, &v36, a8);
        if ( &v43 != (__int128 *)v26 )
        {
          std::vector<enum CDPActivityStorePatchField>::_Tidy(&v43);
          v43 = *(_OWORD *)v26;
          v44 = *(_QWORD *)(v26 + 16);
          *(_QWORD *)v26 = 0;
          *(_QWORD *)(v26 + 8) = 0;
          *(_QWORD *)(v26 + 16) = 0;
        }
        std::vector<enum CDPActivityStorePatchField>::_Tidy(&hstringHeader);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
    }
    catch ( ... )
    {
      v17 = wil::ResultFromCaughtException(v27);
      v42 = v51;
      v46 = v52;
      v10 = v53;
      v9 = v54;
    }
    v18 = v37;
  }
  if ( *(_QWORD *)(v42 + 16) )
  {
    v28 = v43;
    v29 = v43;
    if ( (_QWORD)v43 == *((_QWORD *)&v43 + 1) )
      v29 = 0;
    cdp::HSTRINGtoUTF8(&hstringHeader, v18);
    if ( *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] )
      v30 = std::_String_val<std::_Simple_types<char>>::_Myptr(&hstringHeader);
    else
      v30 = 0;
    v31 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64, int, __int64, __int64))(**(_QWORD **)(v42 + 16)
                                                                                             + 32LL))(
            *(_QWORD *)(v42 + 16),
            v46,
            (unsigned int)v17,
            v29,
            DWORD2(v43) - v28,
            a9,
            v30);
    if ( v31 < 0 )
    {
      cdp::detail::StringFormat(
        v61,
        "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Failure calling OnCallAppServiceComplete\"}",
        v31,
        "..\\cdpcomappcontrolhandler.cpp",
        411);
      shared::LogMessage(1, v61);
      std::string::_Tidy_deallocate(v61);
    }
    std::string::_Tidy_deallocate(&hstringHeader);
  }
  v57 = 2;
  if ( (unsigned int)dword_180094048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180094048, 0x400000000000LL, v16) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180094048,
      (__int64)byte_180083755);
  v32 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v10);
  v33 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v9);
  cdp::detail::StringFormat(
    v61,
    "Invocation of App Service complete. Name = %s, PFN = %s, Result = 0x%08x.",
    v33,
    v32,
    v17);
  shared::LogMessage(3, v61);
  std::string::_Tidy_deallocate(v61);
  WindowsDeleteString(v18);
  std::vector<enum CDPActivityStorePatchField>::_Tidy(&v43);
  std::string::_Tidy_deallocate(v62);
  return _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v57);
}

```

## disassembly

```asm
0x18004bdac  push    rbx
0x18004bdae  push    rsi
0x18004bdaf  push    rdi
0x18004bdb0  push    r12
0x18004bdb2  push    r13
0x18004bdb4  push    r14
0x18004bdb6  push    r15
0x18004bdb8  sub     rsp, 180h
0x18004bdbf  mov     rax, cs:__security_cookie
0x18004bdc6  xor     rax, rsp
0x18004bdc9  mov     [rsp+1B8h+var_48], rax
0x18004bdd1  mov     r12, r9
0x18004bdd4  mov     r13, r8
0x18004bdd7  mov     [rsp+1B8h+var_118], rdx
0x18004bddf  mov     [rsp+1B8h+var_140], rcx
0x18004bde4  mov     r15, [rsp+1B8h+arg_20]
0x18004bdec  mov     [rsp+1B8h+var_F0], rcx
0x18004bdf4  mov     [rsp+1B8h+var_E8], rdx
0x18004bdfc  mov     [rsp+1B8h+var_E0], r8
0x18004be04  mov     [rsp+1B8h+var_D8], r9
0x18004be0c  mov     rax, [rsp+1B8h+arg_28]
0x18004be14  mov     [rsp+1B8h+var_108], rax
0x18004be1c  mov     rax, [rsp+1B8h+arg_30]
0x18004be24  mov     [rsp+1B8h+var_110], rax
0x18004be2c  mov     eax, [rsp+1B8h+arg_38]
0x18004be33  mov     [rsp+1B8h+var_178], eax
0x18004be37  xor     esi, esi
0x18004be39  mov     [rsp+1B8h+var_B0], esi
0x18004be40  mov     [rsp+1B8h+var_AC], sil
0x18004be48  lea     rcx, [rsp+1B8h+var_B0]
0x18004be50  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hCDPUserServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x18004be55  mov     eax, cs:dword_180094048
0x18004be5b  cmp     eax, 5
0x18004be5e  jbe     loc_18004BF19
0x18004be64  mov     rdx, 400000000000h
0x18004be6e  lea     rcx, dword_180094048
0x18004be75  call    _tlgKeywordOn
0x18004be7a  test    al, al
0x18004be7c  jz      loc_18004BF19
0x18004be82  mov     rcx, r12
0x18004be85  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18004be8a  mov     [rsp+1B8h+var_150], rax
0x18004be8f  mov     rcx, r13
0x18004be92  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18004be97  mov     [rsp+1B8h+var_158], rax
0x18004be9c  mov     [rsp+1B8h+var_160], 1000000h
0x18004bea5  cmp     [rsp+1B8h+var_AC], sil
0x18004bead  jz      short loc_18004BEDD
0x18004beaf  cmp     [rsp+1B8h+var_98], esi
0x18004beb6  jnz     short loc_18004BED3
0x18004beb8  cmp     [rsp+1B8h+var_94], esi
0x18004bebf  jnz     short loc_18004BED3
0x18004bec1  cmp     [rsp+1B8h+var_90], esi
0x18004bec8  jnz     short loc_18004BED3
0x18004beca  cmp     [rsp+1B8h+var_8C], esi
0x18004bed1  jz      short loc_18004BEDD
0x18004bed3  lea     r9, [rsp+1B8h+var_98]
0x18004bedb  jmp     short loc_18004BEE0
0x18004bedd  mov     r9, rsi
0x18004bee0  lea     rax, [rsp+1B8h+var_150]
0x18004bee5  mov     [rsp+1B8h+var_188], rax
0x18004beea  lea     rax, [rsp+1B8h+var_158]
0x18004beef  mov     [rsp+1B8h+var_190], rax
0x18004bef4  lea     rax, [rsp+1B8h+var_160]
0x18004bef9  mov     [rsp+1B8h+var_198], rax
0x18004befe  lea     r8, [rsp+1B8h+var_A8]
0x18004bf06  lea     rdx, word_18008379E
0x18004bf0d  lea     rcx, dword_180094048
0x18004bf14  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18004bf19  mov     r8, [r15+8]
0x18004bf1d  mov     rdx, [r15]
0x18004bf20  lea     rcx, [rsp+1B8h+var_68]
0x18004bf28  call    ??$?0V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@0AEBV?$allocator@D@1@@Z; std::string::string(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::allocator<char> const &)
0x18004bf2d  nop
0x18004bf2e  lea     rcx, [rsp+1B8h+var_68]
0x18004bf36  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18004bf3b  mov     rdi, rax
0x18004bf3e  mov     rcx, r12
0x18004bf41  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18004bf46  mov     rbx, rax
0x18004bf49  mov     rcx, r13
0x18004bf4c  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18004bf51  mov     r8, rax
0x18004bf54  mov     [rsp+1B8h+var_198], rdi; int
0x18004bf59  mov     r9, rbx
0x18004bf5c  lea     rdx, aStartingReques; "Starting request to Call App Service. P"...
0x18004bf63  lea     rcx, [rsp+1B8h+hstringHeader]
0x18004bf6b  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x18004bf70  nop
0x18004bf71  lea     rdx, [rsp+1B8h+hstringHeader]
0x18004bf79  mov     ecx, 4
0x18004bf7e  call    ?LogMessage@shared@@YAXW4CDPLogLevel@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; shared::LogMessage(CDPLogLevel,std::string &)
0x18004bf83  nop
0x18004bf84  lea     rcx, [rsp+1B8h+hstringHeader]
0x18004bf8c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004bf91  cmp     [r13+10h], rsi
0x18004bf95  jz      short loc_18004BFA1
0x18004bf97  mov     r14d, esi
0x18004bf9a  cmp     [r12+10h], rsi
0x18004bf9f  jnz     short loc_18004BFA7
0x18004bfa1  mov     r14d, 80070057h
0x18004bfa7  xorps   xmm0, xmm0
0x18004bfaa  movdqu  [rsp+1B8h+var_138], xmm0
0x18004bfb3  mov     [rsp+1B8h+var_128], rsi
0x18004bfbb  mov     rbx, rsi
0x18004bfbe  mov     [rsp+1B8h+var_168], rbx
0x18004bfc3  test    r14d, r14d
0x18004bfc6  js      loc_18004C20B
0x18004bfcc  mov     [rsp+1B8h+var_148], rsi
0x18004bfd1  lea     rcx, [rsp+1B8h+var_148]
0x18004bfd6  call    ??$MakeAndInitialize@VAppServiceHelper@@V1@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VAppServiceHelper@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<AppServiceHelper,AppServiceHelper,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<AppServiceHelper>>)
0x18004bfdb  mov     rcx, [rsp+1B8h]; this
0x18004bfe3  test    eax, eax
0x18004bfe5  js      loc_18004C403
0x18004bfeb  mov     r8d, [rsp+1B8h+var_178]
0x18004bff0  mov     rdx, r15
0x18004bff3  lea     rcx, [rsp+1B8h+var_150]
0x18004bff8  call    ?DeserializeAppServiceData@CDPComAppControlHandler@@CA?AV?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBV?$vector@EV?$allocator@E@std@@@std@@W4CDPComAppServiceDataFormat@@@Z; CDPComAppControlHandler::DeserializeAppServiceData(std::vector<uchar> const &,CDPComAppServiceDataFormat)
0x18004bffd  nop
0x18004bffe  mov     [rsp+1B8h+var_170], rsi
0x18004c003  mov     [rsp+1B8h+var_B8], rsi
0x18004c00b  mov     r9d, 27h ; '''; unsigned int
0x18004c011  lea     r8d, [r9+1]; unsigned int
0x18004c015  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_ValueSet@@3QBGB; "Windows.Foundation.Collections.ValueSet"
0x18004c01c  lea     rcx, [rsp+1B8h+hstringHeader]; hstringHeader
0x18004c024  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004c029  nop
0x18004c02a  lea     rdx, [rsp+1B8h+var_170]
0x18004c02f  mov     rcx, [rsp+1B8h+var_B8]
0x18004c037  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x18004c03c  mov     rcx, [rsp+1B8h]; this
0x18004c044  test    eax, eax
0x18004c046  js      loc_18004C418
0x18004c04c  mov     r15, [rsp+1B8h+var_148]
0x18004c051  xor     ecx, ecx; string
0x18004c053  call    cs:__imp_WindowsDeleteString
0x18004c059  mov     [rsp+1B8h+var_168], rsi
0x18004c05e  mov     rax, [rsp+1B8h+var_150]
0x18004c063  mov     [rsp+1B8h+var_100], rax
0x18004c06b  mov     rdx, [rsp+1B8h+var_110]
0x18004c073  lea     rcx, [rsp+1B8h+var_F8]
0x18004c07b  call    ?UTF8toHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UTF8toHSTRING(std::string const &)
0x18004c080  nop
0x18004c081  mov     r14, [rax]
0x18004c084  mov     rdx, [rsp+1B8h+var_108]
0x18004c08c  lea     rcx, [rsp+1B8h+var_158]
0x18004c091  call    ?UTF8toHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UTF8toHSTRING(std::string const &)
0x18004c096  nop
0x18004c097  mov     rdi, [rax]
0x18004c09a  mov     rdx, r12
0x18004c09d  lea     rcx, [rsp+1B8h+var_160]
0x18004c0a2  call    ?UTF8toHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UTF8toHSTRING(std::string const &)
0x18004c0a7  nop
0x18004c0a8  mov     rbx, [rax]
0x18004c0ab  mov     rdx, r13
0x18004c0ae  lea     rcx, [rsp+1B8h+string]
0x18004c0b6  call    ?UTF8toHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UTF8toHSTRING(std::string const &)
0x18004c0bb  nop
0x18004c0bc  lea     rcx, [rsp+1B8h+var_168]
0x18004c0c1  mov     [rsp+1B8h+var_180], rcx; HSTRING *
0x18004c0c6  lea     rcx, [rsp+1B8h+var_170]
0x18004c0cb  mov     [rsp+1B8h+var_188], rcx; struct Windows::Foundation::Collections::IPropertySet **
0x18004c0d0  mov     rcx, [rsp+1B8h+var_100]
0x18004c0d8  mov     [rsp+1B8h+var_190], rcx; struct Windows::Foundation::Collections::IPropertySet *
0x18004c0dd  mov     [rsp+1B8h+var_198], r14; HSTRING
0x18004c0e2  mov     r9, rdi; HSTRING
0x18004c0e5  mov     r8, rbx; HSTRING
0x18004c0e8  mov     rdx, [rax]; HSTRING
0x18004c0eb  mov     rcx, r15; this
0x18004c0ee  call    ?OpenAppServiceAndSendMessageAsync@AppServiceHelper@@QEAAJPEAUHSTRING__@@000PEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU3456@PEAPEAU2@@Z; AppServiceHelper::OpenAppServiceAndSendMessageAsync(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::Collections::IPropertySet * *,HSTRING__ * *)
0x18004c0f3  mov     r14d, eax
0x18004c0f6  mov     rcx, [rsp+1B8h+string]; string
0x18004c0fe  call    cs:__imp_WindowsDeleteString
0x18004c104  mov     [rsp+1B8h+string], rsi
0x18004c10c  mov     rcx, [rsp+1B8h+var_160]; string
0x18004c111  call    cs:__imp_WindowsDeleteString
0x18004c117  mov     [rsp+1B8h+var_160], rsi
0x18004c11c  mov     rcx, [rsp+1B8h+var_158]; string
0x18004c121  call    cs:__imp_WindowsDeleteString
0x18004c127  mov     [rsp+1B8h+var_158], rsi
0x18004c12c  mov     rcx, [rsp+1B8h+var_F8]; string
0x18004c134  call    cs:__imp_WindowsDeleteString
0x18004c13a  test    r14d, r14d
0x18004c13d  js      short loc_18004C1AF
0x18004c13f  mov     r8d, [rsp+1B8h+var_178]
0x18004c144  lea     rdx, [rsp+1B8h+var_170]
0x18004c149  lea     rcx, [rsp+1B8h+hstringHeader]
0x18004c151  call    ?SerializeAppServiceData@CDPComAppControlHandler@@CA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@W4CDPComAppServiceDataFormat@@@Z; CDPComAppControlHandler::SerializeAppServiceData(Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet> const &,CDPComAppServiceDataFormat)
0x18004c156  mov     rbx, rax
0x18004c159  lea     rax, [rsp+1B8h+var_138]
0x18004c161  cmp     rax, rbx
0x18004c164  jz      short loc_18004C1A1
0x18004c166  lea     rcx, [rsp+1B8h+var_138]
0x18004c16e  call    ?_Tidy@?$vector@W4CDPActivityStorePatchField@@V?$allocator@W4CDPActivityStorePatchField@@@std@@@std@@AEAAXXZ; std::vector<CDPActivityStorePatchField>::_Tidy(void)
0x18004c173  mov     rcx, [rbx]
0x18004c176  mov     qword ptr [rsp+1B8h+var_138], rcx
0x18004c17e  mov     rcx, [rbx+8]
0x18004c182  mov     qword ptr [rsp+1B8h+var_138+8], rcx
0x18004c18a  mov     rax, [rbx+10h]
0x18004c18e  mov     [rsp+1B8h+var_128], rax
0x18004c196  mov     [rbx], rsi
0x18004c199  mov     [rbx+8], rsi
0x18004c19d  mov     [rbx+10h], rsi
0x18004c1a1  lea     rcx, [rsp+1B8h+hstringHeader]
0x18004c1a9  call    ?_Tidy@?$vector@W4CDPActivityStorePatchField@@V?$allocator@W4CDPActivityStorePatchField@@@std@@@std@@AEAAXXZ; std::vector<CDPActivityStorePatchField>::_Tidy(void)
0x18004c1ae  nop
0x18004c1af  lea     rcx, [rsp+1B8h+var_170]
0x18004c1b4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c1b9  nop
0x18004c1ba  lea     rcx, [rsp+1B8h+var_150]
0x18004c1bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c1c4  nop
0x18004c1c5  lea     rcx, [rsp+1B8h+var_148]
0x18004c1ca  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c1cf  nop
0x18004c1d0  jmp     short loc_18004C206
0x18004c1d2  xor     esi, esi
0x18004c1d4  mov     r14d, [rsp+1B8h+var_178]
0x18004c1d9  mov     r13, [rsp+1B8h+var_F0]
0x18004c1e1  mov     [rsp+1B8h+var_140], r13
0x18004c1e6  mov     rax, [rsp+1B8h+var_E8]
0x18004c1ee  mov     [rsp+1B8h+var_118], rax
0x18004c1f6  mov     r13, [rsp+1B8h+var_E0]
0x18004c1fe  mov     r12, [rsp+1B8h+var_D8]
0x18004c206  mov     rbx, [rsp+1B8h+var_168]
0x18004c20b  mov     rax, [rsp+1B8h+var_140]
0x18004c210  cmp     [rax+10h], rsi
0x18004c214  jz      loc_18004C2FF
0x18004c21a  mov     rdi, qword ptr [rsp+1B8h+var_138]
0x18004c222  mov     r15, rdi
0x18004c225  cmp     rdi, qword ptr [rsp+1B8h+var_138+8]
0x18004c22d  cmovz   r15, rsi
0x18004c231  mov     rdx, rbx
0x18004c234  lea     rcx, [rsp+1B8h+hstringHeader]
0x18004c23c  call    ?HSTRINGtoUTF8@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAUHSTRING__@@@Z; cdp::HSTRINGtoUTF8(HSTRING__ * const)
0x18004c241  nop
0x18004c242  cmp     qword ptr [rsp+1B8h+hstringHeader.Reserved+10h], rsi
0x18004c24a  jnz     short loc_18004C251
0x18004c24c  mov     rdx, rsi
0x18004c24f  jmp     short loc_18004C261
0x18004c251  lea     rcx, [rsp+1B8h+hstringHeader]
0x18004c259  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18004c25e  mov     rdx, rax
0x18004c261  mov     rax, [rsp+1B8h+var_140]
0x18004c266  mov     rcx, [rax+10h]
0x18004c26a  mov     r8, [rcx]
0x18004c26d  mov     r10d, dword ptr [rsp+1B8h+var_138+8]
0x18004c275  sub     r10d, edi
0x18004c278  mov     rax, [r8+20h]
0x18004c27c  mov     [rsp+1B8h+var_188], rdx
0x18004c281  mov     r8, [rsp+1B8h+arg_40]
0x18004c289  mov     [rsp+1B8h+var_190], r8
0x18004c28e  mov     dword ptr [rsp+1B8h+var_198], r10d
0x18004c293  mov     r9, r15
0x18004c296  mov     r8d, r14d
0x18004c299  mov     rdx, [rsp+1B8h+var_118]
0x18004c2a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2a6  test    eax, eax
0x18004c2a8  jns     short loc_18004C2F2
0x18004c2aa  mov     dword ptr [rsp+1B8h+var_198], 19Bh
0x18004c2b2  lea     r9, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004c2b9  mov     r8d, eax
0x18004c2bc  lea     rdx, aHr0x08xFileSLi_11; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18004c2c3  lea     rcx, [rsp+1B8h+var_88]
0x18004c2cb  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x18004c2d0  nop
0x18004c2d1  lea     rdx, [rsp+1B8h+var_88]
0x18004c2d9  mov     ecx, 1
0x18004c2de  call    ?LogMessage@shared@@YAXW4CDPLogLevel@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; shared::LogMessage(CDPLogLevel,std::string &)
0x18004c2e3  nop
0x18004c2e4  lea     rcx, [rsp+1B8h+var_88]
0x18004c2ec  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004c2f1  nop
0x18004c2f2  lea     rcx, [rsp+1B8h+hstringHeader]
0x18004c2fa  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004c2ff  mov     [rsp+1B8h+var_B0], 2
0x18004c30a  mov     eax, cs:dword_180094048
0x18004c310  cmp     eax, 5
0x18004c313  jbe     short loc_18004C359
0x18004c315  mov     rdx, 400000000000h
0x18004c31f  lea     rcx, dword_180094048
0x18004c326  call    _tlgKeywordOn
0x18004c32b  test    al, al
0x18004c32d  jz      short loc_18004C359
0x18004c32f  mov     [rsp+1B8h+var_178], r14d
0x18004c334  lea     rax, [rsp+1B8h+var_178]
0x18004c339  mov     [rsp+1B8h+var_198], rax
0x18004c33e  lea     r8, [rsp+1B8h+var_A8]
0x18004c346  lea     rdx, byte_180083755
0x18004c34d  lea     rcx, dword_180094048
0x18004c354  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18004c359  mov     rcx, r13
0x18004c35c  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18004c361  mov     rdi, rax
0x18004c364  mov     rcx, r12
0x18004c367  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18004c36c  mov     r8, rax
0x18004c36f  mov     dword ptr [rsp+1B8h+var_198], r14d
0x18004c374  mov     r9, rdi
0x18004c377  lea     rdx, aInvocationOfAp; "Invocation of App Service complete. Nam"...
  ... truncated ...
```
