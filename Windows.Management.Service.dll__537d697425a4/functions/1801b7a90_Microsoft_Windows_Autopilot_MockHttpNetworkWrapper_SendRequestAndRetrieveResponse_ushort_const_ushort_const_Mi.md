# Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::SendRequestAndRetrieveResponse(ushort const *,ushort const *,Microsoft::Windows::Autopilot::HTTP_VERB,ushort const *,_CERT_CONTEXT const *,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> *,char const *,ulong,ulong &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &)

- ea: `0x1801b7a90`
- end: `0x1801b7ee9`
- name: `?SendRequestAndRetrieveResponse@MockHttpNetworkWrapper@Autopilot@Windows@Microsoft@@UEAAJPEBG0W4HTTP_VERB@234@0PEBU_CERT_CONTEXT@@PEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@PEBDKAEAKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@8@AEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@Z`
- size: `1113`
- prototype: `__int64 __usercall@<rax>(Microsoft::Windows::Autopilot::MockHttpNetworkWrapper *this@<rcx>, int, int, __int64, __int64, int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000b8f0`
- `0x180063f8b`
- `0x180067e54`
- `0x180077e54`
- `0x180081f38`
- `0x1800835bc`
- `0x18008d290`
- `0x1800e1ccc`
- `0x1800e1e8c`
- `0x1800eaeb4`
- `0x1801b70a0`
- `0x1801b73ac`
- `0x1801b7460`
- `0x1801b768c`
- `0x1801b7990`
- `0x1801b7a90`
- `0x1801b7f68`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b7c3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b7cb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b7d6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b7df3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b7e65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b7c3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b7cb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b7d6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b7df3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b7e65`

## string_xrefs

- `0x1801b7c23`: `application/json`
- `0x1801b7ddc`: `application/json`
- `0x1801b7b0b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\mockhttpnetworkwrapper.cpp`
- `0x1801b7c6f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\mockhttpnetworkwrapper.cpp`
- `0x1801b7ce7`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\mockhttpnetworkwrapper.cpp`
- `0x1801b7d3d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\mockhttpnetworkwrapper.cpp`
- `0x1801b7d9e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\mockhttpnetworkwrapper.cpp`
- `0x1801b7e26`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\mockhttpnetworkwrapper.cpp`
- `0x1801b7e98`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\mockhttpnetworkwrapper.cpp`

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
        _BYTE *a7,
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
  _BYTE v35[16]; // [rsp+78h] [rbp-80h] BYREF
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
0x1801b7a90  push    rbx
0x1801b7a92  push    rsi
0x1801b7a93  push    rdi
0x1801b7a94  push    r12
0x1801b7a96  push    r13
0x1801b7a98  push    r14
0x1801b7a9a  push    r15
0x1801b7a9c  sub     rsp, 0C0h
0x1801b7aa3  mov     rax, cs:__security_cookie
0x1801b7aaa  xor     rax, rsp
0x1801b7aad  mov     [rsp+0F8h+var_48], rax
0x1801b7ab5  mov     r12d, r9d
0x1801b7ab8  mov     r13, r8
0x1801b7abb  mov     r14, rcx
0x1801b7abe  mov     rdi, [rsp+0F8h+arg_58]
0x1801b7ac6  mov     rbx, [rsp+0F8h+arg_30]
0x1801b7ace  mov     rsi, [rsp+0F8h+arg_38]
0x1801b7ad6  mov     r15, [rsp+0F8h+arg_48]
0x1801b7ade  mov     rax, [rsp+0F8h+arg_50]
0x1801b7ae6  mov     [rsp+0F8h+var_B8], rax
0x1801b7aeb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x1801b7af2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x1801b7af7  test    al, al
0x1801b7af9  jnz     short loc_1801B7B23
0x1801b7afb  mov     rcx, [rsp+0F8h]; this
0x1801b7b03  mov     ebx, 80004001h
0x1801b7b08  mov     r9d, ebx; char *
0x1801b7b0b  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b7b12  mov     edx, 2Bh ; '+'; void *
0x1801b7b17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b7b1c  mov     eax, ebx
0x1801b7b1e  jmp     loc_1801B7EC5
0x1801b7b23  lea     rcx, [rsp+0F8h+var_A8]; this
0x1801b7b28  call    ??0CapturedRequest@MockHttpNetworkWrapper@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest::CapturedRequest(void)
0x1801b7b2d  nop
0x1801b7b2e  lea     rax, sourceString
0x1801b7b35  mov     rdx, r13
0x1801b7b38  test    r13, r13
0x1801b7b3b  cmovz   rdx, rax
0x1801b7b3f  lea     rcx, [rsp+0F8h+var_A8]
0x1801b7b44  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801b7b49  mov     [rsp+0F8h+var_88], r12d
0x1801b7b4e  test    rbx, rbx
0x1801b7b51  jz      short loc_1801B7B74
0x1801b7b53  lea     rax, [rsp+0F8h+var_80]
0x1801b7b58  cmp     rax, rbx
0x1801b7b5b  jz      short loc_1801B7B74
0x1801b7b5d  lea     rcx, [rsp+0F8h+var_80]
0x1801b7b62  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveCompare@MachineContext@Core@Autopilot@ModernDeployment@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,ModernDeployment::Autopilot::Core::MachineContext::CaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear(void)
0x1801b7b67  mov     rdx, rbx
0x1801b7b6a  lea     rcx, [rsp+0F8h+var_80]
0x1801b7b6f  call    ??$_Copy@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXAEBV01@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Copy<0>(std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>> const &)
0x1801b7b74  test    rsi, rsi
0x1801b7b77  jz      short loc_1801B7B97
0x1801b7b79  mov     eax, [rsp+0F8h+arg_40]
0x1801b7b80  test    eax, eax
0x1801b7b82  jz      short loc_1801B7B97
0x1801b7b84  mov     r8d, eax
0x1801b7b87  mov     rdx, rsi
0x1801b7b8a  lea     rcx, [rsp+0F8h+var_70]
0x1801b7b92  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x1801b7b97  mov     rax, [r14+40h]
0x1801b7b9b  cmp     rax, [r14+48h]
0x1801b7b9f  jz      short loc_1801B7BB5
0x1801b7ba1  lea     rdx, [rsp+0F8h+var_A8]
0x1801b7ba6  mov     rcx, rax
0x1801b7ba9  call    ??0CapturedRequest@MockHttpNetworkWrapper@Autopilot@Windows@Microsoft@@QEAA@$$QEAU01234@@Z; Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest::CapturedRequest(Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest &&)
0x1801b7bae  add     qword ptr [r14+40h], 58h ; 'X'
0x1801b7bb3  jmp     short loc_1801B7BC7
0x1801b7bb5  lea     r8, [rsp+0F8h+var_A8]
0x1801b7bba  mov     rdx, rax
0x1801b7bbd  lea     rcx, [r14+38h]
0x1801b7bc1  call    ??$_Emplace_reallocate@UCapturedRequest@MockHttpNetworkWrapper@Autopilot@Windows@Microsoft@@@?$vector@UCapturedRequest@MockHttpNetworkWrapper@Autopilot@Windows@Microsoft@@V?$allocator@UCapturedRequest@MockHttpNetworkWrapper@Autopilot@Windows@Microsoft@@@std@@@std@@AEAAPEAUCapturedRequest@MockHttpNetworkWrapper@Autopilot@Windows@Microsoft@@QEAU23456@$$QEAU23456@@Z; std::vector<Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest>::_Emplace_reallocate<Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest>(Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest * const,Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest &&)
0x1801b7bc6  nop
0x1801b7bc7  lea     rcx, [rsp+0F8h+var_A8]; this
0x1801b7bcc  call    ??1CapturedRequest@MockHttpNetworkWrapper@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::CapturedRequest::~CapturedRequest(void)
0x1801b7bd1  xor     ebx, ebx
0x1801b7bd3  mov     [rsp+0F8h+var_C8], ebx
0x1801b7bd7  mov     [rsp+0F8h+var_C0], rbx
0x1801b7bdc  lea     rax, [rsp+0F8h+var_C0]
0x1801b7be1  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x1801b7be6  lea     r9, [rsp+0F8h+var_C8]
0x1801b7beb  mov     r8d, r12d
0x1801b7bee  mov     rdx, r13
0x1801b7bf1  mov     rcx, r14
0x1801b7bf4  call    ?TryGetNextSequenceStatus@MockHttpNetworkWrapper@Autopilot@Windows@Microsoft@@AEAA_NPEBGW4HTTP_VERB@234@AEAKAEAPEAV?$vector@EV?$allocator@E@std@@@std@@@Z; Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::TryGetNextSequenceStatus(ushort const *,Microsoft::Windows::Autopilot::HTTP_VERB,ulong &,std::vector<uchar> * &)
0x1801b7bf9  test    al, al
0x1801b7bfb  jz      loc_1801B7D14
0x1801b7c01  mov     eax, [rsp+0F8h+var_C8]
0x1801b7c05  mov     [r15], eax
0x1801b7c08  mov     rsi, [rsp+0F8h+var_C0]
0x1801b7c0d  test    rsi, rsi
0x1801b7c10  jz      loc_1801B7C9A
0x1801b7c16  mov     rax, [rsi+8]
0x1801b7c1a  cmp     [rsi], rax
0x1801b7c1d  jz      short loc_1801B7C9A
0x1801b7c1f  sub     r14, 0FFFFFFFFFFFFFF80h
0x1801b7c23  lea     rdx, aApplicationJso; "application/json"
0x1801b7c2a  mov     rcx, r14
0x1801b7c2d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801b7c32  mov     rbx, [rsi+8]
0x1801b7c36  sub     rbx, [rsi]
0x1801b7c39  mov     rcx, rbx; cb
0x1801b7c3c  call    cs:__imp_CoTaskMemAlloc
0x1801b7c43  nop     dword ptr [rax+rax+00h]
0x1801b7c48  mov     r15, rax
0x1801b7c4b  mov     rcx, rdi
0x1801b7c4e  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b7c53  mov     [rdi], r15
0x1801b7c56  mov     [rdi+8], rbx
0x1801b7c5a  test    r15, r15
0x1801b7c5d  jnz     short loc_1801B7C86
0x1801b7c5f  mov     rcx, [rsp+0F8h]; this
0x1801b7c67  mov     ebx, 8007000Eh
0x1801b7c6c  mov     r9d, ebx; char *
0x1801b7c6f  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b7c76  lea     edx, [r15+4Dh]; void *
0x1801b7c7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b7c7f  mov     eax, ebx
0x1801b7c81  jmp     loc_1801B7EC5
0x1801b7c86  mov     r8, [rsi+8]
0x1801b7c8a  sub     r8, [rsi]; Size
0x1801b7c8d  mov     rdx, [rsi]; Src
0x1801b7c90  mov     rcx, r15; void *
0x1801b7c93  call    memcpy_0
0x1801b7c98  jmp     short loc_1801B7D00
0x1801b7c9a  sub     r14, 0FFFFFFFFFFFFFF80h
0x1801b7c9e  lea     rdx, sourceString
0x1801b7ca5  mov     rcx, r14
0x1801b7ca8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801b7cad  mov     ebx, 1
0x1801b7cb2  mov     ecx, ebx; cb
0x1801b7cb4  call    cs:__imp_CoTaskMemAlloc
0x1801b7cbb  nop     dword ptr [rax+rax+00h]
0x1801b7cc0  mov     rsi, rax
0x1801b7cc3  mov     rcx, rdi
0x1801b7cc6  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b7ccb  mov     [rdi], rsi
0x1801b7cce  mov     [rdi+8], rbx
0x1801b7cd2  test    rsi, rsi
0x1801b7cd5  jnz     short loc_1801B7CFD
0x1801b7cd7  mov     rcx, [rsp+0F8h]; this
0x1801b7cdf  mov     ebx, 8007000Eh
0x1801b7ce4  mov     r9d, ebx; char *
0x1801b7ce7  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b7cee  lea     edx, [rsi+54h]; void *
0x1801b7cf1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b7cf6  mov     eax, ebx
0x1801b7cf8  jmp     loc_1801B7EC5
0x1801b7cfd  mov     byte ptr [rsi], 0
0x1801b7d00  mov     rdx, r14
0x1801b7d03  mov     rcx, [rsp+0F8h+var_B8]
0x1801b7d08  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801b7d0d  xor     eax, eax
0x1801b7d0f  jmp     loc_1801B7EC5
0x1801b7d14  mov     [rsp+0F8h+var_C0], rbx
0x1801b7d19  lea     r9, [rsp+0F8h+var_C0]; struct Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::MockResponseData **
0x1801b7d1e  mov     r8d, r12d; enum HTTP_VERB
0x1801b7d21  mov     rdx, r13; unsigned __int16 *
0x1801b7d24  mov     rcx, r14; this
0x1801b7d27  call    ?FindMockResponse@MockHttpNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBGW4HTTP_VERB@234@PEAPEAUMockResponseData@1234@@Z; Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::FindMockResponse(ushort const *,Microsoft::Windows::Autopilot::HTTP_VERB,Microsoft::Windows::Autopilot::MockHttpNetworkWrapper::MockResponseData * *)
0x1801b7d2c  mov     ebx, eax
0x1801b7d2e  test    eax, eax
0x1801b7d30  jns     short loc_1801B7D55
0x1801b7d32  mov     rcx, [rsp+0F8h]; this
0x1801b7d3a  mov     r9d, eax; char *
0x1801b7d3d  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b7d44  mov     edx, 5Dh ; ']'; void *
0x1801b7d49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b7d4e  mov     eax, ebx
0x1801b7d50  jmp     loc_1801B7EC5
0x1801b7d55  mov     rsi, [rsp+0F8h+var_C0]
0x1801b7d5a  test    rsi, rsi
0x1801b7d5d  jnz     short loc_1801B7DBE
0x1801b7d5f  mov     dword ptr [r15], 194h
0x1801b7d66  lea     ebx, [rsi+1]
0x1801b7d69  mov     ecx, ebx; cb
0x1801b7d6b  call    cs:__imp_CoTaskMemAlloc
0x1801b7d72  nop     dword ptr [rax+rax+00h]
0x1801b7d77  mov     rsi, rax
0x1801b7d7a  mov     rcx, rdi
0x1801b7d7d  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b7d82  mov     [rdi], rsi
0x1801b7d85  mov     [rdi+8], rbx
0x1801b7d89  test    rsi, rsi
0x1801b7d8c  jnz     short loc_1801B7DB4
0x1801b7d8e  mov     rcx, [rsp+0F8h]; this
0x1801b7d96  mov     ebx, 8007000Eh
0x1801b7d9b  mov     r9d, ebx; char *
0x1801b7d9e  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b7da5  lea     edx, [rsi+64h]; void *
0x1801b7da8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b7dad  mov     eax, ebx
0x1801b7daf  jmp     loc_1801B7EC5
0x1801b7db4  mov     byte ptr [rsi], 0
0x1801b7db7  xor     eax, eax
0x1801b7db9  jmp     loc_1801B7EC5
0x1801b7dbe  mov     [r14+0A0h], rsi
0x1801b7dc5  mov     eax, [rsi+24h]
0x1801b7dc8  mov     [r15], eax
0x1801b7dcb  sub     r14, 0FFFFFFFFFFFFFF80h
0x1801b7dcf  mov     rax, [rsi+30h]
0x1801b7dd3  mov     rcx, r14
0x1801b7dd6  cmp     rax, [rsi+28h]
0x1801b7dda  jz      short loc_1801B7E52
0x1801b7ddc  lea     rdx, aApplicationJso; "application/json"
0x1801b7de3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801b7de8  mov     rbx, [rsi+30h]
0x1801b7dec  sub     rbx, [rsi+28h]
0x1801b7df0  mov     rcx, rbx; cb
0x1801b7df3  call    cs:__imp_CoTaskMemAlloc
0x1801b7dfa  nop     dword ptr [rax+rax+00h]
0x1801b7dff  mov     r15, rax
0x1801b7e02  mov     rcx, rdi
0x1801b7e05  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b7e0a  mov     [rdi], r15
0x1801b7e0d  mov     [rdi+8], rbx
0x1801b7e11  test    r15, r15
0x1801b7e14  jnz     short loc_1801B7E3D
0x1801b7e16  mov     rcx, [rsp+0F8h]; this
0x1801b7e1e  mov     ebx, 8007000Eh
0x1801b7e23  mov     r9d, ebx; char *
0x1801b7e26  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b7e2d  lea     edx, [r15+78h]; void *
0x1801b7e31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b7e36  mov     eax, ebx
0x1801b7e38  jmp     loc_1801B7EC5
0x1801b7e3d  mov     rdx, [rsi+28h]; Src
0x1801b7e41  mov     r8, [rsi+30h]
0x1801b7e45  sub     r8, rdx; Size
0x1801b7e48  mov     rcx, r15; void *
0x1801b7e4b  call    memcpy_0
0x1801b7e50  jmp     short loc_1801B7EB0
0x1801b7e52  lea     rdx, sourceString
0x1801b7e59  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801b7e5e  mov     ebx, 1
0x1801b7e63  mov     ecx, ebx; cb
0x1801b7e65  call    cs:__imp_CoTaskMemAlloc
0x1801b7e6c  nop     dword ptr [rax+rax+00h]
0x1801b7e71  mov     rsi, rax
0x1801b7e74  mov     rcx, rdi
0x1801b7e77  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b7e7c  mov     [rdi], rsi
0x1801b7e7f  mov     [rdi+8], rbx
0x1801b7e83  test    rsi, rsi
0x1801b7e86  jnz     short loc_1801B7EAD
0x1801b7e88  mov     rcx, [rsp+0F8h]; this
0x1801b7e90  mov     ebx, 8007000Eh
0x1801b7e95  mov     r9d, ebx; char *
0x1801b7e98  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b7e9f  mov     edx, 84h; void *
0x1801b7ea4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b7ea9  mov     eax, ebx
0x1801b7eab  jmp     short loc_1801B7EC5
0x1801b7ead  mov     byte ptr [rsi], 0
0x1801b7eb0  mov     rdx, r14
0x1801b7eb3  mov     rcx, [rsp+0F8h+var_B8]
0x1801b7eb8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801b7ebd  xor     eax, eax
0x1801b7ebf  jmp     short loc_1801B7EC5
0x1801b7ec1  mov     eax, [rsp+0F8h+var_C8]
0x1801b7ec5  mov     rcx, [rsp+0F8h+var_48]
0x1801b7ecd  xor     rcx, rsp; StackCookie
0x1801b7ed0  call    __security_check_cookie
0x1801b7ed5  add     rsp, 0C0h
0x1801b7edc  pop     r15
0x1801b7ede  pop     r14
0x1801b7ee0  pop     r13
0x1801b7ee2  pop     r12
0x1801b7ee4  pop     rdi
0x1801b7ee5  pop     rsi
0x1801b7ee6  pop     rbx
0x1801b7ee7  retn
```
