# wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x140016bbc`
- end: `0x140016c83`
- name: `?Stop@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `199`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140012bd0`
- `0x14001464c`
- `0x140015d98`

## callees

- `0x140001698`
- `0x14000905c`
- `0x140015d70`
- `0x140015f70`
- `0x1400163d8`
- `0x1400163f8`
- `0x140016920`
- `0x140016bbc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140016c1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140016c1e`

## pseudocode

```c
void __fastcall wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(_QWORD *a1)
{
  char v2; // bl
  __int64 v3; // rcx
  const struct _tlgProvider_t *v4; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v6; // r8
  __int64 v7; // r9
  RTL_SRWLOCK *v8; // [rsp+50h] [rbp+8h] BYREF
  DWORD v9; // [rsp+58h] [rbp+10h] BYREF
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  v9 = 0;
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive((__int64)a1, &v8);
  v2 = wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MDMPushProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v9);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  if ( v2 )
  {
    wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(a1, v9);
  }
  else
  {
    v4 = MDMPushProvider::Provider(v3);
    if ( *(_DWORD *)v4 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v6 = a1[34];
      v9 = CurrentThreadId;
      LODWORD(v8) = 0;
      v10 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v4,
        (__int64)byte_14001F059,
        v6 + 8,
        v7,
        (__int64)&v10,
        (__int64)&v8,
        (__int64)&v9);
    }
  }
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x140016bbc  mov     rax, rsp
0x140016bbf  mov     [rax+20h], rbx
0x140016bc3  mov     [rax+10h], edx
0x140016bc6  push    rdi
0x140016bc7  sub     rsp, 40h
0x140016bcb  lea     rdx, [rax+8]
0x140016bcf  mov     dword ptr [rax+10h], 0
0x140016bd6  mov     rdi, rcx
0x140016bd9  call    ?LockExclusive@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140016bde  mov     rcx, [rdi+110h]
0x140016be5  lea     r8, [rsp+48h+arg_8]
0x140016bea  xor     edx, edx
0x140016bec  call    ?SetStopResult@?$ActivityData@VMDMPushProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MDMPushProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x140016bf1  lea     rcx, [rsp+48h+arg_0]
0x140016bf6  mov     bl, al
0x140016bf8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140016bfd  test    bl, bl
0x140016bff  jz      short loc_140016C0F
0x140016c01  mov     edx, [rsp+48h+arg_8]
0x140016c05  mov     rcx, rdi
0x140016c08  call    ?ReportStopActivity@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x140016c0d  jmp     short loc_140016C71
0x140016c0f  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140016c14  mov     rbx, rax
0x140016c17  mov     ecx, [rax]
0x140016c19  cmp     ecx, 5
0x140016c1c  jbe     short loc_140016C71
0x140016c1e  call    cs:__imp_GetCurrentThreadId
0x140016c24  mov     r8, [rdi+110h]
0x140016c2b  lea     rdx, byte_14001F059
0x140016c32  mov     [rsp+48h+arg_8], eax
0x140016c36  add     r8, 8
0x140016c3a  lea     rax, [rsp+48h+arg_8]
0x140016c3f  mov     dword ptr [rsp+48h+arg_0], 0
0x140016c47  mov     [rsp+48h+var_18], rax
0x140016c4c  mov     rcx, rbx
0x140016c4f  lea     rax, [rsp+48h+arg_0]
0x140016c54  mov     [rsp+48h+arg_10], 1000000h
0x140016c5d  mov     [rsp+48h+var_20], rax
0x140016c62  lea     rax, [rsp+48h+arg_10]
0x140016c67  mov     [rsp+48h+var_28], rax
0x140016c6c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140016c71  mov     rcx, rdi
0x140016c74  mov     rbx, [rsp+48h+arg_18]
0x140016c79  add     rsp, 40h
0x140016c7d  pop     rdi
0x140016c7e  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
