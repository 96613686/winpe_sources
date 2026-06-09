# wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)

- ea: `0x14001c0fc`
- end: `0x14001c166`
- name: `?zInternalStart@?$ActivityBase@VCredUIBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140014684`
- `0x140014730`

## callees

- `0x140002f8c`
- `0x140009158`
- `0x14000ed00`
- `0x140011a1c`
- `0x14001c0fc`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x14001c141`
- `ADVAPI32!EventActivityIdControl` at `0x14001c141`

## pseudocode

```c
void __fastcall wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(
        __int64 a1)
{
  __int64 v2; // rbx
  _DWORD *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  RTL_SRWLOCK *v6; // [rsp+30h] [rbp+8h] BYREF

  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v6);
  v2 = *(_QWORD *)(a1 + 272);
  v3 = (_DWORD *)wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CredUIBrokerLogging,_TlgReflectorTag_Param0IsProviderType>::Provider();
  if ( *v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x200000000000LL, v4, v5) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
}

```

## disassembly

```asm
0x14001c0fc  push    rbx
0x14001c0fe  sub     rsp, 20h
0x14001c102  lea     rdx, [rsp+28h+arg_0]
0x14001c107  mov     rbx, rcx
0x14001c10a  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14001c10f  mov     rbx, [rbx+110h]
0x14001c116  call    ?Provider@?$ActivityData@VCredUIBrokerLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCredUIBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@SAPEBU_tlgProvider_t@@XZ; wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CredUIBrokerLogging,_TlgReflectorTag_Param0IsProviderType>::Provider(void)
0x14001c11b  mov     ecx, [rax]
0x14001c11d  cmp     ecx, 5
0x14001c120  jbe     short loc_14001C149
0x14001c122  mov     rdx, 200000000000h
0x14001c12c  mov     rcx, rax
0x14001c12f  call    _tlgKeywordOn
0x14001c134  test    al, al
0x14001c136  jz      short loc_14001C149
0x14001c138  lea     rdx, [rbx+8]; ActivityId
0x14001c13c  mov     ecx, 3; ControlCode
0x14001c141  call    cs:__imp_EventActivityIdControl
0x14001c147  jmp     short loc_14001C150
0x14001c149  xorps   xmm0, xmm0
0x14001c14c  movups  xmmword ptr [rbx+8], xmm0
0x14001c150  lea     rcx, [rsp+28h+arg_0]
0x14001c155  mov     dword ptr [rbx], 1
0x14001c15b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14001c160  add     rsp, 20h
0x14001c164  pop     rbx
0x14001c165  retn
```
