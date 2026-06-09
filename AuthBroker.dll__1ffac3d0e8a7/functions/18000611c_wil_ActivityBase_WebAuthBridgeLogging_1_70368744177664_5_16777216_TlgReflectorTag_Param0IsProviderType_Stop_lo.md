# wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000611c`
- end: `0x1800061f2`
- name: `?Stop@?$ActivityBase@VWebAuthBridgeLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `214`
- prototype: `void __fastcall(wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> *this, HRESULT hr)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800054bc`
- `0x180019484`

## callees

- `0x1800011b4`
- `0x180001a50`
- `0x18000611c`
- `0x1800066b4`
- `0x180018f40`
- `0x1800197e4`
- `0x180019e08`
- `0x18001adcc`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006194`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006194`

## pseudocode

```c
void __fastcall wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> *this,
        HRESULT hr)
{
  bool v4; // bl
  const _tlgProvider_t *v5; // rax
  const _tlgProvider_t *v6; // rbx
  DWORD CurrentThreadId; // eax
  wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WebAuthBridgeLogging,_TlgReflectorTag_Param0IsProviderType> *m_pActivityData; // r8
  const _GUID *v9; // r9
  HRESULT hrLocal; // [rsp+60h] [rbp+8h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (__cdecl*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive,wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t> > > lock; // [rsp+70h] [rbp+18h] BYREF
  _tlgWrapperByVal<8> v12; // [rsp+78h] [rbp+20h] BYREF

  hrLocal = 0;
  wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &lock);
  v4 = wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WebAuthBridgeLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         this->m_pActivityData,
         hr,
         &hrLocal);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lock);
  if ( v4 )
  {
    this->StopActivity(this);
  }
  else
  {
    v5 = WebAuthBridgeLogging::Provider();
    v6 = v5;
    if ( v5->LevelPlus1 > 5 && tlgKeywordOn(v5, 0x400000000000uLL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      m_pActivityData = this->m_pActivityData;
      hrLocal = CurrentThreadId;
      LODWORD(lock.m_ptr) = hr;
      v12.Value = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        &`wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop'::`12'::_tlgEvent._tlgChannel,
        &m_pActivityData->m_Id,
        v9,
        &v12,
        (const _tlgWrapperByVal<4> *)&lock,
        (const _tlgWrapperByVal<4> *)&hrLocal);
    }
  }
  wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x18000611c  push    rbx
0x18000611e  push    rsi
0x18000611f  push    rdi
0x180006120  sub     rsp, 40h
0x180006124  mov     esi, hr
0x180006126  mov     [rsp+58h+hrLocal], 0
0x18000612e  lea     rdx, [rsp+58h+lock]; result
0x180006133  mov     rdi, this
0x180006136  call    ?LockExclusive@?$ActivityBase@VWebAuthBridgeLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000613b  mov     this, [rdi+110h]; this
0x180006142  lea     r8, [rsp+58h+hrLocal]; phr
0x180006147  mov     hr, esi; hr
0x180006149  call    ?SetStopResult@?$ActivityData@VWebAuthBridgeLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWebAuthBridgeLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WebAuthBridgeLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18000614e  lea     this, [rsp+58h+lock]; this
0x180006153  mov     bl, al
0x180006155  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000615a  test    bl, bl
0x18000615c  jz      short loc_18000616F
0x18000615e  mov     rax, [rdi]
0x180006161  mov     this, rdi
0x180006164  mov     rax, [rax+8]
0x180006168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000616d  jmp     short loc_1800061E3
0x18000616f  call    ?Provider@WebAuthBridgeLogging@@SAPEBU_tlgProvider_t@@XZ; WebAuthBridgeLogging::Provider(void)
0x180006174  mov     rbx, rax
0x180006177  mov     ecx, [rax]
0x180006179  cmp     ecx, 5
0x18000617c  jbe     short loc_1800061E3
0x18000617e  mov     rdx, 400000000000h; keyword
0x180006188  mov     this, rax; hProvider
0x18000618b  call    _tlgKeywordOn
0x180006190  test    al, al
0x180006192  jz      short loc_1800061E3
0x180006194  call    cs:__imp_GetCurrentThreadId; __annotation("_TlgWrite:|936|TraceLoggingType::Provider()|("ActivityIntermediateStop")=|"PartA_PrivTags"=|"wilActivity"=|"hresult"=Failure error code|"threadId"=Identifier of the thread the activity was run on")
0x18000619a  mov     r8, [rdi+110h]
0x1800061a1  lea     rdx, ?_tlgEvent@?M@??Stop@?$ActivityBase@VWebAuthBridgeLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z@4U_unnamed_type__tlgEvent_@?M@??123@QEAAXJ@Z@B._tlgChannel; pEventMetadata
0x1800061a8  mov     [rsp+58h+hrLocal], eax
0x1800061ac  add     r8, 8; <writerArgs_0>
0x1800061b0  lea     rax, [rsp+58h+hrLocal]
0x1800061b5  mov     dword ptr [rsp+58h+lock.m_ptr], esi
0x1800061b9  mov     [rsp+58h+hProvider], rax; hProvider
0x1800061be  mov     this, rbx; hProvider
0x1800061c1  lea     rax, [rsp+58h+lock]
0x1800061c6  mov     [rsp+58h+arg_18.Value], 1000000h
0x1800061cf  mov     [rsp+58h+var_30], rax; <wrappedArgs_2>
0x1800061d4  lea     rax, [rsp+58h+arg_18]
0x1800061d9  mov     [rsp+58h+var_38], rax; <wrappedArgs_1>
0x1800061de  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800061e3  mov     this, rdi
0x1800061e6  add     rsp, 40h
0x1800061ea  pop     rdi
0x1800061eb  pop     rsi
0x1800061ec  pop     rbx
0x1800061ed  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWebAuthBridgeLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
