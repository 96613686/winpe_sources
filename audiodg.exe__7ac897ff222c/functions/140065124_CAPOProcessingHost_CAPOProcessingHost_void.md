# CAPOProcessingHost::~CAPOProcessingHost(void)

- ea: `0x140065124`
- end: `0x140065233`
- name: `??1CAPOProcessingHost@@UEAA@XZ`
- size: `271`
- prototype: `void __fastcall(CAPOProcessingHost *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140065460`

## callees

- `0x140008124`
- `0x140046128`
- `0x1400464ac`
- `0x140046dc0`
- `0x140065124`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140065177`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140065190`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400651e1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400651fa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14006520d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140065177`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140065190`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400651e1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400651fa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14006520d`

## pseudocode

```c
void __fastcall CAPOProcessingHost::~CAPOProcessingHost(CAPOProcessingHost *this)
{
  _QWORD *v2; // rsi
  _QWORD *v3; // rbx

  *(_QWORD *)this = &CAPOProcessingHost::`vftable'{for `IAPOProcessingHost'};
  *((_QWORD *)this + 1) = &CAPOProcessingHost::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMMNotificationClient>'};
  if ( *((_BYTE *)this + 72) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 56LL))(*((_QWORD *)this + 3));
  std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>>>,0>>((char *)this + 456);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 416));
  std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>>>,0>>((char *)this + 352);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 296);
  v2 = (_QWORD *)*((_QWORD *)this + 36);
  *((_QWORD *)this + 36) = 0;
  if ( v2 )
  {
    do
    {
      v3 = (_QWORD *)*v2;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v2 + 1);
      std::_Deallocate<16>(v2, 16);
      v2 = v3;
    }
    while ( v3 );
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 248));
  std::_Hash<std::_Umap_traits<IAudioProcessingObject *,wil::com_ptr_t<CAPOProcessingHostObject,wil::err_returncode_policy>,std::_Uhash_compare<IAudioProcessingObject *,std::hash<IAudioProcessingObject *>,std::equal_to<IAudioProcessingObject *>>,std::allocator<std::pair<IAudioProcessingObject * const,wil::com_ptr_t<CAPOProcessingHostObject,wil::err_returncode_policy>>>,0>>::~_Hash<std::_Umap_traits<IAudioProcessingObject *,wil::com_ptr_t<CAPOProcessingHostObject,wil::err_returncode_policy>,std::_Uhash_compare<IAudioProcessingObject *,std::hash<IAudioProcessingObject *>,std::equal_to<IAudioProcessingObject *>>,std::allocator<std::pair<IAudioProcessingObject * const,wil::com_ptr_t<CAPOProcessingHostObject,wil::err_returncode_policy>>>,0>>((char *)this + 184);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>>>,0>>((char *)this + 80);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 24);
  *((_DWORD *)this + 5) = -1073741823;
}

```

## disassembly

```asm
0x140065124  mov     [rsp+arg_0], rbx
0x140065129  mov     [rsp+arg_8], rsi
0x14006512e  push    rdi
0x14006512f  sub     rsp, 20h
0x140065133  mov     rdi, rcx
0x140065136  lea     rax, ??_7CAPOProcessingHost@@6BIAPOProcessingHost@@@; const CAPOProcessingHost::`vftable'{for `IAPOProcessingHost'}
0x14006513d  mov     [rcx], rax
0x140065140  lea     rdx, [rcx+8]
0x140065144  lea     rax, ??_7CAPOProcessingHost@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMMNotificationClient@@@Details@WRL@Microsoft@@@; const CAPOProcessingHost::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMMNotificationClient>'}
0x14006514b  mov     [rdx], rax
0x14006514e  cmp     byte ptr [rcx+48h], 0
0x140065152  jz      short loc_140065164
0x140065154  mov     rcx, [rcx+18h]
0x140065158  mov     rax, [rcx]
0x14006515b  mov     rax, [rax+38h]
0x14006515f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140065164  lea     rcx, [rdi+1C8h]
0x14006516b  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@VCAPOEndpointNotificationsHandler@@Uerr_returncode_policy@wil@@@wil@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@VCAPOEndpointNotificationsHandler@@Uerr_returncode_policy@wil@@@wil@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>>>,0>>(void)
0x140065170  lea     rcx, [rdi+1A0h]; lpCriticalSection
0x140065177  call    cs:__imp_DeleteCriticalSection
0x14006517d  lea     rcx, [rdi+160h]
0x140065184  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@VCAPOEndpointNotificationsHandler@@Uerr_returncode_policy@wil@@@wil@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@VCAPOEndpointNotificationsHandler@@Uerr_returncode_policy@wil@@@wil@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>>>,0>>(void)
0x140065189  lea     rcx, [rdi+138h]; lpCriticalSection
0x140065190  call    cs:__imp_DeleteCriticalSection
0x140065196  lea     rcx, [rdi+128h]
0x14006519d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400651a2  mov     rsi, [rdi+120h]
0x1400651a9  mov     qword ptr [rdi+120h], 0
0x1400651b4  test    rsi, rsi
0x1400651b7  jz      short loc_1400651DA
0x1400651b9  mov     rbx, [rsi]
0x1400651bc  lea     rcx, [rsi+8]
0x1400651c0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400651c5  mov     edx, 10h
0x1400651ca  mov     rcx, rsi
0x1400651cd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400651d2  mov     rsi, rbx
0x1400651d5  test    rbx, rbx
0x1400651d8  jnz     short loc_1400651B9
0x1400651da  lea     rcx, [rdi+0F8h]; lpCriticalSection
0x1400651e1  call    cs:__imp_DeleteCriticalSection
0x1400651e7  lea     rcx, [rdi+0B8h]
0x1400651ee  call    ??1?$_Hash@V?$_Umap_traits@PEAUIAudioProcessingObject@@V?$com_ptr_t@VCAPOProcessingHostObject@@Uerr_returncode_policy@wil@@@wil@@V?$_Uhash_compare@PEAUIAudioProcessingObject@@U?$hash@PEAUIAudioProcessingObject@@@std@@U?$equal_to@PEAUIAudioProcessingObject@@@3@@std@@V?$allocator@U?$pair@QEAUIAudioProcessingObject@@V?$com_ptr_t@VCAPOProcessingHostObject@@Uerr_returncode_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<IAudioProcessingObject *,wil::com_ptr_t<CAPOProcessingHostObject,wil::err_returncode_policy>,std::_Uhash_compare<IAudioProcessingObject *,std::hash<IAudioProcessingObject *>,std::equal_to<IAudioProcessingObject *>>,std::allocator<std::pair<IAudioProcessingObject * const,wil::com_ptr_t<CAPOProcessingHostObject,wil::err_returncode_policy>>>,0>>::~_Hash<std::_Umap_traits<IAudioProcessingObject *,wil::com_ptr_t<CAPOProcessingHostObject,wil::err_returncode_policy>,std::_Uhash_compare<IAudioProcessingObject *,std::hash<IAudioProcessingObject *>,std::equal_to<IAudioProcessingObject *>>,std::allocator<std::pair<IAudioProcessingObject * const,wil::com_ptr_t<CAPOProcessingHostObject,wil::err_returncode_policy>>>,0>>(void)
0x1400651f3  lea     rcx, [rdi+90h]; lpCriticalSection
0x1400651fa  call    cs:__imp_DeleteCriticalSection
0x140065200  lea     rcx, [rdi+50h]
0x140065204  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@VCAPOEndpointNotificationsHandler@@Uerr_returncode_policy@wil@@@wil@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@VCAPOEndpointNotificationsHandler@@Uerr_returncode_policy@wil@@@wil@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>>>,0>>(void)
0x140065209  lea     rcx, [rdi+20h]; lpCriticalSection
0x14006520d  call    cs:__imp_DeleteCriticalSection
0x140065213  lea     rcx, [rdi+18h]
0x140065217  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14006521c  mov     dword ptr [rdi+14h], 0C0000001h
0x140065223  mov     rbx, [rsp+28h+arg_0]
0x140065228  mov     rsi, [rsp+28h+arg_8]
0x14006522d  add     rsp, 20h
0x140065231  pop     rdi
0x140065232  retn
```
