# __report_gsfailure

- ea: `0x1800030f0`
- end: `0x180003290`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005b70`

## callees

- `0x1800030b0`
- `0x1800030f0`

## import_xrefs

- `ntdll!RtlLookupFunctionEntry` at `0x18000314f`
- `ntdll!RtlLookupFunctionEntry` at `0x18000314f`
- `ntdll!RtlCaptureContext` at `0x180003130`
- `ntdll!RtlCaptureContext` at `0x180003130`
- `ntdll!RtlVirtualUnwind` at `0x18000319c`
- `ntdll!RtlVirtualUnwind` at `0x18000319c`

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
  qword_18000B1C0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18000B1B0 = -1073740791;
  dword_18000B1B4 = 1;
  dword_18000B1C8 = 3;
  qword_18000B1D0[0] = 2;
  qword_18000B1D0[1] = _security_cookie;
  qword_18000B1D0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1800030f0  mov     [rsp+arg_0], rcx
0x1800030f5  sub     rsp, 88h
0x1800030fc  mov     [rsp+88h+ControlPc], 0
0x180003105  mov     [rsp+88h+var_30], 0
0x18000310e  mov     [rsp+88h+FunctionEntry], 0
0x180003117  mov     [rsp+88h+var_28], 0
0x180003120  mov     [rsp+88h+ImageBase], 0
0x180003129  lea     rcx, ContextRecord; ContextRecord
0x180003130  call    cs:__imp_RtlCaptureContext
0x180003136  mov     rax, cs:ContextRecord.Rip
0x18000313d  mov     [rsp+88h+ControlPc], rax
0x180003142  xor     r8d, r8d; HistoryTable
0x180003145  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000314a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000314f  call    cs:__imp_RtlLookupFunctionEntry
0x180003155  mov     [rsp+88h+FunctionEntry], rax
0x18000315a  cmp     [rsp+88h+FunctionEntry], 0
0x180003160  jz      short loc_1800031A5
0x180003162  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000316b  lea     rax, [rsp+88h+var_30]
0x180003170  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180003175  lea     rax, [rsp+88h+var_28]
0x18000317a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000317f  lea     rax, ContextRecord
0x180003186  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x18000318b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180003190  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180003195  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000319a  xor     ecx, ecx; HandlerType
0x18000319c  call    cs:__imp_RtlVirtualUnwind
0x1800031a2  nop
0x1800031a3  jmp     short loc_1800031C8
0x1800031a5  mov     rax, cs:ContextRecord.Rsp
0x1800031ac  mov     rax, [rax]
0x1800031af  mov     cs:ContextRecord.Rip, rax
0x1800031b6  mov     rax, cs:ContextRecord.Rsp
0x1800031bd  add     rax, 8
0x1800031c1  mov     cs:ContextRecord.Rsp, rax
0x1800031c8  mov     rax, cs:ContextRecord.Rip
0x1800031cf  mov     cs:qword_18000B1C0, rax
0x1800031d6  mov     rax, [rsp+88h+arg_0]
0x1800031de  mov     cs:ContextRecord.Rcx, rax
0x1800031e5  mov     cs:dword_18000B1B0, 0C0000409h
0x1800031ef  mov     cs:dword_18000B1B4, 1
0x1800031f9  mov     cs:dword_18000B1C8, 3
0x180003203  mov     eax, 8
0x180003208  imul    rax, 0
0x18000320c  lea     rcx, qword_18000B1D0
0x180003213  mov     qword ptr [rcx+rax], 2
0x18000321b  mov     eax, 8
0x180003220  imul    rax, 1
0x180003224  lea     rcx, qword_18000B1D0
0x18000322b  mov     rdx, cs:__security_cookie
0x180003232  mov     [rcx+rax], rdx
0x180003236  mov     eax, 8
0x18000323b  imul    rax, 2
0x18000323f  lea     rcx, qword_18000B1D0
0x180003246  mov     rdx, cs:__security_cookie_complement
0x18000324d  mov     [rcx+rax], rdx
0x180003251  mov     eax, 8
0x180003256  imul    rax, 0
0x18000325a  mov     rcx, cs:__security_cookie
0x180003261  mov     [rsp+rax+88h+var_20], rcx
0x180003266  mov     eax, 8
0x18000326b  imul    rax, 1
0x18000326f  mov     rcx, cs:__security_cookie_complement
0x180003276  mov     [rsp+rax+88h+var_20], rcx
0x18000327b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180003282  call    __raise_securityfailure
0x180003287  nop
0x180003288  add     rsp, 88h
0x18000328f  retn
```
