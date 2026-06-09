# __report_rangecheckfailure

- ea: `0x180002698`
- end: `0x1800027be`
- name: `__report_rangecheckfailure`
- size: `294`
- prototype: `void __fastcall __noreturn(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006ac0`
- `0x18000f6f0`

## callees

- `0x1800024a8`
- `0x180002698`

## import_xrefs

- `KERNEL32!RtlCaptureContext` at `0x1800026d0`
- `KERNEL32!RtlCaptureContext` at `0x1800026d0`
- `KERNEL32!RtlLookupFunctionEntry` at `0x1800026ef`
- `KERNEL32!RtlLookupFunctionEntry` at `0x1800026ef`
- `KERNEL32!RtlVirtualUnwind` at `0x18000273c`
- `KERNEL32!RtlVirtualUnwind` at `0x18000273c`

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
  qword_18001C120 = ContextRecord.Rip;
  dword_18001C110 = -1073740791;
  dword_18001C114 = 1;
  dword_18001C128 = 1;
  qword_18001C130[0] = 8;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180002698  sub     rsp, 78h
0x18000269c  mov     [rsp+78h+ControlPc], 0
0x1800026a5  mov     [rsp+78h+var_20], 0
0x1800026ae  mov     [rsp+78h+FunctionEntry], 0
0x1800026b7  mov     [rsp+78h+var_18], 0
0x1800026c0  mov     [rsp+78h+ImageBase], 0
0x1800026c9  lea     rcx, ContextRecord; ContextRecord
0x1800026d0  call    cs:__imp_RtlCaptureContext
0x1800026d6  mov     rax, cs:ContextRecord.Rip
0x1800026dd  mov     [rsp+78h+ControlPc], rax
0x1800026e2  xor     r8d, r8d; HistoryTable
0x1800026e5  lea     rdx, [rsp+78h+ImageBase]; ImageBase
0x1800026ea  mov     rcx, [rsp+78h+ControlPc]; ControlPc
0x1800026ef  call    cs:__imp_RtlLookupFunctionEntry
0x1800026f5  mov     [rsp+78h+FunctionEntry], rax
0x1800026fa  cmp     [rsp+78h+FunctionEntry], 0
0x180002700  jz      short loc_180002745
0x180002702  mov     [rsp+78h+ContextPointers], 0; ContextPointers
0x18000270b  lea     rax, [rsp+78h+var_20]
0x180002710  mov     [rsp+78h+EstablisherFrame], rax; EstablisherFrame
0x180002715  lea     rax, [rsp+78h+var_18]
0x18000271a  mov     [rsp+78h+HandlerData], rax; HandlerData
0x18000271f  lea     rax, ContextRecord
0x180002726  mov     [rsp+78h+ContextRecord], rax; ContextRecord
0x18000272b  mov     r9, [rsp+78h+FunctionEntry]; FunctionEntry
0x180002730  mov     r8, [rsp+78h+ControlPc]; ControlPc
0x180002735  mov     rdx, [rsp+78h+ImageBase]; ImageBase
0x18000273a  xor     ecx, ecx; HandlerType
0x18000273c  call    cs:__imp_RtlVirtualUnwind
0x180002742  nop
0x180002743  jmp     short loc_180002768
0x180002745  mov     rax, cs:ContextRecord.Rsp
0x18000274c  mov     rax, [rax]
0x18000274f  mov     cs:ContextRecord.Rip, rax
0x180002756  mov     rax, cs:ContextRecord.Rsp
0x18000275d  add     rax, 8
0x180002761  mov     cs:ContextRecord.Rsp, rax
0x180002768  mov     rax, cs:ContextRecord.Rip
0x18000276f  mov     cs:qword_18001C120, rax
0x180002776  mov     cs:dword_18001C110, 0C0000409h
0x180002780  mov     cs:dword_18001C114, 1
0x18000278a  mov     cs:dword_18001C128, 1
0x180002794  mov     eax, 8
0x180002799  imul    rax, 0
0x18000279d  lea     rcx, qword_18001C130
0x1800027a4  mov     qword ptr [rcx+rax], 8
0x1800027ac  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800027b3  call    __raise_securityfailure
0x1800027b8  nop
0x1800027b9  add     rsp, 78h
0x1800027bd  retn
```
