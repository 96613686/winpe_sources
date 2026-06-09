# CProcess::~CProcess(void)

- ea: `0x18000ecb0`
- end: `0x18000f032`
- name: `??1CProcess@@MEAA@XZ`
- size: `898`
- prototype: `void __fastcall(CProcess *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000e340`

## callees

- `0x180001c74`
- `0x1800088d0`
- `0x18000ac00`
- `0x18000ec54`
- `0x18000ecb0`
- `0x18000f040`
- `0x18000f4e0`
- `0x18000f7b4`
- `0x1800109d0`
- `0x18001999c`
- `0x180019a80`
- `0x18001d858`
- `0x18001f1d0`
- `0x18002c8c4`
- `0x180031e00`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000eea8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000eec1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ef06`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ef1f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000eea8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000eec1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ef06`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ef1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ed7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ed7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000edd7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000edd7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ee18`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ee3d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ee56`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ee5f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ee6c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f018`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ee18`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ee3d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ee56`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ee5f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ee6c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f018`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ed6b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ed6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ef63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ef75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ef87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ef99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ef63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ef75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ef87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ef99`

## pseudocode

```c
void __fastcall CProcess::~CProcess(CProcess *this)
{
  void *v2; // rbx
  void *v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // rcx
  _DWORD *v6; // rbx
  int i; // esi
  void *v8; // rcx
  _DWORD *v9; // rbx
  int j; // esi
  void *v11; // rcx
  __int64 v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  struct std::nothrow_t *v18; // rdx
  struct std::nothrow_t *v19; // [rsp+40h] [rbp+8h] BYREF
  void *v20; // [rsp+48h] [rbp+10h] BYREF

  *(_QWORD *)this = &CProcess::`vftable'{for `IAudioProcess'};
  *((_QWORD *)this + 1) = &CProcess::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAudioProcessInternal>'};
  while ( *((int *)this + 68) > 0 )
  {
    v2 = (void *)**((_QWORD **)this + 33);
    ATL::CSimpleMap<std::wstring,unsigned int *,ATL::CSimpleMapEqualHelper<std::wstring,unsigned int *>>::RemoveAt((char *)this + 256);
    operator delete(v2);
  }
  while ( *((int *)this + 74) > 0 )
  {
    v3 = *(void **)ATL::CSimpleMap<std::wstring,unsigned int *,ATL::CSimpleMapEqualHelper<std::wstring,unsigned int *>>::GetValueAt(
                     (char *)this + 280,
                     0);
    ATL::CSimpleMap<std::wstring,unsigned int *,ATL::CSimpleMapEqualHelper<std::wstring,unsigned int *>>::RemoveAt((char *)this + 280);
    operator delete(v3);
  }
  if ( *((_DWORD *)this + 58) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30));
  if ( *((_QWORD *)this + 73) )
  {
    CProcess::CancelDeferredBamExemptionRelease(this);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 73));
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 368));
  v4 = *((_QWORD *)this + 51);
  if ( v4 )
  {
    (*(void (__fastcall **)(struct CAudioThreadPool *, __int64, __int64))(*(_QWORD *)ThreadPool + 48LL))(
      ThreadPool,
      v4,
      1);
    (*(void (__fastcall **)(struct CAudioThreadPool *, _QWORD))(*(_QWORD *)ThreadPool + 96LL))(
      ThreadPool,
      *((_QWORD *)this + 51));
    *((_QWORD *)this + 51) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAudioProcess,IAudioProcessInternal>::Release(this);
  }
  if ( this != (CProcess *)-368LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 368));
  v5 = *((_QWORD *)this + 95);
  if ( v5 )
  {
    std::_Deallocate<16>(v5, (*((_QWORD *)this + 97) - v5) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 95) = 0;
    *((_QWORD *)this + 96) = 0;
    *((_QWORD *)this + 97) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 712));
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>((char *)this + 704);
  ATL::CAtlMap<IUnknown *,wil::com_ptr_t<IAudioProcessNotification,wil::err_returncode_policy>,ATL::CElementTraits<IUnknown *>,ATL::CElementTraits<wil::com_ptr_t<IAudioProcessNotification,wil::err_returncode_policy>>>::RemoveAll((char *)this + 632);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 592));
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 576);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 536));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 368));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 8);
  v6 = (_DWORD *)((char *)this + 296);
  if ( *((_QWORD *)this + 35) )
  {
    for ( i = 0; i < *v6; ++i )
      std::wstring::~wstring(*((_QWORD *)this + 35) + 32LL * i);
    free(*((void **)this + 35));
    *((_QWORD *)this + 35) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 36);
  if ( v8 )
  {
    free(v8);
    *((_QWORD *)this + 36) = 0;
  }
  *v6 = 0;
  v9 = (_DWORD *)((char *)this + 272);
  if ( *((_QWORD *)this + 32) )
  {
    for ( j = 0; j < *v9; ++j )
      std::wstring::~wstring(*((_QWORD *)this + 32) + 32LL * j);
    free(*((void **)this + 32));
    *((_QWORD *)this + 32) = 0;
  }
  v11 = (void *)*((_QWORD *)this + 33);
  if ( v11 )
  {
    free(v11);
    *((_QWORD *)this + 33) = 0;
  }
  *v9 = 0;
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>((char *)this + 248);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>((char *)this + 240);
  v12 = *((_QWORD *)this + 28);
  if ( v12 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v12);
  v13 = (void *)*((_QWORD *)this + 25);
  if ( v13 )
    CoTaskMemFree(v13);
  v14 = (void *)*((_QWORD *)this + 23);
  if ( v14 )
    CoTaskMemFree(v14);
  v15 = (void *)*((_QWORD *)this + 22);
  if ( v15 )
    CoTaskMemFree(v15);
  v16 = (void *)*((_QWORD *)this + 21);
  if ( v16 )
    CoTaskMemFree(v16);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 152);
  v17 = (void *)*((_QWORD *)this + 16);
  if ( v17 )
  {
    v18 = (struct std::nothrow_t *)((*((_QWORD *)this + 18) - (_QWORD)v17) & 0xFFFFFFFFFFFFFFFCuLL);
    v19 = v18;
    v20 = v17;
    if ( (unsigned __int64)v18 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v20, (unsigned __int64 *)&v19);
      v18 = v19;
      v17 = v20;
    }
    operator delete(v17, v18);
    *((_QWORD *)this + 16) = 0;
    *((_QWORD *)this + 17) = 0;
    *((_QWORD *)this + 18) = 0;
  }
  std::_Hash<std::_Umap_traits<void *,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>>,0>>::~_Hash<std::_Umap_traits<void *,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>>,0>>((char *)this + 64);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *((_DWORD *)this + 5) = -1073741823;
}

```

## disassembly

```asm
0x18000ecb0  mov     [rsp+arg_10], rbx
0x18000ecb5  push    rbp
0x18000ecb6  push    rsi
0x18000ecb7  push    rdi
0x18000ecb8  sub     rsp, 20h
0x18000ecbc  mov     rdi, rcx
0x18000ecbf  lea     rax, ??_7CProcess@@6BIAudioProcess@@@; const CProcess::`vftable'{for `IAudioProcess'}
0x18000ecc6  mov     [rcx], rax
0x18000ecc9  lea     rax, ??_7CProcess@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIAudioProcessInternal@@@Details@WRL@Microsoft@@@; const CProcess::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAudioProcessInternal>'}
0x18000ecd0  mov     [rcx+8], rax
0x18000ecd4  xor     ebp, ebp
0x18000ecd6  cmp     [rcx+110h], ebp
0x18000ecdc  jle     short loc_18000ED04
0x18000ecde  mov     rax, [rdi+108h]
0x18000ece5  mov     rbx, [rax]
0x18000ece8  lea     rcx, [rdi+100h]
0x18000ecef  call    ?RemoveAt@?$CSimpleMap@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAIV?$CSimpleMapEqualHelper@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAI@ATL@@@ATL@@QEAAHH@Z; ATL::CSimpleMap<std::wstring,uint *,ATL::CSimpleMapEqualHelper<std::wstring,uint *>>::RemoveAt(int)
0x18000ecf4  mov     rcx, rbx; void *
0x18000ecf7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ecfc  cmp     [rdi+110h], ebp
0x18000ed02  jg      short loc_18000ECDE
0x18000ed04  cmp     [rdi+128h], ebp
0x18000ed0a  jle     short loc_18000ED38
0x18000ed0c  lea     rsi, [rdi+118h]
0x18000ed13  xor     edx, edx
0x18000ed15  mov     rcx, rsi
0x18000ed18  call    ?GetValueAt@?$CSimpleMap@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAIV?$CSimpleMapEqualHelper@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAI@ATL@@@ATL@@QEBAAEAPEAIH@Z; ATL::CSimpleMap<std::wstring,uint *,ATL::CSimpleMapEqualHelper<std::wstring,uint *>>::GetValueAt(int)
0x18000ed1d  mov     rbx, [rax]
0x18000ed20  mov     rcx, rsi
0x18000ed23  call    ?RemoveAt@?$CSimpleMap@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAIV?$CSimpleMapEqualHelper@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAI@ATL@@@ATL@@QEAAHH@Z; ATL::CSimpleMap<std::wstring,uint *,ATL::CSimpleMapEqualHelper<std::wstring,uint *>>::RemoveAt(int)
0x18000ed28  mov     rcx, rbx; void *
0x18000ed2b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ed30  cmp     [rdi+128h], ebp
0x18000ed36  jg      short loc_18000ED13
0x18000ed38  cmp     [rdi+0E8h], ebp
0x18000ed3e  jz      short loc_18000ED53
0x18000ed40  mov     rcx, [rdi+0F0h]
0x18000ed47  mov     rax, [rcx]
0x18000ed4a  mov     rax, [rax+28h]
0x18000ed4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed53  cmp     [rdi+248h], rbp
0x18000ed5a  jz      short loc_18000ED71
0x18000ed5c  mov     rcx, rdi; this
0x18000ed5f  call    ?CancelDeferredBamExemptionRelease@CProcess@@IEAAXXZ; CProcess::CancelDeferredBamExemptionRelease(void)
0x18000ed64  mov     rcx, [rdi+248h]; pti
0x18000ed6b  call    cs:__imp_CloseThreadpoolTimer
0x18000ed71  lea     rbx, [rdi+170h]
0x18000ed78  mov     rcx, rbx; lpCriticalSection
0x18000ed7b  call    cs:__imp_EnterCriticalSection
0x18000ed81  mov     rdx, [rdi+198h]
0x18000ed88  test    rdx, rdx
0x18000ed8b  jz      short loc_18000EDCF
0x18000ed8d  mov     rcx, cs:?ThreadPool@@3PEAVCAudioThreadPool@@EA; CAudioThreadPool * ThreadPool
0x18000ed94  mov     rax, [rcx]
0x18000ed97  mov     r8d, 1
0x18000ed9d  mov     rax, [rax+30h]
0x18000eda1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eda6  mov     rcx, cs:?ThreadPool@@3PEAVCAudioThreadPool@@EA; CAudioThreadPool * ThreadPool
0x18000edad  mov     rax, [rcx]
0x18000edb0  mov     rdx, [rdi+198h]
0x18000edb7  mov     rax, [rax+60h]
0x18000edbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edc0  mov     [rdi+198h], rbp
0x18000edc7  mov     rcx, rdi
0x18000edca  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAudioProcess@@UIAudioProcessInternal@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAudioProcess,IAudioProcessInternal>::Release(void)
0x18000edcf  test    rbx, rbx
0x18000edd2  jz      short loc_18000EDDD
0x18000edd4  mov     rcx, rbx; lpCriticalSection
0x18000edd7  call    cs:__imp_LeaveCriticalSection
0x18000eddd  mov     rcx, [rdi+2F8h]
0x18000ede4  test    rcx, rcx
0x18000ede7  jz      short loc_18000EE11
0x18000ede9  mov     rdx, [rdi+308h]
0x18000edf0  sub     rdx, rcx
0x18000edf3  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000edf7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000edfc  mov     [rdi+2F8h], rbp
0x18000ee03  mov     [rdi+300h], rbp
0x18000ee0a  mov     [rdi+308h], rbp
0x18000ee11  lea     rcx, [rdi+2C8h]; lpCriticalSection
0x18000ee18  call    cs:__imp_DeleteCriticalSection
0x18000ee1e  lea     rcx, [rdi+2C0h]
0x18000ee25  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18000ee2a  lea     rcx, [rdi+278h]
0x18000ee31  call    ?RemoveAll@?$CAtlMap@PEAUIUnknown@@V?$com_ptr_t@UIAudioProcessNotification@@Uerr_returncode_policy@wil@@@wil@@V?$CElementTraits@PEAUIUnknown@@@ATL@@V?$CElementTraits@V?$com_ptr_t@UIAudioProcessNotification@@Uerr_returncode_policy@wil@@@wil@@@5@@ATL@@QEAAXXZ; ATL::CAtlMap<IUnknown *,wil::com_ptr_t<IAudioProcessNotification,wil::err_returncode_policy>,ATL::CElementTraits<IUnknown *>,ATL::CElementTraits<wil::com_ptr_t<IAudioProcessNotification,wil::err_returncode_policy>>>::RemoveAll(void)
0x18000ee36  lea     rcx, [rdi+250h]; lpCriticalSection
0x18000ee3d  call    cs:__imp_DeleteCriticalSection
0x18000ee43  lea     rcx, [rdi+240h]
0x18000ee4a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000ee4f  lea     rcx, [rdi+218h]; lpCriticalSection
0x18000ee56  call    cs:__imp_DeleteCriticalSection
0x18000ee5c  mov     rcx, rbx; lpCriticalSection
0x18000ee5f  call    cs:__imp_DeleteCriticalSection
0x18000ee65  lea     rcx, [rdi+140h]; lpCriticalSection
0x18000ee6c  call    cs:__imp_DeleteCriticalSection
0x18000ee72  lea     rbx, [rdi+128h]
0x18000ee79  cmp     [rdi+118h], rbp
0x18000ee80  jz      short loc_18000EEB5
0x18000ee82  mov     esi, ebp
0x18000ee84  cmp     [rbx], ebp
0x18000ee86  jle     short loc_18000EEA1
0x18000ee88  movsxd  rcx, esi
0x18000ee8b  shl     rcx, 5
0x18000ee8f  add     rcx, [rdi+118h]
0x18000ee96  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ee9b  inc     esi
0x18000ee9d  cmp     esi, [rbx]
0x18000ee9f  jl      short loc_18000EE88
0x18000eea1  mov     rcx, [rdi+118h]; Block
0x18000eea8  call    cs:__imp_free
0x18000eeae  mov     [rdi+118h], rbp
0x18000eeb5  mov     rcx, [rdi+120h]; Block
0x18000eebc  test    rcx, rcx
0x18000eebf  jz      short loc_18000EECE
0x18000eec1  call    cs:__imp_free
0x18000eec7  mov     [rdi+120h], rbp
0x18000eece  mov     [rbx], ebp
0x18000eed0  lea     rbx, [rdi+110h]
0x18000eed7  cmp     [rdi+100h], rbp
0x18000eede  jz      short loc_18000EF13
0x18000eee0  mov     esi, ebp
0x18000eee2  cmp     [rbx], ebp
0x18000eee4  jle     short loc_18000EEFF
0x18000eee6  movsxd  rcx, esi
0x18000eee9  shl     rcx, 5
0x18000eeed  add     rcx, [rdi+100h]
0x18000eef4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000eef9  inc     esi
0x18000eefb  cmp     esi, [rbx]
0x18000eefd  jl      short loc_18000EEE6
0x18000eeff  mov     rcx, [rdi+100h]; Block
0x18000ef06  call    cs:__imp_free
0x18000ef0c  mov     [rdi+100h], rbp
0x18000ef13  mov     rcx, [rdi+108h]; Block
0x18000ef1a  test    rcx, rcx
0x18000ef1d  jz      short loc_18000EF2C
0x18000ef1f  call    cs:__imp_free
0x18000ef25  mov     [rdi+108h], rbp
0x18000ef2c  mov     [rbx], ebp
0x18000ef2e  lea     rcx, [rdi+0F8h]
0x18000ef35  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18000ef3a  lea     rcx, [rdi+0F0h]
0x18000ef41  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18000ef46  mov     rcx, [rdi+0E0h]
0x18000ef4d  test    rcx, rcx
0x18000ef50  jz      short loc_18000EF57
0x18000ef52  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000ef57  mov     rcx, [rdi+0C8h]; pv
0x18000ef5e  test    rcx, rcx
0x18000ef61  jz      short loc_18000EF69
0x18000ef63  call    cs:__imp_CoTaskMemFree
0x18000ef69  mov     rcx, [rdi+0B8h]; pv
0x18000ef70  test    rcx, rcx
0x18000ef73  jz      short loc_18000EF7B
0x18000ef75  call    cs:__imp_CoTaskMemFree
0x18000ef7b  mov     rcx, [rdi+0B0h]; pv
0x18000ef82  test    rcx, rcx
0x18000ef85  jz      short loc_18000EF8D
0x18000ef87  call    cs:__imp_CoTaskMemFree
0x18000ef8d  mov     rcx, [rdi+0A8h]; pv
0x18000ef94  test    rcx, rcx
0x18000ef97  jz      short loc_18000EF9F
0x18000ef99  call    cs:__imp_CoTaskMemFree
0x18000ef9f  lea     rcx, [rdi+98h]
0x18000efa6  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000efab  mov     rcx, [rdi+80h]
0x18000efb2  test    rcx, rcx
0x18000efb5  jz      short loc_18000F00B
0x18000efb7  mov     rdx, [rdi+90h]
0x18000efbe  sub     rdx, rcx
0x18000efc1  and     rdx, 0FFFFFFFFFFFFFFFCh
0x18000efc5  mov     [rsp+38h+arg_0], rdx
0x18000efca  mov     [rsp+38h+arg_8], rcx
0x18000efcf  cmp     rdx, 1000h
0x18000efd6  jb      short loc_18000EFF1
0x18000efd8  lea     rdx, [rsp+38h+arg_0]; unsigned __int64 *
0x18000efdd  lea     rcx, [rsp+38h+arg_8]; void **
0x18000efe2  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18000efe7  mov     rdx, [rsp+38h+arg_0]; struct std::nothrow_t *
0x18000efec  mov     rcx, [rsp+38h+arg_8]; void *
0x18000eff1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000eff6  mov     [rdi+80h], rbp
0x18000effd  mov     [rdi+88h], rbp
0x18000f004  mov     [rdi+90h], rbp
0x18000f00b  lea     rcx, [rdi+40h]
0x18000f00f  call    ??1?$_Hash@V?$_Umap_traits@PEAXV?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@std@@V?$allocator@U?$pair@QEAXV?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<void *,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>>,0>>::~_Hash<std::_Umap_traits<void *,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>>,0>>(void)
0x18000f014  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000f018  call    cs:__imp_DeleteCriticalSection
0x18000f01e  mov     dword ptr [rdi+14h], 0C0000001h
0x18000f025  mov     rbx, [rsp+38h+arg_10]
0x18000f02a  add     rsp, 20h
0x18000f02e  pop     rdi
0x18000f02f  pop     rsi
0x18000f030  pop     rbp
0x18000f031  retn
```
