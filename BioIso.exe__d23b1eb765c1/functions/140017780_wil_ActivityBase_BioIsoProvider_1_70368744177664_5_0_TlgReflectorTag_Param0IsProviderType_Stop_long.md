# wil::ActivityBase<BioIsoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x140017780`
- end: `0x140017867`
- name: `?Stop@?$ActivityBase@VBioIsoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `231`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140017570`
- `0x140057340`

## callees

- `0x140001bc4`
- `0x1400022c0`
- `0x140002e50`
- `0x140003aa0`
- `0x14000bd48`
- `0x14000d990`
- `0x140013728`
- `0x140017780`
- `0x140085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400177fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400177fc`

## pseudocode

```c
void __fastcall wil::ActivityBase<BioIsoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // bl
  _DWORD *v3; // rbx
  __int64 v4; // r8
  __int64 v5; // r9
  DWORD CurrentThreadId; // eax
  __int64 v7; // r8
  __int64 v8; // r9
  RTL_SRWLOCK *v9; // [rsp+50h] [rbp+8h] BYREF
  DWORD v10; // [rsp+58h] [rbp+10h] BYREF
  __int64 v11; // [rsp+60h] [rbp+18h] BYREF

  v10 = 0;
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(a1, &v9);
  v2 = wil::ActivityBase<BioIsoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<BioIsoProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v10);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v9);
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v3 = (_DWORD *)*((_QWORD *)BioIsoProvider::Instance() + 1);
    if ( *v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL, v4, v5) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v7 = a1[34];
      v10 = CurrentThreadId;
      LODWORD(v9) = 0;
      v11 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v3,
        (unsigned __int8 *)byte_14009C33B,
        (const GUID *)(v7 + 8),
        v8,
        (__int64)&v11,
        (__int64)&v9,
        (__int64)&v10);
    }
  }
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x140017780  mov     rax, rsp
0x140017783  mov     [rax+20h], rbx
0x140017787  mov     [rax+10h], edx
0x14001778a  push    rdi
0x14001778b  sub     rsp, 40h
0x14001778f  lea     rdx, [rax+8]
0x140017793  mov     dword ptr [rax+10h], 0
0x14001779a  mov     rdi, rcx
0x14001779d  call    ?LockExclusive@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400177a2  mov     rcx, [rdi+110h]
0x1400177a9  lea     r8, [rsp+48h+arg_8]
0x1400177ae  xor     edx, edx
0x1400177b0  call    ?SetStopResult@?$ActivityData@VBioIsoProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VBioIsoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<BioIsoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<BioIsoProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x1400177b5  lea     rcx, [rsp+48h+arg_0]
0x1400177ba  mov     bl, al
0x1400177bc  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1400177c1  test    bl, bl
0x1400177c3  jz      short loc_1400177D6
0x1400177c5  mov     rax, [rdi]
0x1400177c8  mov     rcx, rdi
0x1400177cb  mov     rax, [rax+8]
0x1400177cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400177d4  jmp     short loc_140017855
0x1400177d6  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x1400177db  mov     rbx, [rax+8]
0x1400177df  mov     eax, [rbx]
0x1400177e1  cmp     eax, 5
0x1400177e4  jbe     short loc_140017855
0x1400177e6  mov     rdx, 400000000000h
0x1400177f0  mov     rcx, rbx
0x1400177f3  call    _tlgKeywordOn
0x1400177f8  test    al, al
0x1400177fa  jz      short loc_140017855
0x1400177fc  call    cs:__imp_GetCurrentThreadId
0x140017803  nop     dword ptr [rax+rax+00h]
0x140017808  mov     r8, [rdi+110h]
0x14001780f  lea     rdx, byte_14009C33B
0x140017816  mov     [rsp+48h+arg_8], eax
0x14001781a  add     r8, 8
0x14001781e  lea     rax, [rsp+48h+arg_8]
0x140017823  mov     dword ptr [rsp+48h+arg_0], 0
0x14001782b  mov     [rsp+48h+var_18], rax
0x140017830  mov     rcx, rbx
0x140017833  lea     rax, [rsp+48h+arg_0]
0x140017838  mov     [rsp+48h+arg_10], 1000000h
0x140017841  mov     [rsp+48h+var_20], rax
0x140017846  lea     rax, [rsp+48h+arg_10]
0x14001784b  mov     [rsp+48h+var_28], rax
0x140017850  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140017855  mov     rcx, rdi
0x140017858  mov     rbx, [rsp+48h+arg_18]
0x14001785d  add     rsp, 40h
0x140017861  pop     rdi
0x140017862  jmp     ?IgnoreCurrentThread@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
