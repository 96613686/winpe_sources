# __report_gsfailure

- ea: `0x140001660`
- end: `0x140001800`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002d60`

## callees

- `0x140001620`
- `0x140001660`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x14000170c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x14000170c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x1400016bf`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x1400016bf`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1400016a0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1400016a0`

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
  qword_140005150 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_140005140 = -1073740791;
  dword_140005144 = 1;
  dword_140005158 = 3;
  qword_140005160[0] = 2;
  qword_140005160[1] = _security_cookie;
  qword_140005160[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x140001660  mov     [rsp+arg_0], rcx
0x140001665  sub     rsp, 88h
0x14000166c  mov     [rsp+88h+ControlPc], 0
0x140001675  mov     [rsp+88h+var_30], 0
0x14000167e  mov     [rsp+88h+FunctionEntry], 0
0x140001687  mov     [rsp+88h+var_28], 0
0x140001690  mov     [rsp+88h+ImageBase], 0
0x140001699  lea     rcx, ContextRecord; ContextRecord
0x1400016a0  call    cs:__imp_RtlCaptureContext
0x1400016a6  mov     rax, cs:ContextRecord.Rip
0x1400016ad  mov     [rsp+88h+ControlPc], rax
0x1400016b2  xor     r8d, r8d; HistoryTable
0x1400016b5  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x1400016ba  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x1400016bf  call    cs:__imp_RtlLookupFunctionEntry
0x1400016c5  mov     [rsp+88h+FunctionEntry], rax
0x1400016ca  cmp     [rsp+88h+FunctionEntry], 0
0x1400016d0  jz      short loc_140001715
0x1400016d2  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x1400016db  lea     rax, [rsp+88h+var_30]
0x1400016e0  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x1400016e5  lea     rax, [rsp+88h+var_28]
0x1400016ea  mov     [rsp+88h+HandlerData], rax; HandlerData
0x1400016ef  lea     rax, ContextRecord
0x1400016f6  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x1400016fb  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x140001700  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x140001705  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x14000170a  xor     ecx, ecx; HandlerType
0x14000170c  call    cs:__imp_RtlVirtualUnwind
0x140001712  nop
0x140001713  jmp     short loc_140001738
0x140001715  mov     rax, cs:ContextRecord.Rsp
0x14000171c  mov     rax, [rax]
0x14000171f  mov     cs:ContextRecord.Rip, rax
0x140001726  mov     rax, cs:ContextRecord.Rsp
0x14000172d  add     rax, 8
0x140001731  mov     cs:ContextRecord.Rsp, rax
0x140001738  mov     rax, cs:ContextRecord.Rip
0x14000173f  mov     cs:qword_140005150, rax
0x140001746  mov     rax, [rsp+88h+arg_0]
0x14000174e  mov     cs:ContextRecord.Rcx, rax
0x140001755  mov     cs:dword_140005140, 0C0000409h
0x14000175f  mov     cs:dword_140005144, 1
0x140001769  mov     cs:dword_140005158, 3
0x140001773  mov     eax, 8
0x140001778  imul    rax, 0
0x14000177c  lea     rcx, qword_140005160
0x140001783  mov     qword ptr [rcx+rax], 2
0x14000178b  mov     eax, 8
0x140001790  imul    rax, 1
0x140001794  lea     rcx, qword_140005160
0x14000179b  mov     rdx, cs:__security_cookie
0x1400017a2  mov     [rcx+rax], rdx
0x1400017a6  mov     eax, 8
0x1400017ab  imul    rax, 2
0x1400017af  lea     rcx, qword_140005160
0x1400017b6  mov     rdx, cs:__security_cookie_complement
0x1400017bd  mov     [rcx+rax], rdx
0x1400017c1  mov     eax, 8
0x1400017c6  imul    rax, 0
0x1400017ca  mov     rcx, cs:__security_cookie
0x1400017d1  mov     [rsp+rax+88h+var_20], rcx
0x1400017d6  mov     eax, 8
0x1400017db  imul    rax, 1
0x1400017df  mov     rcx, cs:__security_cookie_complement
0x1400017e6  mov     [rsp+rax+88h+var_20], rcx
0x1400017eb  lea     rcx, ExceptionInfo; ExceptionInfo
0x1400017f2  call    __raise_securityfailure
0x1400017f7  nop
0x1400017f8  add     rsp, 88h
0x1400017ff  retn
```
