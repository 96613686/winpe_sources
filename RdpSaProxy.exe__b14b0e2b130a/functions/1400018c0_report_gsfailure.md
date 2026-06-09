# __report_gsfailure

- ea: `0x1400018c0`
- end: `0x140001a60`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400056f0`

## callees

- `0x14000187c`
- `0x1400018c0`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x14000196c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x14000196c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x140001900`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x140001900`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x14000191f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x14000191f`

## pseudocode

```c
void __cdecl __noreturn _report_gsfailure(uintptr_t StackCookie)
{
  struct _RUNTIME_FUNCTION *FunctionEntry; // [rsp+40h] [rbp-48h]
  DWORD64 ControlPc; // [rsp+48h] [rbp-40h]
  unsigned __int64 ImageBase; // [rsp+50h] [rbp-38h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+58h] [rbp-30h] BYREF
  PVOID HandlerData[5]; // [rsp+60h] [rbp-28h] BYREF

  EstablisherFrame = 0;
  HandlerData[0] = 0;
  ImageBase = 0;
  RtlCaptureContext(&ContextRecord);
  ControlPc = ContextRecord.Rip;
  FunctionEntry = RtlLookupFunctionEntry(ContextRecord.Rip, &ImageBase, 0);
  if ( FunctionEntry )
  {
    RtlVirtualUnwind(0, ImageBase, ControlPc, FunctionEntry, &ContextRecord, HandlerData, &EstablisherFrame, 0);
  }
  else
  {
    ContextRecord.Rip = *(_QWORD *)ContextRecord.Rsp;
    ContextRecord.Rsp += 8LL;
  }
  qword_14000B230 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_14000B220 = -1073740791;
  dword_14000B224 = 1;
  dword_14000B238 = 3;
  qword_14000B240[0] = 2;
  qword_14000B240[1] = _security_cookie;
  qword_14000B240[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1400018c0  mov     [rsp+arg_0], rcx
0x1400018c5  sub     rsp, 88h
0x1400018cc  mov     [rsp+88h+ControlPc], 0
0x1400018d5  mov     [rsp+88h+var_30], 0
0x1400018de  mov     [rsp+88h+FunctionEntry], 0
0x1400018e7  mov     [rsp+88h+var_28], 0
0x1400018f0  mov     [rsp+88h+ImageBase], 0
0x1400018f9  lea     rcx, ContextRecord; ContextRecord
0x140001900  call    cs:__imp_RtlCaptureContext
0x140001906  mov     rax, cs:ContextRecord.Rip
0x14000190d  mov     [rsp+88h+ControlPc], rax
0x140001912  xor     r8d, r8d; HistoryTable
0x140001915  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x14000191a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x14000191f  call    cs:__imp_RtlLookupFunctionEntry
0x140001925  mov     [rsp+88h+FunctionEntry], rax
0x14000192a  cmp     [rsp+88h+FunctionEntry], 0
0x140001930  jz      short loc_140001975
0x140001932  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x14000193b  lea     rax, [rsp+88h+var_30]
0x140001940  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x140001945  lea     rax, [rsp+88h+var_28]
0x14000194a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x14000194f  lea     rax, ContextRecord
0x140001956  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x14000195b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x140001960  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x140001965  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x14000196a  xor     ecx, ecx; HandlerType
0x14000196c  call    cs:__imp_RtlVirtualUnwind
0x140001972  nop
0x140001973  jmp     short loc_140001998
0x140001975  mov     rax, cs:ContextRecord.Rsp
0x14000197c  mov     rax, [rax]
0x14000197f  mov     cs:ContextRecord.Rip, rax
0x140001986  mov     rax, cs:ContextRecord.Rsp
0x14000198d  add     rax, 8
0x140001991  mov     cs:ContextRecord.Rsp, rax
0x140001998  mov     rax, cs:ContextRecord.Rip
0x14000199f  mov     cs:qword_14000B230, rax
0x1400019a6  mov     rax, [rsp+88h+arg_0]
0x1400019ae  mov     cs:ContextRecord.Rcx, rax
0x1400019b5  mov     cs:dword_14000B220, 0C0000409h
0x1400019bf  mov     cs:dword_14000B224, 1
0x1400019c9  mov     cs:dword_14000B238, 3
0x1400019d3  mov     eax, 8
0x1400019d8  imul    rax, 0
0x1400019dc  lea     rcx, qword_14000B240
0x1400019e3  mov     qword ptr [rcx+rax], 2
0x1400019eb  mov     eax, 8
0x1400019f0  imul    rax, 1
0x1400019f4  lea     rcx, qword_14000B240
0x1400019fb  mov     rdx, cs:__security_cookie
0x140001a02  mov     [rcx+rax], rdx
0x140001a06  mov     eax, 8
0x140001a0b  imul    rax, 2
0x140001a0f  lea     rcx, qword_14000B240
0x140001a16  mov     rdx, cs:__security_cookie_complement
0x140001a1d  mov     [rcx+rax], rdx
0x140001a21  mov     eax, 8
0x140001a26  imul    rax, 0
0x140001a2a  mov     rcx, cs:__security_cookie
0x140001a31  mov     [rsp+rax+88h+var_20], rcx
0x140001a36  mov     eax, 8
0x140001a3b  imul    rax, 1
0x140001a3f  mov     rcx, cs:__security_cookie_complement
0x140001a46  mov     [rsp+rax+88h+var_20], rcx
0x140001a4b  lea     rcx, ExceptionInfo; ExceptionInfo
0x140001a52  call    __raise_securityfailure
0x140001a57  nop
0x140001a58  add     rsp, 88h
0x140001a5f  retn
```
