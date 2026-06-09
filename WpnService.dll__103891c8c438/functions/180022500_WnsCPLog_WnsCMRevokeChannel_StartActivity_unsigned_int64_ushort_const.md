# WnsCPLog::WnsCMRevokeChannel::StartActivity(unsigned __int64,ushort const *)

- ea: `0x180022500`
- end: `0x1800225bf`
- name: `?StartActivity@WnsCMRevokeChannel@WnsCPLog@@QEAAX_KPEBG@Z`
- size: `191`
- prototype: `void __fastcall(WnsCPLog::WnsCMRevokeChannel *__hidden this, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180014710`

## callees

- `0x180002934`
- `0x18000d830`
- `0x18000d8f0`
- `0x18000dc40`
- `0x180022500`
- `0x180023dc4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022539`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022539`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMRevokeChannel::StartActivity(
        WnsCPLog::WnsCMRevokeChannel *this,
        __int64 a2,
        const unsigned __int16 *a3)
{
  const struct _tlgProvider_t *v6; // r14
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  __int64 v9; // rcx
  __int64 v10; // [rsp+40h] [rbp-28h] BYREF
  _QWORD v11[4]; // [rsp+48h] [rbp-20h] BYREF
  DWORD v12; // [rsp+70h] [rbp+8h] BYREF
  const unsigned __int16 *v13; // [rsp+88h] [rbp+20h] BYREF

  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v6 = WnsCPTracelogger::Provider();
  if ( *(_DWORD *)v6 > 5u )
  {
    v13 = a3;
    v10 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v8 = *((_QWORD *)this + 34);
    v12 = CurrentThreadId;
    v11[0] = 0;
    if ( !*(_BYTE *)(v8 + 4) || _tlgGuidIsZero((const struct _GUID *)(v8 + 24)) )
      v9 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (__int64)v6,
      (__int64)&byte_18003E5B7,
      v8 + 8,
      v9,
      (__int64)v11,
      (__int64)&v12,
      (__int64)&v10,
      &v13);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180022500  mov     [rsp+arg_8], rbx
0x180022505  push    rsi
0x180022506  push    rdi
0x180022507  push    r14
0x180022509  sub     rsp, 50h
0x18002250d  mov     rdi, r8
0x180022510  mov     rsi, rdx
0x180022513  mov     rbx, rcx
0x180022516  call    ?zInternalStart@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18002251b  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180022520  mov     r14, rax
0x180022523  mov     r9d, [rax]
0x180022526  cmp     r9d, 5
0x18002252a  jbe     short loc_1800225AA
0x18002252c  mov     [rsp+68h+arg_18], rdi
0x180022534  mov     [rsp+68h+var_28], rsi
0x180022539  call    cs:__imp_GetCurrentThreadId
0x18002253f  mov     r8, [rbx+110h]
0x180022546  mov     [rsp+68h+arg_0], eax
0x18002254a  mov     [rsp+68h+var_20], 0
0x180022553  cmp     byte ptr [r8+4], 0
0x180022558  jz      short loc_180022567
0x18002255a  lea     rcx, [r8+18h]; struct _GUID *
0x18002255e  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180022563  test    al, al
0x180022565  jz      short loc_180022569
0x180022567  xor     ecx, ecx
0x180022569  lea     rax, [rsp+68h+arg_18]
0x180022571  mov     r9, rcx
0x180022574  mov     [rsp+68h+var_30], rax
0x180022579  lea     rdx, byte_18003E5B7
0x180022580  lea     rax, [rsp+68h+var_28]
0x180022585  add     r8, 8
0x180022589  mov     [rsp+68h+var_38], rax
0x18002258e  mov     rcx, r14
0x180022591  lea     rax, [rsp+68h+arg_0]
0x180022596  mov     [rsp+68h+var_40], rax
0x18002259b  lea     rax, [rsp+68h+var_20]
0x1800225a0  mov     [rsp+68h+var_48], rax
0x1800225a5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x1800225aa  mov     rcx, rbx
0x1800225ad  mov     rbx, [rsp+68h+arg_8]
0x1800225b2  add     rsp, 50h
0x1800225b6  pop     r14
0x1800225b8  pop     rdi
0x1800225b9  pop     rsi
0x1800225ba  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
