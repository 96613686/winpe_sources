# ServiceHostTelemetry::ServiceStopActivity::StartActivity(ushort const *,int)

- ea: `0x18002c3e0`
- end: `0x18002c4d5`
- name: `?StartActivity@ServiceStopActivity@ServiceHostTelemetry@@QEAAXPEBGH@Z`
- size: `245`
- prototype: `void __fastcall(ServiceHostTelemetry::ServiceStopActivity *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18001f588`

## callees

- `0x180002864`
- `0x1800172bc`
- `0x180018430`
- `0x180022838`
- `0x1800238ac`
- `0x180023dc4`
- `0x18002c3e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c440`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c440`

## pseudocode

```c
void __fastcall ServiceHostTelemetry::ServiceStopActivity::StartActivity(
        ServiceHostTelemetry::ServiceStopActivity *this,
        const unsigned __int16 *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  __int64 v6; // rdi
  __int64 v7; // r9
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  __int64 v10; // rcx
  DWORD v11; // [rsp+50h] [rbp-38h] BYREF
  const unsigned __int16 *v12; // [rsp+58h] [rbp-30h] BYREF
  __int64 v13[5]; // [rsp+60h] [rbp-28h] BYREF

  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v4 = ServiceHostLogging::Provider();
  v6 = (__int64)v4;
  v7 = *(unsigned int *)v4;
  if ( (unsigned int)v7 > 5 && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL, v5, v7) )
  {
    v12 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v9 = *((_QWORD *)this + 34);
    v11 = CurrentThreadId;
    v13[0] = 0x1000000;
    if ( !*(_BYTE *)(v9 + 4) || _tlgGuidIsZero((const struct _GUID *)(v9 + 24)) )
      v10 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v6,
      (__int64)&byte_18003D22F,
      v9 + 8,
      v10,
      (__int64)v13,
      (__int64)&v11,
      &v12);
  }
  wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18002c3e0  mov     [rsp+arg_8], rbx
0x18002c3e5  push    rbp
0x18002c3e6  push    rsi
0x18002c3e7  push    rdi
0x18002c3e8  sub     rsp, 70h
0x18002c3ec  mov     esi, r8d
0x18002c3ef  mov     rbp, rdx
0x18002c3f2  mov     rbx, rcx
0x18002c3f5  call    ?zInternalStart@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18002c3fa  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18002c3ff  mov     rdi, rax
0x18002c402  mov     r9d, [rax]
0x18002c405  cmp     r9d, 5
0x18002c409  jbe     loc_18002C4BE
0x18002c40f  mov     rdx, 400000000000h
0x18002c419  mov     rcx, rax
0x18002c41c  call    _tlgKeywordOn
0x18002c421  test    al, al
0x18002c423  jz      loc_18002C4BE
0x18002c429  mov     [rsp+88h+arg_0], 1
0x18002c434  mov     [rsp+88h+arg_18], esi
0x18002c43b  mov     [rsp+88h+var_30], rbp
0x18002c440  call    cs:__imp_GetCurrentThreadId
0x18002c446  mov     r8, [rbx+110h]
0x18002c44d  mov     [rsp+88h+var_38], eax
0x18002c451  mov     [rsp+88h+var_28], 1000000h
0x18002c45a  cmp     byte ptr [r8+4], 0
0x18002c45f  jz      short loc_18002C46E
0x18002c461  lea     rcx, [r8+18h]; struct _GUID *
0x18002c465  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18002c46a  test    al, al
0x18002c46c  jz      short loc_18002C470
0x18002c46e  xor     ecx, ecx
0x18002c470  lea     rax, [rsp+88h+arg_0]
0x18002c478  mov     r9, rcx
0x18002c47b  mov     [rsp+88h+var_48], rax
0x18002c480  lea     rdx, byte_18003D22F
0x18002c487  lea     rax, [rsp+88h+arg_18]
0x18002c48f  add     r8, 8
0x18002c493  mov     [rsp+88h+var_50], rax
0x18002c498  mov     rcx, rdi
0x18002c49b  lea     rax, [rsp+88h+var_30]
0x18002c4a0  mov     [rsp+88h+var_58], rax
0x18002c4a5  lea     rax, [rsp+88h+var_38]
0x18002c4aa  mov     [rsp+88h+var_60], rax
0x18002c4af  lea     rax, [rsp+88h+var_28]
0x18002c4b4  mov     [rsp+88h+var_68], rax
0x18002c4b9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002c4be  mov     rcx, rbx
0x18002c4c1  mov     rbx, [rsp+88h+arg_8]
0x18002c4c9  add     rsp, 70h
0x18002c4cd  pop     rdi
0x18002c4ce  pop     rsi
0x18002c4cf  pop     rbp
0x18002c4d0  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
