# NetworkUxTelemetry::SetAirplaneMode::StartActivity(void)

- ea: `0x18003104c`
- end: `0x1800311b2`
- name: `?StartActivity@SetAirplaneMode@NetworkUxTelemetry@@QEAAXXZ`
- size: `358`
- prototype: `void __fastcall(NetworkUxTelemetry::SetAirplaneMode *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180030b60`

## callees

- `0x180001dfc`
- `0x180001e28`
- `0x180002520`
- `0x1800285e4`
- `0x18002d858`
- `0x18003104c`
- `0x180031204`
- `0x1800356dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800310fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800310fc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800310b0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800310b0`

## pseudocode

```c
void __fastcall NetworkUxTelemetry::SetAirplaneMode::StartActivity(NetworkUxTelemetry::SetAirplaneMode *this)
{
  __int64 v2; // rbx
  _DWORD *v3; // rcx
  __int64 v4; // r8
  _DWORD *v5; // rbx
  __int64 v6; // r8
  __int64 v7; // r8
  const GUID *v8; // r9
  RTL_SRWLOCK *v9; // [rsp+30h] [rbp-9h] BYREF
  __int64 v10; // [rsp+38h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+40h] [rbp+7h] BYREF
  __int64 *v12; // [rsp+60h] [rbp+27h]
  __int64 v13; // [rsp+68h] [rbp+2Fh]
  RTL_SRWLOCK **v14; // [rsp+70h] [rbp+37h]
  __int64 v15; // [rsp+78h] [rbp+3Fh]

  wil::ActivityBase<NetworkUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v9);
  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD **)(wil::details::static_lazy<NetworkUxLogging>::get() + 8);
  if ( *v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL, v4) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  v5 = *(_DWORD **)(wil::details::static_lazy<NetworkUxLogging>::get() + 8);
  if ( *v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL, v6) )
  {
    LODWORD(v9) = GetCurrentThreadId();
    v10 = 0;
    v7 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v7 + 4)
      || (v8 = (const GUID *)(v7 + 24), !*(_DWORD *)(v7 + 24))
      && !*(_DWORD *)(v7 + 28)
      && !*(_DWORD *)(v7 + 32)
      && !*(_DWORD *)(v7 + 36) )
    {
      v8 = 0;
    }
    v14 = &v9;
    v15 = 4;
    v12 = &v10;
    v13 = 8;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)v5,
      (unsigned __int8 *)qword_180074AB0,
      (const GUID *)(v7 + 8),
      v8,
      4u,
      &v11);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((NetworkUxTelemetry::SetAirplaneMode *)((char *)this + 288));
}

```

## disassembly

```asm
0x18003104c  mov     [rsp-8+arg_8], rbx
0x180031051  mov     [rsp-8+arg_10], rdi
0x180031056  push    rbp
0x180031057  lea     rbp, [rsp-57h]
0x18003105c  sub     rsp, 90h
0x180031063  mov     rax, cs:__security_cookie
0x18003106a  xor     rax, rsp
0x18003106d  mov     [rbp+57h+var_10], rax
0x180031071  mov     rdi, rcx
0x180031074  lea     rdx, [rbp+57h+var_60]
0x180031078  call    ?LockExclusive@?$ActivityBase@VNetworkUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<NetworkUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003107d  mov     rbx, [rdi+110h]
0x180031084  call    ?get@?$static_lazy@VNetworkUxLogging@@@details@wil@@QEAAPEAVNetworkUxLogging@@P6AXXZ@Z; wil::details::static_lazy<NetworkUxLogging>::get(void (*)(void))
0x180031089  mov     rcx, [rax+8]
0x18003108d  mov     eax, [rcx]
0x18003108f  cmp     eax, 5
0x180031092  jbe     short loc_1800310B8
0x180031094  mov     rdx, 400000000000h
0x18003109e  call    _tlgKeywordOn
0x1800310a3  test    al, al
0x1800310a5  jz      short loc_1800310B8
0x1800310a7  lea     rdx, [rbx+8]; ActivityId
0x1800310ab  mov     ecx, 3; ControlCode
0x1800310b0  call    cs:__imp_EventActivityIdControl
0x1800310b6  jmp     short loc_1800310BF
0x1800310b8  xorps   xmm0, xmm0
0x1800310bb  movups  xmmword ptr [rbx+8], xmm0
0x1800310bf  mov     dword ptr [rbx], 1
0x1800310c5  lea     rcx, [rbp+57h+var_60]
0x1800310c9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800310ce  call    ?get@?$static_lazy@VNetworkUxLogging@@@details@wil@@QEAAPEAVNetworkUxLogging@@P6AXXZ@Z; wil::details::static_lazy<NetworkUxLogging>::get(void (*)(void))
0x1800310d3  mov     rbx, [rax+8]
0x1800310d7  mov     eax, [rbx]
0x1800310d9  cmp     eax, 5
0x1800310dc  jbe     loc_18003117E
0x1800310e2  mov     rdx, 400000000000h
0x1800310ec  mov     rcx, rbx
0x1800310ef  call    _tlgKeywordOn
0x1800310f4  test    al, al
0x1800310f6  jz      loc_18003117E
0x1800310fc  call    cs:__imp_GetCurrentThreadId
0x180031102  mov     dword ptr [rbp+57h+var_60], eax
0x180031105  mov     [rbp+57h+var_58], 0
0x18003110d  mov     r8, [rdi+110h]
0x180031114  cmp     byte ptr [r8+4], 0
0x180031119  jz      short loc_18003113A
0x18003111b  lea     r9, [r8+18h]
0x18003111f  cmp     dword ptr [r9], 0
0x180031123  jnz     short loc_18003113D
0x180031125  cmp     dword ptr [r9+4], 0
0x18003112a  jnz     short loc_18003113D
0x18003112c  cmp     dword ptr [r9+8], 0
0x180031131  jnz     short loc_18003113D
0x180031133  cmp     dword ptr [r9+0Ch], 0
0x180031138  jnz     short loc_18003113D
0x18003113a  xor     r9d, r9d
0x18003113d  lea     rax, [rbp+57h+var_60]
0x180031141  mov     [rbp+57h+var_20], rax
0x180031145  mov     ecx, 4
0x18003114a  mov     [rbp+57h+var_18], rcx
0x18003114e  lea     rax, [rbp+57h+var_58]
0x180031152  mov     [rbp+57h+var_30], rax
0x180031156  mov     [rbp+57h+var_28], 8
0x18003115e  add     r8, 8
0x180031162  lea     rax, [rbp+57h+var_50]
0x180031166  mov     [rsp+90h+var_68], rax
0x18003116b  mov     [rsp+90h+var_70], ecx
0x18003116f  lea     rdx, qword_180074AB0
0x180031176  mov     rcx, rbx
0x180031179  call    _tlgWriteTransfer_EventWriteTransfer
0x18003117e  lea     rcx, [rdi+120h]; this
0x180031185  cmp     dword ptr [rcx+18h], 0
0x180031189  jnz     short loc_180031191
0x18003118b  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180031190  nop
0x180031191  mov     rcx, [rbp+57h+var_10]
0x180031195  xor     rcx, rsp; StackCookie
0x180031198  call    __security_check_cookie
0x18003119d  lea     r11, [rsp+90h+var_s0]
0x1800311a5  mov     rbx, [r11+18h]
0x1800311a9  mov     rdi, [r11+20h]
0x1800311ad  mov     rsp, r11
0x1800311b0  pop     rbp
0x1800311b1  retn
```
