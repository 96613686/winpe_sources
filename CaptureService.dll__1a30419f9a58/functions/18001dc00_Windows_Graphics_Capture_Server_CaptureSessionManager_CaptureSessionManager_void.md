# Windows::Graphics::Capture::Server::CaptureSessionManager::CaptureSessionManager(void)

- ea: `0x18001dc00`
- end: `0x18001dd56`
- name: `??0CaptureSessionManager@Server@Capture@Graphics@Windows@@QEAA@XZ`
- size: `342`
- prototype: `void *__fastcall(Windows::Graphics::Capture::Server::CaptureSessionManager *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1800028d0`

## callees

- `0x180002e60`
- `0x180005488`
- `0x18000a92c`
- `0x18001d9f0`
- `0x18001dc00`
- `0x18001dda0`
- `0x18001deb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001dc4d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001dc4d`

## string_xrefs

- `0x18001dd32`: `onecoreuap\windows\dwm\capture\svc\dll\capturesessionmanager.cpp`
- `0x18001dd44`: `onecoreuap\windows\dwm\capture\svc\dll\capturesessionmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void *__fastcall Windows::Graphics::Capture::Server::CaptureSessionManager::CaptureSessionManager(
        Windows::Graphics::Capture::Server::CaptureSessionManager *this)
{
  _QWORD *v1; // rax
  const char *v2; // r9
  _QWORD *v3; // rax
  const char *v4; // r9
  __int64 v6; // [rsp+20h] [rbp-39h] BYREF
  _BYTE v7[8]; // [rsp+28h] [rbp-31h] BYREF
  __int64 (__fastcall **v8)(); // [rsp+30h] [rbp-29h] BYREF
  void *v9; // [rsp+38h] [rbp-21h]
  __int64 (__fastcall ***v10)(); // [rsp+98h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  qword_1800331A0 = 0;
  Windows::Graphics::Capture::Server::g_captureSessionManager = 0;
  xmmword_180033190 = 0;
  InitializeCriticalSectionEx(&CriticalSection, 0, 0);
  v8 = off_180024DB8;
  v9 = &Windows::Graphics::Capture::Server::g_captureSessionManager;
  v10 = &v8;
  v1 = wil::make_wnf_subscription_nothrow<wil::details::empty_wnf_state>(
         &v6,
         (__int64)&WNF_CAM_GRAPHICSCAPTUREWITHOUTBORDER_ACCESS_CHANGED,
         (__int64)v7);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
    (char *)&xmmword_180033190 + 8,
    v1);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v6);
  wistd::function<void (void)>::~function<void (void)>(v7);
  if ( !*((_QWORD *)&xmmword_180033190 + 1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturesessionmanager.cpp",
      v2);
  v9 = &Windows::Graphics::Capture::Server::g_captureSessionManager;
  v8 = off_180024D90;
  v10 = &v8;
  v3 = wil::make_wnf_subscription_nothrow<wil::details::empty_wnf_state>(
         &v6,
         (__int64)WNF_CAM_GRAPHICSCAPTUREPROGRAMMATIC_ACCESS_CHANGED,
         (__int64)v7);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
    &qword_1800331A0,
    v3);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v6);
  wistd::function<void (void)>::~function<void (void)>(v7);
  if ( !qword_1800331A0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturesessionmanager.cpp",
      v4);
  return &Windows::Graphics::Capture::Server::g_captureSessionManager;
}

```

## disassembly

```asm
0x18001dc00  mov     [rsp-8+arg_0], rbx
0x18001dc05  push    rbp
0x18001dc06  lea     rbp, [rsp-57h]
0x18001dc0b  sub     rsp, 0B0h
0x18001dc12  mov     rax, cs:__security_cookie
0x18001dc19  xor     rax, rsp
0x18001dc1c  mov     [rbp+57h+var_10], rax
0x18001dc20  xorps   xmm0, xmm0
0x18001dc23  mov     cs:qword_1800331A0, 0
0x18001dc2e  xorps   xmm1, xmm1
0x18001dc31  movdqa  cs:?g_captureSessionManager@Server@Capture@Graphics@Windows@@3VCaptureSessionManager@1234@A, xmm0; Windows::Graphics::Capture::Server::CaptureSessionManager Windows::Graphics::Capture::Server::g_captureSessionManager
0x18001dc39  xor     r8d, r8d; Flags
0x18001dc3c  movdqa  cs:xmmword_180033190, xmm1
0x18001dc44  xor     edx, edx; dwSpinCount
0x18001dc46  lea     rcx, CriticalSection; lpCriticalSection
0x18001dc4d  call    cs:__imp_InitializeCriticalSectionEx
0x18001dc53  lea     rax, off_180024DB8
0x18001dc5a  mov     [rbp+57h+var_80], rax
0x18001dc5e  lea     rbx, ?g_captureSessionManager@Server@Capture@Graphics@Windows@@3VCaptureSessionManager@1234@A; Windows::Graphics::Capture::Server::CaptureSessionManager Windows::Graphics::Capture::Server::g_captureSessionManager
0x18001dc65  lea     rax, [rbp+57h+var_80]
0x18001dc69  mov     [rbp+57h+var_78], rbx
0x18001dc6d  lea     r8, [rbp+57h+var_88]
0x18001dc71  mov     [rbp+57h+var_18], rax
0x18001dc75  lea     rdx, WNF_CAM_GRAPHICSCAPTUREWITHOUTBORDER_ACCESS_CHANGED
0x18001dc7c  lea     rcx, [rbp+57h+var_90]
0x18001dc80  call    ??$make_wnf_subscription_nothrow@Uempty_wnf_state@details@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@K@Z; wil::make_wnf_subscription_nothrow<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong)
0x18001dc85  mov     rdx, rax
0x18001dc88  lea     rcx, xmmword_180033190+8
0x18001dc8f  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x18001dc94  lea     rcx, [rbp+57h+var_90]
0x18001dc98  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18001dc9d  lea     rcx, [rbp+57h+var_88]
0x18001dca1  call    ??1?$function@$$A6AXXZ@wistd@@QEAA@XZ; wistd::function<void (void)>::~function<void (void)>(void)
0x18001dca6  cmp     qword ptr cs:xmmword_180033190+8, 0
0x18001dcae  mov     rcx, [rbp+5Fh]; this
0x18001dcb2  jz      loc_18001DD44
0x18001dcb8  lea     rax, off_180024D90
0x18001dcbf  mov     [rbp+57h+var_78], rbx
0x18001dcc3  mov     [rbp+57h+var_80], rax
0x18001dcc7  lea     r8, [rbp+57h+var_88]
0x18001dccb  lea     rax, [rbp+57h+var_80]
0x18001dccf  lea     rdx, WNF_CAM_GRAPHICSCAPTUREPROGRAMMATIC_ACCESS_CHANGED
0x18001dcd6  mov     [rbp+57h+var_18], rax
0x18001dcda  lea     rcx, [rbp+57h+var_90]
0x18001dcde  call    ??$make_wnf_subscription_nothrow@Uempty_wnf_state@details@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@K@Z; wil::make_wnf_subscription_nothrow<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong)
0x18001dce3  mov     rdx, rax
0x18001dce6  lea     rcx, qword_1800331A0
0x18001dced  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x18001dcf2  lea     rcx, [rbp+57h+var_90]
0x18001dcf6  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18001dcfb  lea     rcx, [rbp+57h+var_88]
0x18001dcff  call    ??1?$function@$$A6AXXZ@wistd@@QEAA@XZ; wistd::function<void (void)>::~function<void (void)>(void)
0x18001dd04  cmp     cs:qword_1800331A0, 0
0x18001dd0c  mov     rcx, [rbp+5Fh]; this
0x18001dd10  jz      short loc_18001DD32
0x18001dd12  mov     rax, rbx
0x18001dd15  mov     rcx, [rbp+57h+var_10]
0x18001dd19  xor     rcx, rsp; StackCookie
0x18001dd1c  call    __security_check_cookie
0x18001dd21  mov     rbx, [rsp+0B0h+arg_0]
0x18001dd29  add     rsp, 0B0h
0x18001dd30  pop     rbp
0x18001dd31  retn
0x18001dd32  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001dd39  mov     edx, 31h ; '1'; void *
0x18001dd3e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001dd44  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001dd4b  mov     edx, 1Bh; void *
0x18001dd50  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
