# wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x14002e3fc`
- end: `0x14002e4c6`
- name: `?Stop@?$ActivityBase@VLogProvider@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `202`
- prototype: ``
- caller_count: `37`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140021f10`
- `0x140022110`
- `0x1400222d0`
- `0x140023920`
- `0x140023e00`
- `0x140024cc0`
- `0x140024f90`
- `0x1400251d0`
- `0x140025750`
- `0x1400259e0`
- `0x140025d10`
- `0x140025f30`
- `0x1400260b0`
- `0x1400261a0`
- `0x140026290`
- `0x140026630`
- `0x140026780`
- `0x140027430`
- `0x1400276c0`
- `0x1400278d0`
- `0x140027ab0`
- `0x140027dd0`
- `0x1400281d0`
- `0x140028600`
- `0x140028b60`
- `0x140028d00`
- `0x140029170`
- `0x140029220`
- `0x1400292d0`
- `0x140029390`
- `0x1400295b0`
- `0x1400298a0`
- `0x140029c30`
- `0x140029e90`
- `0x140029f40`
- `0x14002a560`
- `0x1400413bc`

## callees

- `0x140003124`
- `0x14000c558`
- `0x14000cbe4`
- `0x14001648c`
- `0x140016540`
- `0x140016cd0`
- `0x14002b008`
- `0x14002e3fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002e45e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002e45e`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(__int64 a1)
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
    wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(a1, v12);
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
        (unsigned int)&byte_14008BFEF,
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
0x14002e3fc  mov     rax, rsp
0x14002e3ff  mov     [rax+20h], rbx
0x14002e403  mov     [rax+10h], edx
0x14002e406  push    rdi
0x14002e407  sub     rsp, 40h
0x14002e40b  lea     rdx, [rax+8]
0x14002e40f  mov     dword ptr [rax+10h], 0
0x14002e416  mov     rdi, rcx
0x14002e419  call    ?LockExclusive@?$ActivityBase@VLogProvider@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14002e41e  mov     rcx, [rdi+110h]
0x14002e425  lea     r8, [rsp+48h+arg_8]
0x14002e42a  xor     edx, edx
0x14002e42c  call    ?SetStopResult@?$ActivityData@VLogProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x14002e431  lea     rcx, [rsp+48h+arg_0]
0x14002e436  mov     bl, al
0x14002e438  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14002e43d  test    bl, bl
0x14002e43f  jz      short loc_14002E44F
0x14002e441  mov     edx, [rsp+48h+arg_8]
0x14002e445  mov     rcx, rdi
0x14002e448  call    ?ReportStopActivity@?$ActivityBase@VLogProvider@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x14002e44d  jmp     short loc_14002E4B4
0x14002e44f  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002e454  mov     rbx, rax
0x14002e457  mov     ecx, [rax]
0x14002e459  cmp     ecx, 5
0x14002e45c  jbe     short loc_14002E4B4
0x14002e45e  call    cs:__imp_GetCurrentThreadId
0x14002e464  mov     r8, [rdi+110h]
0x14002e46b  lea     rdx, byte_14008BFEF
0x14002e472  mov     [rsp+48h+arg_8], eax
0x14002e476  add     r8, 8
0x14002e47a  lea     rax, [rsp+48h+arg_8]
0x14002e47f  mov     [rsp+48h+arg_0], 0
0x14002e487  mov     [rsp+48h+var_18], rax
0x14002e48c  xor     r9d, r9d
0x14002e48f  lea     rax, [rsp+48h+arg_0]
0x14002e494  mov     [rsp+48h+arg_10], 1000000h
0x14002e49d  mov     [rsp+48h+var_20], rax
0x14002e4a2  mov     rcx, rbx
0x14002e4a5  lea     rax, [rsp+48h+arg_10]
0x14002e4aa  mov     [rsp+48h+var_28], rax
0x14002e4af  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14002e4b4  mov     rcx, rdi
0x14002e4b7  mov     rbx, [rsp+48h+arg_18]
0x14002e4bc  add     rsp, 40h
0x14002e4c0  pop     rdi
0x14002e4c1  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
