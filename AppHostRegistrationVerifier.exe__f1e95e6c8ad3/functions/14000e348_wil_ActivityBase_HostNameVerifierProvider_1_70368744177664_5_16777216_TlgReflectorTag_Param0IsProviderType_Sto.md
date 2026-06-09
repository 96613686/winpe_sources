# wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x14000e348`
- end: `0x14000e428`
- name: `?Stop@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `224`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14000eb7c`
- `0x14000ed9c`

## callees

- `0x1400012cc`
- `0x140001b4c`
- `0x14000a15c`
- `0x14000d438`
- `0x14000d500`
- `0x14000da38`
- `0x14000df7c`
- `0x14000e348`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000e3c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000e3c3`

## pseudocode

```c
void __fastcall wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // bl
  __int64 v3; // rcx
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  __int64 v6; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  RTL_SRWLOCK *v10; // [rsp+50h] [rbp+8h] BYREF
  DWORD v11; // [rsp+58h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF

  v11 = 0;
  wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &v10);
  v2 = wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<HostNameVerifierProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
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
    v4 = HostNameVerifierProvider::Provider(v3);
    v6 = (__int64)v4;
    if ( *(_DWORD *)v4 > 5u && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL, v5) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v8 = a1[34];
      v11 = CurrentThreadId;
      LODWORD(v10) = 0;
      v12 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (__int64)byte_140015945,
        v8 + 8,
        v9,
        (__int64)&v12,
        (__int64)&v10,
        (__int64)&v11);
    }
  }
  wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x14000e348  mov     rax, rsp
0x14000e34b  mov     [rax+20h], rbx
0x14000e34f  mov     [rax+10h], edx
0x14000e352  push    rdi
0x14000e353  sub     rsp, 40h
0x14000e357  lea     rdx, [rax+8]
0x14000e35b  mov     dword ptr [rax+10h], 0
0x14000e362  mov     rdi, rcx
0x14000e365  call    ?LockExclusive@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000e36a  mov     rcx, [rdi+110h]
0x14000e371  lea     r8, [rsp+48h+arg_8]
0x14000e376  xor     edx, edx
0x14000e378  call    ?SetStopResult@?$ActivityData@VHostNameVerifierProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<HostNameVerifierProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x14000e37d  lea     rcx, [rsp+48h+arg_0]
0x14000e382  mov     bl, al
0x14000e384  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000e389  test    bl, bl
0x14000e38b  jz      short loc_14000E39E
0x14000e38d  mov     rax, [rdi]
0x14000e390  mov     rcx, rdi
0x14000e393  mov     rax, [rax+8]
0x14000e397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e39c  jmp     short loc_14000E416
0x14000e39e  call    ?Provider@HostNameVerifierProvider@@SAPEBU_tlgProvider_t@@XZ; HostNameVerifierProvider::Provider(void)
0x14000e3a3  mov     rbx, rax
0x14000e3a6  mov     ecx, [rax]
0x14000e3a8  cmp     ecx, 5
0x14000e3ab  jbe     short loc_14000E416
0x14000e3ad  mov     rdx, 400000000000h
0x14000e3b7  mov     rcx, rax
0x14000e3ba  call    _tlgKeywordOn
0x14000e3bf  test    al, al
0x14000e3c1  jz      short loc_14000E416
0x14000e3c3  call    cs:__imp_GetCurrentThreadId
0x14000e3c9  mov     r8, [rdi+110h]
0x14000e3d0  lea     rdx, byte_140015945
0x14000e3d7  mov     [rsp+48h+arg_8], eax
0x14000e3db  add     r8, 8
0x14000e3df  lea     rax, [rsp+48h+arg_8]
0x14000e3e4  mov     dword ptr [rsp+48h+arg_0], 0
0x14000e3ec  mov     [rsp+48h+var_18], rax
0x14000e3f1  mov     rcx, rbx
0x14000e3f4  lea     rax, [rsp+48h+arg_0]
0x14000e3f9  mov     [rsp+48h+arg_10], 1000000h
0x14000e402  mov     [rsp+48h+var_20], rax
0x14000e407  lea     rax, [rsp+48h+arg_10]
0x14000e40c  mov     [rsp+48h+var_28], rax
0x14000e411  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000e416  mov     rcx, rdi
0x14000e419  mov     rbx, [rsp+48h+arg_18]
0x14000e41e  add     rsp, 40h
0x14000e422  pop     rdi
0x14000e423  jmp     ?IgnoreCurrentThread@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
