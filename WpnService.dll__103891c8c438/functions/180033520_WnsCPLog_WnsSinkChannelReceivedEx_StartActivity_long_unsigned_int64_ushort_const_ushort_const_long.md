# WnsCPLog::WnsSinkChannelReceivedEx::StartActivity(long,unsigned __int64,ushort const *,ushort const *,long)

- ea: `0x180033520`
- end: `0x180033611`
- name: `?StartActivity@WnsSinkChannelReceivedEx@WnsCPLog@@QEAAXJ_KPEBG1J@Z`
- size: `241`
- prototype: `void __fastcall(WnsCPLog::WnsSinkChannelReceivedEx *__hidden this, int, unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180033100`

## callees

- `0x18000145c`
- `0x18000d830`
- `0x18000d8f0`
- `0x18000dc40`
- `0x180023dc4`
- `0x180033520`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033577`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033577`

## pseudocode

```c
void __fastcall WnsCPLog::WnsSinkChannelReceivedEx::StartActivity(
        WnsCPLog::WnsSinkChannelReceivedEx *this,
        int a2,
        __int64 a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        int a6)
{
  const struct _tlgProvider_t *v10; // r15
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  const GUID *v13; // rcx
  int v14; // [rsp+60h] [rbp-19h] BYREF
  DWORD v15; // [rsp+64h] [rbp-15h] BYREF
  int *v16; // [rsp+68h] [rbp-11h] BYREF
  int *v17; // [rsp+70h] [rbp-9h] BYREF
  __int64 v18; // [rsp+78h] [rbp-1h] BYREF
  _QWORD v19[8]; // [rsp+80h] [rbp+7h] BYREF
  int v20; // [rsp+D0h] [rbp+57h] BYREF

  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v10 = WnsCPTracelogger::Provider();
  if ( *(_DWORD *)v10 > 5u )
  {
    v16 = (int *)a5;
    v20 = a6;
    v17 = (int *)a4;
    v18 = a3;
    v14 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v12 = *((_QWORD *)this + 34);
    v15 = CurrentThreadId;
    v19[0] = 0;
    if ( !*(_BYTE *)(v12 + 4) || _tlgGuidIsZero((const struct _GUID *)(v12 + 24)) )
      v13 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)v10,
      (unsigned __int8 *)byte_180042AB9,
      (const GUID *)(v12 + 8),
      v13,
      (__int64)v19,
      (__int64)&v15,
      (__int64)&v14,
      (__int64)&v18,
      &v17,
      &v16,
      (__int64)&v20);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180033520  push    rbp
0x180033522  push    rbx
0x180033523  push    rsi
0x180033524  push    rdi
0x180033525  push    r14
0x180033527  push    r15
0x180033529  lea     rbp, [rsp-1Fh]
0x18003352e  sub     rsp, 98h
0x180033535  mov     rdi, r9
0x180033538  mov     rsi, r8
0x18003353b  mov     r14d, edx
0x18003353e  mov     rbx, rcx
0x180033541  call    ?zInternalStart@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180033546  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18003354b  mov     r15, rax
0x18003354e  mov     r10d, [rax]
0x180033551  cmp     r10d, 5
0x180033555  jbe     loc_1800335FA
0x18003355b  mov     rdx, [rbp+47h+arg_20]
0x18003355f  mov     r9d, [rbp+47h+arg_28]
0x180033563  mov     [rbp+47h+var_58], rdx
0x180033567  mov     [rbp+47h+arg_0], r9d
0x18003356b  mov     [rbp+47h+var_50], rdi
0x18003356f  mov     [rbp+47h+var_48], rsi
0x180033573  mov     [rbp+47h+var_60], r14d
0x180033577  call    cs:__imp_GetCurrentThreadId
0x18003357d  mov     r8, [rbx+110h]
0x180033584  mov     [rbp+47h+var_5C], eax
0x180033587  mov     [rbp+47h+var_40], 0
0x18003358f  cmp     byte ptr [r8+4], 0
0x180033594  jz      short loc_1800335A3
0x180033596  lea     rcx, [r8+18h]; struct _GUID *
0x18003359a  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18003359f  test    al, al
0x1800335a1  jz      short loc_1800335A5
0x1800335a3  xor     ecx, ecx
0x1800335a5  lea     rax, [rbp+47h+arg_0]
0x1800335a9  mov     r9, rcx
0x1800335ac  mov     [rsp+0C0h+var_70], rax
0x1800335b1  lea     rdx, byte_180042AB9
0x1800335b8  lea     rax, [rbp+47h+var_58]
0x1800335bc  add     r8, 8
0x1800335c0  mov     [rsp+0C0h+var_78], rax
0x1800335c5  mov     rcx, r15
0x1800335c8  lea     rax, [rbp+47h+var_50]
0x1800335cc  mov     [rsp+0C0h+var_80], rax
0x1800335d1  lea     rax, [rbp+47h+var_48]
0x1800335d5  mov     [rsp+0C0h+var_88], rax
0x1800335da  lea     rax, [rbp+47h+var_60]
0x1800335de  mov     [rsp+0C0h+var_90], rax
0x1800335e3  lea     rax, [rbp+47h+var_5C]
0x1800335e7  mov     [rsp+0C0h+var_98], rax
0x1800335ec  lea     rax, [rbp+47h+var_40]
0x1800335f0  mov     [rsp+0C0h+var_A0], rax
0x1800335f5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U1@U?$_tlgWrapSz@G@@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@43AEBU?$_tlgWrapSz@G@@54@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800335fa  mov     rcx, rbx
0x1800335fd  add     rsp, 98h
0x180033604  pop     r15
0x180033606  pop     r14
0x180033608  pop     rdi
0x180033609  pop     rsi
0x18003360a  pop     rbx
0x18003360b  pop     rbp
0x18003360c  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
