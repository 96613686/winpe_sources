# wil::ActivityBase<CloudRestoreLauncherTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x1800411a4`
- end: `0x180041271`
- name: `?Stop@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `205`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `26`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180038994`
- `0x180038ea4`
- `0x18003925c`
- `0x18003d2b4`
- `0x18003e284`
- `0x18005ecd4`
- `0x18005f23c`
- `0x18005f838`
- `0x180060020`
- `0x180060150`
- `0x1800604f0`
- `0x180060990`
- `0x180060b50`
- `0x180060d00`
- `0x180064870`
- `0x180064a30`
- `0x180064c10`
- `0x180067780`
- `0x1800678a0`
- `0x180067980`
- `0x18006ceec`
- `0x18007091c`
- `0x1800776b8`
- `0x18007ed70`
- `0x18007f6b0`
- `0x180081910`

## callees

- `0x180001698`
- `0x1800166e8`
- `0x180018674`
- `0x180018acc`
- `0x1800195cc`
- `0x1800403ac`
- `0x1800411a4`
- `0x18012d010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180041209`
- `KERNEL32!GetCurrentThreadId` at `0x180041209`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<CloudRestoreLauncherTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // bl
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  const struct _tlgProvider_t *v6; // rax
  int v7; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  int v11; // [rsp+50h] [rbp+8h] BYREF
  DWORD v12; // [rsp+58h] [rbp+10h] BYREF
  __int64 v13; // [rsp+60h] [rbp+18h] BYREF

  v12 = 0;
  wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v11);
  v2 = wil::ActivityBase<CloudRestoreLauncherTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CloudRestoreLauncherTelemetry,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v12);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v6 = CloudRestoreLauncherTelemetry::Provider();
    v7 = (int)v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v9 = a1[34];
      v12 = CurrentThreadId;
      v11 = 0;
      v13 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)&unk_180151FD4,
        v9 + 8,
        0,
        (__int64)&v13,
        (__int64)&v11,
        (__int64)&v12);
    }
  }
  return wil::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v3,
           v4,
           v5);
}

```

## disassembly

```asm
0x1800411a4  mov     rax, rsp
0x1800411a7  mov     [rax+20h], rbx
0x1800411ab  mov     [rax+10h], edx
0x1800411ae  push    rdi
0x1800411af  sub     rsp, 40h
0x1800411b3  lea     rdx, [rax+8]
0x1800411b7  mov     dword ptr [rax+10h], 0
0x1800411be  mov     rdi, rcx
0x1800411c1  call    ?LockExclusive@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800411c6  mov     rcx, [rdi+110h]
0x1800411cd  lea     r8, [rsp+48h+arg_8]
0x1800411d2  xor     edx, edx
0x1800411d4  call    ?SetStopResult@?$ActivityData@VCloudRestoreLauncherTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<CloudRestoreLauncherTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CloudRestoreLauncherTelemetry,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x1800411d9  lea     rcx, [rsp+48h+arg_0]
0x1800411de  mov     bl, al
0x1800411e0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800411e5  test    bl, bl
0x1800411e7  jz      short loc_1800411FA
0x1800411e9  mov     rax, [rdi]
0x1800411ec  mov     rcx, rdi
0x1800411ef  mov     rax, [rax+8]
0x1800411f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411f8  jmp     short loc_18004125F
0x1800411fa  call    ?Provider@CloudRestoreLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; CloudRestoreLauncherTelemetry::Provider(void)
0x1800411ff  mov     rbx, rax
0x180041202  mov     ecx, [rax]
0x180041204  cmp     ecx, 5
0x180041207  jbe     short loc_18004125F
0x180041209  call    cs:__imp_GetCurrentThreadId
0x18004120f  mov     r8, [rdi+110h]
0x180041216  lea     rdx, unk_180151FD4
0x18004121d  mov     [rsp+48h+arg_8], eax
0x180041221  add     r8, 8
0x180041225  lea     rax, [rsp+48h+arg_8]
0x18004122a  mov     [rsp+48h+arg_0], 0
0x180041232  mov     [rsp+48h+var_18], rax
0x180041237  xor     r9d, r9d
0x18004123a  lea     rax, [rsp+48h+arg_0]
0x18004123f  mov     [rsp+48h+arg_10], 1000000h
0x180041248  mov     [rsp+48h+var_20], rax
0x18004124d  mov     rcx, rbx
0x180041250  lea     rax, [rsp+48h+arg_10]
0x180041255  mov     [rsp+48h+var_28], rax
0x18004125a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004125f  mov     rcx, rdi
0x180041262  mov     rbx, [rsp+48h+arg_18]
0x180041267  add     rsp, 40h
0x18004126b  pop     rdi
0x18004126c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
