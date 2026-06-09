# wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x14002e4cc`
- end: `0x14002e596`
- name: `?Stop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `202`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140023ce0`
- `0x140023d70`
- `0x140023fa0`
- `0x140024500`
- `0x140028a10`

## callees

- `0x140003124`
- `0x14000c558`
- `0x14000cbe4`
- `0x14001648c`
- `0x140016540`
- `0x140016cd0`
- `0x14002b254`
- `0x14002e4cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002e52e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002e52e`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(__int64 a1)
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
  wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(a1, &v11);
  v2 = wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         *(_QWORD *)(a1 + 272),
         0,
         &v12);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  if ( v2 )
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(a1, v12);
  }
  else
  {
    v6 = LogProvider::Provider();
    v7 = (int)v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v9 = *(_QWORD *)(a1 + 272);
      v12 = CurrentThreadId;
      v11 = 0;
      v13 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)byte_14008C5F3,
        v9 + 8,
        0,
        (__int64)&v13,
        (__int64)&v11,
        (__int64)&v12);
    }
  }
  return wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v3,
           v4,
           v5);
}

```

## disassembly

```asm
0x14002e4cc  mov     rax, rsp
0x14002e4cf  mov     [rax+20h], rbx
0x14002e4d3  mov     [rax+10h], edx
0x14002e4d6  push    rdi
0x14002e4d7  sub     rsp, 40h
0x14002e4db  lea     rdx, [rax+8]
0x14002e4df  mov     dword ptr [rax+10h], 0
0x14002e4e6  mov     rdi, rcx
0x14002e4e9  call    ?LockExclusive@?$ActivityBase@VLogProvider@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14002e4ee  mov     rcx, [rdi+110h]
0x14002e4f5  lea     r8, [rsp+48h+arg_8]
0x14002e4fa  xor     edx, edx
0x14002e4fc  call    ?SetStopResult@?$ActivityData@VLogProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x14002e501  lea     rcx, [rsp+48h+arg_0]
0x14002e506  mov     bl, al
0x14002e508  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14002e50d  test    bl, bl
0x14002e50f  jz      short loc_14002E51F
0x14002e511  mov     edx, [rsp+48h+arg_8]
0x14002e515  mov     rcx, rdi
0x14002e518  call    ?ReportStopActivity@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x14002e51d  jmp     short loc_14002E584
0x14002e51f  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002e524  mov     rbx, rax
0x14002e527  mov     ecx, [rax]
0x14002e529  cmp     ecx, 5
0x14002e52c  jbe     short loc_14002E584
0x14002e52e  call    cs:__imp_GetCurrentThreadId
0x14002e534  mov     r8, [rdi+110h]
0x14002e53b  lea     rdx, byte_14008C5F3
0x14002e542  mov     [rsp+48h+arg_8], eax
0x14002e546  add     r8, 8
0x14002e54a  lea     rax, [rsp+48h+arg_8]
0x14002e54f  mov     [rsp+48h+arg_0], 0
0x14002e557  mov     [rsp+48h+var_18], rax
0x14002e55c  xor     r9d, r9d
0x14002e55f  lea     rax, [rsp+48h+arg_0]
0x14002e564  mov     [rsp+48h+arg_10], 1000000h
0x14002e56d  mov     [rsp+48h+var_20], rax
0x14002e572  mov     rcx, rbx
0x14002e575  lea     rax, [rsp+48h+arg_10]
0x14002e57a  mov     [rsp+48h+var_28], rax
0x14002e57f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14002e584  mov     rcx, rdi
0x14002e587  mov     rbx, [rsp+48h+arg_18]
0x14002e58c  add     rsp, 40h
0x14002e590  pop     rdi
0x14002e591  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
