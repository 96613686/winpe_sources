# wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x140016eb8`
- end: `0x140016f91`
- name: `?Stop@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `217`
- prototype: ``
- caller_count: `22`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14000dca0`
- `0x140022790`
- `0x140024860`
- `0x1400255a0`
- `0x140026860`
- `0x140026b40`
- `0x140026d20`
- `0x1400283f0`
- `0x140028eb0`
- `0x140029470`
- `0x140040de4`
- `0x140040f18`
- `0x14004107c`
- `0x140041264`
- `0x1400416c0`
- `0x14005d534`
- `0x14005d6c0`
- `0x14005d880`
- `0x14005db3c`
- `0x14005e060`
- `0x14005e210`
- `0x14005e368`

## callees

- `0x140003124`
- `0x14000330c`
- `0x14000c558`
- `0x14000cbe4`
- `0x14001648c`
- `0x140016540`
- `0x140016cd0`
- `0x140016eb8`
- `0x140071010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140016f30`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140016f30`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        unsigned int a2)
{
  char v4; // bl
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  const struct _tlgProvider_t *v8; // rax
  int v9; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  DWORD v13; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v14; // [rsp+70h] [rbp+18h] BYREF
  __int64 v15; // [rsp+78h] [rbp+20h] BYREF

  v13 = 0;
  wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(a1, &v14);
  v4 = wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         a2,
         &v13);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
  if ( v4 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v8 = LogProvider::Provider();
    v9 = (int)v8;
    if ( *(_DWORD *)v8 > 5u && (unsigned __int8)tlgKeywordOn(v8, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = a1[34];
      v13 = CurrentThreadId;
      v14 = a2;
      v15 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)byte_1400837C1,
        v11 + 8,
        0,
        (__int64)&v15,
        (__int64)&v14,
        (__int64)&v13);
    }
  }
  return wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v5,
           v6,
           v7);
}

```

## disassembly

```asm
0x140016eb8  push    rbx
0x140016eba  push    rsi
0x140016ebb  push    rdi
0x140016ebc  sub     rsp, 40h
0x140016ec0  mov     esi, edx
0x140016ec2  mov     [rsp+58h+arg_0], 0
0x140016eca  lea     rdx, [rsp+58h+arg_10]
0x140016ecf  mov     rdi, rcx
0x140016ed2  call    ?LockExclusive@?$ActivityBase@VLogProvider@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140016ed7  mov     rcx, [rdi+110h]
0x140016ede  lea     r8, [rsp+58h+arg_0]
0x140016ee3  mov     edx, esi
0x140016ee5  call    ?SetStopResult@?$ActivityData@VLogProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x140016eea  lea     rcx, [rsp+58h+arg_10]
0x140016eef  mov     bl, al
0x140016ef1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140016ef6  test    bl, bl
0x140016ef8  jz      short loc_140016F0B
0x140016efa  mov     rax, [rdi]
0x140016efd  mov     rcx, rdi
0x140016f00  mov     rax, [rax+8]
0x140016f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016f09  jmp     short loc_140016F82
0x140016f0b  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x140016f10  mov     rbx, rax
0x140016f13  mov     ecx, [rax]
0x140016f15  cmp     ecx, 5
0x140016f18  jbe     short loc_140016F82
0x140016f1a  mov     rdx, 400000000000h
0x140016f24  mov     rcx, rax
0x140016f27  call    _tlgKeywordOn
0x140016f2c  test    al, al
0x140016f2e  jz      short loc_140016F82
0x140016f30  call    cs:__imp_GetCurrentThreadId
0x140016f36  mov     r8, [rdi+110h]
0x140016f3d  lea     rdx, byte_1400837C1
0x140016f44  mov     [rsp+58h+arg_0], eax
0x140016f48  add     r8, 8
0x140016f4c  lea     rax, [rsp+58h+arg_0]
0x140016f51  mov     [rsp+58h+arg_10], esi
0x140016f55  mov     [rsp+58h+var_28], rax
0x140016f5a  xor     r9d, r9d
0x140016f5d  lea     rax, [rsp+58h+arg_10]
0x140016f62  mov     [rsp+58h+arg_18], 1000000h
0x140016f6b  mov     [rsp+58h+var_30], rax
0x140016f70  mov     rcx, rbx
0x140016f73  lea     rax, [rsp+58h+arg_18]
0x140016f78  mov     [rsp+58h+var_38], rax
0x140016f7d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140016f82  mov     rcx, rdi
0x140016f85  add     rsp, 40h
0x140016f89  pop     rdi
0x140016f8a  pop     rsi
0x140016f8b  pop     rbx
0x140016f8c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
