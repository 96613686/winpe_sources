# LogProvider::NgcIsoContainerRemoveProtector::StartActivity(NgcCtnrProtectorId)

- ea: `0x180031c9c`
- end: `0x180031dad`
- name: `?StartActivity@NgcIsoContainerRemoveProtector@LogProvider@@QEAAXW4NgcCtnrProtectorId@@@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002fcc0`

## callees

- `0x1800019bc`
- `0x180001de4`
- `0x18000a168`
- `0x18001133c`
- `0x180015108`
- `0x180016374`
- `0x180016828`
- `0x180031c9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031d2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031d2f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180031ce7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180031ce7`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoContainerRemoveProtector::StartActivity(__int64 a1, int a2)
{
  __int64 v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // edi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // ecx
  int v15; // [rsp+60h] [rbp+8h] BYREF
  DWORD v16; // [rsp+70h] [rbp+18h] BYREF
  __int64 v17; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<LogProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v15);
  v4 = *(_QWORD *)(a1 + 272);
  v5 = LogProvider::Provider();
  v7 = *(unsigned int *)v5;
  if ( (unsigned int)v7 > 4 && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL, v7, v6) )
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  else
    *(_OWORD *)(v4 + 8) = 0;
  *(_DWORD *)v4 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
  v8 = LogProvider::Provider();
  v11 = (int)v8;
  if ( *(_DWORD *)v8 > 4u && (unsigned __int8)tlgKeywordOn(v8, 0x400000000000LL, v9, v10) )
  {
    v15 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v13 = *(_QWORD *)(a1 + 272);
    v16 = CurrentThreadId;
    v17 = 0x1000000;
    if ( !*(_BYTE *)(v13 + 4) || _tlgGuidIsZero((const struct _GUID *)(v13 + 24)) )
      v14 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v11,
      (unsigned int)&byte_1800ADEEF,
      v13 + 8,
      v14,
      (__int64)&v17,
      (__int64)&v16,
      (__int64)&v15);
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x180031c9c  push    rbx
0x180031c9e  push    rsi
0x180031c9f  push    rdi
0x180031ca0  sub     rsp, 40h
0x180031ca4  mov     esi, edx
0x180031ca6  mov     rbx, rcx
0x180031ca9  lea     rdx, [rsp+58h+arg_0]
0x180031cae  call    ?LockExclusive@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LogProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180031cb3  mov     rdi, [rbx+110h]
0x180031cba  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x180031cbf  mov     r8d, [rax]
0x180031cc2  cmp     r8d, 4
0x180031cc6  jbe     short loc_180031CEF
0x180031cc8  mov     rdx, 400000000000h
0x180031cd2  mov     rcx, rax
0x180031cd5  call    _tlgKeywordOn
0x180031cda  test    al, al
0x180031cdc  jz      short loc_180031CEF
0x180031cde  lea     rdx, [rdi+8]; ActivityId
0x180031ce2  mov     ecx, 3; ControlCode
0x180031ce7  call    cs:__imp_EventActivityIdControl
0x180031ced  jmp     short loc_180031CF6
0x180031cef  xorps   xmm0, xmm0
0x180031cf2  movups  xmmword ptr [rdi+8], xmm0
0x180031cf6  lea     rcx, [rsp+58h+arg_0]
0x180031cfb  mov     dword ptr [rdi], 1
0x180031d01  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180031d06  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x180031d0b  mov     rdi, rax
0x180031d0e  mov     ecx, [rax]
0x180031d10  cmp     ecx, 4
0x180031d13  jbe     short loc_180031D93
0x180031d15  mov     rdx, 400000000000h
0x180031d1f  mov     rcx, rax
0x180031d22  call    _tlgKeywordOn
0x180031d27  test    al, al
0x180031d29  jz      short loc_180031D93
0x180031d2b  mov     [rsp+58h+arg_0], esi
0x180031d2f  call    cs:__imp_GetCurrentThreadId
0x180031d35  mov     r8, [rbx+110h]
0x180031d3c  mov     [rsp+58h+arg_10], eax
0x180031d40  mov     [rsp+58h+arg_18], 1000000h
0x180031d49  cmp     byte ptr [r8+4], 0
0x180031d4e  jz      short loc_180031D5D
0x180031d50  lea     rcx, [r8+18h]; struct _GUID *
0x180031d54  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180031d59  test    al, al
0x180031d5b  jz      short loc_180031D5F
0x180031d5d  xor     ecx, ecx
0x180031d5f  lea     rax, [rsp+58h+arg_0]
0x180031d64  mov     r9, rcx
0x180031d67  mov     [rsp+58h+var_28], rax
0x180031d6c  lea     rdx, byte_1800ADEEF
0x180031d73  lea     rax, [rsp+58h+arg_10]
0x180031d78  add     r8, 8
0x180031d7c  mov     [rsp+58h+var_30], rax
0x180031d81  mov     rcx, rdi
0x180031d84  lea     rax, [rsp+58h+arg_18]
0x180031d89  mov     [rsp+58h+var_38], rax
0x180031d8e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180031d93  lea     rcx, [rbx+120h]; this
0x180031d9a  cmp     dword ptr [rcx+18h], 0
0x180031d9e  jnz     short loc_180031DA5
0x180031da0  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180031da5  add     rsp, 40h
0x180031da9  pop     rdi
0x180031daa  pop     rsi
0x180031dab  pop     rbx
0x180031dac  retn
```
