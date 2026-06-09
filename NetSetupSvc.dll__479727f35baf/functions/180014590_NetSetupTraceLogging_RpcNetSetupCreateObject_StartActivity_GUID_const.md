# NetSetupTraceLogging::RpcNetSetupCreateObject::StartActivity(_GUID const &)

- ea: `0x180014590`
- end: `0x180014651`
- name: `?StartActivity@RpcNetSetupCreateObject@NetSetupTraceLogging@@QEAAXAEBU_GUID@@@Z`
- size: `193`
- prototype: `void __fastcall(NetSetupTraceLogging::RpcNetSetupCreateObject *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180010ffc`

## callees

- `0x180001abc`
- `0x180001b50`
- `0x1800139d8`
- `0x180014090`
- `0x180014590`
- `0x180017068`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800145ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800145ce`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::RpcNetSetupCreateObject::StartActivity(
        NetSetupTraceLogging::RpcNetSetupCreateObject *this,
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
      (int)&byte_180040A47,
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
0x180014590  push    rbx
0x180014592  push    rsi
0x180014593  push    rdi
0x180014594  sub     rsp, 40h
0x180014598  mov     rsi, rdx
0x18001459b  mov     rbx, rcx
0x18001459e  call    ?zInternalStart@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800145a3  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x1800145a8  mov     rdi, rax
0x1800145ab  mov     r8d, [rax]
0x1800145ae  cmp     r8d, 5
0x1800145b2  jbe     loc_180014642
0x1800145b8  mov     edx, 1
0x1800145bd  mov     rcx, rax
0x1800145c0  call    _tlgKeywordOn
0x1800145c5  test    al, al
0x1800145c7  jz      short loc_180014642
0x1800145c9  mov     [rsp+58h+arg_10], rsi
0x1800145ce  call    cs:__imp_GetCurrentThreadId
0x1800145d4  mov     r8, [rbx+110h]
0x1800145db  mov     dword ptr [rsp+58h+arg_0], eax
0x1800145df  mov     [rsp+58h+arg_18], 0
0x1800145e8  cmp     byte ptr [r8+4], 0
0x1800145ed  jz      short loc_18001460E
0x1800145ef  lea     r9, [r8+18h]
0x1800145f3  cmp     dword ptr [r9], 0
0x1800145f7  jnz     short loc_180014611
0x1800145f9  cmp     dword ptr [r9+4], 0
0x1800145fe  jnz     short loc_180014611
0x180014600  cmp     dword ptr [r9+8], 0
0x180014605  jnz     short loc_180014611
0x180014607  cmp     dword ptr [r9+0Ch], 0
0x18001460c  jnz     short loc_180014611
0x18001460e  xor     r9d, r9d
0x180014611  lea     rax, [rsp+58h+arg_10]
0x180014616  add     r8, 8
0x18001461a  mov     [rsp+58h+var_28], rax; __int64
0x18001461f  lea     rdx, byte_180040A47
0x180014626  lea     rax, [rsp+58h+arg_0]
0x18001462b  mov     rcx, rdi; int
0x18001462e  mov     [rsp+58h+var_30], rax; __int64
0x180014633  lea     rax, [rsp+58h+arg_18]
0x180014638  mov     [rsp+58h+var_38], rax; __int64
0x18001463d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180014642  mov     rcx, rbx
0x180014645  add     rsp, 40h
0x180014649  pop     rdi
0x18001464a  pop     rsi
0x18001464b  pop     rbx
0x18001464c  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
