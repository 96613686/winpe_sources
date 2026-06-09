# wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)

- ea: `0x18001effc`
- end: `0x18001f066`
- name: `?zInternalStart@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `106`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001997c`
- `0x180019a3c`
- `0x180019afc`
- `0x180019bbc`
- `0x180019c7c`
- `0x180019d3c`
- `0x180019dfc`

## callees

- `0x180001acc`
- `0x180011488`
- `0x18001608c`
- `0x180016fc0`
- `0x18001effc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001f041`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001f041`

## pseudocode

```c
void __fastcall wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(
        __int64 a1)
{
  __int64 v2; // rbx
  _DWORD *v3; // rax
  __int64 v4; // r8
  RTL_SRWLOCK *v5; // [rsp+30h] [rbp+8h] BYREF

  wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v5);
  v2 = *(_QWORD *)(a1 + 272);
  v3 = (_DWORD *)wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CoreGlobConfigTraceLogging,_TlgReflectorTag_Param0IsProviderType>::Provider();
  if ( *v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x200000000000LL, v4) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v5);
}

```

## disassembly

```asm
0x18001effc  push    rbx
0x18001effe  sub     rsp, 20h
0x18001f002  lea     rdx, [rsp+28h+arg_0]
0x18001f007  mov     rbx, rcx
0x18001f00a  call    ?LockExclusive@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001f00f  mov     rbx, [rbx+110h]
0x18001f016  call    ?Provider@?$ActivityData@VCoreGlobConfigTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@SAPEBU_tlgProvider_t@@XZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CoreGlobConfigTraceLogging,_TlgReflectorTag_Param0IsProviderType>::Provider(void)
0x18001f01b  mov     ecx, [rax]
0x18001f01d  cmp     ecx, 5
0x18001f020  jbe     short loc_18001F049
0x18001f022  mov     rdx, 200000000000h
0x18001f02c  mov     rcx, rax
0x18001f02f  call    _tlgKeywordOn
0x18001f034  test    al, al
0x18001f036  jz      short loc_18001F049
0x18001f038  lea     rdx, [rbx+8]; ActivityId
0x18001f03c  mov     ecx, 3; ControlCode
0x18001f041  call    cs:__imp_EventActivityIdControl
0x18001f047  jmp     short loc_18001F050
0x18001f049  xorps   xmm0, xmm0
0x18001f04c  movups  xmmword ptr [rbx+8], xmm0
0x18001f050  lea     rcx, [rsp+28h+arg_0]
0x18001f055  mov     dword ptr [rbx], 1
0x18001f05b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001f060  add     rsp, 20h
0x18001f064  pop     rbx
0x18001f065  retn
```
