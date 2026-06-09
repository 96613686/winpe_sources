# NetSetupTraceLogging::RpcNetSetupRollback::StartActivity(_GUID const &)

- ea: `0x180014a40`
- end: `0x180014b01`
- name: `?StartActivity@RpcNetSetupRollback@NetSetupTraceLogging@@QEAAXAEBU_GUID@@@Z`
- size: `193`
- prototype: `void __fastcall(NetSetupTraceLogging::RpcNetSetupRollback *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800117a4`

## callees

- `0x180001abc`
- `0x180001b50`
- `0x1800139d8`
- `0x180014090`
- `0x180014a40`
- `0x180017068`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014a7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014a7e`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::RpcNetSetupRollback::StartActivity(
        NetSetupTraceLogging::RpcNetSetupRollback *this,
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
      (int)&unk_180041038,
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
0x180014a40  push    rbx
0x180014a42  push    rsi
0x180014a43  push    rdi
0x180014a44  sub     rsp, 40h
0x180014a48  mov     rsi, rdx
0x180014a4b  mov     rbx, rcx
0x180014a4e  call    ?zInternalStart@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180014a53  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180014a58  mov     rdi, rax
0x180014a5b  mov     r8d, [rax]
0x180014a5e  cmp     r8d, 5
0x180014a62  jbe     loc_180014AF2
0x180014a68  mov     edx, 1
0x180014a6d  mov     rcx, rax
0x180014a70  call    _tlgKeywordOn
0x180014a75  test    al, al
0x180014a77  jz      short loc_180014AF2
0x180014a79  mov     [rsp+58h+arg_10], rsi
0x180014a7e  call    cs:__imp_GetCurrentThreadId
0x180014a84  mov     r8, [rbx+110h]
0x180014a8b  mov     dword ptr [rsp+58h+arg_0], eax
0x180014a8f  mov     [rsp+58h+arg_18], 0
0x180014a98  cmp     byte ptr [r8+4], 0
0x180014a9d  jz      short loc_180014ABE
0x180014a9f  lea     r9, [r8+18h]
0x180014aa3  cmp     dword ptr [r9], 0
0x180014aa7  jnz     short loc_180014AC1
0x180014aa9  cmp     dword ptr [r9+4], 0
0x180014aae  jnz     short loc_180014AC1
0x180014ab0  cmp     dword ptr [r9+8], 0
0x180014ab5  jnz     short loc_180014AC1
0x180014ab7  cmp     dword ptr [r9+0Ch], 0
0x180014abc  jnz     short loc_180014AC1
0x180014abe  xor     r9d, r9d
0x180014ac1  lea     rax, [rsp+58h+arg_10]
0x180014ac6  add     r8, 8
0x180014aca  mov     [rsp+58h+var_28], rax; __int64
0x180014acf  lea     rdx, unk_180041038
0x180014ad6  lea     rax, [rsp+58h+arg_0]
0x180014adb  mov     rcx, rdi; int
0x180014ade  mov     [rsp+58h+var_30], rax; __int64
0x180014ae3  lea     rax, [rsp+58h+arg_18]
0x180014ae8  mov     [rsp+58h+var_38], rax; __int64
0x180014aed  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180014af2  mov     rcx, rbx
0x180014af5  add     rsp, 40h
0x180014af9  pop     rdi
0x180014afa  pop     rsi
0x180014afb  pop     rbx
0x180014afc  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
