# AnimationClockLoggingTelemetry::GetCommitHandle::StartActivity(_GUID)

- ea: `0x18009d818`
- end: `0x18009d8c5`
- name: `?StartActivity@GetCommitHandle@AnimationClockLoggingTelemetry@@QEAAXU_GUID@@@Z`
- size: `173`
- prototype: `void __fastcall(AnimationClockLoggingTelemetry::GetCommitHandle *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18007ef18`

## callees

- `0x18003a168`
- `0x18005d7cc`
- `0x1800615e0`
- `0x18006ba24`
- `0x18008dee4`
- `0x18009d818`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009d847`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009d847`

## pseudocode

```c
void __fastcall AnimationClockLoggingTelemetry::GetCommitHandle::StartActivity(
        AnimationClockLoggingTelemetry::GetCommitHandle *this,
        struct _GUID *a2)
{
  _DWORD *v4; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v6; // r8
  int v7; // ecx
  DWORD v8; // [rsp+40h] [rbp-28h] BYREF
  struct _GUID *v9; // [rsp+48h] [rbp-20h] BYREF
  __int64 v10; // [rsp+50h] [rbp-18h] BYREF

  wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v4 = *(_DWORD **)(wil::details::static_lazy<AnimationClockLogging>::get() + 8);
  if ( *v4 > 4u )
  {
    v9 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v6 = *((_QWORD *)this + 34);
    v8 = CurrentThreadId;
    v10 = 0;
    if ( !*(_BYTE *)(v6 + 4) || _tlgGuidIsZero((const struct _GUID *)(v6 + 24)) )
      v7 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      (_DWORD)v4,
      (unsigned int)&unk_1800FF68B,
      v6 + 8,
      v7,
      (__int64)&v10,
      (__int64)&v8,
      (__int64)&v9);
  }
  wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x18009d818  mov     [rsp+arg_8], rbx
0x18009d81d  mov     [rsp+arg_10], rsi
0x18009d822  push    rdi
0x18009d823  sub     rsp, 60h
0x18009d827  mov     rdi, rdx
0x18009d82a  mov     rbx, rcx
0x18009d82d  call    ?zInternalStart@?$ActivityBase@VAnimationClockLogging@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18009d832  call    ?get@?$static_lazy@VAnimationClockLogging@@@details@wil@@QEAAPEAVAnimationClockLogging@@P6AXXZ@Z; wil::details::static_lazy<AnimationClockLogging>::get(void (*)(void))
0x18009d837  mov     rsi, [rax+8]
0x18009d83b  mov     eax, [rsi]
0x18009d83d  cmp     eax, 4
0x18009d840  jbe     short loc_18009D8AB
0x18009d842  mov     [rsp+68h+var_20], rdi
0x18009d847  call    cs:__imp_GetCurrentThreadId
0x18009d84d  mov     r8, [rbx+110h]
0x18009d854  mov     [rsp+68h+var_28], eax
0x18009d858  mov     [rsp+68h+var_18], 0
0x18009d861  cmp     byte ptr [r8+4], 0
0x18009d866  jz      short loc_18009D875
0x18009d868  lea     rcx, [r8+18h]; struct _GUID *
0x18009d86c  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18009d871  test    al, al
0x18009d873  jz      short loc_18009D877
0x18009d875  xor     ecx, ecx
0x18009d877  lea     rax, [rsp+68h+var_20]
0x18009d87c  mov     r9, rcx
0x18009d87f  mov     [rsp+68h+var_38], rax
0x18009d884  lea     rdx, unk_1800FF68B
0x18009d88b  lea     rax, [rsp+68h+var_28]
0x18009d890  add     r8, 8
0x18009d894  mov     [rsp+68h+var_40], rax
0x18009d899  mov     rcx, rsi
0x18009d89c  lea     rax, [rsp+68h+var_18]
0x18009d8a1  mov     [rsp+68h+var_48], rax
0x18009d8a6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18009d8ab  mov     rcx, rbx
0x18009d8ae  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VAnimationClockLogging@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18009d8b3  lea     r11, [rsp+68h+var_8]
0x18009d8b8  mov     rbx, [r11+18h]
0x18009d8bc  mov     rsi, [r11+20h]
0x18009d8c0  mov     rsp, r11
0x18009d8c3  pop     rdi
0x18009d8c4  retn
```
