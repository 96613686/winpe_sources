# wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x14000791c`
- end: `0x1400079e3`
- name: `?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `199`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `280`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400058f0`
- `0x140005b00`
- `0x140005ea0`
- `0x140006090`
- `0x1400062b0`
- `0x1400064e0`
- `0x140006760`
- `0x1400069f0`
- `0x140006e20`
- `0x140007030`
- `0x140007280`
- `0x1400074b0`
- `0x140007700`
- `0x140008380`
- `0x1400089e0`
- `0x140008c60`
- `0x140009030`
- `0x1400098b0`
- `0x140009cb0`
- `0x14000a8d0`
- `0x14000ae50`
- `0x14000b070`
- `0x14000b2b0`
- `0x14000bd70`
- `0x14000bff0`
- `0x14000c1b0`
- `0x14000c430`
- `0x14000e83c`
- `0x140012850`
- `0x140012e7c`
- `0x14001314c`
- `0x140013bf0`
- `0x140013e00`
- `0x1400140d0`
- `0x140014300`
- `0x140014510`
- `0x140014720`
- `0x140014940`
- `0x140014b60`
- `0x140014dd0`
- `0x140014fe0`
- `0x140015200`
- `0x140015420`
- `0x1400157f0`
- `0x140015a50`
- `0x140015cd0`
- `0x140015f10`
- `0x1400161a0`
- `0x140016420`
- `0x140016630`

## callees

- `0x140001bc4`
- `0x140002e50`
- `0x14000791c`
- `0x14000bd48`
- `0x14000d990`
- `0x140013018`
- `0x140013728`
- `0x140085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000797f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000797f`

## pseudocode

```c
void __fastcall wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        unsigned int a2)
{
  char v4; // bl
  _DWORD *v5; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v7; // r8
  __int64 v8; // r9
  DWORD v9; // [rsp+60h] [rbp+8h] BYREF
  RTL_SRWLOCK *v10; // [rsp+70h] [rbp+18h] BYREF
  __int64 v11; // [rsp+78h] [rbp+20h] BYREF

  v9 = 0;
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(a1, &v10);
  v4 = wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<BioIsoProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         a2,
         &v9);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v10);
  if ( v4 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v5 = (_DWORD *)*((_QWORD *)BioIsoProvider::Instance() + 1);
    if ( *v5 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v7 = a1[34];
      v9 = CurrentThreadId;
      LODWORD(v10) = a2;
      v11 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v5,
        (unsigned __int8 *)word_140095512,
        (const GUID *)(v7 + 8),
        v8,
        (__int64)&v11,
        (__int64)&v10,
        (__int64)&v9);
    }
  }
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x14000791c  push    rbx
0x14000791e  push    rsi
0x14000791f  push    rdi
0x140007920  sub     rsp, 40h
0x140007924  mov     esi, edx
0x140007926  mov     [rsp+58h+arg_0], 0
0x14000792e  lea     rdx, [rsp+58h+arg_10]
0x140007933  mov     rdi, rcx
0x140007936  call    ?LockExclusive@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000793b  mov     rcx, [rdi+110h]
0x140007942  lea     r8, [rsp+58h+arg_0]
0x140007947  mov     edx, esi
0x140007949  call    ?SetStopResult@?$ActivityData@VBioIsoProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<BioIsoProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x14000794e  lea     rcx, [rsp+58h+arg_10]
0x140007953  mov     bl, al
0x140007955  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14000795a  test    bl, bl
0x14000795c  jz      short loc_14000796F
0x14000795e  mov     rax, [rdi]
0x140007961  mov     rcx, rdi
0x140007964  mov     rax, [rax+8]
0x140007968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000796d  jmp     short loc_1400079D4
0x14000796f  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x140007974  mov     rbx, [rax+8]
0x140007978  mov     eax, [rbx]
0x14000797a  cmp     eax, 5
0x14000797d  jbe     short loc_1400079D4
0x14000797f  call    cs:__imp_GetCurrentThreadId
0x140007986  nop     dword ptr [rax+rax+00h]
0x14000798b  mov     r8, [rdi+110h]
0x140007992  lea     rdx, word_140095512
0x140007999  mov     [rsp+58h+arg_0], eax
0x14000799d  add     r8, 8
0x1400079a1  lea     rax, [rsp+58h+arg_0]
0x1400079a6  mov     dword ptr [rsp+58h+arg_10], esi
0x1400079aa  mov     [rsp+58h+var_28], rax
0x1400079af  mov     rcx, rbx
0x1400079b2  lea     rax, [rsp+58h+arg_10]
0x1400079b7  mov     [rsp+58h+arg_18], 1000000h
0x1400079c0  mov     [rsp+58h+var_30], rax
0x1400079c5  lea     rax, [rsp+58h+arg_18]
0x1400079ca  mov     [rsp+58h+var_38], rax
0x1400079cf  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400079d4  mov     rcx, rdi
0x1400079d7  add     rsp, 40h
0x1400079db  pop     rdi
0x1400079dc  pop     rsi
0x1400079dd  pop     rbx
0x1400079de  jmp     ?IgnoreCurrentThread@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
