# __report_rangecheckfailure

- ea: `0x1800021b8`
- end: `0x1800022de`
- name: `__report_rangecheckfailure`
- size: `294`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004144`
- `0x18000633c`
- `0x1800065d0`

## callees

- `0x180001fc8`
- `0x1800021b8`

## import_xrefs

- `ntdll!RtlVirtualUnwind` at `0x18000225c`
- `ntdll!RtlVirtualUnwind` at `0x18000225c`
- `ntdll!RtlLookupFunctionEntry` at `0x18000220f`
- `ntdll!RtlLookupFunctionEntry` at `0x18000220f`
- `ntdll!RtlCaptureContext` at `0x1800021f0`
- `ntdll!RtlCaptureContext` at `0x1800021f0`

## pseudocode

```c
void __noreturn _report_rangecheckfailure()
{
  struct _RUNTIME_FUNCTION *FunctionEntry; // [rsp+40h] [rbp-38h]
  DWORD64 ControlPc; // [rsp+48h] [rbp-30h]
  unsigned __int64 ImageBase; // [rsp+50h] [rbp-28h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+58h] [rbp-20h] BYREF
  PVOID HandlerData; // [rsp+60h] [rbp-18h] BYREF

  EstablisherFrame = 0;
  HandlerData = 0;
  ImageBase = 0;
  RtlCaptureContext(&ContextRecord);
  ControlPc = ContextRecord.Rip;
  FunctionEntry = RtlLookupFunctionEntry(ContextRecord.Rip, &ImageBase, 0);
  if ( FunctionEntry )
  {
    RtlVirtualUnwind(0, ImageBase, ControlPc, FunctionEntry, &ContextRecord, &HandlerData, &EstablisherFrame, 0);
  }
  else
  {
    ContextRecord.Rip = *(_QWORD *)ContextRecord.Rsp;
    ContextRecord.Rsp += 8LL;
  }
  qword_180013410 = ContextRecord.Rip;
  dword_180013400 = -1073740791;
  dword_180013404 = 1;
  dword_180013418 = 1;
  qword_180013420[0] = 8;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1800021b8  sub     rsp, 78h
0x1800021bc  mov     [rsp+78h+ControlPc], 0
0x1800021c5  mov     [rsp+78h+var_20], 0
0x1800021ce  mov     [rsp+78h+FunctionEntry], 0
0x1800021d7  mov     [rsp+78h+var_18], 0
0x1800021e0  mov     [rsp+78h+ImageBase], 0
0x1800021e9  lea     rcx, ContextRecord; ContextRecord
0x1800021f0  call    cs:__imp_RtlCaptureContext
0x1800021f6  mov     rax, cs:ContextRecord.Rip
0x1800021fd  mov     [rsp+78h+ControlPc], rax
0x180002202  xor     r8d, r8d; HistoryTable
0x180002205  lea     rdx, [rsp+78h+ImageBase]; ImageBase
0x18000220a  mov     rcx, [rsp+78h+ControlPc]; ControlPc
0x18000220f  call    cs:__imp_RtlLookupFunctionEntry
0x180002215  mov     [rsp+78h+FunctionEntry], rax
0x18000221a  cmp     [rsp+78h+FunctionEntry], 0
0x180002220  jz      short loc_180002265
0x180002222  mov     [rsp+78h+ContextPointers], 0; ContextPointers
0x18000222b  lea     rax, [rsp+78h+var_20]
0x180002230  mov     [rsp+78h+EstablisherFrame], rax; EstablisherFrame
0x180002235  lea     rax, [rsp+78h+var_18]
0x18000223a  mov     [rsp+78h+HandlerData], rax; HandlerData
0x18000223f  lea     rax, ContextRecord
0x180002246  mov     [rsp+78h+ContextRecord], rax; ContextRecord
0x18000224b  mov     r9, [rsp+78h+FunctionEntry]; FunctionEntry
0x180002250  mov     r8, [rsp+78h+ControlPc]; ControlPc
0x180002255  mov     rdx, [rsp+78h+ImageBase]; ImageBase
0x18000225a  xor     ecx, ecx; HandlerType
0x18000225c  call    cs:__imp_RtlVirtualUnwind
0x180002262  nop
0x180002263  jmp     short loc_180002288
0x180002265  mov     rax, cs:ContextRecord.Rsp
0x18000226c  mov     rax, [rax]
0x18000226f  mov     cs:ContextRecord.Rip, rax
0x180002276  mov     rax, cs:ContextRecord.Rsp
0x18000227d  add     rax, 8
0x180002281  mov     cs:ContextRecord.Rsp, rax
0x180002288  mov     rax, cs:ContextRecord.Rip
0x18000228f  mov     cs:qword_180013410, rax
0x180002296  mov     cs:dword_180013400, 0C0000409h
0x1800022a0  mov     cs:dword_180013404, 1
0x1800022aa  mov     cs:dword_180013418, 1
0x1800022b4  mov     eax, 8
0x1800022b9  imul    rax, 0
0x1800022bd  lea     rcx, qword_180013420
0x1800022c4  mov     qword ptr [rcx+rax], 8
0x1800022cc  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800022d3  call    __raise_securityfailure
0x1800022d8  nop
0x1800022d9  add     rsp, 78h
0x1800022dd  retn
```
