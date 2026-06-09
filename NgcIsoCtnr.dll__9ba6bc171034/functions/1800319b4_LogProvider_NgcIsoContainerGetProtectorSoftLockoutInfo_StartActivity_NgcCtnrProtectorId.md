# LogProvider::NgcIsoContainerGetProtectorSoftLockoutInfo::StartActivity(NgcCtnrProtectorId)

- ea: `0x1800319b4`
- end: `0x180031ac5`
- name: `?StartActivity@NgcIsoContainerGetProtectorSoftLockoutInfo@LogProvider@@QEAAXW4NgcCtnrProtectorId@@@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002f820`

## callees

- `0x1800019bc`
- `0x180001de4`
- `0x18000a168`
- `0x18001133c`
- `0x180015108`
- `0x180016374`
- `0x180016828`
- `0x1800319b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031a47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031a47`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800319ff`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800319ff`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoContainerGetProtectorSoftLockoutInfo::StartActivity(__int64 a1, int a2)
{
  __int64 v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  int v12; // edi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // ecx
  int v16; // [rsp+60h] [rbp+8h] BYREF
  DWORD v17; // [rsp+70h] [rbp+18h] BYREF
  __int64 v18; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<LogProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v16);
  v4 = *(_QWORD *)(a1 + 272);
  v5 = LogProvider::Provider();
  v7 = *(unsigned int *)v5;
  if ( (unsigned int)v7 > 5 && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL, v7, v6) )
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  else
    *(_OWORD *)(v4 + 8) = 0;
  *(_DWORD *)v4 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
  v8 = LogProvider::Provider();
  v12 = (int)v8;
  if ( *(_DWORD *)v8 > 5u && (unsigned __int8)tlgKeywordOn(v8, 0x400000000000LL, v10, v11) )
  {
    v16 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v14 = *(_QWORD *)(a1 + 272);
    v17 = CurrentThreadId;
    v18 = 16779264;
    if ( !*(_BYTE *)(v14 + 4) || _tlgGuidIsZero((const struct _GUID *)(v14 + 24)) )
      v15 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v12,
      (unsigned int)&dword_1800AE074,
      v14 + 8,
      v15,
      (__int64)&v18,
      (__int64)&v17,
      (__int64)&v16);
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (wil::details::ThreadFailureCallbackHolder *)(a1 + 288),
      v9);
}

```

## disassembly

```asm
0x1800319b4  push    rbx
0x1800319b6  push    rsi
0x1800319b7  push    rdi
0x1800319b8  sub     rsp, 40h
0x1800319bc  mov     esi, edx
0x1800319be  mov     rbx, rcx
0x1800319c1  lea     rdx, [rsp+58h+arg_0]
0x1800319c6  call    ?LockExclusive@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LogProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800319cb  mov     rdi, [rbx+110h]
0x1800319d2  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x1800319d7  mov     r8d, [rax]
0x1800319da  cmp     r8d, 5
0x1800319de  jbe     short loc_180031A07
0x1800319e0  mov     rdx, 400000000000h
0x1800319ea  mov     rcx, rax
0x1800319ed  call    _tlgKeywordOn
0x1800319f2  test    al, al
0x1800319f4  jz      short loc_180031A07
0x1800319f6  lea     rdx, [rdi+8]; ActivityId
0x1800319fa  mov     ecx, 3; ControlCode
0x1800319ff  call    cs:__imp_EventActivityIdControl
0x180031a05  jmp     short loc_180031A0E
0x180031a07  xorps   xmm0, xmm0
0x180031a0a  movups  xmmword ptr [rdi+8], xmm0
0x180031a0e  lea     rcx, [rsp+58h+arg_0]
0x180031a13  mov     dword ptr [rdi], 1
0x180031a19  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180031a1e  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x180031a23  mov     rdi, rax
0x180031a26  mov     ecx, [rax]
0x180031a28  cmp     ecx, 5
0x180031a2b  jbe     short loc_180031AAB
0x180031a2d  mov     rdx, 400000000000h
0x180031a37  mov     rcx, rax
0x180031a3a  call    _tlgKeywordOn
0x180031a3f  test    al, al
0x180031a41  jz      short loc_180031AAB
0x180031a43  mov     [rsp+58h+arg_0], esi
0x180031a47  call    cs:__imp_GetCurrentThreadId
0x180031a4d  mov     r8, [rbx+110h]
0x180031a54  mov     [rsp+58h+arg_10], eax
0x180031a58  mov     [rsp+58h+arg_18], 1000800h
0x180031a61  cmp     byte ptr [r8+4], 0
0x180031a66  jz      short loc_180031A75
0x180031a68  lea     rcx, [r8+18h]; struct _GUID *
0x180031a6c  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180031a71  test    al, al
0x180031a73  jz      short loc_180031A77
0x180031a75  xor     ecx, ecx
0x180031a77  lea     rax, [rsp+58h+arg_0]
0x180031a7c  mov     r9, rcx
0x180031a7f  mov     [rsp+58h+var_28], rax
0x180031a84  lea     rdx, dword_1800AE074
0x180031a8b  lea     rax, [rsp+58h+arg_10]
0x180031a90  add     r8, 8
0x180031a94  mov     [rsp+58h+var_30], rax
0x180031a99  mov     rcx, rdi
0x180031a9c  lea     rax, [rsp+58h+arg_18]
0x180031aa1  mov     [rsp+58h+var_38], rax
0x180031aa6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180031aab  lea     rcx, [rbx+120h]; this
0x180031ab2  cmp     dword ptr [rcx+18h], 0
0x180031ab6  jnz     short loc_180031ABD
0x180031ab8  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180031abd  add     rsp, 40h
0x180031ac1  pop     rdi
0x180031ac2  pop     rsi
0x180031ac3  pop     rbx
0x180031ac4  retn
```
