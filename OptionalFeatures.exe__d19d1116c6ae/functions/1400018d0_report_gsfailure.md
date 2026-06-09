# __report_gsfailure

- ea: `0x1400018d0`
- end: `0x140001a70`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004ba0`

## callees

- `0x14000188c`
- `0x1400018d0`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x140001910`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x140001910`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x14000192f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x14000192f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x14000197c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x14000197c`

## pseudocode

```c
void __cdecl __noreturn _report_gsfailure(uintptr_t StackCookie)
{
  struct _IMAGE_RUNTIME_FUNCTION_ENTRY *FunctionEntry; // [rsp+40h] [rbp-48h]
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
  qword_140008190 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_140008180 = -1073740791;
  dword_140008184 = 1;
  dword_140008198 = 3;
  qword_1400081A0[0] = 2;
  qword_1400081A0[1] = _security_cookie;
  qword_1400081A0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1400018d0  mov     [rsp+arg_0], rcx
0x1400018d5  sub     rsp, 88h
0x1400018dc  mov     [rsp+88h+ControlPc], 0
0x1400018e5  mov     [rsp+88h+var_30], 0
0x1400018ee  mov     [rsp+88h+FunctionEntry], 0
0x1400018f7  mov     [rsp+88h+var_28], 0
0x140001900  mov     [rsp+88h+ImageBase], 0
0x140001909  lea     rcx, ContextRecord; ContextRecord
0x140001910  call    cs:__imp_RtlCaptureContext
0x140001916  mov     rax, cs:ContextRecord.Rip
0x14000191d  mov     [rsp+88h+ControlPc], rax
0x140001922  xor     r8d, r8d; HistoryTable
0x140001925  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x14000192a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x14000192f  call    cs:__imp_RtlLookupFunctionEntry
0x140001935  mov     [rsp+88h+FunctionEntry], rax
0x14000193a  cmp     [rsp+88h+FunctionEntry], 0
0x140001940  jz      short loc_140001985
0x140001942  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x14000194b  lea     rax, [rsp+88h+var_30]
0x140001950  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x140001955  lea     rax, [rsp+88h+var_28]
0x14000195a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x14000195f  lea     rax, ContextRecord
0x140001966  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x14000196b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x140001970  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x140001975  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x14000197a  xor     ecx, ecx; HandlerType
0x14000197c  call    cs:__imp_RtlVirtualUnwind
0x140001982  nop
0x140001983  jmp     short loc_1400019A8
0x140001985  mov     rax, cs:ContextRecord.Rsp
0x14000198c  mov     rax, [rax]
0x14000198f  mov     cs:ContextRecord.Rip, rax
0x140001996  mov     rax, cs:ContextRecord.Rsp
0x14000199d  add     rax, 8
0x1400019a1  mov     cs:ContextRecord.Rsp, rax
0x1400019a8  mov     rax, cs:ContextRecord.Rip
0x1400019af  mov     cs:qword_140008190, rax
0x1400019b6  mov     rax, [rsp+88h+arg_0]
0x1400019be  mov     cs:ContextRecord.Rcx, rax
0x1400019c5  mov     cs:dword_140008180, 0C0000409h
0x1400019cf  mov     cs:dword_140008184, 1
0x1400019d9  mov     cs:dword_140008198, 3
0x1400019e3  mov     eax, 8
0x1400019e8  imul    rax, 0
0x1400019ec  lea     rcx, qword_1400081A0
0x1400019f3  mov     qword ptr [rcx+rax], 2
0x1400019fb  mov     eax, 8
0x140001a00  imul    rax, 1
0x140001a04  lea     rcx, qword_1400081A0
0x140001a0b  mov     rdx, cs:__security_cookie
0x140001a12  mov     [rcx+rax], rdx
0x140001a16  mov     eax, 8
0x140001a1b  imul    rax, 2
0x140001a1f  lea     rcx, qword_1400081A0
0x140001a26  mov     rdx, cs:__security_cookie_complement
0x140001a2d  mov     [rcx+rax], rdx
0x140001a31  mov     eax, 8
0x140001a36  imul    rax, 0
0x140001a3a  mov     rcx, cs:__security_cookie
0x140001a41  mov     [rsp+rax+88h+var_20], rcx
0x140001a46  mov     eax, 8
0x140001a4b  imul    rax, 1
0x140001a4f  mov     rcx, cs:__security_cookie_complement
0x140001a56  mov     [rsp+rax+88h+var_20], rcx
0x140001a5b  lea     rcx, ExceptionInfo; ExceptionInfo
0x140001a62  call    __raise_securityfailure
0x140001a67  nop
0x140001a68  add     rsp, 88h
0x140001a6f  retn
```
