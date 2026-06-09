# WnsCPLog::WnsSinkUserRemoved::StartActivity(unsigned __int64,long)

- ea: `0x180017a58`
- end: `0x180017b16`
- name: `?StartActivity@WnsSinkUserRemoved@WnsCPLog@@QEAAX_KJ@Z`
- size: `190`
- prototype: `void __fastcall(WnsCPLog::WnsSinkUserRemoved *__hidden this, unsigned __int64, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800179c0`

## callees

- `0x18000d830`
- `0x18000d8f0`
- `0x18000dc40`
- `0x1800113b0`
- `0x180017a58`
- `0x180023dc4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017a8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017a8d`

## pseudocode

```c
void __fastcall WnsCPLog::WnsSinkUserRemoved::StartActivity(WnsCPLog::WnsSinkUserRemoved *this, __int64 a2, int a3)
{
  const struct _tlgProvider_t *v6; // r14
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  const GUID *v9; // rcx
  __int64 v10; // [rsp+40h] [rbp-28h] BYREF
  _QWORD v11[4]; // [rsp+48h] [rbp-20h] BYREF
  int v12; // [rsp+70h] [rbp+8h] BYREF
  DWORD v13; // [rsp+88h] [rbp+20h] BYREF

  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v6 = WnsCPTracelogger::Provider();
  if ( *(_DWORD *)v6 > 5u )
  {
    v12 = a3;
    v10 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v8 = *((_QWORD *)this + 34);
    v13 = CurrentThreadId;
    v11[0] = 0;
    if ( !*(_BYTE *)(v8 + 4) || _tlgGuidIsZero((const struct _GUID *)(v8 + 24)) )
      v9 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)v6,
      (unsigned __int8 *)&word_180041876,
      (const GUID *)(v8 + 8),
      v9,
      (__int64)v11,
      (__int64)&v13,
      (__int64)&v10,
      (__int64)&v12);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180017a58  mov     [rsp+arg_8], rbx
0x180017a5d  push    rsi
0x180017a5e  push    rdi
0x180017a5f  push    r14
0x180017a61  sub     rsp, 50h
0x180017a65  mov     edi, r8d
0x180017a68  mov     rsi, rdx
0x180017a6b  mov     rbx, rcx
0x180017a6e  call    ?zInternalStart@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180017a73  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180017a78  mov     r14, rax
0x180017a7b  mov     r9d, [rax]
0x180017a7e  cmp     r9d, 5
0x180017a82  jbe     short loc_180017B01
0x180017a84  mov     [rsp+68h+arg_0], edi
0x180017a88  mov     [rsp+68h+var_28], rsi
0x180017a8d  call    cs:__imp_GetCurrentThreadId
0x180017a93  mov     r8, [rbx+110h]
0x180017a9a  mov     [rsp+68h+arg_18], eax
0x180017aa1  mov     [rsp+68h+var_20], 0
0x180017aaa  cmp     byte ptr [r8+4], 0
0x180017aaf  jz      short loc_180017ABE
0x180017ab1  lea     rcx, [r8+18h]; struct _GUID *
0x180017ab5  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180017aba  test    al, al
0x180017abc  jz      short loc_180017AC0
0x180017abe  xor     ecx, ecx
0x180017ac0  lea     rax, [rsp+68h+arg_0]
0x180017ac5  mov     r9, rcx
0x180017ac8  mov     [rsp+68h+var_30], rax
0x180017acd  lea     rdx, word_180041876
0x180017ad4  lea     rax, [rsp+68h+var_28]
0x180017ad9  add     r8, 8
0x180017add  mov     [rsp+68h+var_38], rax
0x180017ae2  mov     rcx, r14
0x180017ae5  lea     rax, [rsp+68h+arg_18]
0x180017aed  mov     [rsp+68h+var_40], rax
0x180017af2  lea     rax, [rsp+68h+var_20]
0x180017af7  mov     [rsp+68h+var_48], rax
0x180017afc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180017b01  mov     rcx, rbx
0x180017b04  mov     rbx, [rsp+68h+arg_8]
0x180017b09  add     rsp, 50h
0x180017b0d  pop     r14
0x180017b0f  pop     rdi
0x180017b10  pop     rsi
0x180017b11  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
