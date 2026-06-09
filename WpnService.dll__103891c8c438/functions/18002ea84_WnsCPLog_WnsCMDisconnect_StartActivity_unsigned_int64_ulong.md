# WnsCPLog::WnsCMDisconnect::StartActivity(unsigned __int64,ulong)

- ea: `0x18002ea84`
- end: `0x18002eb42`
- name: `?StartActivity@WnsCMDisconnect@WnsCPLog@@QEAAX_KK@Z`
- size: `190`
- prototype: `void __fastcall(WnsCPLog::WnsCMDisconnect *__hidden this, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180025530`

## callees

- `0x18000d830`
- `0x18000d8f0`
- `0x18000dc40`
- `0x1800113b0`
- `0x180023dc4`
- `0x18002ea84`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002eab9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002eab9`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMDisconnect::StartActivity(WnsCPLog::WnsCMDisconnect *this, __int64 a2, int a3)
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
      (unsigned __int8 *)&byte_18003F677,
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
0x18002ea84  mov     [rsp+arg_8], rbx
0x18002ea89  push    rsi
0x18002ea8a  push    rdi
0x18002ea8b  push    r14
0x18002ea8d  sub     rsp, 50h
0x18002ea91  mov     edi, r8d
0x18002ea94  mov     rsi, rdx
0x18002ea97  mov     rbx, rcx
0x18002ea9a  call    ?zInternalStart@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18002ea9f  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18002eaa4  mov     r14, rax
0x18002eaa7  mov     r9d, [rax]
0x18002eaaa  cmp     r9d, 5
0x18002eaae  jbe     short loc_18002EB2D
0x18002eab0  mov     [rsp+68h+arg_0], edi
0x18002eab4  mov     [rsp+68h+var_28], rsi
0x18002eab9  call    cs:__imp_GetCurrentThreadId
0x18002eabf  mov     r8, [rbx+110h]
0x18002eac6  mov     [rsp+68h+arg_18], eax
0x18002eacd  mov     [rsp+68h+var_20], 0
0x18002ead6  cmp     byte ptr [r8+4], 0
0x18002eadb  jz      short loc_18002EAEA
0x18002eadd  lea     rcx, [r8+18h]; struct _GUID *
0x18002eae1  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18002eae6  test    al, al
0x18002eae8  jz      short loc_18002EAEC
0x18002eaea  xor     ecx, ecx
0x18002eaec  lea     rax, [rsp+68h+arg_0]
0x18002eaf1  mov     r9, rcx
0x18002eaf4  mov     [rsp+68h+var_30], rax
0x18002eaf9  lea     rdx, byte_18003F677
0x18002eb00  lea     rax, [rsp+68h+var_28]
0x18002eb05  add     r8, 8
0x18002eb09  mov     [rsp+68h+var_38], rax
0x18002eb0e  mov     rcx, r14
0x18002eb11  lea     rax, [rsp+68h+arg_18]
0x18002eb19  mov     [rsp+68h+var_40], rax
0x18002eb1e  lea     rax, [rsp+68h+var_20]
0x18002eb23  mov     [rsp+68h+var_48], rax
0x18002eb28  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18002eb2d  mov     rcx, rbx
0x18002eb30  mov     rbx, [rsp+68h+arg_8]
0x18002eb35  add     rsp, 50h
0x18002eb39  pop     r14
0x18002eb3b  pop     rdi
0x18002eb3c  pop     rsi
0x18002eb3d  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
