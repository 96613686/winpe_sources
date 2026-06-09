# NetSetupTraceLogging::BindGraphDeltaApplication::StartActivity(_GUID const &)

- ea: `0x180054484`
- end: `0x180054531`
- name: `?StartActivity@BindGraphDeltaApplication@NetSetupTraceLogging@@QEAAXAEBU_GUID@@@Z`
- size: `173`
- prototype: `void __fastcall(NetSetupTraceLogging::BindGraphDeltaApplication *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180054394`

## callees

- `0x180001be8`
- `0x180013aa4`
- `0x180033720`
- `0x18003e218`
- `0x180046ed0`
- `0x180054484`
- `0x180069144`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800544be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800544be`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::BindGraphDeltaApplication::StartActivity(
        NetSetupTraceLogging::BindGraphDeltaApplication *this,
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
      (int)&byte_1800B33B7,
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
0x180054484  push    rbx
0x180054486  push    rsi
0x180054487  push    rdi
0x180054488  sub     rsp, 40h
0x18005448c  mov     rsi, rdx
0x18005448f  mov     rbx, rcx
0x180054492  call    ?zInternalStart@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180054497  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x18005449c  mov     rdi, rax
0x18005449f  mov     r8d, [rax]
0x1800544a2  cmp     r8d, 5
0x1800544a6  jbe     short loc_180054522
0x1800544a8  mov     edx, 1
0x1800544ad  mov     rcx, rax
0x1800544b0  call    _tlgKeywordOn
0x1800544b5  test    al, al
0x1800544b7  jz      short loc_180054522
0x1800544b9  mov     [rsp+58h+arg_10], rsi
0x1800544be  call    cs:__imp_GetCurrentThreadId
0x1800544c4  mov     r8, [rbx+110h]
0x1800544cb  mov     dword ptr [rsp+58h+arg_0], eax
0x1800544cf  mov     [rsp+58h+arg_18], 0
0x1800544d8  cmp     byte ptr [r8+4], 0
0x1800544dd  jz      short loc_1800544EC
0x1800544df  lea     rcx, [r8+18h]; struct _GUID *
0x1800544e3  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800544e8  test    al, al
0x1800544ea  jz      short loc_1800544EE
0x1800544ec  xor     ecx, ecx
0x1800544ee  lea     rax, [rsp+58h+arg_10]
0x1800544f3  mov     r9, rcx
0x1800544f6  mov     [rsp+58h+var_28], rax; __int64
0x1800544fb  lea     rdx, byte_1800B33B7
0x180054502  lea     rax, [rsp+58h+arg_0]
0x180054507  add     r8, 8
0x18005450b  mov     [rsp+58h+var_30], rax; __int64
0x180054510  mov     rcx, rdi; int
0x180054513  lea     rax, [rsp+58h+arg_18]
0x180054518  mov     [rsp+58h+var_38], rax; __int64
0x18005451d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180054522  mov     rcx, rbx
0x180054525  add     rsp, 40h
0x180054529  pop     rdi
0x18005452a  pop     rsi
0x18005452b  pop     rbx
0x18005452c  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
