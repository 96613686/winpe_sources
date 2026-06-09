# AssignedAccessTelemetry::MdmTask_Process::StartActivity(void)

- ea: `0x1800689a0`
- end: `0x180068ab9`
- name: `?StartActivity@MdmTask_Process@AssignedAccessTelemetry@@QEAAXXZ`
- size: `281`
- prototype: `void __fastcall(AssignedAccessTelemetry::MdmTask_Process *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180067510`

## callees

- `0x180001a0c`
- `0x180001dec`
- `0x18000d80c`
- `0x1800153a0`
- `0x18001b000`
- `0x18001f23c`
- `0x1800689a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068a31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068a31`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800689e9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800689e9`

## pseudocode

```c
void __fastcall AssignedAccessTelemetry::MdmTask_Process::StartActivity(AssignedAccessTelemetry::MdmTask_Process *this)
{
  __int64 v2; // rbx
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // ebx
  __int64 v10; // r8
  int v11; // r9d
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v13; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &CurrentThreadId);
  v2 = *((_QWORD *)this + 34);
  v3 = AssignedAccessTelemetry::Provider();
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL, v4, v5) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&CurrentThreadId);
  v6 = AssignedAccessTelemetry::Provider();
  v9 = (int)v6;
  if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v7, v8) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v13 = 2048;
    v10 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v10 + 4)
      || (v11 = v10 + 24, !*(_DWORD *)(v10 + 24))
      && !*(_DWORD *)(v10 + 28)
      && !*(_DWORD *)(v10 + 32)
      && !*(_DWORD *)(v10 + 36) )
    {
      v11 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v9,
      (unsigned int)&dword_1800B4BEC,
      v10 + 8,
      v11,
      (__int64)&v13,
      (__int64)&CurrentThreadId);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((AssignedAccessTelemetry::MdmTask_Process *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800689a0  mov     [rsp+arg_10], rbx
0x1800689a5  push    rdi
0x1800689a6  sub     rsp, 30h
0x1800689aa  mov     rdi, rcx
0x1800689ad  lea     rdx, [rsp+38h+arg_0]
0x1800689b2  call    ?LockExclusive@?$ActivityBase@VAssignedAccessTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800689b7  mov     rbx, [rdi+110h]
0x1800689be  call    ?Provider@AssignedAccessTelemetry@@SAPEBU_tlgProvider_t@@XZ; AssignedAccessTelemetry::Provider(void)
0x1800689c3  mov     edx, [rax]
0x1800689c5  cmp     edx, 5
0x1800689c8  jbe     short loc_1800689F1
0x1800689ca  mov     rdx, 400000000000h
0x1800689d4  mov     rcx, rax
0x1800689d7  call    _tlgKeywordOn
0x1800689dc  test    al, al
0x1800689de  jz      short loc_1800689F1
0x1800689e0  lea     rdx, [rbx+8]; ActivityId
0x1800689e4  mov     ecx, 3; ControlCode
0x1800689e9  call    cs:__imp_EventActivityIdControl
0x1800689ef  jmp     short loc_1800689F8
0x1800689f1  xorps   xmm0, xmm0
0x1800689f4  movups  xmmword ptr [rbx+8], xmm0
0x1800689f8  mov     dword ptr [rbx], 1
0x1800689fe  lea     rcx, [rsp+38h+arg_0]
0x180068a03  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180068a08  call    ?Provider@AssignedAccessTelemetry@@SAPEBU_tlgProvider_t@@XZ; AssignedAccessTelemetry::Provider(void)
0x180068a0d  mov     rbx, rax
0x180068a10  mov     ecx, [rax]
0x180068a12  cmp     ecx, 5
0x180068a15  jbe     loc_180068A9B
0x180068a1b  mov     rdx, 400000000000h
0x180068a25  mov     rcx, rax
0x180068a28  call    _tlgKeywordOn
0x180068a2d  test    al, al
0x180068a2f  jz      short loc_180068A9B
0x180068a31  call    cs:__imp_GetCurrentThreadId
0x180068a37  mov     [rsp+38h+arg_0], eax
0x180068a3b  mov     [rsp+38h+arg_8], 800h
0x180068a44  mov     r8, [rdi+110h]
0x180068a4b  cmp     byte ptr [r8+4], 0
0x180068a50  jz      short loc_180068A71
0x180068a52  lea     r9, [r8+18h]
0x180068a56  cmp     dword ptr [r9], 0
0x180068a5a  jnz     short loc_180068A74
0x180068a5c  cmp     dword ptr [r9+4], 0
0x180068a61  jnz     short loc_180068A74
0x180068a63  cmp     dword ptr [r9+8], 0
0x180068a68  jnz     short loc_180068A74
0x180068a6a  cmp     dword ptr [r9+0Ch], 0
0x180068a6f  jnz     short loc_180068A74
0x180068a71  xor     r9d, r9d
0x180068a74  add     r8, 8
0x180068a78  lea     rax, [rsp+38h+arg_0]
0x180068a7d  mov     [rsp+38h+var_10], rax
0x180068a82  lea     rax, [rsp+38h+arg_8]
0x180068a87  mov     [rsp+38h+var_18], rax
0x180068a8c  lea     rdx, dword_1800B4BEC
0x180068a93  mov     rcx, rbx
0x180068a96  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180068a9b  lea     rcx, [rdi+120h]; this
0x180068aa2  cmp     dword ptr [rcx+18h], 0
0x180068aa6  jnz     short loc_180068AAE
0x180068aa8  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180068aad  nop
0x180068aae  mov     rbx, [rsp+38h+arg_10]
0x180068ab3  add     rsp, 30h
0x180068ab7  pop     rdi
0x180068ab8  retn
```
