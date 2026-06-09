# TelemetryWriter::~TelemetryWriter(void)

- ea: `0x140009938`
- end: `0x140009a02`
- name: `??1TelemetryWriter@@QEAA@XZ`
- size: `202`
- prototype: `void __fastcall(TelemetryWriter *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140008694`
- `0x14000a325`

## callees

- `0x140001258`
- `0x140001280`
- `0x140009900`
- `0x140009938`
- `0x140009d00`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1400099da`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1400099da`

## pseudocode

```c
void __fastcall TelemetryWriter::~TelemetryWriter(TelemetryWriter *this, __int64 a2, __int64 a3)
{
  char *v3; // rbx
  __int64 v4; // rcx
  int *v5; // r9
  REGHANDLE v6; // rcx
  int v7; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+38h] [rbp-40h] BYREF
  int *v9; // [rsp+58h] [rbp-20h]
  __int64 v10; // [rsp+60h] [rbp-18h]

  v3 = (char *)this + 4;
  *((_DWORD *)this + 1) = 2;
  if ( (unsigned int)dword_140012000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140012000, 0x200000000000LL, a3, this) )
  {
    v7 = *v5;
    v10 = 4;
    v9 = &v7;
    tlgWriteTransfer_EventWriteTransfer(v4, (unsigned __int8 *)byte_14000F99F, (const GUID *)(v3 + 8), 0, 3u, &v8);
  }
  v6 = RegHandle;
  dword_140012000 = 0;
  RegHandle = 0;
  EventUnregister(v6);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDiagnosticsToolTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDiagnosticsToolTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(v3);
}

```

## disassembly

```asm
0x140009938  push    rbx
0x14000993a  sub     rsp, 70h
0x14000993e  mov     rax, cs:__security_cookie
0x140009945  xor     rax, rsp
0x140009948  mov     [rsp+78h+var_10], rax
0x14000994d  lea     rbx, [rcx+4]
0x140009951  mov     r9, rcx
0x140009954  mov     dword ptr [rbx], 2
0x14000995a  mov     eax, cs:dword_140012000
0x140009960  cmp     eax, 5
0x140009963  jbe     short loc_1400099BE
0x140009965  mov     rdx, 200000000000h
0x14000996f  lea     rcx, dword_140012000
0x140009976  call    _tlgKeywordOn
0x14000997b  test    al, al
0x14000997d  jz      short loc_1400099BE
0x14000997f  mov     eax, [r9]
0x140009982  lea     r8, [rbx+8]
0x140009986  mov     [rsp+78h+var_48], eax
0x14000998a  lea     rdx, byte_14000F99F
0x140009991  lea     rax, [rsp+78h+var_48]
0x140009996  mov     [rsp+78h+var_18], 4
0x14000999f  mov     [rsp+78h+var_20], rax
0x1400099a4  xor     r9d, r9d
0x1400099a7  lea     rax, [rsp+78h+var_40]
0x1400099ac  mov     [rsp+78h+var_50], rax
0x1400099b1  mov     [rsp+78h+var_58], 3
0x1400099b9  call    _tlgWriteTransfer_EventWriteTransfer
0x1400099be  mov     rcx, cs:RegHandle; RegHandle
0x1400099c5  mov     cs:dword_140012000, 0
0x1400099cf  mov     cs:RegHandle, 0
0x1400099da  call    cs:__imp_EventUnregister
0x1400099e1  nop     dword ptr [rax+rax+00h]
0x1400099e6  mov     rcx, rbx
0x1400099e9  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hDiagnosticsToolTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDiagnosticsToolTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDiagnosticsToolTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(void)
0x1400099ee  mov     rcx, [rsp+78h+var_10]
0x1400099f3  xor     rcx, rsp; StackCookie
0x1400099f6  call    __security_check_cookie
0x1400099fb  add     rsp, 70h
0x1400099ff  pop     rbx
0x140009a00  retn
```
