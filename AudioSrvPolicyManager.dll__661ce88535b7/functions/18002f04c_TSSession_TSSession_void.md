# TSSession::~TSSession(void)

- ea: `0x18002f04c`
- end: `0x18002f1b7`
- name: `??1TSSession@@QEAA@XZ`
- size: `363`
- prototype: `void __fastcall(TSSession *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180041f88`

## callees

- `0x180001c74`
- `0x180007b60`
- `0x18000ac00`
- `0x18001ada0`
- `0x180020d50`
- `0x18002c92c`
- `0x18002f04c`
- `0x18002f1c0`
- `0x18002f21c`
- `0x180041c50`
- `0x180041c6c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f06f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f06f`

## pseudocode

```c
void __fastcall TSSession::~TSSession(TSSession *this)
{
  void *v2; // rcx
  _QWORD *v3; // rsi
  _QWORD *v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rcx
  _QWORD *v7; // rsi
  _QWORD *v8; // rbx

  TSSession::UnregisterSessionDisplayNotificationCallback(this);
  v2 = (void *)*((_QWORD *)this + 138);
  if ( v2 )
    CoTaskMemFree(v2);
  Microsoft::WRL::Details::MakeAllocator<CAudioSessionPropertyStore>::~MakeAllocator<CAudioSessionPropertyStore>((char *)this + 1096);
  std::unique_ptr<CDriverListener>::~unique_ptr<CDriverListener>((char *)this + 1080);
  v3 = (_QWORD *)*((_QWORD *)this + 133);
  *((_QWORD *)this + 133) = 0;
  if ( v3 )
  {
    do
    {
      v4 = (_QWORD *)*v3;
      std::unique_ptr<DuckingDescriptorAndId>::~unique_ptr<DuckingDescriptorAndId>(v3 + 1);
      std::_Deallocate<16>(v3, 16);
      v3 = v4;
    }
    while ( v4 );
  }
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>((char *)this + 1056);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>((char *)this + 1048);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>((char *)this + 1040);
  v5 = *((_QWORD *)this + 123);
  if ( v5 )
  {
    std::_Deallocate<16>(v5, (*((_QWORD *)this + 125) - v5) & 0xFFFFFFFFFFFFFFFCuLL);
    *((_QWORD *)this + 123) = 0;
    *((_QWORD *)this + 124) = 0;
    *((_QWORD *)this + 125) = 0;
  }
  CStreamClassPolicyGainsWrapper::~CStreamClassPolicyGainsWrapper((TSSession *)((char *)this + 72));
  v6 = *((_QWORD *)this + 6);
  if ( v6 )
  {
    std::_Deallocate<16>(v6, (*((_QWORD *)this + 8) - v6) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 6) = 0;
    *((_QWORD *)this + 7) = 0;
    *((_QWORD *)this + 8) = 0;
  }
  std::forward_list<wil::com_ptr_t<CProcess,wil::err_returncode_policy>>::clear((char *)this + 40);
  wil::details::unique_storage<wil::details::resource_policy<_WTSINFOW *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_WTSINFOW *,_WTSINFOW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WTSINFOW *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_WTSINFOW *,_WTSINFOW *,0,std::nullptr_t>>((char *)this + 24);
  v7 = (_QWORD *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  if ( v7 )
  {
    do
    {
      v8 = (_QWORD *)*v7;
      std::unique_ptr<AUDIOPROTOCOLNOTIFY>::~unique_ptr<AUDIOPROTOCOLNOTIFY>(v7 + 1);
      std::_Deallocate<16>(v7, 16);
      v7 = v8;
    }
    while ( v8 );
  }
}

```

## disassembly

```asm
0x18002f04c  mov     [rsp+arg_0], rbx
0x18002f051  mov     [rsp+arg_8], rsi
0x18002f056  push    rdi
0x18002f057  sub     rsp, 20h
0x18002f05b  mov     rdi, rcx
0x18002f05e  call    ?UnregisterSessionDisplayNotificationCallback@TSSession@@QEAAXXZ; TSSession::UnregisterSessionDisplayNotificationCallback(void)
0x18002f063  mov     rcx, [rdi+450h]; pv
0x18002f06a  test    rcx, rcx
0x18002f06d  jz      short loc_18002F075
0x18002f06f  call    cs:__imp_CoTaskMemFree
0x18002f075  lea     rcx, [rdi+448h]
0x18002f07c  call    ??1?$MakeAllocator@VCAudioSessionPropertyStore@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CAudioSessionPropertyStore>::~MakeAllocator<CAudioSessionPropertyStore>(void)
0x18002f081  lea     rcx, [rdi+438h]
0x18002f088  call    ??1?$unique_ptr@VCDriverListener@@U?$default_delete@VCDriverListener@@@std@@@std@@QEAA@XZ; std::unique_ptr<CDriverListener>::~unique_ptr<CDriverListener>(void)
0x18002f08d  mov     rsi, [rdi+428h]
0x18002f094  mov     qword ptr [rdi+428h], 0
0x18002f09f  test    rsi, rsi
0x18002f0a2  jz      short loc_18002F0C5
0x18002f0a4  mov     rbx, [rsi]
0x18002f0a7  lea     rcx, [rsi+8]
0x18002f0ab  call    ??1?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@QEAA@XZ; std::unique_ptr<DuckingDescriptorAndId>::~unique_ptr<DuckingDescriptorAndId>(void)
0x18002f0b0  mov     edx, 10h
0x18002f0b5  mov     rcx, rsi
0x18002f0b8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002f0bd  mov     rsi, rbx
0x18002f0c0  test    rbx, rbx
0x18002f0c3  jnz     short loc_18002F0A4
0x18002f0c5  lea     rcx, [rdi+420h]
0x18002f0cc  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18002f0d1  lea     rcx, [rdi+418h]
0x18002f0d8  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18002f0dd  lea     rcx, [rdi+410h]
0x18002f0e4  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18002f0e9  mov     rcx, [rdi+3D8h]
0x18002f0f0  test    rcx, rcx
0x18002f0f3  jz      short loc_18002F129
0x18002f0f5  mov     rdx, [rdi+3E8h]
0x18002f0fc  sub     rdx, rcx
0x18002f0ff  and     rdx, 0FFFFFFFFFFFFFFFCh
0x18002f103  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002f108  mov     qword ptr [rdi+3D8h], 0
0x18002f113  mov     qword ptr [rdi+3E0h], 0
0x18002f11e  mov     qword ptr [rdi+3E8h], 0
0x18002f129  lea     rcx, [rdi+48h]; this
0x18002f12d  call    ??1CStreamClassPolicyGainsWrapper@@QEAA@XZ; CStreamClassPolicyGainsWrapper::~CStreamClassPolicyGainsWrapper(void)
0x18002f132  mov     rcx, [rdi+30h]
0x18002f136  test    rcx, rcx
0x18002f139  jz      short loc_18002F163
0x18002f13b  mov     rdx, [rdi+40h]
0x18002f13f  sub     rdx, rcx
0x18002f142  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18002f146  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002f14b  mov     qword ptr [rdi+30h], 0
0x18002f153  mov     qword ptr [rdi+38h], 0
0x18002f15b  mov     qword ptr [rdi+40h], 0
0x18002f163  lea     rcx, [rdi+28h]
0x18002f167  call    ?clear@?$forward_list@V?$com_ptr_t@VCProcess@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCProcess@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAAXXZ; std::forward_list<wil::com_ptr_t<CProcess,wil::err_returncode_policy>>::clear(void)
0x18002f16c  lea     rcx, [rdi+18h]
0x18002f170  call    ??1?$unique_storage@U?$resource_policy@PEAU_WTSINFOW@@P6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_WTSINFOW *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_WTSINFOW *,_WTSINFOW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WTSINFOW *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_WTSINFOW *,_WTSINFOW *,0,std::nullptr_t>>(void)
0x18002f175  mov     rsi, [rdi+10h]
0x18002f179  mov     qword ptr [rdi+10h], 0
0x18002f181  test    rsi, rsi
0x18002f184  jz      short loc_18002F1A7
0x18002f186  mov     rbx, [rsi]
0x18002f189  lea     rcx, [rsi+8]
0x18002f18d  call    ??1?$unique_ptr@UAUDIOPROTOCOLNOTIFY@@U?$default_delete@UAUDIOPROTOCOLNOTIFY@@@std@@@std@@QEAA@XZ; std::unique_ptr<AUDIOPROTOCOLNOTIFY>::~unique_ptr<AUDIOPROTOCOLNOTIFY>(void)
0x18002f192  mov     edx, 10h
0x18002f197  mov     rcx, rsi
0x18002f19a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002f19f  mov     rsi, rbx
0x18002f1a2  test    rbx, rbx
0x18002f1a5  jnz     short loc_18002F186
0x18002f1a7  mov     rbx, [rsp+28h+arg_0]
0x18002f1ac  mov     rsi, [rsp+28h+arg_8]
0x18002f1b1  add     rsp, 20h
0x18002f1b5  pop     rdi
0x18002f1b6  retn
```
