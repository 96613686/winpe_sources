# NetSetupTraceLogging::RpcNetSetupGetObjects::StartActivity(_GUID const &)

- ea: `0x1800148b0`
- end: `0x180014971`
- name: `?StartActivity@RpcNetSetupGetObjects@NetSetupTraceLogging@@QEAAXAEBU_GUID@@@Z`
- size: `193`
- prototype: `void __fastcall(NetSetupTraceLogging::RpcNetSetupGetObjects *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001161c`

## callees

- `0x180001abc`
- `0x180001b50`
- `0x1800139d8`
- `0x180014090`
- `0x1800148b0`
- `0x180017068`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800148ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800148ee`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::RpcNetSetupGetObjects::StartActivity(
        NetSetupTraceLogging::RpcNetSetupGetObjects *this,
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
      (int)&unk_18003FFE0,
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
0x1800148b0  push    rbx
0x1800148b2  push    rsi
0x1800148b3  push    rdi
0x1800148b4  sub     rsp, 40h
0x1800148b8  mov     rsi, rdx
0x1800148bb  mov     rbx, rcx
0x1800148be  call    ?zInternalStart@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800148c3  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x1800148c8  mov     rdi, rax
0x1800148cb  mov     r8d, [rax]
0x1800148ce  cmp     r8d, 5
0x1800148d2  jbe     loc_180014962
0x1800148d8  mov     edx, 1
0x1800148dd  mov     rcx, rax
0x1800148e0  call    _tlgKeywordOn
0x1800148e5  test    al, al
0x1800148e7  jz      short loc_180014962
0x1800148e9  mov     [rsp+58h+arg_10], rsi
0x1800148ee  call    cs:__imp_GetCurrentThreadId
0x1800148f4  mov     r8, [rbx+110h]
0x1800148fb  mov     dword ptr [rsp+58h+arg_0], eax
0x1800148ff  mov     [rsp+58h+arg_18], 0
0x180014908  cmp     byte ptr [r8+4], 0
0x18001490d  jz      short loc_18001492E
0x18001490f  lea     r9, [r8+18h]
0x180014913  cmp     dword ptr [r9], 0
0x180014917  jnz     short loc_180014931
0x180014919  cmp     dword ptr [r9+4], 0
0x18001491e  jnz     short loc_180014931
0x180014920  cmp     dword ptr [r9+8], 0
0x180014925  jnz     short loc_180014931
0x180014927  cmp     dword ptr [r9+0Ch], 0
0x18001492c  jnz     short loc_180014931
0x18001492e  xor     r9d, r9d
0x180014931  lea     rax, [rsp+58h+arg_10]
0x180014936  add     r8, 8
0x18001493a  mov     [rsp+58h+var_28], rax; __int64
0x18001493f  lea     rdx, unk_18003FFE0
0x180014946  lea     rax, [rsp+58h+arg_0]
0x18001494b  mov     rcx, rdi; int
0x18001494e  mov     [rsp+58h+var_30], rax; __int64
0x180014953  lea     rax, [rsp+58h+arg_18]
0x180014958  mov     [rsp+58h+var_38], rax; __int64
0x18001495d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180014962  mov     rcx, rbx
0x180014965  add     rsp, 40h
0x180014969  pop     rdi
0x18001496a  pop     rsi
0x18001496b  pop     rbx
0x18001496c  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
