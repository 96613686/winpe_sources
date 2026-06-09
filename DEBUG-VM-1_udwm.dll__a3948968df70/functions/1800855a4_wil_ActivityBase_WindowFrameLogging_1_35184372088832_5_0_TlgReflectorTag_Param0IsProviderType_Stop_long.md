# wil::ActivityBase<WindowFrameLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x1800855a4`
- end: `0x180085685`
- name: `?Stop@?$ActivityBase@VWindowFrameLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `225`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180044c60`
- `0x1800850a0`
- `0x180085580`
- `0x180094c30`
- `0x1800a7510`

## callees

- `0x18005da8c`
- `0x18006125c`
- `0x180062e98`
- `0x180067450`
- `0x18006cadc`
- `0x180071570`
- `0x1800794cc`
- `0x1800855a4`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180085620`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180085620`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<WindowFrameLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // bl
  __int64 v3; // rdx
  __int64 v4; // rcx
  _DWORD *v5; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v7; // r8
  __int64 v8; // r9
  int v10; // [rsp+50h] [rbp+8h] BYREF
  DWORD v11; // [rsp+58h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF

  v11 = 0;
  wil::ActivityBase<WindowFrameLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v10);
  v2 = wil::ActivityBase<WindowFrameLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WindowFrameLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v11);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v5 = (_DWORD *)*((_QWORD *)wil::details::static_lazy<WindowFrameLogging>::get(v4, v3) + 1);
    if ( *v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v7 = a1[34];
      v11 = CurrentThreadId;
      v10 = 0;
      v12 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v5,
        byte_180100EEB,
        v7 + 8,
        v8,
        (__int64)&v12,
        (__int64)&v10,
        (__int64)&v11);
    }
  }
  return wil::ActivityBase<WindowFrameLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x1800855a4  mov     rax, rsp
0x1800855a7  mov     [rax+20h], rbx
0x1800855ab  mov     [rax+10h], edx
0x1800855ae  push    rdi
0x1800855af  sub     rsp, 40h
0x1800855b3  lea     rdx, [rax+8]
0x1800855b7  mov     dword ptr [rax+10h], 0
0x1800855be  mov     rdi, rcx
0x1800855c1  call    ?LockExclusive@?$ActivityBase@VWindowFrameLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WindowFrameLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800855c6  mov     rcx, [rdi+110h]
0x1800855cd  lea     r8, [rsp+48h+arg_8]
0x1800855d2  xor     edx, edx
0x1800855d4  call    ?SetStopResult@?$ActivityData@VWindowFrameLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWindowFrameLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<WindowFrameLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WindowFrameLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x1800855d9  lea     rcx, [rsp+48h+arg_0]
0x1800855de  mov     bl, al
0x1800855e0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800855e5  test    bl, bl
0x1800855e7  jz      short loc_1800855FA
0x1800855e9  mov     rax, [rdi]
0x1800855ec  mov     rcx, rdi
0x1800855ef  mov     rax, [rax+8]
0x1800855f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800855f8  jmp     short loc_180085673
0x1800855fa  call    ?get@?$static_lazy@VWindowFrameLogging@@@details@wil@@QEAAPEAVWindowFrameLogging@@P6AXXZ@Z; wil::details::static_lazy<WindowFrameLogging>::get(void (*)(void))
0x1800855ff  mov     rbx, [rax+8]
0x180085603  mov     eax, [rbx]
0x180085605  cmp     eax, 5
0x180085608  jbe     short loc_180085673
0x18008560a  mov     rdx, 200000000000h
0x180085614  mov     rcx, rbx
0x180085617  call    _tlgKeywordOn
0x18008561c  test    al, al
0x18008561e  jz      short loc_180085673
0x180085620  call    cs:__imp_GetCurrentThreadId
0x180085626  mov     r8, [rdi+110h]
0x18008562d  lea     rdx, byte_180100EEB
0x180085634  mov     [rsp+48h+arg_8], eax
0x180085638  add     r8, 8
0x18008563c  lea     rax, [rsp+48h+arg_8]
0x180085641  mov     [rsp+48h+arg_0], 0
0x180085649  mov     [rsp+48h+var_18], rax
0x18008564e  mov     rcx, rbx
0x180085651  lea     rax, [rsp+48h+arg_0]
0x180085656  mov     [rsp+48h+arg_10], 1000000h
0x18008565f  mov     [rsp+48h+var_20], rax
0x180085664  lea     rax, [rsp+48h+arg_10]
0x180085669  mov     [rsp+48h+var_28], rax
0x18008566e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180085673  mov     rcx, rdi
0x180085676  mov     rbx, [rsp+48h+arg_18]
0x18008567b  add     rsp, 40h
0x18008567f  pop     rdi
0x180085680  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWindowFrameLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WindowFrameLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
