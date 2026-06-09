# __report_gsfailure

- ea: `0x1400019b0`
- end: `0x140001b50`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006b90`

## callees

- `0x14000196c`
- `0x1400019b0`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x140001a5c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x140001a5c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1400019f0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1400019f0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x140001a0f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x140001a0f`

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
  qword_14000C190 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_14000C180 = -1073740791;
  dword_14000C184 = 1;
  dword_14000C198 = 3;
  qword_14000C1A0[0] = 2;
  qword_14000C1A0[1] = _security_cookie;
  qword_14000C1A0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1400019b0  mov     [rsp+arg_0], rcx
0x1400019b5  sub     rsp, 88h
0x1400019bc  mov     [rsp+88h+ControlPc], 0
0x1400019c5  mov     [rsp+88h+var_30], 0
0x1400019ce  mov     [rsp+88h+FunctionEntry], 0
0x1400019d7  mov     [rsp+88h+var_28], 0
0x1400019e0  mov     [rsp+88h+ImageBase], 0
0x1400019e9  lea     rcx, ContextRecord; ContextRecord
0x1400019f0  call    cs:__imp_RtlCaptureContext
0x1400019f6  mov     rax, cs:ContextRecord.Rip
0x1400019fd  mov     [rsp+88h+ControlPc], rax
0x140001a02  xor     r8d, r8d; HistoryTable
0x140001a05  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x140001a0a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x140001a0f  call    cs:__imp_RtlLookupFunctionEntry
0x140001a15  mov     [rsp+88h+FunctionEntry], rax
0x140001a1a  cmp     [rsp+88h+FunctionEntry], 0
0x140001a20  jz      short loc_140001A65
0x140001a22  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x140001a2b  lea     rax, [rsp+88h+var_30]
0x140001a30  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x140001a35  lea     rax, [rsp+88h+var_28]
0x140001a3a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x140001a3f  lea     rax, ContextRecord
0x140001a46  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x140001a4b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x140001a50  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x140001a55  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x140001a5a  xor     ecx, ecx; HandlerType
0x140001a5c  call    cs:__imp_RtlVirtualUnwind
0x140001a62  nop
0x140001a63  jmp     short loc_140001A88
0x140001a65  mov     rax, cs:ContextRecord.Rsp
0x140001a6c  mov     rax, [rax]
0x140001a6f  mov     cs:ContextRecord.Rip, rax
0x140001a76  mov     rax, cs:ContextRecord.Rsp
0x140001a7d  add     rax, 8
0x140001a81  mov     cs:ContextRecord.Rsp, rax
0x140001a88  mov     rax, cs:ContextRecord.Rip
0x140001a8f  mov     cs:qword_14000C190, rax
0x140001a96  mov     rax, [rsp+88h+arg_0]
0x140001a9e  mov     cs:ContextRecord.Rcx, rax
0x140001aa5  mov     cs:dword_14000C180, 0C0000409h
0x140001aaf  mov     cs:dword_14000C184, 1
0x140001ab9  mov     cs:dword_14000C198, 3
0x140001ac3  mov     eax, 8
0x140001ac8  imul    rax, 0
0x140001acc  lea     rcx, qword_14000C1A0
0x140001ad3  mov     qword ptr [rcx+rax], 2
0x140001adb  mov     eax, 8
0x140001ae0  imul    rax, 1
0x140001ae4  lea     rcx, qword_14000C1A0
0x140001aeb  mov     rdx, cs:__security_cookie
0x140001af2  mov     [rcx+rax], rdx
0x140001af6  mov     eax, 8
0x140001afb  imul    rax, 2
0x140001aff  lea     rcx, qword_14000C1A0
0x140001b06  mov     rdx, cs:__security_cookie_complement
0x140001b0d  mov     [rcx+rax], rdx
0x140001b11  mov     eax, 8
0x140001b16  imul    rax, 0
0x140001b1a  mov     rcx, cs:__security_cookie
0x140001b21  mov     [rsp+rax+88h+var_20], rcx
0x140001b26  mov     eax, 8
0x140001b2b  imul    rax, 1
0x140001b2f  mov     rcx, cs:__security_cookie_complement
0x140001b36  mov     [rsp+rax+88h+var_20], rcx
0x140001b3b  lea     rcx, ExceptionInfo; ExceptionInfo
0x140001b42  call    __raise_securityfailure
0x140001b47  nop
0x140001b48  add     rsp, 88h
0x140001b4f  retn
```
