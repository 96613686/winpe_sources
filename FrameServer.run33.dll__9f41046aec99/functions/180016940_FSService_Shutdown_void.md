# FSService::Shutdown(void)

- ea: `0x180016940`
- end: `0x180016e30`
- name: `?Shutdown@FSService@@UEAAJXZ`
- size: `1264`
- prototype: `__int64 __fastcall(FSService *__hidden this)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000157c`
- `0x18000162c`
- `0x180009494`
- `0x1800095c8`
- `0x180009608`
- `0x18000a6b0`
- `0x18000a8e4`
- `0x180014f08`
- `0x180014f60`
- `0x1800168d8`
- `0x180016940`
- `0x1800176b4`
- `0x18001794c`
- `0x180017b60`
- `0x18001807c`
- `0x1800547bc`
- `0x180054840`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180016b63`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180016b63`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180016a85`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180016a85`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016a7c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016a7c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016a51`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016a51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016b8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016c95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016b8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016c95`
- `RPCRT4!RpcEpUnregister` at `0x180016a9e`
- `RPCRT4!RpcEpUnregister` at `0x180016a9e`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x180016ab0`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x180016ab0`
- `RPCRT4!RpcBindingVectorFree` at `0x180016aba`
- `RPCRT4!RpcBindingVectorFree` at `0x180016aba`
- `MFPlat!MFCancelWorkItem` at `0x180016a17`
- `MFPlat!MFCancelWorkItem` at `0x180016a30`
- `MFPlat!MFCancelWorkItem` at `0x180016a17`
- `MFPlat!MFCancelWorkItem` at `0x180016a30`
- `MFPlat!MFUnregisterPlatformFromMMCSS` at `0x180016c50`
- `MFPlat!MFUnregisterPlatformFromMMCSS` at `0x180016c50`
- `MFPlat!MFUnlockWorkQueue` at `0x180016c67`
- `MFPlat!MFUnlockWorkQueue` at `0x180016c7d`
- `MFPlat!MFUnlockWorkQueue` at `0x180016c67`
- `MFPlat!MFUnlockWorkQueue` at `0x180016c7d`

## pseudocode

```c
__int64 __fastcall FSService::Shutdown(HANDLE *this)
{
  unsigned int v1; // r15d
  RPC_BINDING_VECTOR *v3; // rax
  struct _TP_TIMER *v4; // r14
  MFWORKITEM_KEY v5; // rcx
  MFWORKITEM_KEY v6; // rcx
  struct _TP_TIMER *v7; // rcx
  HANDLE v8; // rcx
  HANDLE v9; // rcx
  HANDLE v10; // rcx
  HANDLE v11; // rcx
  unsigned int v12; // r14d
  char *v13; // rdi
  __int64 v14; // rcx
  unsigned int v15; // r15d
  __int64 v16; // r14
  char *v17; // rdi
  __int64 v18; // rcx
  HANDLE v19; // rcx
  DWORD v20; // ecx
  DWORD v21; // ecx
  HANDLE v22; // rcx
  HANDLE v23; // rcx
  unsigned int v24; // r15d
  unsigned int v25; // r14d
  char *v26; // rdi
  __int64 v27; // rcx
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  __int64 v32; // [rsp+50h] [rbp-28h] BYREF
  __int64 v33; // [rsp+58h] [rbp-20h] BYREF
  char *v34; // [rsp+60h] [rbp-18h] BYREF
  __int64 v35; // [rsp+C0h] [rbp+48h] BYREF
  int v36; // [rsp+C8h] [rbp+50h] BYREF
  int v37; // [rsp+D0h] [rbp+58h] BYREF
  RPC_BINDING_VECTOR *BindingVector; // [rsp+D8h] [rbp+60h] BYREF

  v1 = 0;
  BindingVector = 0;
  v32 = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 143, &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids, this);
  CFSLock::Lock((CFSLock *)(this + 8), this, -2147023436, 0, 0);
  if ( *((_DWORD *)this + 244) == 3 )
  {
    CFSLock::Unlock((CFSLock *)(this + 8));
  }
  else
  {
    v3 = (RPC_BINDING_VECTOR *)this[119];
    *((_DWORD *)this + 244) = 3;
    BindingVector = v3;
    v4 = 0;
    this[119] = 0;
    v35 = 0;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
      &v32,
      this + 135);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
      this + 135,
      &v35);
    wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v35);
    v5 = (MFWORKITEM_KEY)this[123];
    if ( v5 )
    {
      MFCancelWorkItem(v5);
      this[123] = 0;
    }
    v6 = (MFWORKITEM_KEY)this[129];
    if ( v6 )
    {
      MFCancelWorkItem(v6);
      this[129] = 0;
    }
    v7 = (struct _TP_TIMER *)this[136];
    if ( v7 )
    {
      SetThreadpoolTimer(v7, 0, 0, 0);
      v4 = (struct _TP_TIMER *)this[136];
      this[136] = 0;
    }
    CFSLock::Unlock((CFSLock *)(this + 8));
    if ( v4 )
    {
      WaitForThreadpoolTimerCallbacks(v4, 1);
      CloseThreadpoolTimer(v4);
    }
    if ( BindingVector )
    {
      RpcEpUnregister(&unk_1800EFFA0, BindingVector, 0);
      RpcServerUnregisterIfEx(&unk_1800EFFA0, 0, 1);
      RpcBindingVectorFree(&BindingVector);
    }
    v8 = this[138];
    if ( v8 )
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v8 + 24LL))(v8);
    v9 = this[137];
    if ( v9 )
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v9 + 24LL))(v9);
    v10 = this[139];
    if ( v10 )
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v10 + 24LL))(v10);
    wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(
      &v32,
      0);
    if ( this[134] )
    {
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
        WPP_SF_qq(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          144,
          &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids,
          this,
          this[134]);
      WaitForSingleObject(this[134], 0x7530u);
    }
    CFSLock::Lock((CFSLock *)(this + 8), this, -1072869852, 0, 0);
    v11 = this[134];
    if ( v11 )
    {
      CloseHandle(v11);
      this[134] = 0;
    }
    v12 = *((_DWORD *)this + 220);
    if ( v12 )
    {
      do
      {
        v13 = (char *)(this + 109);
        v14 = *((_QWORD *)this[109] + v1);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 280LL))(v14);
        ++v1;
      }
      while ( v1 < v12 );
    }
    else
    {
      v13 = (char *)(this + 109);
    }
    CTUnkArray<IFSMemStream>::RemoveAll(v13);
    v15 = *((_DWORD *)this + 226);
    v16 = 0;
    if ( v15 )
    {
      do
      {
        v17 = (char *)(this + 112);
        v18 = *((_QWORD *)this[112] + v16);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 120LL))(v18);
        v16 = (unsigned int)(v16 + 1);
      }
      while ( (unsigned int)v16 < v15 );
    }
    else
    {
      v17 = (char *)(this + 112);
    }
    CTUnkArray<IFSMemStream>::RemoveAll(v17);
    v19 = this[148];
    if ( v19 )
    {
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v19 + 40LL))(v19);
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(this + 148);
    }
    if ( *((_BYTE *)this + 960) )
    {
      MFUnregisterPlatformFromMMCSS();
      *((_BYTE *)this + 960) = 0;
    }
    v20 = *((_DWORD *)this + 242);
    if ( v20 )
    {
      MFUnlockWorkQueue(v20);
      *((_DWORD *)this + 242) = 0;
    }
    v21 = *((_DWORD *)this + 241);
    if ( v21 )
    {
      MFUnlockWorkQueue(v21);
      *((_DWORD *)this + 241) = 0;
    }
    v22 = this[125];
    if ( v22 )
    {
      CloseHandle(v22);
      this[125] = 0;
    }
    utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::clear(this + 115);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(this + 138);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(this + 137);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(this + 139);
    v23 = this[118];
    this[118] = 0;
    if ( v23 )
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v23 + 16LL))(v23);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraTelemetryTracking>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CameraTelemetryTracking>::GetImpl'::`2'::impl) )
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(this + 149);
    v24 = *((_DWORD *)this + 254);
    v25 = 0;
    if ( v24 )
    {
      do
      {
        v26 = (char *)(this + 126);
        v27 = *((_QWORD *)this[126] + v25);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 40LL))(v27);
        ++v25;
      }
      while ( v25 < v24 );
    }
    else
    {
      v26 = (char *)(this + 126);
    }
    CTUnkArray<IFSSourceIdentity>::RemoveAll(v26);
    if ( dword_18010C208 && (unsigned __int8)tlgKeywordOn(&dword_18010C208, 0x400000000000LL) )
    {
      v36 = *((_DWORD *)this + 264);
      v37 = *((_DWORD *)this + 263);
      v34 = (char *)this + 44;
      LODWORD(v35) = 0;
      v33 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v28,
        (unsigned int)&unk_180102A31,
        v29,
        v30,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v37,
        (__int64)&v36,
        (__int64)&v35);
    }
    CFSLock::Unlock((CFSLock *)(this + 8));
    AutoMF::Shutdown((AutoMF *)(this + 150));
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 145, &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids, this, 0);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v32);
  return 0;
}

```

## disassembly

```asm
0x180016940  push    rbp
0x180016942  push    rbx
0x180016943  push    rsi
0x180016944  push    rdi
0x180016945  push    r12
0x180016947  push    r13
0x180016949  push    r14
0x18001694b  push    r15
0x18001694d  mov     rbp, rsp
0x180016950  sub     rsp, 78h
0x180016954  xor     r15d, r15d
0x180016957  mov     rsi, rcx
0x18001695a  mov     [rbp+BindingVector], r15
0x18001695e  mov     [rbp+var_28], r15
0x180016962  cmp     cs:byte_18010EC4D, 8
0x180016969  jb      short loc_18001698D
0x18001696b  mov     r9, rcx
0x18001696e  lea     r8, WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids
0x180016975  mov     rcx, cs:WPP_GLOBAL_Control
0x18001697c  mov     edx, 8Fh
0x180016981  mov     rcx, [rcx+0D8h]
0x180016988  call    WPP_SF_q
0x18001698d  lea     rbx, [rsi+40h]
0x180016991  mov     [rsp+78h+var_58], r15; unsigned __int64 *
0x180016996  mov     rcx, rbx; this
0x180016999  xor     r9d, r9d; unsigned int
0x18001699c  mov     r8d, 800705B4h; int
0x1800169a2  mov     rdx, rsi; void *
0x1800169a5  call    ?Lock@CFSLock@@QEAAXPEAXJKPEA_K@Z; CFSLock::Lock(void *,long,ulong,unsigned __int64 *)
0x1800169aa  cmp     dword ptr [rsi+3D0h], 3
0x1800169b1  jnz     short loc_1800169C0
0x1800169b3  mov     rcx, rbx; this
0x1800169b6  call    ?Unlock@CFSLock@@QEAAXXZ; CFSLock::Unlock(void)
0x1800169bb  jmp     loc_180016DE4
0x1800169c0  mov     rax, [rsi+3B8h]
0x1800169c7  lea     rdi, [rsi+438h]
0x1800169ce  mov     rdx, rdi
0x1800169d1  mov     dword ptr [rsi+3D0h], 3
0x1800169db  lea     rcx, [rbp+var_28]
0x1800169df  mov     [rbp+BindingVector], rax
0x1800169e3  mov     r14, r15
0x1800169e6  mov     [rsi+3B8h], r15
0x1800169ed  mov     [rbp+arg_0], r15
0x1800169f1  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x1800169f6  lea     rdx, [rbp+arg_0]
0x1800169fa  mov     rcx, rdi
0x1800169fd  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x180016a02  lea     rcx, [rbp+arg_0]
0x180016a06  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x180016a0b  mov     rcx, [rsi+3D8h]; Key
0x180016a12  test    rcx, rcx
0x180016a15  jz      short loc_180016A24
0x180016a17  call    cs:__imp_MFCancelWorkItem
0x180016a1d  mov     [rsi+3D8h], r15
0x180016a24  mov     rcx, [rsi+408h]; Key
0x180016a2b  test    rcx, rcx
0x180016a2e  jz      short loc_180016A3D
0x180016a30  call    cs:__imp_MFCancelWorkItem
0x180016a36  mov     [rsi+408h], r15
0x180016a3d  mov     rcx, [rsi+440h]; pti
0x180016a44  test    rcx, rcx
0x180016a47  jz      short loc_180016A65
0x180016a49  xor     r9d, r9d; msWindowLength
0x180016a4c  xor     r8d, r8d; msPeriod
0x180016a4f  xor     edx, edx; pftDueTime
0x180016a51  call    cs:__imp_SetThreadpoolTimer
0x180016a57  mov     r14, [rsi+440h]
0x180016a5e  mov     [rsi+440h], r15
0x180016a65  mov     rcx, rbx; this
0x180016a68  call    ?Unlock@CFSLock@@QEAAXXZ; CFSLock::Unlock(void)
0x180016a6d  mov     edi, 1
0x180016a72  test    r14, r14
0x180016a75  jz      short loc_180016A8B
0x180016a77  mov     edx, edi; fCancelPendingCallbacks
0x180016a79  mov     rcx, r14; pti
0x180016a7c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180016a82  mov     rcx, r14; pti
0x180016a85  call    cs:__imp_CloseThreadpoolTimer
0x180016a8b  mov     rdx, [rbp+BindingVector]; BindingVector
0x180016a8f  test    rdx, rdx
0x180016a92  jz      short loc_180016AC0
0x180016a94  xor     r8d, r8d; UuidVector
0x180016a97  lea     rcx, unk_1800EFFA0; IfSpec
0x180016a9e  call    cs:__imp_RpcEpUnregister
0x180016aa4  mov     r8d, edi; RundownContextHandles
0x180016aa7  lea     rcx, unk_1800EFFA0; IfSpec
0x180016aae  xor     edx, edx; MgrTypeUuid
0x180016ab0  call    cs:__imp_RpcServerUnregisterIfEx
0x180016ab6  lea     rcx, [rbp+BindingVector]; BindingVector
0x180016aba  call    cs:__imp_RpcBindingVectorFree
0x180016ac0  mov     rcx, [rsi+450h]
0x180016ac7  test    rcx, rcx
0x180016aca  jz      short loc_180016AD8
0x180016acc  mov     rax, [rcx]
0x180016acf  mov     rax, [rax+18h]
0x180016ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ad8  lea     r13, [rsi+448h]
0x180016adf  mov     rcx, [r13+0]
0x180016ae3  test    rcx, rcx
0x180016ae6  jz      short loc_180016AF4
0x180016ae8  mov     rax, [rcx]
0x180016aeb  mov     rax, [rax+18h]
0x180016aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016af4  lea     r12, [rsi+458h]
0x180016afb  mov     rcx, [r12]
0x180016aff  test    rcx, rcx
0x180016b02  jz      short loc_180016B10
0x180016b04  mov     rax, [rcx]
0x180016b07  mov     rax, [rax+18h]
0x180016b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b10  xor     edx, edx
0x180016b12  lea     rcx, [rbp+var_28]
0x180016b16  call    ?reset@?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUwnf_subscription_state_base@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(wil::details::wnf_subscription_state_base *)
0x180016b1b  mov     rax, [rsi+430h]
0x180016b22  test    rax, rax
0x180016b25  jz      short loc_180016B69
0x180016b27  cmp     cs:byte_18010EC4D, 8
0x180016b2e  jb      short loc_180016B57
0x180016b30  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b37  lea     r8, WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids
0x180016b3e  mov     edx, 90h
0x180016b43  mov     [rsp+78h+var_58], rax
0x180016b48  mov     r9, rsi
0x180016b4b  mov     rcx, [rcx+0D8h]
0x180016b52  call    WPP_SF_qq
0x180016b57  mov     rcx, [rsi+430h]; hHandle
0x180016b5e  mov     edx, 7530h; dwMilliseconds
0x180016b63  call    cs:__imp_WaitForSingleObject
0x180016b69  xor     r9d, r9d; unsigned int
0x180016b6c  mov     [rsp+78h+var_58], r15; unsigned __int64 *
0x180016b71  mov     r8d, 0C00D4E24h; int
0x180016b77  mov     rdx, rsi; void *
0x180016b7a  mov     rcx, rbx; this
0x180016b7d  call    ?Lock@CFSLock@@QEAAXPEAXJKPEA_K@Z; CFSLock::Lock(void *,long,ulong,unsigned __int64 *)
0x180016b82  mov     rcx, [rsi+430h]; hObject
0x180016b89  test    rcx, rcx
0x180016b8c  jz      short loc_180016B9B
0x180016b8e  call    cs:__imp_CloseHandle
0x180016b94  mov     [rsi+430h], r15
0x180016b9b  mov     r14d, [rsi+370h]
0x180016ba2  test    r14d, r14d
0x180016ba5  jz      short loc_180016BD1
0x180016ba7  lea     rdi, [rsi+368h]
0x180016bae  mov     ecx, r15d
0x180016bb1  mov     rax, [rdi]
0x180016bb4  mov     rcx, [rax+rcx*8]
0x180016bb8  mov     rax, [rcx]
0x180016bbb  mov     rax, [rax+118h]
0x180016bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bc7  inc     r15d
0x180016bca  cmp     r15d, r14d
0x180016bcd  jb      short loc_180016BA7
0x180016bcf  jmp     short loc_180016BD8
0x180016bd1  lea     rdi, [rsi+368h]
0x180016bd8  mov     rcx, rdi
0x180016bdb  call    ?RemoveAll@?$CTUnkArray@UIFSMemStream@@@@QEAAXXZ; CTUnkArray<IFSMemStream>::RemoveAll(void)
0x180016be0  mov     r15d, [rsi+388h]
0x180016be7  xor     r14d, r14d
0x180016bea  test    r15d, r15d
0x180016bed  jz      short loc_180016C13
0x180016bef  lea     rdi, [rsi+380h]
0x180016bf6  mov     rax, [rdi]
0x180016bf9  mov     rcx, [rax+r14*8]
0x180016bfd  mov     rax, [rcx]
0x180016c00  mov     rax, [rax+78h]
0x180016c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c09  inc     r14d
0x180016c0c  cmp     r14d, r15d
0x180016c0f  jb      short loc_180016BEF
0x180016c11  jmp     short loc_180016C1A
0x180016c13  lea     rdi, [rsi+380h]
0x180016c1a  mov     rcx, rdi
0x180016c1d  call    ?RemoveAll@?$CTUnkArray@UIFSMemStream@@@@QEAAXXZ; CTUnkArray<IFSMemStream>::RemoveAll(void)
0x180016c22  lea     rdi, [rsi+4A0h]
0x180016c29  mov     rcx, [rdi]
0x180016c2c  test    rcx, rcx
0x180016c2f  jz      short loc_180016C45
0x180016c31  mov     rax, [rcx]
0x180016c34  mov     rax, [rax+28h]
0x180016c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c3d  mov     rcx, rdi
0x180016c40  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180016c45  xor     edi, edi
0x180016c47  cmp     [rsi+3C0h], dil
0x180016c4e  jz      short loc_180016C5D
0x180016c50  call    cs:__imp_MFUnregisterPlatformFromMMCSS
0x180016c56  mov     [rsi+3C0h], dil
0x180016c5d  mov     ecx, [rsi+3C8h]; dwWorkQueue
0x180016c63  test    ecx, ecx
0x180016c65  jz      short loc_180016C73
0x180016c67  call    cs:__imp_MFUnlockWorkQueue
0x180016c6d  mov     [rsi+3C8h], edi
0x180016c73  mov     ecx, [rsi+3C4h]; dwWorkQueue
0x180016c79  test    ecx, ecx
0x180016c7b  jz      short loc_180016C89
0x180016c7d  call    cs:__imp_MFUnlockWorkQueue
0x180016c83  mov     [rsi+3C4h], edi
0x180016c89  mov     rcx, [rsi+3E8h]; hObject
0x180016c90  test    rcx, rcx
0x180016c93  jz      short loc_180016CA2
0x180016c95  call    cs:__imp_CloseHandle
0x180016c9b  mov     [rsi+3E8h], rdi
0x180016ca2  lea     rcx, [rsi+398h]
0x180016ca9  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAAXXZ; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::clear(void)
0x180016cae  lea     rcx, [rsi+450h]
0x180016cb5  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180016cba  mov     rcx, r13
0x180016cbd  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180016cc2  mov     rcx, r12
0x180016cc5  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180016cca  mov     rcx, [rsi+3B0h]
0x180016cd1  mov     [rsi+3B0h], rdi
0x180016cd8  test    rcx, rcx
0x180016cdb  jz      short loc_180016CE9
0x180016cdd  mov     rax, [rcx]
0x180016ce0  mov     rax, [rax+10h]
0x180016ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ce9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CameraTelemetryTracking@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CameraTelemetryTracking@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraTelemetryTracking> `wil::Feature<__WilFeatureTraits_Feature_CameraTelemetryTracking>::GetImpl(void)'::`2'::impl
0x180016cf0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CameraTelemetryTracking@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraTelemetryTracking>::__private_IsEnabled(void)
0x180016cf5  test    al, al
0x180016cf7  jz      short loc_180016D05
0x180016cf9  lea     rcx, [rsi+4A8h]
0x180016d00  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180016d05  mov     r15d, [rsi+3F8h]
0x180016d0c  mov     r14d, edi
0x180016d0f  test    r15d, r15d
0x180016d12  jz      short loc_180016D3B
0x180016d14  lea     rdi, [rsi+3F0h]
0x180016d1b  mov     ecx, r14d
0x180016d1e  mov     rax, [rdi]
0x180016d21  mov     rcx, [rax+rcx*8]
0x180016d25  mov     rax, [rcx]
0x180016d28  mov     rax, [rax+28h]
0x180016d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d31  inc     r14d
0x180016d34  cmp     r14d, r15d
0x180016d37  jb      short loc_180016D14
0x180016d39  jmp     short loc_180016D42
0x180016d3b  lea     rdi, [rsi+3F0h]
0x180016d42  mov     rcx, rdi
0x180016d45  call    ?RemoveAll@?$CTUnkArray@UIFSSourceIdentity@@@@QEAAXXZ; CTUnkArray<IFSSourceIdentity>::RemoveAll(void)
0x180016d4a  mov     eax, cs:dword_18010C208
0x180016d50  xor     r15d, r15d
0x180016d53  test    eax, eax
0x180016d55  jz      short loc_180016DD0
0x180016d57  mov     rdx, 400000000000h
0x180016d61  lea     rcx, dword_18010C208
0x180016d68  call    _tlgKeywordOn
0x180016d6d  test    al, al
0x180016d6f  jz      short loc_180016DD0
0x180016d71  mov     eax, [rsi+420h]
0x180016d77  lea     rdx, unk_180102A31
0x180016d7e  mov     [rbp+arg_8], eax
0x180016d81  mov     eax, [rsi+41Ch]
0x180016d87  mov     [rbp+arg_10], eax
0x180016d8a  lea     rax, [rsi+2Ch]
0x180016d8e  mov     [rbp+var_18], rax
0x180016d92  lea     rax, [rbp+arg_0]
0x180016d96  mov     [rsp+78h+var_38], rax
0x180016d9b  lea     rax, [rbp+arg_8]
0x180016d9f  mov     [rsp+78h+var_40], rax
0x180016da4  lea     rax, [rbp+arg_10]
0x180016da8  mov     [rsp+78h+var_48], rax
0x180016dad  lea     rax, [rbp+var_20]
0x180016db1  mov     [rsp+78h+var_50], rax
0x180016db6  lea     rax, [rbp+var_18]
0x180016dba  mov     [rsp+78h+var_58], rax
0x180016dbf  mov     dword ptr [rbp+arg_0], r15d
0x180016dc3  mov     [rbp+var_20], 3000000h
0x180016dcb  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180016dd0  mov     rcx, rbx; this
0x180016dd3  call    ?Unlock@CFSLock@@QEAAXXZ; CFSLock::Unlock(void)
0x180016dd8  lea     rcx, [rsi+4B0h]; this
0x180016ddf  call    ?Shutdown@AutoMF@@QEAAJXZ; AutoMF::Shutdown(void)
0x180016de4  cmp     cs:byte_18010EC4D, 8
0x180016deb  jb      short loc_180016E14
0x180016ded  mov     rcx, cs:WPP_GLOBAL_Control
0x180016df4  lea     r8, WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids
0x180016dfb  mov     edx, 91h
0x180016e00  mov     dword ptr [rsp+78h+var_58], r15d
0x180016e05  mov     r9, rsi
0x180016e08  mov     rcx, [rcx+0D8h]
0x180016e0f  call    WPP_SF_qD
0x180016e14  lea     rcx, [rbp+var_28]
0x180016e18  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x180016e1d  xor     eax, eax
0x180016e1f  add     rsp, 78h
0x180016e23  pop     r15
0x180016e25  pop     r14
0x180016e27  pop     r13
0x180016e29  pop     r12
0x180016e2b  pop     rdi
0x180016e2c  pop     rsi
0x180016e2d  pop     rbx
0x180016e2e  pop     rbp
0x180016e2f  retn
```
