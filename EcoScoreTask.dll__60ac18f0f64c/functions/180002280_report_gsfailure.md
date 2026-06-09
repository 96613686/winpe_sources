# __report_gsfailure

- ea: `0x180002280`
- end: `0x180002420`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007c90`

## callees

- `0x180002240`
- `0x180002280`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800022c0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800022c0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x1800022df`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x1800022df`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000232c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000232c`

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
  qword_18000D1A0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18000D190 = -1073740791;
  dword_18000D194 = 1;
  dword_18000D1A8 = 3;
  qword_18000D1B0[0] = 2;
  qword_18000D1B0[1] = _security_cookie;
  qword_18000D1B0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180002280  mov     [rsp+arg_0], rcx
0x180002285  sub     rsp, 88h
0x18000228c  mov     [rsp+88h+ControlPc], 0
0x180002295  mov     [rsp+88h+var_30], 0
0x18000229e  mov     [rsp+88h+FunctionEntry], 0
0x1800022a7  mov     [rsp+88h+var_28], 0
0x1800022b0  mov     [rsp+88h+ImageBase], 0
0x1800022b9  lea     rcx, ContextRecord; ContextRecord
0x1800022c0  call    cs:__imp_RtlCaptureContext
0x1800022c6  mov     rax, cs:ContextRecord.Rip
0x1800022cd  mov     [rsp+88h+ControlPc], rax
0x1800022d2  xor     r8d, r8d; HistoryTable
0x1800022d5  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800022da  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x1800022df  call    cs:__imp_RtlLookupFunctionEntry
0x1800022e5  mov     [rsp+88h+FunctionEntry], rax
0x1800022ea  cmp     [rsp+88h+FunctionEntry], 0
0x1800022f0  jz      short loc_180002335
0x1800022f2  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x1800022fb  lea     rax, [rsp+88h+var_30]
0x180002300  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180002305  lea     rax, [rsp+88h+var_28]
0x18000230a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000230f  lea     rax, ContextRecord
0x180002316  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x18000231b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180002320  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180002325  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000232a  xor     ecx, ecx; HandlerType
0x18000232c  call    cs:__imp_RtlVirtualUnwind
0x180002332  nop
0x180002333  jmp     short loc_180002358
0x180002335  mov     rax, cs:ContextRecord.Rsp
0x18000233c  mov     rax, [rax]
0x18000233f  mov     cs:ContextRecord.Rip, rax
0x180002346  mov     rax, cs:ContextRecord.Rsp
0x18000234d  add     rax, 8
0x180002351  mov     cs:ContextRecord.Rsp, rax
0x180002358  mov     rax, cs:ContextRecord.Rip
0x18000235f  mov     cs:qword_18000D1A0, rax
0x180002366  mov     rax, [rsp+88h+arg_0]
0x18000236e  mov     cs:ContextRecord.Rcx, rax
0x180002375  mov     cs:dword_18000D190, 0C0000409h
0x18000237f  mov     cs:dword_18000D194, 1
0x180002389  mov     cs:dword_18000D1A8, 3
0x180002393  mov     eax, 8
0x180002398  imul    rax, 0
0x18000239c  lea     rcx, qword_18000D1B0
0x1800023a3  mov     qword ptr [rcx+rax], 2
0x1800023ab  mov     eax, 8
0x1800023b0  imul    rax, 1
0x1800023b4  lea     rcx, qword_18000D1B0
0x1800023bb  mov     rdx, cs:__security_cookie
0x1800023c2  mov     [rcx+rax], rdx
0x1800023c6  mov     eax, 8
0x1800023cb  imul    rax, 2
0x1800023cf  lea     rcx, qword_18000D1B0
0x1800023d6  mov     rdx, cs:__security_cookie_complement
0x1800023dd  mov     [rcx+rax], rdx
0x1800023e1  mov     eax, 8
0x1800023e6  imul    rax, 0
0x1800023ea  mov     rcx, cs:__security_cookie
0x1800023f1  mov     [rsp+rax+88h+var_20], rcx
0x1800023f6  mov     eax, 8
0x1800023fb  imul    rax, 1
0x1800023ff  mov     rcx, cs:__security_cookie_complement
0x180002406  mov     [rsp+rax+88h+var_20], rcx
0x18000240b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180002412  call    __raise_securityfailure
0x180002417  nop
0x180002418  add     rsp, 88h
0x18000241f  retn
```
