# wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180014dd4`
- end: `0x180014eaf`
- name: `?Stop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `219`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x180010e68`
- `0x180010ffc`
- `0x180011184`
- `0x18001130c`
- `0x180011494`
- `0x18001161c`
- `0x1800117a4`
- `0x180011938`
- `0x180011ac0`
- `0x180012714`
- `0x1800127fc`
- `0x180013230`

## callees

- `0x180001734`
- `0x180001b50`
- `0x180008eb8`
- `0x180013aa4`
- `0x180013c24`
- `0x180014090`
- `0x1800143a0`
- `0x180014dd4`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014e4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014e4a`

## pseudocode

```c
void __fastcall wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(_QWORD *a1)
{
  char v2; // bl
  __int64 v3; // rcx
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  int v6; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  RTL_SRWLOCK *v10; // [rsp+50h] [rbp+8h] BYREF
  DWORD v11; // [rsp+58h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF

  v11 = 0;
  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(a1, &v10);
  v2 = wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
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
    v4 = NetSetupTraceLogging::Provider(v3);
    v6 = (int)v4;
    if ( *(_DWORD *)v4 > 5u && (unsigned __int8)tlgKeywordOn(v4, 1, v5) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v8 = a1[34];
      v11 = CurrentThreadId;
      LODWORD(v10) = 0;
      v12 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (int)byte_18003FC35,
        v8 + 8,
        v9,
        (__int64)&v12,
        (__int64)&v10,
        (__int64)&v11);
    }
  }
  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x180014dd4  mov     rax, rsp
0x180014dd7  mov     [rax+20h], rbx
0x180014ddb  mov     [rax+10h], edx
0x180014dde  push    rdi
0x180014ddf  sub     rsp, 40h
0x180014de3  lea     rdx, [rax+8]
0x180014de7  mov     dword ptr [rax+10h], 0
0x180014dee  mov     rdi, rcx
0x180014df1  call    ?LockExclusive@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180014df6  mov     rcx, [rdi+110h]
0x180014dfd  lea     r8, [rsp+48h+arg_8]
0x180014e02  xor     edx, edx
0x180014e04  call    ?SetStopResult@?$ActivityData@VNetSetupTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180014e09  lea     rcx, [rsp+48h+arg_0]
0x180014e0e  mov     bl, al
0x180014e10  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014e15  test    bl, bl
0x180014e17  jz      short loc_180014E2A
0x180014e19  mov     rax, [rdi]
0x180014e1c  mov     rcx, rdi
0x180014e1f  mov     rax, [rax+8]
0x180014e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e28  jmp     short loc_180014E9D
0x180014e2a  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180014e2f  mov     rbx, rax
0x180014e32  mov     ecx, [rax]
0x180014e34  cmp     ecx, 5
0x180014e37  jbe     short loc_180014E9D
0x180014e39  mov     edx, 1
0x180014e3e  mov     rcx, rax
0x180014e41  call    _tlgKeywordOn
0x180014e46  test    al, al
0x180014e48  jz      short loc_180014E9D
0x180014e4a  call    cs:__imp_GetCurrentThreadId
0x180014e50  mov     r8, [rdi+110h]
0x180014e57  lea     rdx, byte_18003FC35
0x180014e5e  mov     [rsp+48h+arg_8], eax
0x180014e62  add     r8, 8
0x180014e66  lea     rax, [rsp+48h+arg_8]
0x180014e6b  mov     dword ptr [rsp+48h+arg_0], 0
0x180014e73  mov     [rsp+48h+var_18], rax
0x180014e78  mov     rcx, rbx
0x180014e7b  lea     rax, [rsp+48h+arg_0]
0x180014e80  mov     [rsp+48h+arg_10], 1000000h
0x180014e89  mov     [rsp+48h+var_20], rax
0x180014e8e  lea     rax, [rsp+48h+arg_10]
0x180014e93  mov     [rsp+48h+var_28], rax
0x180014e98  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180014e9d  mov     rcx, rdi
0x180014ea0  mov     rbx, [rsp+48h+arg_18]
0x180014ea5  add     rsp, 40h
0x180014ea9  pop     rdi
0x180014eaa  jmp     ?IgnoreCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
