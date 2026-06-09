# NetSetupTraceLogging::PrepareTransaction::StartActivity(_GUID const &)

- ea: `0x1800580d4`
- end: `0x180058181`
- name: `?StartActivity@PrepareTransaction@NetSetupTraceLogging@@QEAAXAEBU_GUID@@@Z`
- size: `173`
- prototype: `void __fastcall(NetSetupTraceLogging::PrepareTransaction *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180029708`

## callees

- `0x180001be8`
- `0x180013aa4`
- `0x180033720`
- `0x18003e218`
- `0x180046ed0`
- `0x1800580d4`
- `0x180069144`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005810e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005810e`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::PrepareTransaction::StartActivity(
        NetSetupTraceLogging::PrepareTransaction *this,
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
      (int)&word_1800B217E,
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
0x1800580d4  push    rbx
0x1800580d6  push    rsi
0x1800580d7  push    rdi
0x1800580d8  sub     rsp, 40h
0x1800580dc  mov     rsi, rdx
0x1800580df  mov     rbx, rcx
0x1800580e2  call    ?zInternalStart@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800580e7  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x1800580ec  mov     rdi, rax
0x1800580ef  mov     r8d, [rax]
0x1800580f2  cmp     r8d, 5
0x1800580f6  jbe     short loc_180058172
0x1800580f8  mov     edx, 1
0x1800580fd  mov     rcx, rax
0x180058100  call    _tlgKeywordOn
0x180058105  test    al, al
0x180058107  jz      short loc_180058172
0x180058109  mov     [rsp+58h+arg_10], rsi
0x18005810e  call    cs:__imp_GetCurrentThreadId
0x180058114  mov     r8, [rbx+110h]
0x18005811b  mov     dword ptr [rsp+58h+arg_0], eax
0x18005811f  mov     [rsp+58h+arg_18], 0
0x180058128  cmp     byte ptr [r8+4], 0
0x18005812d  jz      short loc_18005813C
0x18005812f  lea     rcx, [r8+18h]; struct _GUID *
0x180058133  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180058138  test    al, al
0x18005813a  jz      short loc_18005813E
0x18005813c  xor     ecx, ecx
0x18005813e  lea     rax, [rsp+58h+arg_10]
0x180058143  mov     r9, rcx
0x180058146  mov     [rsp+58h+var_28], rax; __int64
0x18005814b  lea     rdx, word_1800B217E
0x180058152  lea     rax, [rsp+58h+arg_0]
0x180058157  add     r8, 8
0x18005815b  mov     [rsp+58h+var_30], rax; __int64
0x180058160  mov     rcx, rdi; int
0x180058163  lea     rax, [rsp+58h+arg_18]
0x180058168  mov     [rsp+58h+var_38], rax; __int64
0x18005816d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180058172  mov     rcx, rbx
0x180058175  add     rsp, 40h
0x180058179  pop     rdi
0x18005817a  pop     rsi
0x18005817b  pop     rbx
0x18005817c  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
