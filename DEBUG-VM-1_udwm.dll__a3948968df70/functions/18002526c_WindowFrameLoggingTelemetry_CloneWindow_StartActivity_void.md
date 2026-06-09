# WindowFrameLoggingTelemetry::CloneWindow::StartActivity(void)

- ea: `0x18002526c`
- end: `0x18002534a`
- name: `?StartActivity@CloneWindow@WindowFrameLoggingTelemetry@@QEAAXXZ`
- size: `222`
- prototype: `void __fastcall(WindowFrameLoggingTelemetry::CloneWindow *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1800250a0`

## callees

- `0x18002526c`
- `0x18003a18c`
- `0x18005d3ec`
- `0x18005da8c`
- `0x180062d94`
- `0x180062e98`
- `0x18008dee4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800252d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800252d2`
- `ntdll!EtwEventActivityIdControl` at `0x1800252a3`
- `ntdll!EtwEventActivityIdControl` at `0x1800252a3`

## pseudocode

```c
void __fastcall WindowFrameLoggingTelemetry::CloneWindow::StartActivity(WindowFrameLoggingTelemetry::CloneWindow *this)
{
  __int64 v2; // rdi
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdx
  _DWORD *v8; // rdi
  __int64 v9; // r8
  __int64 v10; // rcx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v12; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<WindowFrameLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &CurrentThreadId);
  v2 = *((_QWORD *)this + 34);
  if ( **((_DWORD **)wil::details::static_lazy<WindowFrameLogging>::get(v4, v3) + 1) <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EtwEventActivityIdControl(3, v2 + 8);
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&CurrentThreadId);
  v8 = (_DWORD *)*((_QWORD *)wil::details::static_lazy<WindowFrameLogging>::get(v6, v5) + 1);
  if ( *v8 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v12 = 0;
    v9 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v9 + 4) || _tlgGuidIsZero((const struct _GUID *)(v9 + 24)) )
      v10 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)v8,
      byte_180101666,
      v9 + 8,
      v10,
      (__int64)&v12,
      (__int64)&CurrentThreadId);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (WindowFrameLoggingTelemetry::CloneWindow *)((char *)this + 288),
      v7);
}

```

## disassembly

```asm
0x18002526c  mov     [rsp+arg_10], rbx
0x180025271  push    rdi
0x180025272  sub     rsp, 30h
0x180025276  mov     rbx, rcx
0x180025279  lea     rdx, [rsp+38h+arg_0]
0x18002527e  call    ?LockExclusive@?$ActivityBase@VWindowFrameLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WindowFrameLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180025283  mov     rdi, [rbx+110h]
0x18002528a  call    ?get@?$static_lazy@VWindowFrameLogging@@@details@wil@@QEAAPEAVWindowFrameLogging@@P6AXXZ@Z; wil::details::static_lazy<WindowFrameLogging>::get(void (*)(void))
0x18002528f  mov     rdx, [rax+8]
0x180025293  mov     eax, [rdx]
0x180025295  cmp     eax, 5
0x180025298  jbe     short loc_1800252AB
0x18002529a  lea     rdx, [rdi+8]
0x18002529e  mov     ecx, 3
0x1800252a3  call    cs:__imp_EtwEventActivityIdControl
0x1800252a9  jmp     short loc_1800252B2
0x1800252ab  xorps   xmm0, xmm0
0x1800252ae  movups  xmmword ptr [rdi+8], xmm0
0x1800252b2  mov     dword ptr [rdi], 1
0x1800252b8  lea     rcx, [rsp+38h+arg_0]
0x1800252bd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800252c2  call    ?get@?$static_lazy@VWindowFrameLogging@@@details@wil@@QEAAPEAVWindowFrameLogging@@P6AXXZ@Z; wil::details::static_lazy<WindowFrameLogging>::get(void (*)(void))
0x1800252c7  mov     rdi, [rax+8]
0x1800252cb  mov     eax, [rdi]
0x1800252cd  cmp     eax, 5
0x1800252d0  jbe     short loc_18002532C
0x1800252d2  call    cs:__imp_GetCurrentThreadId
0x1800252d8  mov     [rsp+38h+arg_0], eax
0x1800252dc  mov     [rsp+38h+arg_8], 0
0x1800252e5  mov     r8, [rbx+110h]
0x1800252ec  cmp     byte ptr [r8+4], 0
0x1800252f1  jz      short loc_180025300
0x1800252f3  lea     rcx, [r8+18h]; struct _GUID *
0x1800252f7  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800252fc  test    al, al
0x1800252fe  jz      short loc_180025302
0x180025300  xor     ecx, ecx
0x180025302  add     r8, 8
0x180025306  lea     rax, [rsp+38h+arg_0]
0x18002530b  mov     [rsp+38h+var_10], rax
0x180025310  lea     rax, [rsp+38h+arg_8]
0x180025315  mov     [rsp+38h+var_18], rax
0x18002531a  mov     r9, rcx
0x18002531d  lea     rdx, byte_180101666
0x180025324  mov     rcx, rdi
0x180025327  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18002532c  lea     rcx, [rbx+120h]; this
0x180025333  cmp     dword ptr [rcx+18h], 0
0x180025337  jnz     short loc_18002533F
0x180025339  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18002533e  nop
0x18002533f  mov     rbx, [rsp+38h+arg_10]
0x180025344  add     rsp, 30h
0x180025348  pop     rdi
0x180025349  retn
```
