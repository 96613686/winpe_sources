# __report_gsfailure

- ea: `0x180001fe0`
- end: `0x180002180`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002340`

## callees

- `0x180001fa4`
- `0x180001fe0`

## import_xrefs

- `KERNEL32!RtlVirtualUnwind` at `0x18000208c`
- `KERNEL32!RtlVirtualUnwind` at `0x18000208c`
- `KERNEL32!RtlLookupFunctionEntry` at `0x18000203f`
- `KERNEL32!RtlLookupFunctionEntry` at `0x18000203f`
- `KERNEL32!RtlCaptureContext` at `0x180002020`
- `KERNEL32!RtlCaptureContext` at `0x180002020`

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
  qword_1800060C0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_1800060B0 = -1073740791;
  dword_1800060B4 = 1;
  dword_1800060C8 = 3;
  qword_1800060D0[0] = 2;
  qword_1800060D0[1] = _security_cookie;
  qword_1800060D0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001fe0  mov     [rsp+arg_0], rcx
0x180001fe5  sub     rsp, 88h
0x180001fec  mov     [rsp+88h+ControlPc], 0
0x180001ff5  mov     [rsp+88h+var_30], 0
0x180001ffe  mov     [rsp+88h+FunctionEntry], 0
0x180002007  mov     [rsp+88h+var_28], 0
0x180002010  mov     [rsp+88h+ImageBase], 0
0x180002019  lea     rcx, ContextRecord; ContextRecord
0x180002020  call    cs:__imp_RtlCaptureContext
0x180002026  mov     rax, cs:ContextRecord.Rip
0x18000202d  mov     [rsp+88h+ControlPc], rax
0x180002032  xor     r8d, r8d; HistoryTable
0x180002035  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000203a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000203f  call    cs:__imp_RtlLookupFunctionEntry
0x180002045  mov     [rsp+88h+FunctionEntry], rax
0x18000204a  cmp     [rsp+88h+FunctionEntry], 0
0x180002050  jz      short loc_180002095
0x180002052  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000205b  lea     rax, [rsp+88h+var_30]
0x180002060  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180002065  lea     rax, [rsp+88h+var_28]
0x18000206a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000206f  lea     rax, ContextRecord
0x180002076  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x18000207b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180002080  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180002085  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000208a  xor     ecx, ecx; HandlerType
0x18000208c  call    cs:__imp_RtlVirtualUnwind
0x180002092  nop
0x180002093  jmp     short loc_1800020B8
0x180002095  mov     rax, cs:ContextRecord.Rsp
0x18000209c  mov     rax, [rax]
0x18000209f  mov     cs:ContextRecord.Rip, rax
0x1800020a6  mov     rax, cs:ContextRecord.Rsp
0x1800020ad  add     rax, 8
0x1800020b1  mov     cs:ContextRecord.Rsp, rax
0x1800020b8  mov     rax, cs:ContextRecord.Rip
0x1800020bf  mov     cs:qword_1800060C0, rax
0x1800020c6  mov     rax, [rsp+88h+arg_0]
0x1800020ce  mov     cs:ContextRecord.Rcx, rax
0x1800020d5  mov     cs:dword_1800060B0, 0C0000409h
0x1800020df  mov     cs:dword_1800060B4, 1
0x1800020e9  mov     cs:dword_1800060C8, 3
0x1800020f3  mov     eax, 8
0x1800020f8  imul    rax, 0
0x1800020fc  lea     rcx, qword_1800060D0
0x180002103  mov     qword ptr [rcx+rax], 2
0x18000210b  mov     eax, 8
0x180002110  imul    rax, 1
0x180002114  lea     rcx, qword_1800060D0
0x18000211b  mov     rdx, cs:__security_cookie
0x180002122  mov     [rcx+rax], rdx
0x180002126  mov     eax, 8
0x18000212b  imul    rax, 2
0x18000212f  lea     rcx, qword_1800060D0
0x180002136  mov     rdx, cs:__security_cookie_complement
0x18000213d  mov     [rcx+rax], rdx
0x180002141  mov     eax, 8
0x180002146  imul    rax, 0
0x18000214a  mov     rcx, cs:__security_cookie
0x180002151  mov     [rsp+rax+88h+var_20], rcx
0x180002156  mov     eax, 8
0x18000215b  imul    rax, 1
0x18000215f  mov     rcx, cs:__security_cookie_complement
0x180002166  mov     [rsp+rax+88h+var_20], rcx
0x18000216b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180002172  call    __raise_securityfailure
0x180002177  nop
0x180002178  add     rsp, 88h
0x18000217f  retn
```
