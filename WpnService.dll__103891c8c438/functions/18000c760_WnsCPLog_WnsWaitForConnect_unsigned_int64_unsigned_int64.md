# WnsCPLog::WnsWaitForConnect<unsigned __int64 &>(unsigned __int64 &)

- ea: `0x18000c760`
- end: `0x18000c986`
- name: `??$WnsWaitForConnect@AEA_K@WnsCPLog@@SAXAEA_K@Z`
- size: `550`
- prototype: `ULONG __fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b720`

## callees

- `0x18000c760`
- `0x180026200`
- `0x1800265b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c968`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c968`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000c879`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000c879`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000c85e`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000c85e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000c79e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000c79e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c8a8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c8a8`

## pseudocode

```c
ULONG __fastcall WnsCPLog::WnsWaitForConnect<unsigned __int64 &>(LPVOID *a1)
{
  _QWORD *v2; // rbx
  ULONGLONG *v3; // r9
  __int64 v4; // rcx
  ULONG result; // eax
  WINBOOL fPending; // [rsp+30h] [rbp-19h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-11h] BYREF
  GUID ProviderId; // [rsp+40h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp+7h] BYREF
  char *v10; // [rsp+60h] [rbp+17h]
  int v11; // [rsp+68h] [rbp+1Fh]
  int v12; // [rsp+6Ch] [rbp+23h]
  LPVOID *p_Context; // [rsp+70h] [rbp+27h]
  __int64 v14; // [rsp+78h] [rbp+2Fh]

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    Context = &qword_18004A760;
    qword_18004A768 = 0;
    byte_18004A770 = 0;
    dword_18004A774 = 0;
    qword_18004A760 = (__int64)&wil::details::FeatureLogging::`vftable';
    CallbackContext = &`WnsCPTracelogger::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_633a74d489e420a2ff0e92495a1626f6_::_lambda_invoker_cdecl_);
    v2 = CallbackContext;
    qword_18004A768 = (__int64)CallbackContext;
    byte_18004A770 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    v3 = (ULONGLONG *)((char *)CallbackContext + 32);
    *((_QWORD *)CallbackContext + 5) = 0;
    v2[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v2, v3) )
      EventSetInformation(v2[4], 2, v2[1], *(unsigned __int16 *)v2[1]);
    dword_18004A774 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18004A760 + 8))(&qword_18004A760);
    InitOnceComplete(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, &qword_18004A760);
  }
  v4 = *((_QWORD *)Context + 1);
  result = *(_DWORD *)v4;
  if ( *(_DWORD *)v4 > 5u )
  {
    Context = *a1;
    v14 = 8;
    p_Context = &Context;
    *(_DWORD *)&ProviderId.Data2 = 5;
    UserData.Ptr = *(_QWORD *)(v4 + 8);
    ProviderId.Data1 = 184549376;
    *(_QWORD *)ProviderId.Data4 = 0;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v10 = byte_180041111;
    UserData.Reserved = 2;
    v11 = 29;
    v12 = 1;
    fPending = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    return EventWriteTransfer(*(_QWORD *)(v4 + 32), (PCEVENT_DESCRIPTOR)&ProviderId, 0, 0, 3u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x18000c760  push    rbp
0x18000c762  push    rsi
0x18000c763  push    r14
0x18000c765  lea     rbp, [rsp-47h]
0x18000c76a  sub     rsp, 90h
0x18000c771  mov     rax, cs:__security_cookie
0x18000c778  xor     rax, rsp
0x18000c77b  mov     [rbp+57h+var_20], rax
0x18000c77f  mov     rsi, rcx
0x18000c782  lea     r9, [rbp+57h+Context]; lpContext
0x18000c786  xor     r14d, r14d
0x18000c789  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18000c790  lea     r8, [rbp+57h+fPending]; fPending
0x18000c794  mov     [rbp+57h+Context], r14
0x18000c798  xor     edx, edx; dwFlags
0x18000c79a  mov     [rbp+57h+fPending], r14d
0x18000c79e  call    cs:__imp_InitOnceBeginInitialize
0x18000c7a4  test    eax, eax
0x18000c7a6  jz      loc_18000C8C6
0x18000c7ac  cmp     [rbp+57h+fPending], r14d
0x18000c7b0  jz      loc_18000C8C6
0x18000c7b6  mov     [rsp+0A0h+arg_0], rbx
0x18000c7be  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x18000c7c5  mov     [rsp+0A0h+arg_8], rdi
0x18000c7cd  mov     [rsp+0A0h+arg_10], r15
0x18000c7d5  lea     r15, qword_18004A760
0x18000c7dc  mov     [rbp+57h+Context], r15
0x18000c7e0  mov     cs:qword_18004A768, r14
0x18000c7e7  mov     cs:byte_18004A770, r14b
0x18000c7ee  mov     cs:dword_18004A774, r14d
0x18000c7f5  mov     cs:qword_18004A760, rax
0x18000c7fc  lea     rax, ?__hInner@?1???0StaticHandle@WnsCPTracelogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WnsCPTracelogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000c803  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_633a74d489e420a2ff0e92495a1626f6_@@CA@XZ; void (__cdecl *)()
0x18000c80a  mov     cs:CallbackContext, rax
0x18000c811  call    atexit
0x18000c816  mov     rbx, cs:CallbackContext
0x18000c81d  mov     cs:qword_18004A768, rbx
0x18000c824  mov     cs:byte_18004A770, 1
0x18000c82b  mov     rax, [rbx+8]
0x18000c82f  movups  xmm0, xmmword ptr [rax-10h]
0x18000c833  movups  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x18000c837  cmp     [rbx+20h], r14
0x18000c83b  jz      short loc_18000C844
0x18000c83d  mov     ecx, 5
0x18000c842  int     29h; Win8: RtlFailFast(ecx)
0x18000c844  lea     r9, [rbx+20h]; RegHandle
0x18000c848  mov     [rbx+28h], r14
0x18000c84c  mov     r8, rbx; CallbackContext
0x18000c84f  mov     [rbx+30h], r14
0x18000c853  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000c85a  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x18000c85e  call    cs:__imp_EventRegister
0x18000c864  test    eax, eax
0x18000c866  jnz     short loc_18000C87F
0x18000c868  mov     r8, [rbx+8]
0x18000c86c  mov     edx, 2
0x18000c871  mov     rcx, [rbx+20h]
0x18000c875  movzx   r9d, word ptr [r8]
0x18000c879  call    cs:__imp_EventSetInformation
0x18000c87f  mov     rax, cs:qword_18004A760
0x18000c886  mov     rcx, r15
0x18000c889  mov     cs:dword_18004A774, 1
0x18000c893  mov     rax, [rax+8]
0x18000c897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c89c  mov     r8, r15; lpContext
0x18000c89f  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18000c8a6  xor     edx, edx; dwFlags
0x18000c8a8  call    cs:__imp_InitOnceComplete
0x18000c8ae  mov     r15, [rsp+0A0h+arg_10]
0x18000c8b6  mov     rdi, [rsp+0A0h+arg_8]
0x18000c8be  mov     rbx, [rsp+0A0h+arg_0]
0x18000c8c6  mov     rax, [rbp+57h+Context]
0x18000c8ca  mov     rcx, [rax+8]
0x18000c8ce  mov     eax, [rcx]
0x18000c8d0  cmp     eax, 5
0x18000c8d3  jbe     loc_18000C96E
0x18000c8d9  mov     rax, [rsi]
0x18000c8dc  lea     rdx, _TraceLoggingMetadata
0x18000c8e3  mov     [rbp+57h+Context], rax
0x18000c8e7  xor     r9d, r9d; RelatedActivityId
0x18000c8ea  lea     rax, [rbp+57h+Context]
0x18000c8ee  mov     [rbp+57h+var_28], 8
0x18000c8f6  mov     [rbp+57h+var_30], rax
0x18000c8fa  xor     r8d, r8d; ActivityId
0x18000c8fd  movzx   eax, cs:word_180041107
0x18000c904  mov     dword ptr [rbp+57h+ProviderId.Data2], eax
0x18000c907  mov     rax, [rcx+8]
0x18000c90b  mov     [rbp+57h+var_50.Ptr], rax
0x18000c90f  mov     [rbp+57h+ProviderId.Data1], 0B000000h
0x18000c916  mov     qword ptr [rbp+57h+ProviderId.Data4], r14
0x18000c91a  movzx   eax, word ptr [rax]
0x18000c91d  mov     [rbp+57h+var_50.Size], eax
0x18000c920  lea     rax, byte_180041111
0x18000c927  mov     [rbp+57h+var_40], rax
0x18000c92b  lea     rax, _TraceLoggingMetadataEnd
0x18000c932  sub     eax, edx
0x18000c934  mov     dword ptr [rbp+57h+var_50.0Ch], 2
0x18000c93b  mov     [rbp+57h+var_38], 1Dh
0x18000c942  lea     rdx, [rbp+57h+ProviderId]; EventDescriptor
0x18000c946  mov     [rbp+57h+var_34], 1
0x18000c94d  mov     [rbp+57h+fPending], eax
0x18000c950  mov     eax, [rbp+57h+fPending]
0x18000c953  mov     rcx, [rcx+20h]; RegHandle
0x18000c957  lea     rax, [rbp+57h+var_50]
0x18000c95b  mov     [rsp+0A0h+UserData], rax; UserData
0x18000c960  mov     [rsp+0A0h+UserDataCount], 3; UserDataCount
0x18000c968  call    cs:__imp_EventWriteTransfer
0x18000c96e  mov     rcx, [rbp+57h+var_20]
0x18000c972  xor     rcx, rsp; StackCookie
0x18000c975  call    __security_check_cookie
0x18000c97a  add     rsp, 90h
0x18000c981  pop     r14
0x18000c983  pop     rsi
0x18000c984  pop     rbp
0x18000c985  retn
```
