# NetSetupTraceLogging::PartialBindGraphCalculation::StartActivity(_GUID const &)

- ea: `0x180053b80`
- end: `0x180053c2d`
- name: `?StartActivity@PartialBindGraphCalculation@NetSetupTraceLogging@@QEAAXAEBU_GUID@@@Z`
- size: `173`
- prototype: `void __fastcall(NetSetupTraceLogging::PartialBindGraphCalculation *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180053a90`

## callees

- `0x180001be8`
- `0x180013aa4`
- `0x180033720`
- `0x18003e218`
- `0x180046ed0`
- `0x180053b80`
- `0x180069144`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053bba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053bba`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::PartialBindGraphCalculation::StartActivity(
        NetSetupTraceLogging::PartialBindGraphCalculation *this,
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
      (int)byte_1800B37CD,
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
0x180053b80  push    rbx
0x180053b82  push    rsi
0x180053b83  push    rdi
0x180053b84  sub     rsp, 40h
0x180053b88  mov     rsi, rdx
0x180053b8b  mov     rbx, rcx
0x180053b8e  call    ?zInternalStart@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180053b93  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180053b98  mov     rdi, rax
0x180053b9b  mov     r8d, [rax]
0x180053b9e  cmp     r8d, 5
0x180053ba2  jbe     short loc_180053C1E
0x180053ba4  mov     edx, 1
0x180053ba9  mov     rcx, rax
0x180053bac  call    _tlgKeywordOn
0x180053bb1  test    al, al
0x180053bb3  jz      short loc_180053C1E
0x180053bb5  mov     [rsp+58h+arg_10], rsi
0x180053bba  call    cs:__imp_GetCurrentThreadId
0x180053bc0  mov     r8, [rbx+110h]
0x180053bc7  mov     dword ptr [rsp+58h+arg_0], eax
0x180053bcb  mov     [rsp+58h+arg_18], 0
0x180053bd4  cmp     byte ptr [r8+4], 0
0x180053bd9  jz      short loc_180053BE8
0x180053bdb  lea     rcx, [r8+18h]; struct _GUID *
0x180053bdf  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180053be4  test    al, al
0x180053be6  jz      short loc_180053BEA
0x180053be8  xor     ecx, ecx
0x180053bea  lea     rax, [rsp+58h+arg_10]
0x180053bef  mov     r9, rcx
0x180053bf2  mov     [rsp+58h+var_28], rax; __int64
0x180053bf7  lea     rdx, byte_1800B37CD
0x180053bfe  lea     rax, [rsp+58h+arg_0]
0x180053c03  add     r8, 8
0x180053c07  mov     [rsp+58h+var_30], rax; __int64
0x180053c0c  mov     rcx, rdi; int
0x180053c0f  lea     rax, [rsp+58h+arg_18]
0x180053c14  mov     [rsp+58h+var_38], rax; __int64
0x180053c19  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180053c1e  mov     rcx, rbx
0x180053c21  add     rsp, 40h
0x180053c25  pop     rdi
0x180053c26  pop     rsi
0x180053c27  pop     rbx
0x180053c28  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
