# WnsCPLog::WnsCMChannelRequestExpired::StartActivity(long)

- ea: `0x180020c44`
- end: `0x180020cf4`
- name: `?StartActivity@WnsCMChannelRequestExpired@WnsCPLog@@QEAAXJ@Z`
- size: `176`
- prototype: `void __fastcall(WnsCPLog::WnsCMChannelRequestExpired *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180020b74`

## callees

- `0x18000d830`
- `0x18000f2f0`
- `0x18001546c`
- `0x180018430`
- `0x180020c44`
- `0x1800238ac`
- `0x180023dc4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020c81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020c81`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMChannelRequestExpired::StartActivity(WnsCPLog::WnsCMChannelRequestExpired *this, int a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r9
  __int64 v6; // rdi
  __int64 v7; // r8
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  const GUID *v10; // rcx
  int v11; // [rsp+60h] [rbp+8h] BYREF
  DWORD v12; // [rsp+70h] [rbp+18h] BYREF
  __int64 v13; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v4 = WnsCPTracelogger::Provider();
  v6 = (__int64)v4;
  v7 = *(unsigned int *)v4;
  if ( (unsigned int)v7 > 5 && (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL, v7, v5) )
  {
    v11 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v9 = *((_QWORD *)this + 34);
    v12 = CurrentThreadId;
    v13 = 0;
    if ( !*(_BYTE *)(v9 + 4) || _tlgGuidIsZero((const struct _GUID *)(v9 + 24)) )
      v10 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v6,
      (unsigned __int8 *)byte_18004021B,
      (const GUID *)(v9 + 8),
      v10,
      (__int64)&v13,
      (__int64)&v12,
      (__int64)&v11);
  }
  wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180020c44  push    rbx
0x180020c46  push    rsi
0x180020c47  push    rdi
0x180020c48  sub     rsp, 40h
0x180020c4c  mov     esi, edx
0x180020c4e  mov     rbx, rcx
0x180020c51  call    ?zInternalStart@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180020c56  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180020c5b  mov     rdi, rax
0x180020c5e  mov     r8d, [rax]
0x180020c61  cmp     r8d, 5
0x180020c65  jbe     short loc_180020CE5
0x180020c67  mov     rdx, 200000000000h
0x180020c71  mov     rcx, rax
0x180020c74  call    _tlgKeywordOn
0x180020c79  test    al, al
0x180020c7b  jz      short loc_180020CE5
0x180020c7d  mov     [rsp+58h+arg_0], esi
0x180020c81  call    cs:__imp_GetCurrentThreadId
0x180020c87  mov     r8, [rbx+110h]
0x180020c8e  mov     [rsp+58h+arg_10], eax
0x180020c92  mov     [rsp+58h+arg_18], 0
0x180020c9b  cmp     byte ptr [r8+4], 0
0x180020ca0  jz      short loc_180020CAF
0x180020ca2  lea     rcx, [r8+18h]; struct _GUID *
0x180020ca6  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180020cab  test    al, al
0x180020cad  jz      short loc_180020CB1
0x180020caf  xor     ecx, ecx
0x180020cb1  lea     rax, [rsp+58h+arg_0]
0x180020cb6  mov     r9, rcx
0x180020cb9  mov     [rsp+58h+var_28], rax
0x180020cbe  lea     rdx, byte_18004021B
0x180020cc5  lea     rax, [rsp+58h+arg_10]
0x180020cca  add     r8, 8
0x180020cce  mov     [rsp+58h+var_30], rax
0x180020cd3  mov     rcx, rdi
0x180020cd6  lea     rax, [rsp+58h+arg_18]
0x180020cdb  mov     [rsp+58h+var_38], rax
0x180020ce0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180020ce5  mov     rcx, rbx
0x180020ce8  add     rsp, 40h
0x180020cec  pop     rdi
0x180020ced  pop     rsi
0x180020cee  pop     rbx
0x180020cef  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
