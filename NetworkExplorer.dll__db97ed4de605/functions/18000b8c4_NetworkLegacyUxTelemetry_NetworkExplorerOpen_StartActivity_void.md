# NetworkLegacyUxTelemetry::NetworkExplorerOpen::StartActivity(void)

- ea: `0x18000b8c4`
- end: `0x18000ba28`
- name: `?StartActivity@NetworkExplorerOpen@NetworkLegacyUxTelemetry@@QEAAXXZ`
- size: `356`
- prototype: `void __fastcall(NetworkLegacyUxTelemetry::NetworkExplorerOpen *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000c984`

## callees

- `0x180001008`
- `0x1800019ac`
- `0x180008bf0`
- `0x18000a218`
- `0x18000ac88`
- `0x18000b8c4`
- `0x18000ba30`
- `0x18000f0a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b972`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b972`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000b927`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000b927`

## pseudocode

```c
void __fastcall NetworkLegacyUxTelemetry::NetworkExplorerOpen::StartActivity(
        NetworkLegacyUxTelemetry::NetworkExplorerOpen *this)
{
  __int64 v2; // rbx
  const struct _tlgProvider_t *v3; // rax
  const struct _tlgProvider_t *v4; // rax
  const struct _tlgProvider_t *v5; // rbx
  __int64 v6; // r8
  DWORD CurrentThreadId; // [rsp+30h] [rbp-9h] BYREF
  _QWORD v8[9]; // [rsp+38h] [rbp-1h] BYREF

  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &CurrentThreadId);
  v2 = *((_QWORD *)this + 34);
  v3 = NetworkLegacyUxLogging::Provider();
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&CurrentThreadId);
  v4 = NetworkLegacyUxLogging::Provider();
  v5 = v4;
  if ( *(_DWORD *)v4 > 5u && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v8[0] = 0;
    v6 = *((_QWORD *)this + 34);
    v8[7] = &CurrentThreadId;
    v8[8] = 4;
    v8[5] = v8;
    v8[6] = 8;
    tlgWriteTransfer_EventWriteTransfer(v5, byte_180014B33, v6 + 8);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((NetworkLegacyUxTelemetry::NetworkExplorerOpen *)((char *)this + 288));
}

```

## disassembly

```asm
0x18000b8c4  mov     [rsp-8+arg_8], rbx
0x18000b8c9  mov     [rsp-8+arg_10], rdi
0x18000b8ce  push    rbp
0x18000b8cf  lea     rbp, [rsp-57h]
0x18000b8d4  sub     rsp, 90h
0x18000b8db  mov     rax, cs:__security_cookie
0x18000b8e2  xor     rax, rsp
0x18000b8e5  mov     [rbp+57h+var_10], rax
0x18000b8e9  mov     rdi, rcx
0x18000b8ec  lea     rdx, [rbp+57h+var_60]
0x18000b8f0  call    ?LockExclusive@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b8f5  mov     rbx, [rdi+110h]
0x18000b8fc  call    ?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ; NetworkLegacyUxLogging::Provider(void)
0x18000b901  mov     edx, [rax]
0x18000b903  cmp     edx, 5
0x18000b906  jbe     short loc_18000B92F
0x18000b908  mov     rdx, 400000000000h
0x18000b912  mov     rcx, rax
0x18000b915  call    _tlgKeywordOn
0x18000b91a  test    al, al
0x18000b91c  jz      short loc_18000B92F
0x18000b91e  lea     rdx, [rbx+8]; ActivityId
0x18000b922  mov     ecx, 3; ControlCode
0x18000b927  call    cs:__imp_EventActivityIdControl
0x18000b92d  jmp     short loc_18000B936
0x18000b92f  xorps   xmm0, xmm0
0x18000b932  movups  xmmword ptr [rbx+8], xmm0
0x18000b936  mov     dword ptr [rbx], 1
0x18000b93c  lea     rcx, [rbp+57h+var_60]
0x18000b940  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b945  call    ?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ; NetworkLegacyUxLogging::Provider(void)
0x18000b94a  mov     rbx, rax
0x18000b94d  mov     ecx, [rax]
0x18000b94f  cmp     ecx, 5
0x18000b952  jbe     loc_18000B9F4
0x18000b958  mov     rdx, 400000000000h
0x18000b962  mov     rcx, rax
0x18000b965  call    _tlgKeywordOn
0x18000b96a  test    al, al
0x18000b96c  jz      loc_18000B9F4
0x18000b972  call    cs:__imp_GetCurrentThreadId
0x18000b978  mov     [rbp+57h+var_60], eax
0x18000b97b  mov     [rbp+57h+var_58], 0
0x18000b983  mov     r8, [rdi+110h]
0x18000b98a  cmp     byte ptr [r8+4], 0
0x18000b98f  jz      short loc_18000B9B0
0x18000b991  lea     r9, [r8+18h]
0x18000b995  cmp     dword ptr [r9], 0
0x18000b999  jnz     short loc_18000B9B3
0x18000b99b  cmp     dword ptr [r9+4], 0
0x18000b9a0  jnz     short loc_18000B9B3
0x18000b9a2  cmp     dword ptr [r9+8], 0
0x18000b9a7  jnz     short loc_18000B9B3
0x18000b9a9  cmp     dword ptr [r9+0Ch], 0
0x18000b9ae  jnz     short loc_18000B9B3
0x18000b9b0  xor     r9d, r9d
0x18000b9b3  lea     rax, [rbp+57h+var_60]
0x18000b9b7  mov     [rbp+57h+var_20], rax
0x18000b9bb  mov     ecx, 4
0x18000b9c0  mov     [rbp+57h+var_18], rcx
0x18000b9c4  lea     rax, [rbp+57h+var_58]
0x18000b9c8  mov     [rbp+57h+var_30], rax
0x18000b9cc  mov     [rbp+57h+var_28], 8
0x18000b9d4  add     r8, 8
0x18000b9d8  lea     rax, [rbp+57h+var_50]
0x18000b9dc  mov     [rsp+90h+var_68], rax
0x18000b9e1  mov     [rsp+90h+var_70], ecx
0x18000b9e5  lea     rdx, byte_180014B33
0x18000b9ec  mov     rcx, rbx
0x18000b9ef  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b9f4  lea     rcx, [rdi+120h]; this
0x18000b9fb  cmp     dword ptr [rcx+18h], 0
0x18000b9ff  jnz     short loc_18000BA07
0x18000ba01  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000ba06  nop
0x18000ba07  mov     rcx, [rbp+57h+var_10]
0x18000ba0b  xor     rcx, rsp; StackCookie
0x18000ba0e  call    __security_check_cookie
0x18000ba13  lea     r11, [rsp+90h+var_s0]
0x18000ba1b  mov     rbx, [r11+18h]
0x18000ba1f  mov     rdi, [r11+20h]
0x18000ba23  mov     rsp, r11
0x18000ba26  pop     rbp
0x18000ba27  retn
```
