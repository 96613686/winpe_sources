# wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x140017878`
- end: `0x140017945`
- name: `?Stop@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `205`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14001351c`
- `0x1400151d8`
- `0x140016a28`

## callees

- `0x14000169c`
- `0x140009434`
- `0x140016a00`
- `0x140016c14`
- `0x140017078`
- `0x140017098`
- `0x1400175c8`
- `0x140017878`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400178da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400178da`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(_QWORD *a1)
{
  char v2; // bl
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  const struct _tlgProvider_t *v6; // rax
  int v7; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  int v10; // r9d
  int v12; // [rsp+50h] [rbp+8h] BYREF
  DWORD v13; // [rsp+58h] [rbp+10h] BYREF
  __int64 v14; // [rsp+60h] [rbp+18h] BYREF

  v13 = 0;
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(a1, &v12);
  v2 = wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MDMPushProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v13);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  if ( v2 )
  {
    wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(a1, v13);
  }
  else
  {
    v6 = MDMPushProvider::Provider();
    v7 = (int)v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v9 = a1[34];
      v13 = CurrentThreadId;
      v12 = 0;
      v14 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)byte_140020059,
        v9 + 8,
        v10,
        (__int64)&v14,
        (__int64)&v12,
        (__int64)&v13);
    }
  }
  return wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v3,
           v4,
           v5);
}

```

## disassembly

```asm
0x140017878  mov     rax, rsp
0x14001787b  mov     [rax+20h], rbx
0x14001787f  mov     [rax+10h], edx
0x140017882  push    rdi
0x140017883  sub     rsp, 40h
0x140017887  lea     rdx, [rax+8]
0x14001788b  mov     dword ptr [rax+10h], 0
0x140017892  mov     rdi, rcx
0x140017895  call    ?LockExclusive@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14001789a  mov     rcx, [rdi+110h]
0x1400178a1  lea     r8, [rsp+48h+arg_8]
0x1400178a6  xor     edx, edx
0x1400178a8  call    ?SetStopResult@?$ActivityData@VMDMPushProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MDMPushProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x1400178ad  lea     rcx, [rsp+48h+arg_0]
0x1400178b2  mov     bl, al
0x1400178b4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400178b9  test    bl, bl
0x1400178bb  jz      short loc_1400178CB
0x1400178bd  mov     edx, [rsp+48h+arg_8]
0x1400178c1  mov     rcx, rdi
0x1400178c4  call    ?ReportStopActivity@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x1400178c9  jmp     short loc_140017933
0x1400178cb  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x1400178d0  mov     rbx, rax
0x1400178d3  mov     ecx, [rax]
0x1400178d5  cmp     ecx, 5
0x1400178d8  jbe     short loc_140017933
0x1400178da  call    cs:__imp_GetCurrentThreadId
0x1400178e1  nop     dword ptr [rax+rax+00h]
0x1400178e6  mov     r8, [rdi+110h]
0x1400178ed  lea     rdx, byte_140020059
0x1400178f4  mov     [rsp+48h+arg_8], eax
0x1400178f8  add     r8, 8
0x1400178fc  lea     rax, [rsp+48h+arg_8]
0x140017901  mov     [rsp+48h+arg_0], 0
0x140017909  mov     [rsp+48h+var_18], rax
0x14001790e  mov     rcx, rbx
0x140017911  lea     rax, [rsp+48h+arg_0]
0x140017916  mov     [rsp+48h+arg_10], 1000000h
0x14001791f  mov     [rsp+48h+var_20], rax
0x140017924  lea     rax, [rsp+48h+arg_10]
0x140017929  mov     [rsp+48h+var_28], rax
0x14001792e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140017933  mov     rcx, rdi
0x140017936  mov     rbx, [rsp+48h+arg_18]
0x14001793b  add     rsp, 40h
0x14001793f  pop     rdi
0x140017940  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
