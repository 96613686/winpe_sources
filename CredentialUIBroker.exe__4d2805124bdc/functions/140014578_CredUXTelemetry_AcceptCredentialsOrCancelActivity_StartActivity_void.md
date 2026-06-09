# CredUXTelemetry::AcceptCredentialsOrCancelActivity::StartActivity(void)

- ea: `0x140014578`
- end: `0x14001467c`
- name: `?StartActivity@AcceptCredentialsOrCancelActivity@CredUXTelemetry@@QEAAXXZ`
- size: `260`
- prototype: `void __fastcall(CredUXTelemetry::AcceptCredentialsOrCancelActivity *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1400111ac`

## callees

- `0x140002370`
- `0x140002f8c`
- `0x140009158`
- `0x14000ed00`
- `0x140011a60`
- `0x140014578`
- `0x140014a54`
- `0x140018fc0`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x1400145c1`
- `ADVAPI32!EventActivityIdControl` at `0x1400145c1`
- `KERNEL32!GetCurrentThreadId` at `0x140014605`
- `KERNEL32!GetCurrentThreadId` at `0x140014605`

## pseudocode

```c
void __fastcall CredUXTelemetry::AcceptCredentialsOrCancelActivity::StartActivity(
        CredUXTelemetry::AcceptCredentialsOrCancelActivity *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  __int64 v12; // rcx
  RTL_SRWLOCK *v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v13);
  v2 = *((_QWORD *)this + 34);
  v3 = CredUXLogging::Provider();
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x200000000000LL, v4, v5) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  v6 = CredUXLogging::Provider();
  v9 = (__int64)v6;
  if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x200000000000LL, v7, v8) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v11 = *((_QWORD *)this + 34);
    LODWORD(v13) = CurrentThreadId;
    v14 = 50331648;
    if ( !*(_BYTE *)(v11 + 4) || _tlgGuidIsZero((const struct _GUID *)(v11 + 24)) )
      v12 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v9,
      (__int64)byte_140025B03,
      v11 + 8,
      v12,
      (__int64)&v14,
      (__int64)&v13);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((CredUXTelemetry::AcceptCredentialsOrCancelActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x140014578  mov     [rsp+arg_10], rbx
0x14001457d  push    rdi
0x14001457e  sub     rsp, 30h
0x140014582  lea     rdx, [rsp+38h+arg_0]
0x140014587  mov     rbx, rcx
0x14001458a  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14001458f  mov     rdi, [rbx+110h]
0x140014596  call    ?Provider@CredUXLogging@@SAPEBU_tlgProvider_t@@XZ; CredUXLogging::Provider(void)
0x14001459b  mov     edx, [rax]
0x14001459d  cmp     edx, 5
0x1400145a0  jbe     short loc_1400145C9
0x1400145a2  mov     rdx, 200000000000h
0x1400145ac  mov     rcx, rax
0x1400145af  call    _tlgKeywordOn
0x1400145b4  test    al, al
0x1400145b6  jz      short loc_1400145C9
0x1400145b8  lea     rdx, [rdi+8]; ActivityId
0x1400145bc  mov     ecx, 3; ControlCode
0x1400145c1  call    cs:__imp_EventActivityIdControl
0x1400145c7  jmp     short loc_1400145D0
0x1400145c9  xorps   xmm0, xmm0
0x1400145cc  movups  xmmword ptr [rdi+8], xmm0
0x1400145d0  lea     rcx, [rsp+38h+arg_0]
0x1400145d5  mov     dword ptr [rdi], 1
0x1400145db  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400145e0  call    ?Provider@CredUXLogging@@SAPEBU_tlgProvider_t@@XZ; CredUXLogging::Provider(void)
0x1400145e5  mov     rdi, rax
0x1400145e8  mov     ecx, [rax]
0x1400145ea  cmp     ecx, 5
0x1400145ed  jbe     short loc_14001465F
0x1400145ef  mov     rdx, 200000000000h
0x1400145f9  mov     rcx, rax
0x1400145fc  call    _tlgKeywordOn
0x140014601  test    al, al
0x140014603  jz      short loc_14001465F
0x140014605  call    cs:__imp_GetCurrentThreadId
0x14001460b  mov     r8, [rbx+110h]
0x140014612  mov     dword ptr [rsp+38h+arg_0], eax
0x140014616  mov     [rsp+38h+arg_8], 3000000h
0x14001461f  cmp     byte ptr [r8+4], 0
0x140014624  jz      short loc_140014633
0x140014626  lea     rcx, [r8+18h]; struct _GUID *
0x14001462a  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x14001462f  test    al, al
0x140014631  jz      short loc_140014635
0x140014633  xor     ecx, ecx
0x140014635  lea     rax, [rsp+38h+arg_0]
0x14001463a  mov     r9, rcx
0x14001463d  mov     [rsp+38h+var_10], rax
0x140014642  lea     rdx, byte_140025B03
0x140014649  lea     rax, [rsp+38h+arg_8]
0x14001464e  add     r8, 8
0x140014652  mov     rcx, rdi
0x140014655  mov     [rsp+38h+var_18], rax
0x14001465a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x14001465f  lea     rcx, [rbx+120h]; this
0x140014666  cmp     dword ptr [rcx+18h], 0
0x14001466a  jnz     short loc_140014671
0x14001466c  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x140014671  mov     rbx, [rsp+38h+arg_10]
0x140014676  add     rsp, 30h
0x14001467a  pop     rdi
0x14001467b  retn
```
