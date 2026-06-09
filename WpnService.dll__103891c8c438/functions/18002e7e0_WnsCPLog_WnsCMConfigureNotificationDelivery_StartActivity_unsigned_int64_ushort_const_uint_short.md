# WnsCPLog::WnsCMConfigureNotificationDelivery::StartActivity(unsigned __int64,ushort const *,uint,short)

- ea: `0x18002e7e0`
- end: `0x18002e8b9`
- name: `?StartActivity@WnsCMConfigureNotificationDelivery@WnsCPLog@@QEAAX_KPEBGIF@Z`
- size: `217`
- prototype: `void __fastcall(WnsCPLog::WnsCMConfigureNotificationDelivery *__hidden this, unsigned __int64, const unsigned __int16 *, unsigned int, __int16)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180021e50`

## callees

- `0x1800029f4`
- `0x18000d830`
- `0x18000d8f0`
- `0x18000dc40`
- `0x180023dc4`
- `0x18002e7e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e82b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e82b`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMConfigureNotificationDelivery::StartActivity(
        WnsCPLog::WnsCMConfigureNotificationDelivery *this,
        __int64 a2,
        const unsigned __int16 *a3)
{
  const struct _tlgProvider_t *v6; // r15
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  __int64 v9; // rcx
  DWORD v10; // [rsp+54h] [rbp-24h] BYREF
  const unsigned __int16 *v11; // [rsp+58h] [rbp-20h] BYREF
  __int64 v12; // [rsp+60h] [rbp-18h] BYREF
  __int64 v13; // [rsp+68h] [rbp-10h] BYREF

  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v6 = WnsCPTracelogger::Provider();
  if ( *(_DWORD *)v6 > 5u )
  {
    v11 = a3;
    v12 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v8 = *((_QWORD *)this + 34);
    v10 = CurrentThreadId;
    v13 = 0;
    if ( !*(_BYTE *)(v8 + 4) || _tlgGuidIsZero((const struct _GUID *)(v8 + 24)) )
      v9 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>>(
      (__int64)v6,
      (__int64)&byte_18003E9DF,
      v8 + 8,
      v9,
      (__int64)&v13,
      (__int64)&v10,
      (__int64)&v12,
      &v11);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18002e7e0  push    rbp
0x18002e7e2  push    rbx
0x18002e7e3  push    rsi
0x18002e7e4  push    rdi
0x18002e7e5  push    r14
0x18002e7e7  push    r15
0x18002e7e9  mov     rbp, rsp
0x18002e7ec  sub     rsp, 78h
0x18002e7f0  mov     edi, r9d
0x18002e7f3  mov     rsi, r8
0x18002e7f6  mov     r14, rdx
0x18002e7f9  mov     rbx, rcx
0x18002e7fc  call    ?zInternalStart@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18002e801  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18002e806  mov     r15, rax
0x18002e809  mov     r10d, [rax]
0x18002e80c  cmp     r10d, 5
0x18002e810  jbe     loc_18002E8A5
0x18002e816  movzx   r9d, [rbp+arg_20]
0x18002e81b  mov     [rbp+arg_0], r9w
0x18002e820  mov     [rbp+var_28], edi
0x18002e823  mov     [rbp+var_20], rsi
0x18002e827  mov     [rbp+var_18], r14
0x18002e82b  call    cs:__imp_GetCurrentThreadId
0x18002e831  mov     r8, [rbx+110h]
0x18002e838  mov     [rbp+var_24], eax
0x18002e83b  mov     [rbp+var_10], 0
0x18002e843  cmp     byte ptr [r8+4], 0
0x18002e848  jz      short loc_18002E857
0x18002e84a  lea     rcx, [r8+18h]; struct _GUID *
0x18002e84e  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18002e853  test    al, al
0x18002e855  jz      short loc_18002E859
0x18002e857  xor     ecx, ecx
0x18002e859  lea     rax, [rbp+arg_0]
0x18002e85d  mov     r9, rcx
0x18002e860  mov     [rsp+78h+var_30], rax
0x18002e865  lea     rdx, byte_18003E9DF
0x18002e86c  lea     rax, [rbp+var_28]
0x18002e870  add     r8, 8
0x18002e874  mov     [rsp+78h+var_38], rax
0x18002e879  mov     rcx, r15
0x18002e87c  lea     rax, [rbp+var_20]
0x18002e880  mov     [rsp+78h+var_40], rax
0x18002e885  lea     rax, [rbp+var_18]
0x18002e889  mov     [rsp+78h+var_48], rax
0x18002e88e  lea     rax, [rbp+var_24]
0x18002e892  mov     [rsp+78h+var_50], rax
0x18002e897  lea     rax, [rbp+var_10]
0x18002e89b  mov     [rsp+78h+var_58], rax
0x18002e8a0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &)
0x18002e8a5  mov     rcx, rbx
0x18002e8a8  add     rsp, 78h
0x18002e8ac  pop     r15
0x18002e8ae  pop     r14
0x18002e8b0  pop     rdi
0x18002e8b1  pop     rsi
0x18002e8b2  pop     rbx
0x18002e8b3  pop     rbp
0x18002e8b4  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
