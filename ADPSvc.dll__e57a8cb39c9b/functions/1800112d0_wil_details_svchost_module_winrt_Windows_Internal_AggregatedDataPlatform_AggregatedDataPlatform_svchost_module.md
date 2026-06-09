# wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::~svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>(void)

- ea: `0x1800112d0`
- end: `0x1800113ee`
- name: `??1?$svchost_module@UAggregatedDataPlatform@1Internal@Windows@winrt@@@details@wil@@QEAA@XZ`
- size: `286`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800113f4`
- `0x18001195c`
- `0x180011b50`

## callees

- `0x180002274`
- `0x180003a89`
- `0x1800112d0`
- `0x180011c3c`
- `0x180011e9c`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoRevokeActivationFactories` at `0x1800113c4`
- `api-ms-win-core-winrt-l1-1-0!RoRevokeActivationFactories` at `0x1800113c4`

## string_xrefs

- `0x180011358`: `onecore\internal\sdk\inc\wil\cppwinrtservice.h`

## pseudocode

```c
void __fastcall wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::~svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>(
        _QWORD *a1)
{
  PSLIST_ENTRY v2; // r8
  struct _SLIST_ENTRY *Next; // rsi
  struct _SLIST_ENTRY *v4; // r9
  __int128 v5; // rt0
  unsigned __int8 v6; // tt
  int v7; // eax
  __int128 v8; // [rsp+40h] [rbp-38h] BYREF
  int v9; // [rsp+50h] [rbp-28h] BYREF
  const char *v10; // [rsp+58h] [rbp-20h]
  __int64 v11; // [rsp+60h] [rbp-18h]
  _QWORD *v12; // [rsp+A0h] [rbp+28h] BYREF

  v2 = WINRT_IMPL_InterlockedFlushSList(&`winrt::impl::get_factory_cache'::`2'::cache);
  if ( v2 )
  {
    do
    {
      Next = v2->Next;
      v4 = v2[-1].Next;
      if ( v4 )
      {
        v5 = (unsigned __int64)v2[-1].Next;
        v6 = _InterlockedCompareExchange128((volatile signed __int64 *)&v2[-1], 0, 0, (signed __int64 *)&v5);
        v8 = v5;
        if ( v6 != 0 )
          ((void (__fastcall *)(struct _SLIST_ENTRY *))v4->Next[1].Next)(v4);
      }
      v2 = Next;
    }
    while ( Next );
  }
  v12 = a1;
  *(_QWORD *)&v8 = 0;
  *((_QWORD *)&v8 + 1) = &v12;
  v9 = 192;
  v10 = "onecore\\internal\\sdk\\inc\\wil\\cppwinrtservice.h";
  v11 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(), __int128 *, GUID *, int, _QWORD))(*(_QWORD *)*a1 + 24LL))(
         *a1,
         __lambda_invoker_cdecl___lambda_1___1____RunInContext_V_lambda_1___1__unregister_and_stop_and_wait___svchost_module_UAggregatedDataPlatform_1Internal_Windows_winrt___details_wil__AEAAXXZ____svchost_module_UAggregatedDataPlatform_1Internal_Windows_winrt___details_wil__AEAAX__QEAV1_1__unregister_and_stop_and_wait_234_AEAAXXZ__Z_SAJPEAUtagComCallData___Z,
         &v8,
         &IID_IContextCallback,
         5,
         0);
  if ( v7 < 0 )
    winrt::throw_hresult((unsigned int)v7, &v9);
  `eh vector destructor iterator'(
    a1 + 2,
    4u,
    1u,
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned long,long (*)(unsigned long),&long CoRevokeClassObject(unsigned long),wistd::integral_constant<unsigned __int64,0>,unsigned long,unsigned long,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned long,long (*)(unsigned long),&long CoRevokeClassObject(unsigned long),wistd::integral_constant<unsigned __int64,0>,unsigned long,unsigned long,0,std::nullptr_t>>>);
  if ( a1[1] )
    RoRevokeActivationFactories();
  if ( *a1 )
    winrt::com_ptr<IContextCallback>::unconditional_release_ref(a1);
}

```

## disassembly

```asm
0x1800112d0  push    rbp
0x1800112d2  push    rbx
0x1800112d3  push    rsi
0x1800112d4  push    rdi
0x1800112d5  mov     rbp, rsp
0x1800112d8  sub     rsp, 78h
0x1800112dc  mov     rdi, rcx
0x1800112df  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800112e6  call    WINRT_IMPL_InterlockedFlushSList
0x1800112eb  mov     r8, rax
0x1800112ee  test    rax, rax
0x1800112f1  jz      short loc_18001133D
0x1800112f3  mov     rsi, [r8]
0x1800112f6  mov     r9, [r8-10h]
0x1800112fa  nop
0x1800112fb  test    r9, r9
0x1800112fe  jz      short loc_180011335
0x180011300  mov     [rbp+var_38], r9
0x180011304  xor     edx, edx
0x180011306  mov     [rbp+var_30], rdx
0x18001130a  xor     ecx, ecx
0x18001130c  xor     ebx, ebx
0x18001130e  mov     rax, r9
0x180011311  lock cmpxchg16b xmmword ptr [r8-10h]
0x180011317  mov     [rbp+var_38], rax
0x18001131b  mov     [rbp+var_30], rdx
0x18001131f  setz    al
0x180011322  cmp     al, 1
0x180011324  jnz     short loc_180011335
0x180011326  mov     rax, [r9]
0x180011329  mov     rcx, r9
0x18001132c  mov     rax, [rax+10h]
0x180011330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011335  mov     r8, rsi
0x180011338  test    rsi, rsi
0x18001133b  jnz     short loc_1800112F3
0x18001133d  mov     [rbp+arg_0], rdi
0x180011341  mov     [rbp+var_38], 0
0x180011349  lea     rax, [rbp+arg_0]
0x18001134d  mov     [rbp+var_30], rax
0x180011351  mov     [rbp+var_28], 0C0h
0x180011358  lea     rax, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\cppwi"...
0x18001135f  mov     [rbp+var_20], rax
0x180011363  mov     [rbp+var_18], 0
0x18001136b  mov     rcx, [rdi]
0x18001136e  mov     rax, [rcx]
0x180011371  mov     [rsp+78h+var_50], 0
0x18001137a  mov     [rsp+78h+var_58], 5
0x180011382  lea     r9, IID_IContextCallback
0x180011389  lea     r8, [rbp+var_38]
0x18001138d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$RunInContext@V_lambda_1_@?1??unregister_and_stop_and_wait@?$svchost_module@UAggregatedDataPlatform@1Internal@Windows@winrt@@@details@wil@@AEAAXXZ@@?$svchost_module@UAggregatedDataPlatform@1Internal@Windows@winrt@@@details@wil@@AEAAX$$QEAV1?1??unregister_and_stop_and_wait@234@AEAAXXZ@@Z@SAJPEAUtagComCallData@@@Z; `wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::RunInContext<`wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::unregister_and_stop_and_wait(void)'::`2'::_lambda_1_>(`wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::unregister_and_stop_and_wait(void)'::`2'::_lambda_1_ &&)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(tagComCallData *)
0x180011394  mov     rax, [rax+18h]
0x180011398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001139d  test    eax, eax
0x18001139f  js      short loc_1800113E2
0x1800113a1  lea     rcx, [rdi+10h]; void *
0x1800113a5  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@KP6AJK@Z$1?CoRevokeClassObject@@YAJK@ZU?$integral_constant@_K$0A@@wistd@@KK$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x1800113ac  mov     edx, 4; unsigned __int64
0x1800113b1  lea     r8d, [rdx-3]; unsigned __int64
0x1800113b5  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800113ba  nop
0x1800113bb  mov     rcx, [rdi+8]
0x1800113bf  test    rcx, rcx
0x1800113c2  jz      short loc_1800113CA
0x1800113c4  call    cs:__imp_RoRevokeActivationFactories
0x1800113ca  cmp     qword ptr [rdi], 0
0x1800113ce  jz      short loc_1800113D9
0x1800113d0  mov     rcx, rdi
0x1800113d3  call    ?unconditional_release_ref@?$com_ptr@UIContextCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IContextCallback>::unconditional_release_ref(void)
0x1800113d8  nop
0x1800113d9  add     rsp, 78h
0x1800113dd  pop     rdi
0x1800113de  pop     rsi
0x1800113df  pop     rbx
0x1800113e0  pop     rbp
0x1800113e1  retn
0x1800113e2  lea     rdx, [rbp+var_28]
0x1800113e6  mov     ecx, eax
0x1800113e8  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
