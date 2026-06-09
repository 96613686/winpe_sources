# CVirtualAudioClient::~CVirtualAudioClient(void)

- ea: `0x180007f8c`
- end: `0x180008196`
- name: `??1CVirtualAudioClient@@UEAA@XZ`
- size: `522`
- prototype: `void __fastcall(CVirtualAudioClient *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007f50`

## callees

- `0x180007f00`
- `0x180007f30`
- `0x180007f8c`
- `0x18000819c`
- `0x18000821c`
- `0x18000cb1c`
- `0x1800154e0`
- `0x18002d6ac`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008057`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008064`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008057`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008064`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008039`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008039`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008081`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000808e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800080e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008105`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008081`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000808e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800080e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008105`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008176`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008176`

## pseudocode

```c
void __fastcall CVirtualAudioClient::~CVirtualAudioClient(CVirtualAudioClient *this)
{
  char *v2; // r14
  void *v3; // rdx
  void *v4; // rcx
  void *v5; // rdx
  wil::details *v6; // rcx
  wil::details *v7; // rcx
  wil::details *v8; // rcx

  *(_QWORD *)this = &CVirtualAudioClient::`vftable'{for `IAudioClient'};
  *((_QWORD *)this + 1) = &CVirtualAudioClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAudioClient2,IAudioClient3,IAudioClock,IAudioClock2,IAudioRenderClient,IAudioCaptureClient,IRetryableAudioClient>'};
  *((_QWORD *)this + 2) = &CVirtualAudioClient::`vftable'{for `IAudioClient3'};
  *((_QWORD *)this + 3) = &CVirtualAudioClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAudioClock,IAudioClock2,IAudioRenderClient,IAudioCaptureClient,IRetryableAudioClient>'};
  *((_QWORD *)this + 4) = &CVirtualAudioClient::`vftable'{for `IAudioClock2'};
  *((_QWORD *)this + 5) = &CVirtualAudioClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAudioRenderClient,IAudioCaptureClient,IRetryableAudioClient>'};
  *((_QWORD *)this + 6) = &CVirtualAudioClient::`vftable'{for `IAudioCaptureClient'};
  *((_QWORD *)this + 7) = &CVirtualAudioClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IRetryableAudioClient>'};
  v2 = (char *)this + 192;
  v3 = (void *)*((_QWORD *)this + 24);
  if ( v3 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 23) + 80LL))(*((_QWORD *)this + 23));
  if ( ((*((_QWORD *)this + 36) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    wil::details::SetEvent(*((wil::details **)this + 35), v3);
    WaitForSingleObject(*((HANDLE *)this + 36), 0xFFFFFFFF);
  }
  ATL::CAtlList<ATL::CAutoPtr<WorkItemChangeEndpoint>,ATL::CAutoPtrElementTraits<WorkItemChangeEndpoint>>::RemoveAll((char *)this + 72);
  CVirtualAudioClient::ReleaseSubAudioClient(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 10);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 9);
  v4 = (void *)*((_QWORD *)this + 39);
  *((_QWORD *)this + 39) = 0;
  if ( v4 )
    CoTaskMemFree(v4);
  CoTaskMemFree(*((LPVOID *)this + 38));
  *((_QWORD *)this + 38) = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 288);
  v6 = (wil::details *)*((_QWORD *)this + 35);
  if ( v6 )
    wil::details::CloseHandle(v6, v5);
  v7 = (wil::details *)*((_QWORD *)this + 34);
  if ( v7 )
    wil::details::CloseHandle(v7, v5);
  v8 = (wil::details *)*((_QWORD *)this + 33);
  if ( v8 )
    wil::details::CloseHandle(v8, v5);
  CoTaskMemFree(*((LPVOID *)this + 28));
  *((_QWORD *)this + 28) = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((char *)this + 216);
  CoTaskMemFree(*((LPVOID *)this + 26));
  *((_QWORD *)this + 26) = 0;
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 200);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(v2);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 184);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 176);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 168);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 160);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 152);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 144);
  PropVariantClear((PROPVARIANT *)this + 15);
  ATL::CAtlList<ATL::CAutoPtr<WorkItemChangeEndpoint>,ATL::CAutoPtrElementTraits<WorkItemChangeEndpoint>>::RemoveAll((char *)this + 72);
  *((_DWORD *)this + 17) = -1073741823;
}

```

## disassembly

```asm
0x180007f8c  push    rbx
0x180007f8e  push    rsi
0x180007f8f  push    rdi
0x180007f90  push    r14
0x180007f92  sub     rsp, 28h
0x180007f96  mov     rbx, rcx
0x180007f99  lea     rax, ??_7CVirtualAudioClient@@6BIAudioClient@@@; const CVirtualAudioClient::`vftable'{for `IAudioClient'}
0x180007fa0  mov     [rcx], rax
0x180007fa3  lea     rax, ??_7CVirtualAudioClient@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIAudioClient2@@UIAudioClient3@@UIAudioClock@@UIAudioClock2@@UIAudioRenderClient@@UIAudioCaptureClient@@UIRetryableAudioClient@@@Details@WRL@Microsoft@@@; const CVirtualAudioClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAudioClient2,IAudioClient3,IAudioClock,IAudioClock2,IAudioRenderClient,IAudioCaptureClient,IRetryableAudioClient>'}
0x180007faa  mov     [rcx+8], rax
0x180007fae  lea     rax, ??_7CVirtualAudioClient@@6BIAudioClient3@@@; const CVirtualAudioClient::`vftable'{for `IAudioClient3'}
0x180007fb5  mov     [rcx+10h], rax
0x180007fb9  lea     rax, ??_7CVirtualAudioClient@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIAudioClock@@UIAudioClock2@@UIAudioRenderClient@@UIAudioCaptureClient@@UIRetryableAudioClient@@@Details@WRL@Microsoft@@@; const CVirtualAudioClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAudioClock,IAudioClock2,IAudioRenderClient,IAudioCaptureClient,IRetryableAudioClient>'}
0x180007fc0  mov     [rcx+18h], rax
0x180007fc4  lea     rax, ??_7CVirtualAudioClient@@6BIAudioClock2@@@; const CVirtualAudioClient::`vftable'{for `IAudioClock2'}
0x180007fcb  mov     [rcx+20h], rax
0x180007fcf  lea     rax, ??_7CVirtualAudioClient@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIAudioRenderClient@@UIAudioCaptureClient@@UIRetryableAudioClient@@@Details@WRL@Microsoft@@@; const CVirtualAudioClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAudioRenderClient,IAudioCaptureClient,IRetryableAudioClient>'}
0x180007fd6  mov     [rcx+28h], rax
0x180007fda  lea     rax, ??_7CVirtualAudioClient@@6BIAudioCaptureClient@@@; const CVirtualAudioClient::`vftable'{for `IAudioCaptureClient'}
0x180007fe1  mov     [rcx+30h], rax
0x180007fe5  lea     rax, ??_7CVirtualAudioClient@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIRetryableAudioClient@@@Details@WRL@Microsoft@@@; const CVirtualAudioClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IRetryableAudioClient>'}
0x180007fec  mov     [rcx+38h], rax
0x180007ff0  lea     r14, [rcx+0C0h]
0x180007ff7  mov     rdx, [r14]
0x180007ffa  test    rdx, rdx
0x180007ffd  jz      short loc_180008012
0x180007fff  mov     rcx, [rcx+0B8h]
0x180008006  mov     rax, [rcx]
0x180008009  mov     rax, [rax+50h]
0x18000800d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008012  lea     rdi, [rbx+120h]
0x180008019  mov     rax, [rdi]
0x18000801c  inc     rax
0x18000801f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180008025  jz      short loc_18000803F
0x180008027  mov     rcx, [rbx+118h]; this
0x18000802e  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180008033  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008036  mov     rcx, [rdi]; hHandle
0x180008039  call    cs:__imp_WaitForSingleObject
0x18000803f  lea     rcx, [rbx+48h]
0x180008043  call    ?RemoveAll@?$CAtlList@V?$CAutoPtr@VWorkItemChangeEndpoint@@@ATL@@V?$CAutoPtrElementTraits@VWorkItemChangeEndpoint@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CAutoPtr<WorkItemChangeEndpoint>,ATL::CAutoPtrElementTraits<WorkItemChangeEndpoint>>::RemoveAll(void)
0x180008048  mov     rcx, rbx; this
0x18000804b  call    ?ReleaseSubAudioClient@CVirtualAudioClient@@AEAAXXZ; CVirtualAudioClient::ReleaseSubAudioClient(void)
0x180008050  lea     rcx, [rbx+190h]; lpCriticalSection
0x180008057  call    cs:__imp_DeleteCriticalSection
0x18000805d  lea     rcx, [rbx+168h]; lpCriticalSection
0x180008064  call    cs:__imp_DeleteCriticalSection
0x18000806a  mov     rcx, [rbx+138h]; pv
0x180008071  mov     qword ptr [rbx+138h], 0
0x18000807c  test    rcx, rcx
0x18000807f  jz      short loc_180008087
0x180008081  call    cs:__imp_CoTaskMemFree
0x180008087  mov     rcx, [rbx+130h]; pv
0x18000808e  call    cs:__imp_CoTaskMemFree
0x180008094  mov     qword ptr [rbx+130h], 0
0x18000809f  mov     rcx, rdi
0x1800080a2  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800080a7  mov     rcx, [rbx+118h]; this
0x1800080ae  test    rcx, rcx
0x1800080b1  jz      short loc_1800080B8
0x1800080b3  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800080b8  mov     rcx, [rbx+110h]; this
0x1800080bf  test    rcx, rcx
0x1800080c2  jz      short loc_1800080C9
0x1800080c4  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800080c9  mov     rcx, [rbx+108h]; this
0x1800080d0  test    rcx, rcx
0x1800080d3  jz      short loc_1800080DA
0x1800080d5  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800080da  mov     rcx, [rbx+0E0h]; pv
0x1800080e1  call    cs:__imp_CoTaskMemFree
0x1800080e7  mov     qword ptr [rbx+0E0h], 0
0x1800080f2  lea     rcx, [rbx+0D8h]
0x1800080f9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800080fe  mov     rcx, [rbx+0D0h]; pv
0x180008105  call    cs:__imp_CoTaskMemFree
0x18000810b  mov     qword ptr [rbx+0D0h], 0
0x180008116  lea     rcx, [rbx+0C8h]; void *
0x18000811d  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x180008122  mov     rcx, r14; void *
0x180008125  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x18000812a  lea     rcx, [rbx+0B8h]; void *
0x180008131  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x180008136  lea     rcx, [rbx+0B0h]; void *
0x18000813d  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x180008142  lea     rcx, [rbx+0A8h]; void *
0x180008149  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x18000814e  lea     rcx, [rbx+0A0h]; void *
0x180008155  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x18000815a  lea     rcx, [rbx+98h]; void *
0x180008161  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x180008166  lea     rcx, [rbx+90h]; void *
0x18000816d  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x180008172  lea     rcx, [rbx+78h]; pvar
0x180008176  call    cs:__imp_PropVariantClear
0x18000817c  lea     rcx, [rbx+48h]
0x180008180  call    ?RemoveAll@?$CAtlList@V?$CAutoPtr@VWorkItemChangeEndpoint@@@ATL@@V?$CAutoPtrElementTraits@VWorkItemChangeEndpoint@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CAutoPtr<WorkItemChangeEndpoint>,ATL::CAutoPtrElementTraits<WorkItemChangeEndpoint>>::RemoveAll(void)
0x180008185  mov     dword ptr [rbx+44h], 0C0000001h
0x18000818c  add     rsp, 28h
0x180008190  pop     r14
0x180008192  pop     rdi
0x180008193  pop     rsi
0x180008194  pop     rbx
0x180008195  retn
```
