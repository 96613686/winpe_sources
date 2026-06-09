# DataStoreCache::MRTHelper::ResolveString(HSTRING__ *)

- ea: `0x180030fbc`
- end: `0x180031448`
- name: `?ResolveString@MRTHelper@DataStoreCache@@QEAA?AVHString@Wrappers@WRL@Microsoft@@PEAUHSTRING__@@@Z`
- size: `1164`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f898`
- `0x1802e3350`

## callees

- `0x18000ce94`
- `0x18000db14`
- `0x18000dc10`
- `0x18000dcc8`
- `0x18000dd8c`
- `0x18000dde8`
- `0x18000de8c`
- `0x18000dec0`
- `0x18000e158`
- `0x18000fe88`
- `0x18001dac0`
- `0x18001dfb8`
- `0x18002f1fc`
- `0x180030fbc`
- `0x180031450`
- `0x18003153c`
- `0x18003b500`
- `0x1800c1318`
- `0x1800c18c4`
- `0x1800f0854`
- `0x180161204`
- `0x180201e50`
- `0x18036be6c`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031262`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031426`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031262`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031426`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003101a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003139a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003101a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003139a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031212`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800312d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031212`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800312d0`

## string_xrefs

- `0x180031298`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrthelper.cpp`
- `0x1800312ad`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrthelper.cpp`
- `0x1800313b6`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrthelper.cpp`
- `0x1800313d9`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrthelper.cpp`
- `0x1800313f6`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
Microsoft::WRL::Wrappers::HString *__fastcall DataStoreCache::MRTHelper::ResolveString(
        HSTRING *a1,
        Microsoft::WRL::Wrappers::HString *a2,
        __int64 a3)
{
  const unsigned __int16 *StringRawBuffer; // rsi
  char v6; // r12
  HSTRING v7; // rdx
  int v8; // edi
  int v9; // eax
  struct IMrtResourceManager *v10; // rbx
  __int64 (__fastcall *v11)(struct IMrtResourceManager *, GUID *, __int64 *); // rdi
  int v12; // eax
  struct IResourceMap *v13; // rbx
  __int64 v14; // rcx
  struct IResourceMap *v15; // rcx
  struct IMrtResourceManager *v16; // rcx
  __int64 v17; // r8
  const unsigned __int16 *v18; // rdx
  int v19; // eax
  __int64 v20; // rdx
  __int64 (__fastcall *v22)(struct IResourceMap *, __int64, const unsigned __int16 *, LPVOID *); // rdi
  unsigned __int16 **v23; // r8
  int v24; // eax
  __int64 v25; // rbx
  struct IResourceMap *v26; // rsi
  __int64 (__fastcall *v27)(struct IResourceMap *, __int64, __int64, LPVOID *); // rdi
  int v28; // [rsp+20h] [rbp-E0h]
  bool v29; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v30; // [rsp+38h] [rbp-C8h] BYREF
  struct IResourceMap *v31; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+58h] [rbp-A8h]
  __int64 v35; // [rsp+60h] [rbp-A0h]
  UINT32 length; // [rsp+68h] [rbp-98h] BYREF
  struct IMrtResourceManager *v37; // [rsp+70h] [rbp-90h] BYREF
  HSTRING__ v38[2]; // [rsp+78h] [rbp-88h] BYREF
  int v39; // [rsp+80h] [rbp-80h]
  const unsigned __int16 *v40; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v41[2]; // [rsp+90h] [rbp-70h] BYREF
  void **v42; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v43[272]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v44[8]; // [rsp+1B8h] [rbp+B8h] BYREF
  _BYTE v45[48]; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v41[1] = a2;
  v39 = 0;
  DataStoreCache::MRTHelper::SimplifyFullyQualifiedResourceStringIfApplicable(&string, a3);
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
  v40 = StringRawBuffer;
  wil::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v42);
  v42 = &MRTTransformerTelemetry::ResolveMrtString::`vftable';
  MRTTransformerTelemetry::ResolveMrtString::StartActivity(&v42, 0, StringRawBuffer);
  v6 = 0;
  pv = 0;
  v29 = 0;
  v34 = -1;
  v35 = -1;
  v8 = DataStoreCache::MRTHelper::TryResolveDllReference(StringRawBuffer, length, &v29, (unsigned __int16 **)&pv);
  if ( v29 )
    goto LABEL_16;
  if ( !ShellMRTHelper::Common::HasMsResourceUriScheme((ShellMRTHelper::Common *)string, v7) )
  {
    v8 = -2147024809;
    goto LABEL_16;
  }
  v37 = 0;
  v31 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  v9 = DataStoreCache::MRTHelper::TryEnsureResourceManagerAndMap((DataStoreCache::MRTHelper *)a1, &v37, &v31);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrthelper.cpp",
      (const char *)(unsigned int)v9,
      v28);
  v30 = 0;
  v10 = v37;
  if ( v37 )
  {
    v11 = *(__int64 (__fastcall **)(struct IMrtResourceManager *, GUID *, __int64 *))(*(_QWORD *)v37 + 72LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    v12 = v11(v10, &GUID_e3c22b30_8502_4b2f_9133_559674587e51, &v30);
    if ( v12 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrthelper.cpp",
        (const char *)(unsigned int)v12,
        v28);
  }
  v13 = v31;
  if ( v31 && v30 )
  {
    v22 = *(__int64 (__fastcall **)(struct IResourceMap *, __int64, const unsigned __int16 *, LPVOID *))(*(_QWORD *)v31 + 48LL);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v34 = -1;
    v35 = -1;
    v8 = v22(v13, v30, StringRawBuffer, &pv);
    if ( v8 >= 0 )
      goto LABEL_10;
    *(_QWORD *)&v38[0].unused = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      v38,
      0);
    v24 = ShellMRTHelper::Common::TryRemoveImplicitResourcesPrefixFromShortenedMsResourceUri(
            (ShellMRTHelper::Common *)string,
            v38,
            v23);
    if ( v24 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x77,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrthelper.cpp",
        (const char *)(unsigned int)v24,
        v28);
    }
    else
    {
      v25 = *(_QWORD *)&v38[0].unused;
      if ( *(_QWORD *)&v38[0].unused )
      {
        if ( **(_WORD **)&v38[0].unused )
        {
          v26 = v31;
          v27 = *(__int64 (__fastcall **)(struct IResourceMap *, __int64, __int64, LPVOID *))(*(_QWORD *)v31 + 48LL);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
          v34 = -1;
          v35 = -1;
          v8 = v27(v26, v30, v25, &pv);
          if ( v8 >= 0 )
            goto LABEL_43;
        }
      }
    }
    if ( v8 == -2147009769 )
    {
      v41[0] = WindowsGetStringRawBuffer(a1[1], 0);
      MRTTransformerTelemetry::NamedResourceNotFound<unsigned short const *,unsigned short const * const &>(v41, &v40);
    }
    else
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x88,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrthelper.cpp",
        (const char *)(unsigned int)v8,
        v28);
    }
LABEL_43:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v38);
    goto LABEL_10;
  }
  v6 = 1;
  v8 = -2147023728;
LABEL_10:
  v14 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v15 = v31;
  if ( v31 )
  {
    v31 = 0;
    (*(void (__fastcall **)(struct IResourceMap *))(*(_QWORD *)v15 + 16LL))(v15);
  }
  v16 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(struct IMrtResourceManager *))(*(_QWORD *)v16 + 16LL))(v16);
  }
LABEL_16:
  *(_QWORD *)a2 = 0;
  v39 = 1;
  if ( v8 < 0 )
  {
    WindowsDeleteString(0);
    *(_QWORD *)a2 = string;
    string = 0;
    v20 = 0;
    if ( !v6 )
      v20 = (unsigned int)v8;
  }
  else
  {
    LODWORD(v17) = v34;
    if ( v34 == -1 )
    {
      if ( pv )
      {
        v17 = -1;
        do
          ++v17;
        while ( *((_WORD *)pv + v17) );
        v34 = v17;
      }
      else
      {
        LODWORD(v17) = 0;
        v34 = 0;
      }
    }
    v18 = &String1;
    if ( pv )
      v18 = (const unsigned __int16 *)pv;
    v19 = Microsoft::WRL::Wrappers::HString::Set(a2, v18, v17);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9C,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrthelper.cpp",
        (const char *)(unsigned int)v19,
        v28);
    v20 = 0;
  }
  wil::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v42, v20);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v34 = 0;
  v35 = 0;
  v42 = &MRTTransformerTelemetry::ResolveMrtString::`vftable';
  wil::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v42);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v45);
  wil::details::shared_object<wil::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MRTTransformerLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v44);
  wil::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MRTTransformerLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<MRTTransformerLogging,_TlgReflectorTag_Param0IsProviderType>(v43);
  WindowsDeleteString(string);
  return a2;
}

```

## disassembly

```asm
0x180030fbc  mov     [rsp-8+arg_18], rbx
0x180030fc1  push    rbp
0x180030fc2  push    rsi
0x180030fc3  push    rdi
0x180030fc4  push    r12
0x180030fc6  push    r13
0x180030fc8  push    r14
0x180030fca  push    r15
0x180030fcc  lea     rbp, [rsp-100h]
0x180030fd4  sub     rsp, 200h
0x180030fdb  mov     rax, cs:__security_cookie
0x180030fe2  xor     rax, rsp
0x180030fe5  mov     [rbp+130h+var_40], rax
0x180030fec  mov     r14, rdx
0x180030fef  mov     r15, rcx
0x180030ff2  mov     [rbp+130h+var_198], rdx
0x180030ff6  xor     r13d, r13d
0x180030ff9  mov     [rbp+130h+var_1B0], r13d
0x180030ffd  mov     rdx, r8
0x180031000  lea     rcx, [rsp+230h+string]
0x180031005  call    ?SimplifyFullyQualifiedResourceStringIfApplicable@MRTHelper@DataStoreCache@@KA?AVHString@Wrappers@WRL@Microsoft@@PEAUHSTRING__@@@Z; DataStoreCache::MRTHelper::SimplifyFullyQualifiedResourceStringIfApplicable(HSTRING__ *)
0x18003100a  nop
0x18003100b  mov     [rsp+230h+length], r13d
0x180031010  lea     rdx, [rsp+230h+length]; length
0x180031015  mov     rcx, [rsp+230h+string]; string
0x18003101a  call    cs:__imp_WindowsGetStringRawBuffer
0x180031020  mov     rsi, rax
0x180031023  mov     [rbp+130h+var_1A8], rax
0x180031027  lea     rdx, aResolvemrtstri; "ResolveMrtString"
0x18003102e  lea     rcx, [rbp+130h+var_190]; struct wil::details::IFailureCallback *
0x180031032  call    ??0?$ActivityBase@VMRTTransformerLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180031037  lea     rax, ??_7ResolveMrtString@MRTTransformerTelemetry@@6B@; const MRTTransformerTelemetry::ResolveMrtString::`vftable'
0x18003103e  mov     [rbp+130h+var_190], rax
0x180031042  mov     r8, rsi
0x180031045  xor     edx, edx
0x180031047  lea     rcx, [rbp+130h+var_190]
0x18003104b  call    ?StartActivity@ResolveMrtString@MRTTransformerTelemetry@@QEAAXW4MRTResolutionType@MRTHelper@DataStoreCache@@PEBG@Z; MRTTransformerTelemetry::ResolveMrtString::StartActivity(DataStoreCache::MRTHelper::MRTResolutionType,ushort const *)
0x180031050  nop
0x180031051  mov     r12b, r13b
0x180031054  mov     [rsp+230h+pv], r13
0x180031059  mov     [rsp+230h+var_200], r13b
0x18003105e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180031062  mov     [rsp+230h+var_1D8], rbx
0x180031067  mov     [rsp+230h+var_1D0], rbx
0x18003106c  lea     r9, [rsp+230h+pv]; unsigned __int16 **
0x180031071  lea     r8, [rsp+230h+var_200]; bool *
0x180031076  mov     edx, [rsp+230h+length]; unsigned int
0x18003107a  mov     rcx, rsi; unsigned __int16 *
0x18003107d  call    ?TryResolveDllReference@MRTHelper@DataStoreCache@@KAJPEBGIPEA_NPEAPEAG@Z; DataStoreCache::MRTHelper::TryResolveDllReference(ushort const *,uint,bool *,ushort * *)
0x180031082  mov     edi, eax
0x180031084  cmp     [rsp+230h+var_200], r13b
0x180031089  jnz     loc_18003119B
0x18003108f  mov     rcx, [rsp+230h+string]; this
0x180031094  call    ?HasMsResourceUriScheme@Common@ShellMRTHelper@@YA_NPEAUHSTRING__@@@Z; ShellMRTHelper::Common::HasMsResourceUriScheme(HSTRING__ *)
0x180031099  test    al, al
0x18003109b  jz      loc_1800313CC
0x1800310a1  mov     [rsp+230h+var_1C0], r13
0x1800310a6  mov     [rsp+230h+var_1F0], r13
0x1800310ab  lea     rcx, [rsp+230h+var_1F0]
0x1800310b0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800310b5  lea     rcx, [rsp+230h+var_1C0]
0x1800310ba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800310bf  lea     r8, [rsp+230h+var_1F0]; struct IResourceMap **
0x1800310c4  lea     rdx, [rsp+230h+var_1C0]; struct IMrtResourceManager **
0x1800310c9  mov     rcx, r15; this
0x1800310cc  call    ?TryEnsureResourceManagerAndMap@MRTHelper@DataStoreCache@@IEAAJPEAPEAUIMrtResourceManager@@PEAPEAUIResourceMap@@@Z; DataStoreCache::MRTHelper::TryEnsureResourceManagerAndMap(IMrtResourceManager * *,IResourceMap * *)
0x1800310d1  mov     rcx, [rbp+138h]; this
0x1800310d8  test    eax, eax
0x1800310da  js      loc_1800312AA
0x1800310e0  mov     [rsp+230h+var_1F8], r13
0x1800310e5  mov     rbx, [rsp+230h+var_1C0]
0x1800310ea  test    rbx, rbx
0x1800310ed  jz      short loc_180031126
0x1800310ef  mov     rax, [rbx]
0x1800310f2  mov     rdi, [rax+48h]
0x1800310f6  lea     rcx, [rsp+230h+var_1F8]
0x1800310fb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180031100  lea     r8, [rsp+230h+var_1F8]
0x180031105  lea     rdx, _GUID_e3c22b30_8502_4b2f_9133_559674587e51
0x18003110c  mov     rcx, rbx
0x18003110f  mov     rax, rdi
0x180031112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031117  mov     rcx, [rbp+138h]; this
0x18003111e  test    eax, eax
0x180031120  js      loc_1800313B3
0x180031126  mov     rbx, [rsp+230h+var_1F0]
0x18003112b  test    rbx, rbx
0x18003112e  jz      short loc_18003113B
0x180031130  cmp     [rsp+230h+var_1F8], r13
0x180031135  jnz     loc_1800312BF
0x18003113b  mov     r12b, 1
0x18003113e  mov     edi, 80070490h
0x180031143  mov     rcx, [rsp+230h+var_1F8]
0x180031148  test    rcx, rcx
0x18003114b  jz      short loc_18003115F
0x18003114d  mov     [rsp+230h+var_1F8], r13
0x180031152  mov     rax, [rcx]
0x180031155  mov     rax, [rax+10h]
0x180031159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003115e  nop
0x18003115f  mov     rcx, [rsp+230h+var_1F0]
0x180031164  test    rcx, rcx
0x180031167  jz      short loc_18003117B
0x180031169  mov     [rsp+230h+var_1F0], r13
0x18003116e  mov     rax, [rcx]
0x180031171  mov     rax, [rax+10h]
0x180031175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003117a  nop
0x18003117b  mov     rcx, [rsp+230h+var_1C0]
0x180031180  test    rcx, rcx
0x180031183  jz      short loc_180031197
0x180031185  mov     [rsp+230h+var_1C0], r13
0x18003118a  mov     rax, [rcx]
0x18003118d  mov     rax, [rax+10h]
0x180031191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031196  nop
0x180031197  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003119b  mov     [r14], r13
0x18003119e  mov     [rbp+130h+var_1B0], 1
0x1800311a5  test    edi, edi
0x1800311a7  js      loc_180031424
0x1800311ad  mov     rax, [rsp+230h+pv]
0x1800311b2  mov     r8, [rsp+230h+var_1D8]
0x1800311b7  cmp     r8, rbx
0x1800311ba  jnz     short loc_1800311D7
0x1800311bc  test    rax, rax
0x1800311bf  jz      loc_180031417
0x1800311c5  mov     r8, rbx
0x1800311c8  inc     r8; unsigned int
0x1800311cb  cmp     [rax+r8*2], r13w
0x1800311d0  jnz     short loc_1800311C8
0x1800311d2  mov     [rsp+230h+var_1D8], r8
0x1800311d7  lea     rdx, String1
0x1800311de  test    rax, rax
0x1800311e1  cmovnz  rdx, rax; unsigned __int16 *
0x1800311e5  mov     rcx, r14; this
0x1800311e8  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1800311ed  mov     rcx, [rbp+138h]; this
0x1800311f4  test    eax, eax
0x1800311f6  js      loc_180031295
0x1800311fc  xor     edx, edx
0x1800311fe  lea     rcx, [rbp+130h+var_190]
0x180031202  call    ?Stop@?$ActivityBase@VMRTTransformerLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180031207  nop
0x180031208  mov     rcx, [rsp+230h+pv]; pv
0x18003120d  test    rcx, rcx
0x180031210  jz      short loc_18003121D
0x180031212  call    cs:__imp_CoTaskMemFree
0x180031218  mov     [rsp+230h+pv], r13
0x18003121d  mov     [rsp+230h+var_1D8], r13
0x180031222  mov     [rsp+230h+var_1D0], r13
0x180031227  lea     rax, ??_7ResolveMrtString@MRTTransformerTelemetry@@6B@; const MRTTransformerTelemetry::ResolveMrtString::`vftable'
0x18003122e  mov     [rbp+130h+var_190], rax
0x180031232  lea     rcx, [rbp+130h+var_190]
0x180031236  call    ?Destroy@?$ActivityBase@VMRTTransformerLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18003123b  lea     rcx, [rbp+130h+var_70]; this
0x180031242  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180031247  lea     rcx, [rbp+130h+var_78]
0x18003124e  call    ?reset@?$shared_object@V?$ActivityData@VMRTTransformerLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VMRTTransformerLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MRTTransformerLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180031253  lea     rcx, [rbp+130h+var_188]
0x180031257  call    ??1?$ActivityData@VMRTTransformerLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VMRTTransformerLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MRTTransformerLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<MRTTransformerLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18003125c  nop
0x18003125d  mov     rcx, [rsp+230h+string]; string
0x180031262  call    cs:__imp_WindowsDeleteString
0x180031268  mov     rax, r14
0x18003126b  mov     rcx, [rbp+130h+var_40]
0x180031272  xor     rcx, rsp; StackCookie
0x180031275  call    __security_check_cookie
0x18003127a  mov     rbx, [rsp+230h+arg_18]
0x180031282  add     rsp, 200h
0x180031289  pop     r15
0x18003128b  pop     r14
0x18003128d  pop     r13
0x18003128f  pop     r12
0x180031291  pop     rdi
0x180031292  pop     rsi
0x180031293  pop     rbp
0x180031294  retn
0x180031295  mov     r9d, eax; char *
0x180031298  lea     r8, aShellcommonShe_207; "shellcommon\\shell\\datastorecache\\tra"...
0x18003129f  mov     edx, 9Ch; void *
0x1800312a4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800312aa  mov     r9d, eax; char *
0x1800312ad  lea     r8, aShellcommonShe_207; "shellcommon\\shell\\datastorecache\\tra"...
0x1800312b4  mov     edx, 4Bh ; 'K'; void *
0x1800312b9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800312bf  mov     rax, [rbx]
0x1800312c2  mov     rdi, [rax+30h]
0x1800312c6  mov     rcx, [rsp+230h+pv]; pv
0x1800312cb  test    rcx, rcx
0x1800312ce  jz      short loc_1800312DB
0x1800312d0  call    cs:__imp_CoTaskMemFree
0x1800312d6  mov     [rsp+230h+pv], r13
0x1800312db  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800312df  mov     [rsp+230h+var_1D8], rax
0x1800312e4  mov     [rsp+230h+var_1D0], rax
0x1800312e9  lea     r9, [rsp+230h+pv]
0x1800312ee  mov     r8, rsi
0x1800312f1  mov     rdx, [rsp+230h+var_1F8]
0x1800312f6  mov     rcx, rbx
0x1800312f9  mov     rax, rdi
0x1800312fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031301  mov     edi, eax
0x180031303  test    eax, eax
0x180031305  jns     loc_180031143
0x18003130b  mov     qword ptr [rsp+230h+var_1B8.unused], r13
0x180031310  xor     edx, edx
0x180031312  lea     rcx, [rsp+230h+var_1B8]
0x180031317  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003131c  lea     rdx, [rsp+230h+var_1B8]; HSTRING
0x180031321  mov     rcx, [rsp+230h+string]; this
0x180031326  call    ?TryRemoveImplicitResourcesPrefixFromShortenedMsResourceUri@Common@ShellMRTHelper@@YAJPEAUHSTRING__@@PEAPEAG@Z; ShellMRTHelper::Common::TryRemoveImplicitResourcesPrefixFromShortenedMsResourceUri(HSTRING__ *,ushort * *)
0x18003132b  mov     rcx, [rbp+138h]; this
0x180031332  test    eax, eax
0x180031334  js      loc_1800313D6
0x18003133a  mov     rbx, qword ptr [rsp+230h+var_1B8.unused]
0x18003133f  test    rbx, rbx
0x180031342  jz      short loc_18003138C
0x180031344  cmp     [rbx], r13w
0x180031348  jz      short loc_18003138C
0x18003134a  mov     rsi, [rsp+230h+var_1F0]
0x18003134f  mov     rax, [rsi]
0x180031352  mov     rdi, [rax+30h]
0x180031356  lea     rcx, [rsp+230h+pv]
0x18003135b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180031360  or      rax, 0FFFFFFFFFFFFFFFFh
0x180031364  mov     [rsp+230h+var_1D8], rax
0x180031369  mov     [rsp+230h+var_1D0], rax
0x18003136e  lea     r9, [rsp+230h+pv]
0x180031373  mov     r8, rbx
0x180031376  mov     rdx, [rsp+230h+var_1F8]
0x18003137b  mov     rcx, rsi
0x18003137e  mov     rax, rdi
0x180031381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031386  mov     edi, eax
0x180031388  test    eax, eax
0x18003138a  jns     short loc_180031408
0x18003138c  cmp     edi, 80073B17h
0x180031392  jnz     short loc_1800313EC
0x180031394  xor     edx, edx; length
0x180031396  mov     rcx, [r15+8]; string
0x18003139a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800313a0  mov     [rbp+130h+var_1A0], rax
0x1800313a4  lea     rdx, [rbp+130h+var_1A8]
0x1800313a8  lea     rcx, [rbp+130h+var_1A0]
0x1800313ac  call    ??$NamedResourceNotFound@PEBGAEBQEBG@MRTTransformerTelemetry@@SAX$$QEAPEBGAEBQEBG@Z; MRTTransformerTelemetry::NamedResourceNotFound<ushort const *,ushort const * const &>(ushort const * &&,ushort const * const &)
0x1800313b1  jmp     short loc_180031408
0x1800313b3  mov     r9d, eax; char *
0x1800313b6  lea     r8, aShellcommonShe_207; "shellcommon\\shell\\datastorecache\\tra"...
0x1800313bd  mov     edx, 52h ; 'R'; void *
0x1800313c2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800313c7  jmp     loc_180031126
0x1800313cc  mov     edi, 80070057h
0x1800313d1  jmp     loc_18003119B
0x1800313d6  mov     r9d, eax; char *
0x1800313d9  lea     r8, aShellcommonShe_207; "shellcommon\\shell\\datastorecache\\tra"...
0x1800313e0  mov     edx, 77h ; 'w'; void *
0x1800313e5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800313ea  jmp     short loc_18003138C
0x1800313ec  mov     rcx, [rbp+138h]; this
0x1800313f3  mov     r9d, edi; char *
0x1800313f6  lea     r8, aShellcommonShe_207; "shellcommon\\shell\\datastorecache\\tra"...
0x1800313fd  mov     edx, 88h; void *
0x180031402  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180031407  nop
0x180031408  lea     rcx, [rsp+230h+var_1B8]
0x18003140d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180031412  jmp     loc_180031143
0x180031417  mov     r8, r13
0x18003141a  mov     [rsp+230h+var_1D8], r13
0x18003141f  jmp     loc_1800311D7
0x180031424  xor     ecx, ecx; string
0x180031426  call    cs:__imp_WindowsDeleteString
0x18003142c  mov     rax, [rsp+230h+string]
0x180031431  mov     [r14], rax
0x180031434  mov     [rsp+230h+string], r13
0x180031439  mov     edx, r13d
0x18003143c  test    r12b, r12b
0x18003143f  cmovz   edx, edi
0x180031442  jmp     loc_1800311FE
```
