# NetSetupTraceLogging::Transaction::StartActivity(_GUID const &)

- ea: `0x180010e80`
- end: `0x180010f2d`
- name: `?StartActivity@Transaction@NetSetupTraceLogging@@QEAAXAEBU_GUID@@@Z`
- size: `173`
- prototype: `void __fastcall(NetSetupTraceLogging::Transaction *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18000ee54`

## callees

- `0x180001be8`
- `0x180010e80`
- `0x180013aa4`
- `0x180033720`
- `0x18003e218`
- `0x180046ed0`
- `0x180069144`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010eba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010eba`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::Transaction::StartActivity(
        NetSetupTraceLogging::Transaction *this,
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
      (int)qword_1800B2FC8,
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
0x180010e80  push    rbx
0x180010e82  push    rsi
0x180010e83  push    rdi
0x180010e84  sub     rsp, 40h
0x180010e88  mov     rsi, rdx
0x180010e8b  mov     rbx, rcx
0x180010e8e  call    ?zInternalStart@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180010e93  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180010e98  mov     rdi, rax
0x180010e9b  mov     r8d, [rax]
0x180010e9e  cmp     r8d, 5
0x180010ea2  jbe     short loc_180010F1E
0x180010ea4  mov     edx, 1
0x180010ea9  mov     rcx, rax
0x180010eac  call    _tlgKeywordOn
0x180010eb1  test    al, al
0x180010eb3  jz      short loc_180010F1E
0x180010eb5  mov     [rsp+58h+arg_10], rsi
0x180010eba  call    cs:__imp_GetCurrentThreadId
0x180010ec0  mov     r8, [rbx+110h]
0x180010ec7  mov     dword ptr [rsp+58h+arg_0], eax
0x180010ecb  mov     [rsp+58h+arg_18], 0
0x180010ed4  cmp     byte ptr [r8+4], 0
0x180010ed9  jz      short loc_180010EE8
0x180010edb  lea     rcx, [r8+18h]; struct _GUID *
0x180010edf  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180010ee4  test    al, al
0x180010ee6  jz      short loc_180010EEA
0x180010ee8  xor     ecx, ecx
0x180010eea  lea     rax, [rsp+58h+arg_10]
0x180010eef  mov     r9, rcx
0x180010ef2  mov     [rsp+58h+var_28], rax; __int64
0x180010ef7  lea     rdx, qword_1800B2FC8
0x180010efe  lea     rax, [rsp+58h+arg_0]
0x180010f03  add     r8, 8
0x180010f07  mov     [rsp+58h+var_30], rax; __int64
0x180010f0c  mov     rcx, rdi; int
0x180010f0f  lea     rax, [rsp+58h+arg_18]
0x180010f14  mov     [rsp+58h+var_38], rax; __int64
0x180010f19  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180010f1e  mov     rcx, rbx
0x180010f21  add     rsp, 40h
0x180010f25  pop     rdi
0x180010f26  pop     rsi
0x180010f27  pop     rbx
0x180010f28  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
