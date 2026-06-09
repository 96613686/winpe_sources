# NetSetupTraceLogging::ZwCommitTransaction::StartActivity(_GUID const &)

- ea: `0x180046fb0`
- end: `0x18004705d`
- name: `?StartActivity@ZwCommitTransaction@NetSetupTraceLogging@@QEAAXAEBU_GUID@@@Z`
- size: `173`
- prototype: `void __fastcall(NetSetupTraceLogging::ZwCommitTransaction *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005719c`

## callees

- `0x180001be8`
- `0x180013aa4`
- `0x180033720`
- `0x18003e218`
- `0x180046ed0`
- `0x180046fb0`
- `0x180069144`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046fea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046fea`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::ZwCommitTransaction::StartActivity(
        NetSetupTraceLogging::ZwCommitTransaction *this,
        const struct _GUID *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r9
  int v6; // edi
  __int64 v7; // r8
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  int v10; // ecx
  __int64 v11; // [rsp+60h] [rbp+8h] BYREF
  __int64 v12; // [rsp+70h] [rbp+18h] BYREF
  __int64 v13; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v4 = NetSetupTraceLogging::Provider();
  v6 = (int)v4;
  v7 = *(unsigned int *)v4;
  if ( (unsigned int)v7 > 5 && (unsigned __int8)tlgKeywordOn(v4, 1, v7, v5) )
  {
    v12 = (__int64)a2;
    CurrentThreadId = GetCurrentThreadId();
    v9 = *((_QWORD *)this + 34);
    LODWORD(v11) = CurrentThreadId;
    v13 = 0;
    if ( !*(_BYTE *)(v9 + 4) || _tlgGuidIsZero((const struct _GUID *)(v9 + 24)) )
      v10 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      v6,
      (int)&dword_1800B29D4,
      v9 + 8,
      v10,
      (__int64)&v13,
      (__int64)&v11,
      &v12);
  }
  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180046fb0  push    rbx
0x180046fb2  push    rsi
0x180046fb3  push    rdi
0x180046fb4  sub     rsp, 40h
0x180046fb8  mov     rsi, rdx
0x180046fbb  mov     rbx, rcx
0x180046fbe  call    ?zInternalStart@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180046fc3  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180046fc8  mov     rdi, rax
0x180046fcb  mov     r8d, [rax]
0x180046fce  cmp     r8d, 5
0x180046fd2  jbe     short loc_18004704E
0x180046fd4  mov     edx, 1
0x180046fd9  mov     rcx, rax
0x180046fdc  call    _tlgKeywordOn
0x180046fe1  test    al, al
0x180046fe3  jz      short loc_18004704E
0x180046fe5  mov     [rsp+58h+arg_10], rsi
0x180046fea  call    cs:__imp_GetCurrentThreadId
0x180046ff0  mov     r8, [rbx+110h]
0x180046ff7  mov     dword ptr [rsp+58h+arg_0], eax
0x180046ffb  mov     [rsp+58h+arg_18], 0
0x180047004  cmp     byte ptr [r8+4], 0
0x180047009  jz      short loc_180047018
0x18004700b  lea     rcx, [r8+18h]; struct _GUID *
0x18004700f  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180047014  test    al, al
0x180047016  jz      short loc_18004701A
0x180047018  xor     ecx, ecx
0x18004701a  lea     rax, [rsp+58h+arg_10]
0x18004701f  mov     r9, rcx
0x180047022  mov     [rsp+58h+var_28], rax; __int64
0x180047027  lea     rdx, dword_1800B29D4
0x18004702e  lea     rax, [rsp+58h+arg_0]
0x180047033  add     r8, 8
0x180047037  mov     [rsp+58h+var_30], rax; __int64
0x18004703c  mov     rcx, rdi; int
0x18004703f  lea     rax, [rsp+58h+arg_18]
0x180047044  mov     [rsp+58h+var_38], rax; __int64
0x180047049  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18004704e  mov     rcx, rbx
0x180047051  add     rsp, 40h
0x180047055  pop     rdi
0x180047056  pop     rsi
0x180047057  pop     rbx
0x180047058  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
