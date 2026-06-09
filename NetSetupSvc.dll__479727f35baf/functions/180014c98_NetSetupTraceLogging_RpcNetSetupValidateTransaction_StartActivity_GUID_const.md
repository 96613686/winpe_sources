# NetSetupTraceLogging::RpcNetSetupValidateTransaction::StartActivity(_GUID const &)

- ea: `0x180014c98`
- end: `0x180014d59`
- name: `?StartActivity@RpcNetSetupValidateTransaction@NetSetupTraceLogging@@QEAAXAEBU_GUID@@@Z`
- size: `193`
- prototype: `void __fastcall(NetSetupTraceLogging::RpcNetSetupValidateTransaction *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180011ac0`

## callees

- `0x180001abc`
- `0x180001b50`
- `0x1800139d8`
- `0x180014090`
- `0x180014c98`
- `0x180017068`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014cd6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014cd6`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::RpcNetSetupValidateTransaction::StartActivity(
        NetSetupTraceLogging::RpcNetSetupValidateTransaction *this,
        const struct _GUID *a2)
{
  __int64 v4; // rcx
  const struct _tlgProvider_t *v5; // rax
  int v6; // edi
  __int64 v7; // r8
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  int v10; // r9d
  __int64 v11; // [rsp+60h] [rbp+8h] BYREF
  __int64 v12; // [rsp+70h] [rbp+18h] BYREF
  __int64 v13; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v5 = NetSetupTraceLogging::Provider(v4);
  v6 = (int)v5;
  v7 = *(unsigned int *)v5;
  if ( (unsigned int)v7 > 5 && (unsigned __int8)tlgKeywordOn(v5, 1, v7) )
  {
    v12 = (__int64)a2;
    CurrentThreadId = GetCurrentThreadId();
    v9 = *((_QWORD *)this + 34);
    LODWORD(v11) = CurrentThreadId;
    v13 = 0;
    if ( !*(_BYTE *)(v9 + 4)
      || (v10 = v9 + 24, !*(_DWORD *)(v9 + 24))
      && !*(_DWORD *)(v9 + 28)
      && !*(_DWORD *)(v9 + 32)
      && !*(_DWORD *)(v9 + 36) )
    {
      v10 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      v6,
      (int)&dword_180041234,
      v9 + 8,
      v10,
      (__int64)&v13,
      (__int64)&v11,
      &v12);
  }
  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180014c98  push    rbx
0x180014c9a  push    rsi
0x180014c9b  push    rdi
0x180014c9c  sub     rsp, 40h
0x180014ca0  mov     rsi, rdx
0x180014ca3  mov     rbx, rcx
0x180014ca6  call    ?zInternalStart@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180014cab  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180014cb0  mov     rdi, rax
0x180014cb3  mov     r8d, [rax]
0x180014cb6  cmp     r8d, 5
0x180014cba  jbe     loc_180014D4A
0x180014cc0  mov     edx, 1
0x180014cc5  mov     rcx, rax
0x180014cc8  call    _tlgKeywordOn
0x180014ccd  test    al, al
0x180014ccf  jz      short loc_180014D4A
0x180014cd1  mov     [rsp+58h+arg_10], rsi
0x180014cd6  call    cs:__imp_GetCurrentThreadId
0x180014cdc  mov     r8, [rbx+110h]
0x180014ce3  mov     dword ptr [rsp+58h+arg_0], eax
0x180014ce7  mov     [rsp+58h+arg_18], 0
0x180014cf0  cmp     byte ptr [r8+4], 0
0x180014cf5  jz      short loc_180014D16
0x180014cf7  lea     r9, [r8+18h]
0x180014cfb  cmp     dword ptr [r9], 0
0x180014cff  jnz     short loc_180014D19
0x180014d01  cmp     dword ptr [r9+4], 0
0x180014d06  jnz     short loc_180014D19
0x180014d08  cmp     dword ptr [r9+8], 0
0x180014d0d  jnz     short loc_180014D19
0x180014d0f  cmp     dword ptr [r9+0Ch], 0
0x180014d14  jnz     short loc_180014D19
0x180014d16  xor     r9d, r9d
0x180014d19  lea     rax, [rsp+58h+arg_10]
0x180014d1e  add     r8, 8
0x180014d22  mov     [rsp+58h+var_28], rax; __int64
0x180014d27  lea     rdx, dword_180041234
0x180014d2e  lea     rax, [rsp+58h+arg_0]
0x180014d33  mov     rcx, rdi; int
0x180014d36  mov     [rsp+58h+var_30], rax; __int64
0x180014d3b  lea     rax, [rsp+58h+arg_18]
0x180014d40  mov     [rsp+58h+var_38], rax; __int64
0x180014d45  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180014d4a  mov     rcx, rbx
0x180014d4d  add     rsp, 40h
0x180014d51  pop     rdi
0x180014d52  pop     rsi
0x180014d53  pop     rbx
0x180014d54  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
