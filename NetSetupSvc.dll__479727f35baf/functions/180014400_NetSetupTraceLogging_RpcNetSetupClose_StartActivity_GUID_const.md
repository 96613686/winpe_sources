# NetSetupTraceLogging::RpcNetSetupClose::StartActivity(_GUID const &)

- ea: `0x180014400`
- end: `0x1800144c1`
- name: `?StartActivity@RpcNetSetupClose@NetSetupTraceLogging@@QEAAXAEBU_GUID@@@Z`
- size: `193`
- prototype: `void __fastcall(NetSetupTraceLogging::RpcNetSetupClose *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800127fc`

## callees

- `0x180001abc`
- `0x180001b50`
- `0x1800139d8`
- `0x180014090`
- `0x180014400`
- `0x180017068`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001443e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001443e`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::RpcNetSetupClose::StartActivity(
        NetSetupTraceLogging::RpcNetSetupClose *this,
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
      (int)&byte_180040C4F,
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
0x180014400  push    rbx
0x180014402  push    rsi
0x180014403  push    rdi
0x180014404  sub     rsp, 40h
0x180014408  mov     rsi, rdx
0x18001440b  mov     rbx, rcx
0x18001440e  call    ?zInternalStart@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180014413  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180014418  mov     rdi, rax
0x18001441b  mov     r8d, [rax]
0x18001441e  cmp     r8d, 5
0x180014422  jbe     loc_1800144B2
0x180014428  mov     edx, 1
0x18001442d  mov     rcx, rax
0x180014430  call    _tlgKeywordOn
0x180014435  test    al, al
0x180014437  jz      short loc_1800144B2
0x180014439  mov     [rsp+58h+arg_10], rsi
0x18001443e  call    cs:__imp_GetCurrentThreadId
0x180014444  mov     r8, [rbx+110h]
0x18001444b  mov     dword ptr [rsp+58h+arg_0], eax
0x18001444f  mov     [rsp+58h+arg_18], 0
0x180014458  cmp     byte ptr [r8+4], 0
0x18001445d  jz      short loc_18001447E
0x18001445f  lea     r9, [r8+18h]
0x180014463  cmp     dword ptr [r9], 0
0x180014467  jnz     short loc_180014481
0x180014469  cmp     dword ptr [r9+4], 0
0x18001446e  jnz     short loc_180014481
0x180014470  cmp     dword ptr [r9+8], 0
0x180014475  jnz     short loc_180014481
0x180014477  cmp     dword ptr [r9+0Ch], 0
0x18001447c  jnz     short loc_180014481
0x18001447e  xor     r9d, r9d
0x180014481  lea     rax, [rsp+58h+arg_10]
0x180014486  add     r8, 8
0x18001448a  mov     [rsp+58h+var_28], rax; __int64
0x18001448f  lea     rdx, byte_180040C4F
0x180014496  lea     rax, [rsp+58h+arg_0]
0x18001449b  mov     rcx, rdi; int
0x18001449e  mov     [rsp+58h+var_30], rax; __int64
0x1800144a3  lea     rax, [rsp+58h+arg_18]
0x1800144a8  mov     [rsp+58h+var_38], rax; __int64
0x1800144ad  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x1800144b2  mov     rcx, rbx
0x1800144b5  add     rsp, 40h
0x1800144b9  pop     rdi
0x1800144ba  pop     rsi
0x1800144bb  pop     rbx
0x1800144bc  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
