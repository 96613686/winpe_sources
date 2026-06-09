# __report_rangecheckfailure

- ea: `0x180001a68`
- end: `0x180001b8e`
- name: `__report_rangecheckfailure`
- size: `294`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000672c`
- `0x180006b14`

## callees

- `0x18000187c`
- `0x180001a68`

## import_xrefs

- `KERNEL32!RtlVirtualUnwind` at `0x180001b0c`
- `KERNEL32!RtlVirtualUnwind` at `0x180001b0c`
- `KERNEL32!RtlLookupFunctionEntry` at `0x180001abf`
- `KERNEL32!RtlLookupFunctionEntry` at `0x180001abf`
- `KERNEL32!RtlCaptureContext` at `0x180001aa0`
- `KERNEL32!RtlCaptureContext` at `0x180001aa0`

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
  qword_180012300 = ContextRecord.Rip;
  dword_1800122F0 = -1073740791;
  dword_1800122F4 = 1;
  dword_180012308 = 1;
  qword_180012310[0] = 8;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001a68  sub     rsp, 78h
0x180001a6c  mov     [rsp+78h+ControlPc], 0
0x180001a75  mov     [rsp+78h+var_20], 0
0x180001a7e  mov     [rsp+78h+FunctionEntry], 0
0x180001a87  mov     [rsp+78h+var_18], 0
0x180001a90  mov     [rsp+78h+ImageBase], 0
0x180001a99  lea     rcx, ContextRecord; ContextRecord
0x180001aa0  call    cs:__imp_RtlCaptureContext
0x180001aa6  mov     rax, cs:ContextRecord.Rip
0x180001aad  mov     [rsp+78h+ControlPc], rax
0x180001ab2  xor     r8d, r8d; HistoryTable
0x180001ab5  lea     rdx, [rsp+78h+ImageBase]; ImageBase
0x180001aba  mov     rcx, [rsp+78h+ControlPc]; ControlPc
0x180001abf  call    cs:__imp_RtlLookupFunctionEntry
0x180001ac5  mov     [rsp+78h+FunctionEntry], rax
0x180001aca  cmp     [rsp+78h+FunctionEntry], 0
0x180001ad0  jz      short loc_180001B15
0x180001ad2  mov     [rsp+78h+ContextPointers], 0; ContextPointers
0x180001adb  lea     rax, [rsp+78h+var_20]
0x180001ae0  mov     [rsp+78h+EstablisherFrame], rax; EstablisherFrame
0x180001ae5  lea     rax, [rsp+78h+var_18]
0x180001aea  mov     [rsp+78h+HandlerData], rax; HandlerData
0x180001aef  lea     rax, ContextRecord
0x180001af6  mov     [rsp+78h+ContextRecord], rax; ContextRecord
0x180001afb  mov     r9, [rsp+78h+FunctionEntry]; FunctionEntry
0x180001b00  mov     r8, [rsp+78h+ControlPc]; ControlPc
0x180001b05  mov     rdx, [rsp+78h+ImageBase]; ImageBase
0x180001b0a  xor     ecx, ecx; HandlerType
0x180001b0c  call    cs:__imp_RtlVirtualUnwind
0x180001b12  nop
0x180001b13  jmp     short loc_180001B38
0x180001b15  mov     rax, cs:ContextRecord.Rsp
0x180001b1c  mov     rax, [rax]
0x180001b1f  mov     cs:ContextRecord.Rip, rax
0x180001b26  mov     rax, cs:ContextRecord.Rsp
0x180001b2d  add     rax, 8
0x180001b31  mov     cs:ContextRecord.Rsp, rax
0x180001b38  mov     rax, cs:ContextRecord.Rip
0x180001b3f  mov     cs:qword_180012300, rax
0x180001b46  mov     cs:dword_1800122F0, 0C0000409h
0x180001b50  mov     cs:dword_1800122F4, 1
0x180001b5a  mov     cs:dword_180012308, 1
0x180001b64  mov     eax, 8
0x180001b69  imul    rax, 0
0x180001b6d  lea     rcx, qword_180012310
0x180001b74  mov     qword ptr [rcx+rax], 8
0x180001b7c  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001b83  call    __raise_securityfailure
0x180001b88  nop
0x180001b89  add     rsp, 78h
0x180001b8d  retn
```
