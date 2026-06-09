# __report_rangecheckfailure

- ea: `0x180001898`
- end: `0x1800019be`
- name: `__report_rangecheckfailure`
- size: `294`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003378`
- `0x180004bac`

## callees

- `0x1800016a8`
- `0x180001898`

## import_xrefs

- `KERNEL32!RtlVirtualUnwind` at `0x18000193c`
- `KERNEL32!RtlVirtualUnwind` at `0x18000193c`
- `KERNEL32!RtlLookupFunctionEntry` at `0x1800018ef`
- `KERNEL32!RtlLookupFunctionEntry` at `0x1800018ef`
- `KERNEL32!RtlCaptureContext` at `0x1800018d0`
- `KERNEL32!RtlCaptureContext` at `0x1800018d0`

## pseudocode

```c
void __noreturn _report_rangecheckfailure()
{
  struct _IMAGE_RUNTIME_FUNCTION_ENTRY *FunctionEntry; // [rsp+40h] [rbp-38h]
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
  qword_18000B280 = ContextRecord.Rip;
  dword_18000B270 = -1073740791;
  dword_18000B274 = 1;
  dword_18000B288 = 1;
  qword_18000B290[0] = 8;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001898  sub     rsp, 78h
0x18000189c  mov     [rsp+78h+ControlPc], 0
0x1800018a5  mov     [rsp+78h+var_20], 0
0x1800018ae  mov     [rsp+78h+FunctionEntry], 0
0x1800018b7  mov     [rsp+78h+var_18], 0
0x1800018c0  mov     [rsp+78h+ImageBase], 0
0x1800018c9  lea     rcx, ContextRecord; ContextRecord
0x1800018d0  call    cs:__imp_RtlCaptureContext
0x1800018d6  mov     rax, cs:ContextRecord.Rip
0x1800018dd  mov     [rsp+78h+ControlPc], rax
0x1800018e2  xor     r8d, r8d; HistoryTable
0x1800018e5  lea     rdx, [rsp+78h+ImageBase]; ImageBase
0x1800018ea  mov     rcx, [rsp+78h+ControlPc]; ControlPc
0x1800018ef  call    cs:__imp_RtlLookupFunctionEntry
0x1800018f5  mov     [rsp+78h+FunctionEntry], rax
0x1800018fa  cmp     [rsp+78h+FunctionEntry], 0
0x180001900  jz      short loc_180001945
0x180001902  mov     [rsp+78h+ContextPointers], 0; ContextPointers
0x18000190b  lea     rax, [rsp+78h+var_20]
0x180001910  mov     [rsp+78h+EstablisherFrame], rax; EstablisherFrame
0x180001915  lea     rax, [rsp+78h+var_18]
0x18000191a  mov     [rsp+78h+HandlerData], rax; HandlerData
0x18000191f  lea     rax, ContextRecord
0x180001926  mov     [rsp+78h+ContextRecord], rax; ContextRecord
0x18000192b  mov     r9, [rsp+78h+FunctionEntry]; FunctionEntry
0x180001930  mov     r8, [rsp+78h+ControlPc]; ControlPc
0x180001935  mov     rdx, [rsp+78h+ImageBase]; ImageBase
0x18000193a  xor     ecx, ecx; HandlerType
0x18000193c  call    cs:__imp_RtlVirtualUnwind
0x180001942  nop
0x180001943  jmp     short loc_180001968
0x180001945  mov     rax, cs:ContextRecord.Rsp
0x18000194c  mov     rax, [rax]
0x18000194f  mov     cs:ContextRecord.Rip, rax
0x180001956  mov     rax, cs:ContextRecord.Rsp
0x18000195d  add     rax, 8
0x180001961  mov     cs:ContextRecord.Rsp, rax
0x180001968  mov     rax, cs:ContextRecord.Rip
0x18000196f  mov     cs:qword_18000B280, rax
0x180001976  mov     cs:dword_18000B270, 0C0000409h
0x180001980  mov     cs:dword_18000B274, 1
0x18000198a  mov     cs:dword_18000B288, 1
0x180001994  mov     eax, 8
0x180001999  imul    rax, 0
0x18000199d  lea     rcx, qword_18000B290
0x1800019a4  mov     qword ptr [rcx+rax], 8
0x1800019ac  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800019b3  call    __raise_securityfailure
0x1800019b8  nop
0x1800019b9  add     rsp, 78h
0x1800019bd  retn
```
