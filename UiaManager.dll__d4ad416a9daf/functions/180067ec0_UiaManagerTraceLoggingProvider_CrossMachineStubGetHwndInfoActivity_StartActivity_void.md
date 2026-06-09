# UiaManagerTraceLoggingProvider::CrossMachineStubGetHwndInfoActivity::StartActivity(void)

- ea: `0x180067ec0`
- end: `0x180067ff6`
- name: `?StartActivity@CrossMachineStubGetHwndInfoActivity@UiaManagerTraceLoggingProvider@@QEAAXXZ`
- size: `310`
- prototype: `void __fastcall(UiaManagerTraceLoggingProvider::CrossMachineStubGetHwndInfoActivity *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18005da18`

## callees

- `0x18000c7f0`
- `0x18000dc9c`
- `0x180025c48`
- `0x180043680`
- `0x180066b54`
- `0x180067ec0`
- `0x180067ffc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067f40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067f40`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180067f0f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180067f0f`

## pseudocode

```c
void __fastcall UiaManagerTraceLoggingProvider::CrossMachineStubGetHwndInfoActivity::StartActivity(
        UiaManagerTraceLoggingProvider::CrossMachineStubGetHwndInfoActivity *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rdi
  __int64 v4; // r8
  const GUID *v5; // r9
  DWORD CurrentThreadId; // [rsp+30h] [rbp-9h] BYREF
  __int64 v7; // [rsp+38h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp+7h] BYREF
  __int64 *v9; // [rsp+60h] [rbp+27h]
  __int64 v10; // [rsp+68h] [rbp+2Fh]
  DWORD *p_CurrentThreadId; // [rsp+70h] [rbp+37h]
  __int64 v12; // [rsp+78h] [rbp+3Fh]

  wil::ActivityBase<UiaManagerTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &CurrentThreadId);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)UiaManagerTraceLoggingProvider::Provider() <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&CurrentThreadId);
  v3 = UiaManagerTraceLoggingProvider::Provider();
  if ( *(_DWORD *)v3 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = 0;
    v4 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v4 + 4)
      || (v5 = (const GUID *)(v4 + 24), !*(_DWORD *)(v4 + 24))
      && !*(_DWORD *)(v4 + 28)
      && !*(_DWORD *)(v4 + 32)
      && !*(_DWORD *)(v4 + 36) )
    {
      v5 = 0;
    }
    p_CurrentThreadId = &CurrentThreadId;
    v12 = 4;
    v9 = &v7;
    v10 = 8;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)v3,
      (unsigned __int8 *)byte_1800AD1FD,
      (const GUID *)(v4 + 8),
      v5,
      4u,
      &v8);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((UiaManagerTraceLoggingProvider::CrossMachineStubGetHwndInfoActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x180067ec0  mov     [rsp-8+arg_8], rbx
0x180067ec5  mov     [rsp-8+arg_10], rdi
0x180067eca  push    rbp
0x180067ecb  lea     rbp, [rsp-57h]
0x180067ed0  sub     rsp, 90h
0x180067ed7  mov     rax, cs:__security_cookie
0x180067ede  xor     rax, rsp
0x180067ee1  mov     [rbp+57h+var_10], rax
0x180067ee5  mov     rbx, rcx
0x180067ee8  lea     rdx, [rbp+57h+var_60]
0x180067eec  call    ?LockExclusive@?$ActivityBase@VUiaManagerTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<UiaManagerTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180067ef1  mov     rdi, [rbx+110h]
0x180067ef8  call    ?Provider@UiaManagerTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; UiaManagerTraceLoggingProvider::Provider(void)
0x180067efd  mov     r8d, [rax]
0x180067f00  cmp     r8d, 5
0x180067f04  jbe     short loc_180067F17
0x180067f06  lea     rdx, [rdi+8]; ActivityId
0x180067f0a  mov     ecx, 3; ControlCode
0x180067f0f  call    cs:__imp_EventActivityIdControl
0x180067f15  jmp     short loc_180067F1E
0x180067f17  xorps   xmm0, xmm0
0x180067f1a  movups  xmmword ptr [rdi+8], xmm0
0x180067f1e  mov     dword ptr [rdi], 1
0x180067f24  lea     rcx, [rbp+57h+var_60]
0x180067f28  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180067f2d  call    ?Provider@UiaManagerTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; UiaManagerTraceLoggingProvider::Provider(void)
0x180067f32  mov     rdi, rax
0x180067f35  mov     ecx, [rax]
0x180067f37  cmp     ecx, 5
0x180067f3a  jbe     loc_180067FC2
0x180067f40  call    cs:__imp_GetCurrentThreadId
0x180067f46  mov     [rbp+57h+var_60], eax
0x180067f49  mov     [rbp+57h+var_58], 0
0x180067f51  mov     r8, [rbx+110h]
0x180067f58  cmp     byte ptr [r8+4], 0
0x180067f5d  jz      short loc_180067F7E
0x180067f5f  lea     r9, [r8+18h]
0x180067f63  cmp     dword ptr [r9], 0
0x180067f67  jnz     short loc_180067F81
0x180067f69  cmp     dword ptr [r9+4], 0
0x180067f6e  jnz     short loc_180067F81
0x180067f70  cmp     dword ptr [r9+8], 0
0x180067f75  jnz     short loc_180067F81
0x180067f77  cmp     dword ptr [r9+0Ch], 0
0x180067f7c  jnz     short loc_180067F81
0x180067f7e  xor     r9d, r9d
0x180067f81  lea     rax, [rbp+57h+var_60]
0x180067f85  mov     [rbp+57h+var_20], rax
0x180067f89  mov     ecx, 4
0x180067f8e  mov     [rbp+57h+var_18], rcx
0x180067f92  lea     rax, [rbp+57h+var_58]
0x180067f96  mov     [rbp+57h+var_30], rax
0x180067f9a  mov     [rbp+57h+var_28], 8
0x180067fa2  add     r8, 8
0x180067fa6  lea     rax, [rbp+57h+var_50]
0x180067faa  mov     [rsp+90h+var_68], rax
0x180067faf  mov     [rsp+90h+var_70], ecx
0x180067fb3  lea     rdx, byte_1800AD1FD
0x180067fba  mov     rcx, rdi
0x180067fbd  call    _tlgWriteTransfer_EventWriteTransfer
0x180067fc2  lea     rcx, [rbx+120h]; this
0x180067fc9  cmp     dword ptr [rcx+18h], 0
0x180067fcd  jnz     short loc_180067FD5
0x180067fcf  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180067fd4  nop
0x180067fd5  mov     rcx, [rbp+57h+var_10]
0x180067fd9  xor     rcx, rsp; StackCookie
0x180067fdc  call    __security_check_cookie
0x180067fe1  lea     r11, [rsp+90h+var_s0]
0x180067fe9  mov     rbx, [r11+18h]
0x180067fed  mov     rdi, [r11+20h]
0x180067ff1  mov     rsp, r11
0x180067ff4  pop     rbp
0x180067ff5  retn
```
