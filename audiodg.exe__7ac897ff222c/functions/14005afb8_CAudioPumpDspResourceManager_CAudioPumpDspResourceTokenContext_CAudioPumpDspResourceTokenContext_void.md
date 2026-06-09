# CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext::~CAudioPumpDspResourceTokenContext(void)

- ea: `0x14005afb8`
- end: `0x14005b0f6`
- name: `??1CAudioPumpDspResourceTokenContext@CAudioPumpDspResourceManager@@UEAA@XZ`
- size: `318`
- prototype: `void __fastcall(CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14008e340`

## callees

- `0x140005b40`
- `0x140011e00`
- `0x1400127bc`
- `0x140016f30`
- `0x140016f68`
- `0x14005afb8`
- `0x14005b0fc`
- `0x14005b1b8`
- `0x1400903c0`
- `0x14009053c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14005b052`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14005b052`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14005b0a9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14005b0a9`

## pseudocode

```c
void __fastcall CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext::~CAudioPumpDspResourceTokenContext(
        CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext *this,
        void *a2)
{
  char *v3; // rcx
  CAudioPumpDspResourceManager *v4; // rcx
  unsigned __int64 v5; // rdx
  unsigned int v6; // edx
  void *v7; // rdx
  wil::details *v8; // rcx
  wil::details *v9; // rcx

  *(_QWORD *)this = &CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext::`vftable';
  *((_QWORD *)this + 1) = &CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext::`vftable'{for `IDeviceGraphBufferFactory'};
  *((_QWORD *)this + 2) = &CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IDspAudioProcessingObjectFactory,IDspAudioEndpointFactory,IDspCrossProcessAudioEndpointFactory,IDspBridgeAudioEndpointFactory,IDspAudioProcessorFactory,IDspAudioPumpFactory,IDspAudioPumpContext>'};
  *((_QWORD *)this + 3) = &CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext::`vftable'{for `IDspAudioEndpointFactory'};
  *((_QWORD *)this + 4) = &CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IDspCrossProcessAudioEndpointFactory,IDspBridgeAudioEndpointFactory,IDspAudioProcessorFactory,IDspAudioPumpFactory,IDspAudioPumpContext>'};
  *((_QWORD *)this + 5) = &CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext::`vftable'{for `IDspBridgeAudioEndpointFactory'};
  *((_QWORD *)this + 6) = &CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IDspAudioProcessorFactory,IDspAudioPumpFactory,IDspAudioPumpContext>'};
  *((_QWORD *)this + 7) = &CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext::`vftable'{for `IDspAudioPumpFactory'};
  *((_QWORD *)this + 8) = &CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IDspAudioPumpContext>'};
  wil::details::SetEvent(*((wil::details **)this + 17), a2);
  v3 = (char *)*((_QWORD *)this + 27);
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    WaitForSingleObjectEx(v3, 0xFFFFFFFF, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 216,
      0);
  }
  v4 = (CAudioPumpDspResourceManager *)*((_QWORD *)this + 11);
  if ( v4 )
  {
    v5 = *((_QWORD *)this + 14);
    if ( v5 )
      CAudioPumpDspResourceManager::ReleasePumpContext(v4, v5);
    v6 = *((_DWORD *)this + 36);
    if ( v6 )
      CAudioPumpDspResourceManager::ReleasePumpResourceId(*((CAudioPumpDspResourceManager **)this + 11), v6);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 216);
  std::vector<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>>::_Tidy((char *)this + 192);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  v8 = (wil::details *)*((_QWORD *)this + 17);
  if ( v8 )
    wil::details::CloseHandle(v8, v7);
  v9 = (wil::details *)*((_QWORD *)this + 15);
  if ( v9 )
    wil::details::CloseHandle(v9, v7);
  wil::com_ptr_t<CAudioPumpDspResourceManager,wil::err_returncode_policy>::~com_ptr_t<CAudioPumpDspResourceManager,wil::err_returncode_policy>((char *)this + 88);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)this + 10);
  *((_DWORD *)this + 19) = -1073741823;
}

```

## disassembly

```asm
0x14005afb8  mov     [rsp+arg_0], rbx
0x14005afbd  mov     [rsp+arg_8], rsi
0x14005afc2  push    rdi
0x14005afc3  sub     rsp, 20h
0x14005afc7  mov     rbx, rcx
0x14005afca  lea     rax, ??_7CAudioPumpDspResourceTokenContext@CAudioPumpDspResourceManager@@6B@; const CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext::`vftable'
0x14005afd1  mov     [rcx], rax
0x14005afd4  lea     rax, ??_7CAudioPumpDspResourceTokenContext@CAudioPumpDspResourceManager@@6BIDeviceGraphBufferFactory@@@; const CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext::`vftable'{for `IDeviceGraphBufferFactory'}
0x14005afdb  mov     [rcx+8], rax
0x14005afdf  lea     rax, ??_7CAudioPumpDspResourceTokenContext@CAudioPumpDspResourceManager@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIDspAudioProcessingObjectFactory@@UIDspAudioEndpointFactory@@UIDspCrossProcessAudioEndpointFactory@@UIDspBridgeAudioEndpointFactory@@UIDspAudioProcessorFactory@@UIDspAudioPumpFactory@@UIDspAudioPumpContext@@@Details@WRL@Microsoft@@@; const CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IDspAudioProcessingObjectFactory,IDspAudioEndpointFactory,IDspCrossProcessAudioEndpointFactory,IDspBridgeAudioEndpointFactory,IDspAudioProcessorFactory,IDspAudioPumpFactory,IDspAudioPumpContext>'}
0x14005afe6  mov     [rcx+10h], rax
0x14005afea  lea     rax, ??_7CAudioPumpDspResourceTokenContext@CAudioPumpDspResourceManager@@6BIDspAudioEndpointFactory@@@; const CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext::`vftable'{for `IDspAudioEndpointFactory'}
0x14005aff1  mov     [rcx+18h], rax
0x14005aff5  lea     rax, ??_7CAudioPumpDspResourceTokenContext@CAudioPumpDspResourceManager@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIDspCrossProcessAudioEndpointFactory@@UIDspBridgeAudioEndpointFactory@@UIDspAudioProcessorFactory@@UIDspAudioPumpFactory@@UIDspAudioPumpContext@@@Details@WRL@Microsoft@@@; const CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IDspCrossProcessAudioEndpointFactory,IDspBridgeAudioEndpointFactory,IDspAudioProcessorFactory,IDspAudioPumpFactory,IDspAudioPumpContext>'}
0x14005affc  mov     [rcx+20h], rax
0x14005b000  lea     rax, ??_7CAudioPumpDspResourceTokenContext@CAudioPumpDspResourceManager@@6BIDspBridgeAudioEndpointFactory@@@; const CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext::`vftable'{for `IDspBridgeAudioEndpointFactory'}
0x14005b007  mov     [rcx+28h], rax
0x14005b00b  lea     rax, ??_7CAudioPumpDspResourceTokenContext@CAudioPumpDspResourceManager@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIDspAudioProcessorFactory@@UIDspAudioPumpFactory@@UIDspAudioPumpContext@@@Details@WRL@Microsoft@@@; const CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IDspAudioProcessorFactory,IDspAudioPumpFactory,IDspAudioPumpContext>'}
0x14005b012  mov     [rcx+30h], rax
0x14005b016  lea     rax, ??_7CAudioPumpDspResourceTokenContext@CAudioPumpDspResourceManager@@6BIDspAudioPumpFactory@@@; const CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext::`vftable'{for `IDspAudioPumpFactory'}
0x14005b01d  mov     [rcx+38h], rax
0x14005b021  lea     rax, ??_7CAudioPumpDspResourceTokenContext@CAudioPumpDspResourceManager@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIDspAudioPumpContext@@@Details@WRL@Microsoft@@@; const CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IDspAudioPumpContext>'}
0x14005b028  mov     [rcx+40h], rax
0x14005b02c  mov     rcx, [rcx+88h]; this
0x14005b033  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x14005b038  lea     rsi, [rbx+0D8h]
0x14005b03f  mov     rcx, [rsi]; hHandle
0x14005b042  lea     rax, [rcx-1]
0x14005b046  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14005b04a  ja      short loc_14005B062
0x14005b04c  xor     r8d, r8d; bAlertable
0x14005b04f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14005b052  call    cs:__imp_WaitForSingleObjectEx
0x14005b058  xor     edx, edx
0x14005b05a  mov     rcx, rsi
0x14005b05d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14005b062  lea     rdi, [rbx+58h]
0x14005b066  mov     rcx, [rdi]; this
0x14005b069  test    rcx, rcx
0x14005b06c  jz      short loc_14005B08E
0x14005b06e  mov     rdx, [rbx+70h]; unsigned __int64
0x14005b072  test    rdx, rdx
0x14005b075  jz      short loc_14005B07C
0x14005b077  call    ?ReleasePumpContext@CAudioPumpDspResourceManager@@QEAAJ_K@Z; CAudioPumpDspResourceManager::ReleasePumpContext(unsigned __int64)
0x14005b07c  mov     edx, [rbx+90h]; unsigned int
0x14005b082  test    edx, edx
0x14005b084  jz      short loc_14005B08E
0x14005b086  mov     rcx, [rdi]; this
0x14005b089  call    ?ReleasePumpResourceId@CAudioPumpDspResourceManager@@QEAAJI@Z; CAudioPumpDspResourceManager::ReleasePumpResourceId(uint)
0x14005b08e  mov     rcx, rsi
0x14005b091  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14005b096  lea     rcx, [rbx+0C0h]
0x14005b09d  call    ?_Tidy@?$vector@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>>::_Tidy(void)
0x14005b0a2  lea     rcx, [rbx+98h]; lpCriticalSection
0x14005b0a9  call    cs:__imp_DeleteCriticalSection
0x14005b0af  mov     rcx, [rbx+88h]; this
0x14005b0b6  test    rcx, rcx
0x14005b0b9  jz      short loc_14005B0C0
0x14005b0bb  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14005b0c0  mov     rcx, [rbx+78h]; this
0x14005b0c4  test    rcx, rcx
0x14005b0c7  jz      short loc_14005B0CE
0x14005b0c9  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14005b0ce  mov     rcx, rdi
0x14005b0d1  call    ??1?$com_ptr_t@VCAudioPumpDspResourceManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CAudioPumpDspResourceManager,wil::err_returncode_policy>::~com_ptr_t<CAudioPumpDspResourceManager,wil::err_returncode_policy>(void)
0x14005b0d6  lea     rcx, [rbx+50h]
0x14005b0da  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14005b0df  mov     dword ptr [rbx+4Ch], 0C0000001h
0x14005b0e6  mov     rbx, [rsp+28h+arg_0]
0x14005b0eb  mov     rsi, [rsp+28h+arg_8]
0x14005b0f0  add     rsp, 20h
0x14005b0f4  pop     rdi
0x14005b0f5  retn
```
