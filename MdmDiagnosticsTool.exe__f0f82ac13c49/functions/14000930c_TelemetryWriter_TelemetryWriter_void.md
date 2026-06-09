# TelemetryWriter::~TelemetryWriter(void)

- ea: `0x14000930c`
- end: `0x1400093cf`
- name: `??1TelemetryWriter@@QEAA@XZ`
- size: `195`
- prototype: `void __fastcall(TelemetryWriter *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140008130`
- `0x140009cf0`

## callees

- `0x140001248`
- `0x14000126c`
- `0x1400092d4`
- `0x14000930c`
- `0x1400096d0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1400093ae`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1400093ae`

## pseudocode

```c
void __fastcall TelemetryWriter::~TelemetryWriter(TelemetryWriter *this)
{
  char *v1; // rbx
  __int64 v2; // rcx
  int *v3; // r9
  REGHANDLE v4; // rcx
  int v5; // [rsp+30h] [rbp-48h] BYREF
  int *v6; // [rsp+58h] [rbp-20h]
  __int64 v7; // [rsp+60h] [rbp-18h]

  v1 = (char *)this + 4;
  *((_DWORD *)this + 1) = 2;
  if ( (unsigned int)dword_140011000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140011000, 0x200000000000LL) )
  {
    v5 = *v3;
    v7 = 4;
    v6 = &v5;
    tlgWriteTransfer_EventWriteTransfer(v2, &byte_14000E99F);
  }
  v4 = RegHandle;
  dword_140011000 = 0;
  RegHandle = 0;
  EventUnregister(v4);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDiagnosticsToolTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDiagnosticsToolTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(v1);
}

```

## disassembly

```asm
0x14000930c  push    rbx
0x14000930e  sub     rsp, 70h
0x140009312  mov     rax, cs:__security_cookie
0x140009319  xor     rax, rsp
0x14000931c  mov     [rsp+78h+var_10], rax
0x140009321  lea     rbx, [rcx+4]
0x140009325  mov     r9, rcx
0x140009328  mov     dword ptr [rbx], 2
0x14000932e  mov     eax, cs:dword_140011000
0x140009334  cmp     eax, 5
0x140009337  jbe     short loc_140009392
0x140009339  mov     rdx, 200000000000h
0x140009343  lea     rcx, dword_140011000
0x14000934a  call    _tlgKeywordOn
0x14000934f  test    al, al
0x140009351  jz      short loc_140009392
0x140009353  mov     eax, [r9]
0x140009356  lea     r8, [rbx+8]
0x14000935a  mov     [rsp+78h+var_48], eax
0x14000935e  lea     rdx, byte_14000E99F
0x140009365  lea     rax, [rsp+78h+var_48]
0x14000936a  mov     [rsp+78h+var_18], 4
0x140009373  mov     [rsp+78h+var_20], rax
0x140009378  xor     r9d, r9d
0x14000937b  lea     rax, [rsp+78h+var_40]
0x140009380  mov     [rsp+78h+var_50], rax
0x140009385  mov     [rsp+78h+var_58], 3
0x14000938d  call    _tlgWriteTransfer_EventWriteTransfer
0x140009392  mov     rcx, cs:RegHandle; RegHandle
0x140009399  mov     cs:dword_140011000, 0
0x1400093a3  mov     cs:RegHandle, 0
0x1400093ae  call    cs:__imp_EventUnregister
0x1400093b4  mov     rcx, rbx
0x1400093b7  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hDiagnosticsToolTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDiagnosticsToolTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDiagnosticsToolTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(void)
0x1400093bc  mov     rcx, [rsp+78h+var_10]
0x1400093c1  xor     rcx, rsp; StackCookie
0x1400093c4  call    __security_check_cookie
0x1400093c9  add     rsp, 70h
0x1400093cd  pop     rbx
0x1400093ce  retn
```
