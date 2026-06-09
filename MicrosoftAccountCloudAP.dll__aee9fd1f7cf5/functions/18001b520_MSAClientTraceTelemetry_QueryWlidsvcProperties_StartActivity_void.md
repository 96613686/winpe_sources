# MSAClientTraceTelemetry::QueryWlidsvcProperties::StartActivity(void)

- ea: `0x18001b520`
- end: `0x18001b60b`
- name: `?StartActivity@QueryWlidsvcProperties@MSAClientTraceTelemetry@@QEAAXXZ`
- size: `235`
- prototype: `void __fastcall(MSAClientTraceTelemetry::QueryWlidsvcProperties *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180019a2c`

## callees

- `0x180001aa8`
- `0x18000862c`
- `0x18001a89c`
- `0x18001acec`
- `0x18001b520`
- `0x18001b614`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b583`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b583`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001b555`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001b555`

## pseudocode

```c
void __fastcall MSAClientTraceTelemetry::QueryWlidsvcProperties::StartActivity(
        MSAClientTraceTelemetry::QueryWlidsvcProperties *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rdi
  __int64 v4; // r8
  __int64 v5; // r9
  RTL_SRWLOCK *v6; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v6);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)MSAClientTraceTelemetry::Provider() <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
  v3 = MSAClientTraceTelemetry::Provider();
  if ( *(_DWORD *)v3 > 5u )
  {
    LODWORD(v6) = GetCurrentThreadId();
    v7 = 0x1000000;
    v4 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v4 + 4)
      || (v5 = v4 + 24, !*(_DWORD *)(v4 + 24))
      && !*(_DWORD *)(v4 + 28)
      && !*(_DWORD *)(v4 + 32)
      && !*(_DWORD *)(v4 + 36) )
    {
      v5 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)v3,
      (__int64)&dword_18004535C,
      v4 + 8,
      v5,
      (__int64)&v7,
      (__int64)&v6);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((MSAClientTraceTelemetry::QueryWlidsvcProperties *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001b520  mov     [rsp+arg_10], rbx
0x18001b525  push    rdi
0x18001b526  sub     rsp, 30h
0x18001b52a  mov     rbx, rcx
0x18001b52d  lea     rdx, [rsp+38h+arg_0]
0x18001b532  call    ?LockExclusive@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001b537  mov     rdi, [rbx+110h]
0x18001b53e  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x18001b543  mov     r8d, [rax]
0x18001b546  cmp     r8d, 5
0x18001b54a  jbe     short loc_18001B55D
0x18001b54c  lea     rdx, [rdi+8]; ActivityId
0x18001b550  mov     ecx, 3; ControlCode
0x18001b555  call    cs:__imp_EventActivityIdControl
0x18001b55b  jmp     short loc_18001B564
0x18001b55d  xorps   xmm0, xmm0
0x18001b560  movups  xmmword ptr [rdi+8], xmm0
0x18001b564  mov     dword ptr [rdi], 1
0x18001b56a  lea     rcx, [rsp+38h+arg_0]
0x18001b56f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001b574  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x18001b579  mov     rdi, rax
0x18001b57c  mov     ecx, [rax]
0x18001b57e  cmp     ecx, 5
0x18001b581  jbe     short loc_18001B5ED
0x18001b583  call    cs:__imp_GetCurrentThreadId
0x18001b589  mov     dword ptr [rsp+38h+arg_0], eax
0x18001b58d  mov     [rsp+38h+arg_8], 1000000h
0x18001b596  mov     r8, [rbx+110h]
0x18001b59d  cmp     byte ptr [r8+4], 0
0x18001b5a2  jz      short loc_18001B5C3
0x18001b5a4  lea     r9, [r8+18h]
0x18001b5a8  cmp     dword ptr [r9], 0
0x18001b5ac  jnz     short loc_18001B5C6
0x18001b5ae  cmp     dword ptr [r9+4], 0
0x18001b5b3  jnz     short loc_18001B5C6
0x18001b5b5  cmp     dword ptr [r9+8], 0
0x18001b5ba  jnz     short loc_18001B5C6
0x18001b5bc  cmp     dword ptr [r9+0Ch], 0
0x18001b5c1  jnz     short loc_18001B5C6
0x18001b5c3  xor     r9d, r9d
0x18001b5c6  add     r8, 8
0x18001b5ca  lea     rax, [rsp+38h+arg_0]
0x18001b5cf  mov     [rsp+38h+var_10], rax
0x18001b5d4  lea     rax, [rsp+38h+arg_8]
0x18001b5d9  mov     [rsp+38h+var_18], rax
0x18001b5de  lea     rdx, dword_18004535C
0x18001b5e5  mov     rcx, rdi
0x18001b5e8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001b5ed  lea     rcx, [rbx+120h]; this
0x18001b5f4  cmp     dword ptr [rcx+18h], 0
0x18001b5f8  jnz     short loc_18001B600
0x18001b5fa  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001b5ff  nop
0x18001b600  mov     rbx, [rsp+38h+arg_10]
0x18001b605  add     rsp, 30h
0x18001b609  pop     rdi
0x18001b60a  retn
```
