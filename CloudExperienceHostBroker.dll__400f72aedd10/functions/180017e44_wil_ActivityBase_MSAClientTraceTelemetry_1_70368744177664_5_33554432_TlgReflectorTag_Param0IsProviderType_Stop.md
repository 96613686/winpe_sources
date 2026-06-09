# wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180017e44`
- end: `0x180017f24`
- name: `?Stop@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `224`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180012dc0`
- `0x180013e54`

## callees

- `0x180001d58`
- `0x180002000`
- `0x1800084a8`
- `0x180015540`
- `0x1800158a4`
- `0x18001610c`
- `0x180017b30`
- `0x180017e44`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017ebf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017ebf`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // bl
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v7; // r8
  __int64 v8; // r9
  int v10; // [rsp+50h] [rbp+8h] BYREF
  DWORD v11; // [rsp+58h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF

  v11 = 0;
  wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v10);
  v2 = wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
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
    v3 = MSAClientTraceTelemetry::Provider();
    v5 = (__int64)v3;
    if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL, v4) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v7 = a1[34];
      v11 = CurrentThreadId;
      v10 = 0;
      v12 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v5,
        (__int64)&word_18004669E,
        v7 + 8,
        v8,
        (__int64)&v12,
        (__int64)&v10,
        (__int64)&v11);
    }
  }
  return wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x180017e44  mov     rax, rsp
0x180017e47  mov     [rax+20h], rbx
0x180017e4b  mov     [rax+10h], edx
0x180017e4e  push    rdi
0x180017e4f  sub     rsp, 40h
0x180017e53  lea     rdx, [rax+8]
0x180017e57  mov     dword ptr [rax+10h], 0
0x180017e5e  mov     rdi, rcx
0x180017e61  call    ?LockExclusive@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180017e66  mov     rcx, [rdi+110h]
0x180017e6d  lea     r8, [rsp+48h+arg_8]
0x180017e72  xor     edx, edx
0x180017e74  call    ?SetStopResult@?$ActivityData@VMSAClientTraceTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180017e79  lea     rcx, [rsp+48h+arg_0]
0x180017e7e  mov     bl, al
0x180017e80  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180017e85  test    bl, bl
0x180017e87  jz      short loc_180017E9A
0x180017e89  mov     rax, [rdi]
0x180017e8c  mov     rcx, rdi
0x180017e8f  mov     rax, [rax+8]
0x180017e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e98  jmp     short loc_180017F12
0x180017e9a  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x180017e9f  mov     rbx, rax
0x180017ea2  mov     ecx, [rax]
0x180017ea4  cmp     ecx, 5
0x180017ea7  jbe     short loc_180017F12
0x180017ea9  mov     rdx, 400000000000h
0x180017eb3  mov     rcx, rax
0x180017eb6  call    _tlgKeywordOn
0x180017ebb  test    al, al
0x180017ebd  jz      short loc_180017F12
0x180017ebf  call    cs:__imp_GetCurrentThreadId
0x180017ec5  mov     r8, [rdi+110h]
0x180017ecc  lea     rdx, word_18004669E
0x180017ed3  mov     [rsp+48h+arg_8], eax
0x180017ed7  add     r8, 8
0x180017edb  lea     rax, [rsp+48h+arg_8]
0x180017ee0  mov     [rsp+48h+arg_0], 0
0x180017ee8  mov     [rsp+48h+var_18], rax
0x180017eed  mov     rcx, rbx
0x180017ef0  lea     rax, [rsp+48h+arg_0]
0x180017ef5  mov     [rsp+48h+arg_10], 1000000h
0x180017efe  mov     [rsp+48h+var_20], rax
0x180017f03  lea     rax, [rsp+48h+arg_10]
0x180017f08  mov     [rsp+48h+var_28], rax
0x180017f0d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180017f12  mov     rcx, rdi
0x180017f15  mov     rbx, [rsp+48h+arg_18]
0x180017f1a  add     rsp, 40h
0x180017f1e  pop     rdi
0x180017f1f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
