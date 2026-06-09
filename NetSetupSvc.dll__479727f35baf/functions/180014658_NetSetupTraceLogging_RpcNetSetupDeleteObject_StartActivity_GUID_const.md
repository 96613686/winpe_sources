# NetSetupTraceLogging::RpcNetSetupDeleteObject::StartActivity(_GUID const &)

- ea: `0x180014658`
- end: `0x180014719`
- name: `?StartActivity@RpcNetSetupDeleteObject@NetSetupTraceLogging@@QEAAXAEBU_GUID@@@Z`
- size: `193`
- prototype: `void __fastcall(NetSetupTraceLogging::RpcNetSetupDeleteObject *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180011184`

## callees

- `0x180001abc`
- `0x180001b50`
- `0x1800139d8`
- `0x180014090`
- `0x180014658`
- `0x180017068`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014696`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014696`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::RpcNetSetupDeleteObject::StartActivity(
        NetSetupTraceLogging::RpcNetSetupDeleteObject *this,
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
      (int)&byte_18004083F,
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
0x180014658  push    rbx
0x18001465a  push    rsi
0x18001465b  push    rdi
0x18001465c  sub     rsp, 40h
0x180014660  mov     rsi, rdx
0x180014663  mov     rbx, rcx
0x180014666  call    ?zInternalStart@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001466b  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180014670  mov     rdi, rax
0x180014673  mov     r8d, [rax]
0x180014676  cmp     r8d, 5
0x18001467a  jbe     loc_18001470A
0x180014680  mov     edx, 1
0x180014685  mov     rcx, rax
0x180014688  call    _tlgKeywordOn
0x18001468d  test    al, al
0x18001468f  jz      short loc_18001470A
0x180014691  mov     [rsp+58h+arg_10], rsi
0x180014696  call    cs:__imp_GetCurrentThreadId
0x18001469c  mov     r8, [rbx+110h]
0x1800146a3  mov     dword ptr [rsp+58h+arg_0], eax
0x1800146a7  mov     [rsp+58h+arg_18], 0
0x1800146b0  cmp     byte ptr [r8+4], 0
0x1800146b5  jz      short loc_1800146D6
0x1800146b7  lea     r9, [r8+18h]
0x1800146bb  cmp     dword ptr [r9], 0
0x1800146bf  jnz     short loc_1800146D9
0x1800146c1  cmp     dword ptr [r9+4], 0
0x1800146c6  jnz     short loc_1800146D9
0x1800146c8  cmp     dword ptr [r9+8], 0
0x1800146cd  jnz     short loc_1800146D9
0x1800146cf  cmp     dword ptr [r9+0Ch], 0
0x1800146d4  jnz     short loc_1800146D9
0x1800146d6  xor     r9d, r9d
0x1800146d9  lea     rax, [rsp+58h+arg_10]
0x1800146de  add     r8, 8
0x1800146e2  mov     [rsp+58h+var_28], rax; __int64
0x1800146e7  lea     rdx, byte_18004083F
0x1800146ee  lea     rax, [rsp+58h+arg_0]
0x1800146f3  mov     rcx, rdi; int
0x1800146f6  mov     [rsp+58h+var_30], rax; __int64
0x1800146fb  lea     rax, [rsp+58h+arg_18]
0x180014700  mov     [rsp+58h+var_38], rax; __int64
0x180014705  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18001470a  mov     rcx, rbx
0x18001470d  add     rsp, 40h
0x180014711  pop     rdi
0x180014712  pop     rsi
0x180014713  pop     rbx
0x180014714  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
