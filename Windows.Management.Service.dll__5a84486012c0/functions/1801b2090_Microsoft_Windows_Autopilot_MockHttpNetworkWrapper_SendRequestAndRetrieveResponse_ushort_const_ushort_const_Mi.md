# Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::SendRequestAndRetrieveResponse(ushort const *,ushort const *,Microsoft::Windows::Autopilot::HTTP_VERB,ushort const *,_CERT_CONTEXT const *,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> *,char const *,ulong,ulong &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &)

- ea: `0x1801b2090`
- end: `0x1801b24c7`
- name: `?SendRequestAndRetrieveResponse@MockHttpNetworkWrapper@Autopilot@Windows@Microsoft@@UEAAJPEBG0W4HTTP_VERB@234@0PEBU_CERT_CONTEXT@@PEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@PEBDKAEAKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@8@AEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@Z`
- size: `1079`
- prototype: `__int64 __usercall@<rax>(Microsoft::Windows::Autopilot::MockHttpNetworkWrapper *this@<rcx>, int, int, __int64, __int64, int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000b820`
- `0x180063dab`
- `0x180067a54`
- `0x1800775c4`
- `0x1800814a8`
- `0x180082a40`
- `0x18008c244`
- `0x1800df498`
- `0x1800df644`
- `0x1800e83f0`
- `0x1801b16b0`
- `0x1801b19b4`
- `0x1801b1a64`
- `0x1801b1c88`
- `0x1801b1f90`
- `0x1801b2090`
- `0x1801b2548`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b2238`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b22aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b235b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b23dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b2449`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b2238`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b22aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b235b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b23dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b2449`

## string_xrefs

- `0x1801b221f`: `application/json`
- `0x1801b23c6`: `application/json`
- `0x1801b210b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\mockhttpnetworkwrapper.cpp`
- `0x1801b2265`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\mockhttpnetworkwrapper.cpp`
- `0x1801b22d7`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\mockhttpnetworkwrapper.cpp`
- `0x1801b232d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\mockhttpnetworkwrapper.cpp`
- `0x1801b2388`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\mockhttpnetworkwrapper.cpp`
- `0x1801b240a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\mockhttpnetworkwrapper.cpp`
- `0x1801b2476`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\mockhttpnetworkwrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::SendRequestAndRetrieveResponse(
        Microsoft::Windows::Autopilot::MockHttpNetworkWrapper *this,
        __int64 a2,
        const unsigned __int16 *a3,
        enum HTTP_VERB a4,
        int a5,
        int a6,
        _QWORD *a7,
        __int64 a8,
        unsigned int a9,
        _DWORD *a10,
        __int64 a11,
        _QWORD *a12)
{
  const WCHAR *v16; // rdx
  struct Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::MockResponseData *v17; // rsi
  char *v18; // r14
  SIZE_T v19; // rbx
  void *v20; // r15
  _BYTE *v21; // rsi
  int MockResponse; // eax
  unsigned int v23; // ebx
  struct Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::MockResponseData *v24; // rsi
  _BYTE *v25; // rsi
  SIZE_T v26; // rbx
  void *v27; // r15
  _BYTE *v28; // rsi
  int v29; // [rsp+20h] [rbp-D8h]
  int v30; // [rsp+30h] [rbp-C8h] BYREF
  struct Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::MockResponseData *v31; // [rsp+38h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+40h] [rbp-B8h]
  _BYTE v33[32]; // [rsp+50h] [rbp-A8h] BYREF
  enum HTTP_VERB v34; // [rsp+70h] [rbp-88h]
  _QWORD v35[2]; // [rsp+78h] [rbp-80h] BYREF
  _BYTE v36[40]; // [rsp+88h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v32 = a11;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\mockhttpnetworkwrapper.cpp",
      (const char *)0x80004001LL,
      v29);
    return 2147500033LL;
  }
  Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest::CapturedRequest((Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest *)v33);
  v16 = a3;
  if ( !a3 )
    v16 = &sourceString;
  std::wstring::assign(v33, v16);
  v34 = a4;
  if ( a7 && v35 != a7 )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,ModernDeployment::Autopilot::Core::MachineContext::CaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear(v35);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Copy<0>(
      v35,
      a7);
  }
  if ( a8 && a9 )
    std::string::_Assign<char>(v36, a8, a9);
  if ( *((_QWORD *)this + 8) == *((_QWORD *)this + 9) )
  {
    std::vector<Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest>::_Emplace_reallocate<Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest>(
      (char *)this + 56,
      *((_QWORD *)this + 8),
      v33);
  }
  else
  {
    Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest::CapturedRequest(*((_QWORD *)this + 8), v33);
    *((_QWORD *)this + 8) += 88LL;
  }
  Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest::~CapturedRequest((Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest *)v33);
  v30 = 0;
  v31 = 0;
  if ( (unsigned __int8)Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::TryGetNextSequenceStatus(
                          this,
                          a3,
                          (unsigned int)a4,
                          &v30) )
  {
    *a10 = v30;
    v17 = v31;
    if ( !v31 || *(_QWORD *)v31 == *((_QWORD *)v31 + 1) )
    {
      v18 = (char *)this + 128;
      std::wstring::assign(v18, &sourceString);
      v21 = CoTaskMemAlloc(1u);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(a12);
      *a12 = v21;
      a12[1] = 1;
      if ( !v21 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x54,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\mockhttpnetworkwrapper.cpp",
          (const char *)0x8007000ELL,
          (int)&v31);
        return 2147942414LL;
      }
      *v21 = 0;
    }
    else
    {
      v18 = (char *)this + 128;
      std::wstring::assign(v18, L"application/json");
      v19 = *((_QWORD *)v17 + 1) - *(_QWORD *)v17;
      v20 = CoTaskMemAlloc(v19);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(a12);
      *a12 = v20;
      a12[1] = v19;
      if ( !v20 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4D,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\mockhttpnetworkwrapper.cpp",
          (const char *)0x8007000ELL,
          (int)&v31);
        return 2147942414LL;
      }
      memcpy_0(v20, *(const void **)v17, *((_QWORD *)v17 + 1) - *(_QWORD *)v17);
    }
LABEL_36:
    std::wstring::operator=(v32, v18);
    return 0;
  }
  v31 = 0;
  MockResponse = Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::FindMockResponse(this, a3, a4, &v31);
  v23 = MockResponse;
  if ( MockResponse < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\mockhttpnetworkwrapper.cpp",
      (const char *)(unsigned int)MockResponse,
      (int)&v31);
    return v23;
  }
  v24 = v31;
  if ( v31 )
  {
    *((_QWORD *)this + 20) = v31;
    *a10 = *((_DWORD *)v24 + 9);
    v18 = (char *)this + 128;
    if ( *((_QWORD *)v24 + 6) == *((_QWORD *)v24 + 5) )
    {
      std::wstring::assign(v18, &sourceString);
      v28 = CoTaskMemAlloc(1u);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(a12);
      *a12 = v28;
      a12[1] = 1;
      if ( !v28 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x84,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\mockhttpnetworkwrapper.cpp",
          (const char *)0x8007000ELL,
          (int)&v31);
        return 2147942414LL;
      }
      *v28 = 0;
    }
    else
    {
      std::wstring::assign(v18, L"application/json");
      v26 = *((_QWORD *)v24 + 6) - *((_QWORD *)v24 + 5);
      v27 = CoTaskMemAlloc(v26);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(a12);
      *a12 = v27;
      a12[1] = v26;
      if ( !v27 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x78,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\mockhttpnetworkwrapper.cpp",
          (const char *)0x8007000ELL,
          (int)&v31);
        return 2147942414LL;
      }
      memcpy_0(v27, *((const void **)v24 + 5), *((_QWORD *)v24 + 6) - *((_QWORD *)v24 + 5));
    }
    goto LABEL_36;
  }
  *a10 = 404;
  v25 = CoTaskMemAlloc(1u);
  wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(a12);
  *a12 = v25;
  a12[1] = 1;
  if ( v25 )
  {
    *v25 = 0;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\mockhttpnetworkwrapper.cpp",
      (const char *)0x8007000ELL,
      (int)&v31);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1801b2090  push    rbx
0x1801b2092  push    rsi
0x1801b2093  push    rdi
0x1801b2094  push    r12
0x1801b2096  push    r13
0x1801b2098  push    r14
0x1801b209a  push    r15
0x1801b209c  sub     rsp, 0C0h
0x1801b20a3  mov     rax, cs:__security_cookie
0x1801b20aa  xor     rax, rsp
0x1801b20ad  mov     [rsp+0F8h+var_48], rax
0x1801b20b5  mov     r12d, r9d
0x1801b20b8  mov     r13, r8
0x1801b20bb  mov     r14, rcx
0x1801b20be  mov     rdi, [rsp+0F8h+arg_58]
0x1801b20c6  mov     rbx, [rsp+0F8h+arg_30]
0x1801b20ce  mov     rsi, [rsp+0F8h+arg_38]
0x1801b20d6  mov     r15, [rsp+0F8h+arg_48]
0x1801b20de  mov     rax, [rsp+0F8h+arg_50]
0x1801b20e6  mov     [rsp+0F8h+var_B8], rax
0x1801b20eb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x1801b20f2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x1801b20f7  test    al, al
0x1801b20f9  jnz     short loc_1801B2123
0x1801b20fb  mov     rcx, [rsp+0F8h]; this
0x1801b2103  mov     ebx, 80004001h
0x1801b2108  mov     r9d, ebx; char *
0x1801b210b  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b2112  mov     edx, 2Bh ; '+'; void *
0x1801b2117  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b211c  mov     eax, ebx
0x1801b211e  jmp     loc_1801B24A3
0x1801b2123  lea     rcx, [rsp+0F8h+var_A8]; this
0x1801b2128  call    ??0CapturedRequest@MockHttpNetworkWrapper@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest::CapturedRequest(void)
0x1801b212d  nop
0x1801b212e  lea     rax, sourceString
0x1801b2135  mov     rdx, r13
0x1801b2138  test    r13, r13
0x1801b213b  cmovz   rdx, rax
0x1801b213f  lea     rcx, [rsp+0F8h+var_A8]
0x1801b2144  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801b2149  mov     [rsp+0F8h+var_88], r12d
0x1801b214e  test    rbx, rbx
0x1801b2151  jz      short loc_1801B2174
0x1801b2153  lea     rax, [rsp+0F8h+var_80]
0x1801b2158  cmp     rax, rbx
0x1801b215b  jz      short loc_1801B2174
0x1801b215d  lea     rcx, [rsp+0F8h+var_80]
0x1801b2162  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveCompare@MachineContext@Core@Autopilot@ModernDeployment@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,ModernDeployment::Autopilot::Core::MachineContext::CaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear(void)
0x1801b2167  mov     rdx, rbx
0x1801b216a  lea     rcx, [rsp+0F8h+var_80]
0x1801b216f  call    ??$_Copy@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXAEBV01@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Copy<0>(std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>> const &)
0x1801b2174  test    rsi, rsi
0x1801b2177  jz      short loc_1801B2197
0x1801b2179  mov     eax, [rsp+0F8h+arg_40]
0x1801b2180  test    eax, eax
0x1801b2182  jz      short loc_1801B2197
0x1801b2184  mov     r8d, eax
0x1801b2187  mov     rdx, rsi
0x1801b218a  lea     rcx, [rsp+0F8h+var_70]
0x1801b2192  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x1801b2197  mov     rax, [r14+40h]
0x1801b219b  cmp     rax, [r14+48h]
0x1801b219f  jz      short loc_1801B21B5
0x1801b21a1  lea     rdx, [rsp+0F8h+var_A8]
0x1801b21a6  mov     rcx, rax
0x1801b21a9  call    ??0CapturedRequest@MockHttpNetworkWrapper@Autopilot@Windows@Microsoft@@QEAA@$$QEAU01234@@Z; Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest::CapturedRequest(Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest &&)
0x1801b21ae  add     qword ptr [r14+40h], 58h ; 'X'
0x1801b21b3  jmp     short loc_1801B21C7
0x1801b21b5  lea     r8, [rsp+0F8h+var_A8]
0x1801b21ba  mov     rdx, rax
0x1801b21bd  lea     rcx, [r14+38h]
0x1801b21c1  call    ??$_Emplace_reallocate@UCapturedRequest@MockHttpNetworkWrapper@Autopilot@Windows@Microsoft@@@?$vector@UCapturedRequest@MockHttpNetworkWrapper@Autopilot@Windows@Microsoft@@V?$allocator@UCapturedRequest@MockHttpNetworkWrapper@Autopilot@Windows@Microsoft@@@std@@@std@@AEAAPEAUCapturedRequest@MockHttpNetworkWrapper@Autopilot@Windows@Microsoft@@QEAU23456@$$QEAU23456@@Z; std::vector<Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest>::_Emplace_reallocate<Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest>(Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest * const,Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest &&)
0x1801b21c6  nop
0x1801b21c7  lea     rcx, [rsp+0F8h+var_A8]; this
0x1801b21cc  call    ??1CapturedRequest@MockHttpNetworkWrapper@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest::~CapturedRequest(void)
0x1801b21d1  xor     ebx, ebx
0x1801b21d3  mov     [rsp+0F8h+var_C8], ebx
0x1801b21d7  mov     [rsp+0F8h+var_C0], rbx
0x1801b21dc  lea     rax, [rsp+0F8h+var_C0]
0x1801b21e1  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x1801b21e6  lea     r9, [rsp+0F8h+var_C8]
0x1801b21eb  mov     r8d, r12d
0x1801b21ee  mov     rdx, r13
0x1801b21f1  mov     rcx, r14
0x1801b21f4  call    ?TryGetNextSequenceStatus@MockHttpNetworkWrapper@Autopilot@Windows@Microsoft@@AEAA_NPEBGW4HTTP_VERB@234@AEAKAEAPEAV?$vector@EV?$allocator@E@std@@@std@@@Z; Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::TryGetNextSequenceStatus(ushort const *,Microsoft::Windows::Autopilot::HTTP_VERB,ulong &,std::vector<uchar> * &)
0x1801b21f9  test    al, al
0x1801b21fb  jz      loc_1801B2304
0x1801b2201  mov     eax, [rsp+0F8h+var_C8]
0x1801b2205  mov     [r15], eax
0x1801b2208  mov     rsi, [rsp+0F8h+var_C0]
0x1801b220d  test    rsi, rsi
0x1801b2210  jz      short loc_1801B2290
0x1801b2212  mov     rax, [rsi+8]
0x1801b2216  cmp     [rsi], rax
0x1801b2219  jz      short loc_1801B2290
0x1801b221b  sub     r14, 0FFFFFFFFFFFFFF80h
0x1801b221f  lea     rdx, aApplicationJso; "application/json"
0x1801b2226  mov     rcx, r14
0x1801b2229  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801b222e  mov     rbx, [rsi+8]
0x1801b2232  sub     rbx, [rsi]
0x1801b2235  mov     rcx, rbx; cb
0x1801b2238  call    cs:__imp_CoTaskMemAlloc
0x1801b223e  mov     r15, rax
0x1801b2241  mov     rcx, rdi
0x1801b2244  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b2249  mov     [rdi], r15
0x1801b224c  mov     [rdi+8], rbx
0x1801b2250  test    r15, r15
0x1801b2253  jnz     short loc_1801B227C
0x1801b2255  mov     rcx, [rsp+0F8h]; this
0x1801b225d  mov     ebx, 8007000Eh
0x1801b2262  mov     r9d, ebx; char *
0x1801b2265  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b226c  lea     edx, [r15+4Dh]; void *
0x1801b2270  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b2275  mov     eax, ebx
0x1801b2277  jmp     loc_1801B24A3
0x1801b227c  mov     r8, [rsi+8]
0x1801b2280  sub     r8, [rsi]; Size
0x1801b2283  mov     rdx, [rsi]; Src
0x1801b2286  mov     rcx, r15; void *
0x1801b2289  call    memcpy_0
0x1801b228e  jmp     short loc_1801B22F0
0x1801b2290  sub     r14, 0FFFFFFFFFFFFFF80h
0x1801b2294  lea     rdx, sourceString
0x1801b229b  mov     rcx, r14
0x1801b229e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801b22a3  mov     ebx, 1
0x1801b22a8  mov     ecx, ebx; cb
0x1801b22aa  call    cs:__imp_CoTaskMemAlloc
0x1801b22b0  mov     rsi, rax
0x1801b22b3  mov     rcx, rdi
0x1801b22b6  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b22bb  mov     [rdi], rsi
0x1801b22be  mov     [rdi+8], rbx
0x1801b22c2  test    rsi, rsi
0x1801b22c5  jnz     short loc_1801B22ED
0x1801b22c7  mov     rcx, [rsp+0F8h]; this
0x1801b22cf  mov     ebx, 8007000Eh
0x1801b22d4  mov     r9d, ebx; char *
0x1801b22d7  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b22de  lea     edx, [rsi+54h]; void *
0x1801b22e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b22e6  mov     eax, ebx
0x1801b22e8  jmp     loc_1801B24A3
0x1801b22ed  mov     byte ptr [rsi], 0
0x1801b22f0  mov     rdx, r14
0x1801b22f3  mov     rcx, [rsp+0F8h+var_B8]
0x1801b22f8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801b22fd  xor     eax, eax
0x1801b22ff  jmp     loc_1801B24A3
0x1801b2304  mov     [rsp+0F8h+var_C0], rbx
0x1801b2309  lea     r9, [rsp+0F8h+var_C0]; struct Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::MockResponseData **
0x1801b230e  mov     r8d, r12d; enum HTTP_VERB
0x1801b2311  mov     rdx, r13; unsigned __int16 *
0x1801b2314  mov     rcx, r14; this
0x1801b2317  call    ?FindMockResponse@MockHttpNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBGW4HTTP_VERB@234@PEAPEAUMockResponseData@1234@@Z; Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::FindMockResponse(ushort const *,Microsoft::Windows::Autopilot::HTTP_VERB,Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::MockResponseData * *)
0x1801b231c  mov     ebx, eax
0x1801b231e  test    eax, eax
0x1801b2320  jns     short loc_1801B2345
0x1801b2322  mov     rcx, [rsp+0F8h]; this
0x1801b232a  mov     r9d, eax; char *
0x1801b232d  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b2334  mov     edx, 5Dh ; ']'; void *
0x1801b2339  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b233e  mov     eax, ebx
0x1801b2340  jmp     loc_1801B24A3
0x1801b2345  mov     rsi, [rsp+0F8h+var_C0]
0x1801b234a  test    rsi, rsi
0x1801b234d  jnz     short loc_1801B23A8
0x1801b234f  mov     dword ptr [r15], 194h
0x1801b2356  lea     ebx, [rsi+1]
0x1801b2359  mov     ecx, ebx; cb
0x1801b235b  call    cs:__imp_CoTaskMemAlloc
0x1801b2361  mov     rsi, rax
0x1801b2364  mov     rcx, rdi
0x1801b2367  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b236c  mov     [rdi], rsi
0x1801b236f  mov     [rdi+8], rbx
0x1801b2373  test    rsi, rsi
0x1801b2376  jnz     short loc_1801B239E
0x1801b2378  mov     rcx, [rsp+0F8h]; this
0x1801b2380  mov     ebx, 8007000Eh
0x1801b2385  mov     r9d, ebx; char *
0x1801b2388  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b238f  lea     edx, [rsi+64h]; void *
0x1801b2392  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b2397  mov     eax, ebx
0x1801b2399  jmp     loc_1801B24A3
0x1801b239e  mov     byte ptr [rsi], 0
0x1801b23a1  xor     eax, eax
0x1801b23a3  jmp     loc_1801B24A3
0x1801b23a8  mov     [r14+0A0h], rsi
0x1801b23af  mov     eax, [rsi+24h]
0x1801b23b2  mov     [r15], eax
0x1801b23b5  sub     r14, 0FFFFFFFFFFFFFF80h
0x1801b23b9  mov     rax, [rsi+30h]
0x1801b23bd  mov     rcx, r14
0x1801b23c0  cmp     rax, [rsi+28h]
0x1801b23c4  jz      short loc_1801B2436
0x1801b23c6  lea     rdx, aApplicationJso; "application/json"
0x1801b23cd  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801b23d2  mov     rbx, [rsi+30h]
0x1801b23d6  sub     rbx, [rsi+28h]
0x1801b23da  mov     rcx, rbx; cb
0x1801b23dd  call    cs:__imp_CoTaskMemAlloc
0x1801b23e3  mov     r15, rax
0x1801b23e6  mov     rcx, rdi
0x1801b23e9  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b23ee  mov     [rdi], r15
0x1801b23f1  mov     [rdi+8], rbx
0x1801b23f5  test    r15, r15
0x1801b23f8  jnz     short loc_1801B2421
0x1801b23fa  mov     rcx, [rsp+0F8h]; this
0x1801b2402  mov     ebx, 8007000Eh
0x1801b2407  mov     r9d, ebx; char *
0x1801b240a  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b2411  lea     edx, [r15+78h]; void *
0x1801b2415  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b241a  mov     eax, ebx
0x1801b241c  jmp     loc_1801B24A3
0x1801b2421  mov     rdx, [rsi+28h]; Src
0x1801b2425  mov     r8, [rsi+30h]
0x1801b2429  sub     r8, rdx; Size
0x1801b242c  mov     rcx, r15; void *
0x1801b242f  call    memcpy_0
0x1801b2434  jmp     short loc_1801B248E
0x1801b2436  lea     rdx, sourceString
0x1801b243d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801b2442  mov     ebx, 1
0x1801b2447  mov     ecx, ebx; cb
0x1801b2449  call    cs:__imp_CoTaskMemAlloc
0x1801b244f  mov     rsi, rax
0x1801b2452  mov     rcx, rdi
0x1801b2455  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b245a  mov     [rdi], rsi
0x1801b245d  mov     [rdi+8], rbx
0x1801b2461  test    rsi, rsi
0x1801b2464  jnz     short loc_1801B248B
0x1801b2466  mov     rcx, [rsp+0F8h]; this
0x1801b246e  mov     ebx, 8007000Eh
0x1801b2473  mov     r9d, ebx; char *
0x1801b2476  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b247d  mov     edx, 84h; void *
0x1801b2482  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b2487  mov     eax, ebx
0x1801b2489  jmp     short loc_1801B24A3
0x1801b248b  mov     byte ptr [rsi], 0
0x1801b248e  mov     rdx, r14
0x1801b2491  mov     rcx, [rsp+0F8h+var_B8]
0x1801b2496  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801b249b  xor     eax, eax
0x1801b249d  jmp     short loc_1801B24A3
0x1801b249f  mov     eax, [rsp+0F8h+var_C8]
0x1801b24a3  mov     rcx, [rsp+0F8h+var_48]
0x1801b24ab  xor     rcx, rsp; StackCookie
0x1801b24ae  call    __security_check_cookie
0x1801b24b3  add     rsp, 0C0h
0x1801b24ba  pop     r15
0x1801b24bc  pop     r14
0x1801b24be  pop     r13
0x1801b24c0  pop     r12
0x1801b24c2  pop     rdi
0x1801b24c3  pop     rsi
0x1801b24c4  pop     rbx
0x1801b24c5  retn
```
