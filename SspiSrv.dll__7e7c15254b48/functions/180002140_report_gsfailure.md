# __report_gsfailure

- ea: `0x180002140`
- end: `0x1800022e0`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003340`

## callees

- `0x180002104`
- `0x180002140`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x180002180`
- `ntdll!RtlCaptureContext` at `0x180002180`
- `ntdll!RtlLookupFunctionEntry` at `0x18000219f`
- `ntdll!RtlLookupFunctionEntry` at `0x18000219f`
- `ntdll!RtlVirtualUnwind` at `0x1800021ec`
- `ntdll!RtlVirtualUnwind` at `0x1800021ec`

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
  qword_18000A0F0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18000A0E0 = -1073740791;
  dword_18000A0E4 = 1;
  dword_18000A0F8 = 3;
  qword_18000A100[0] = 2;
  qword_18000A100[1] = _security_cookie;
  qword_18000A100[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180002140  mov     [rsp+arg_0], rcx
0x180002145  sub     rsp, 88h
0x18000214c  mov     [rsp+88h+ControlPc], 0
0x180002155  mov     [rsp+88h+var_30], 0
0x18000215e  mov     [rsp+88h+FunctionEntry], 0
0x180002167  mov     [rsp+88h+var_28], 0
0x180002170  mov     [rsp+88h+ImageBase], 0
0x180002179  lea     rcx, ContextRecord; ContextRecord
0x180002180  call    cs:__imp_RtlCaptureContext
0x180002186  mov     rax, cs:ContextRecord.Rip
0x18000218d  mov     [rsp+88h+ControlPc], rax
0x180002192  xor     r8d, r8d; HistoryTable
0x180002195  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000219a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000219f  call    cs:__imp_RtlLookupFunctionEntry
0x1800021a5  mov     [rsp+88h+FunctionEntry], rax
0x1800021aa  cmp     [rsp+88h+FunctionEntry], 0
0x1800021b0  jz      short loc_1800021F5
0x1800021b2  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x1800021bb  lea     rax, [rsp+88h+var_30]
0x1800021c0  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x1800021c5  lea     rax, [rsp+88h+var_28]
0x1800021ca  mov     [rsp+88h+HandlerData], rax; HandlerData
0x1800021cf  lea     rax, ContextRecord
0x1800021d6  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x1800021db  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x1800021e0  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x1800021e5  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800021ea  xor     ecx, ecx; HandlerType
0x1800021ec  call    cs:__imp_RtlVirtualUnwind
0x1800021f2  nop
0x1800021f3  jmp     short loc_180002218
0x1800021f5  mov     rax, cs:ContextRecord.Rsp
0x1800021fc  mov     rax, [rax]
0x1800021ff  mov     cs:ContextRecord.Rip, rax
0x180002206  mov     rax, cs:ContextRecord.Rsp
0x18000220d  add     rax, 8
0x180002211  mov     cs:ContextRecord.Rsp, rax
0x180002218  mov     rax, cs:ContextRecord.Rip
0x18000221f  mov     cs:qword_18000A0F0, rax
0x180002226  mov     rax, [rsp+88h+arg_0]
0x18000222e  mov     cs:ContextRecord.Rcx, rax
0x180002235  mov     cs:dword_18000A0E0, 0C0000409h
0x18000223f  mov     cs:dword_18000A0E4, 1
0x180002249  mov     cs:dword_18000A0F8, 3
0x180002253  mov     eax, 8
0x180002258  imul    rax, 0
0x18000225c  lea     rcx, qword_18000A100
0x180002263  mov     qword ptr [rcx+rax], 2
0x18000226b  mov     eax, 8
0x180002270  imul    rax, 1
0x180002274  lea     rcx, qword_18000A100
0x18000227b  mov     rdx, cs:__security_cookie
0x180002282  mov     [rcx+rax], rdx
0x180002286  mov     eax, 8
0x18000228b  imul    rax, 2
0x18000228f  lea     rcx, qword_18000A100
0x180002296  mov     rdx, cs:__security_cookie_complement
0x18000229d  mov     [rcx+rax], rdx
0x1800022a1  mov     eax, 8
0x1800022a6  imul    rax, 0
0x1800022aa  mov     rcx, cs:__security_cookie
0x1800022b1  mov     [rsp+rax+88h+var_20], rcx
0x1800022b6  mov     eax, 8
0x1800022bb  imul    rax, 1
0x1800022bf  mov     rcx, cs:__security_cookie_complement
0x1800022c6  mov     [rsp+rax+88h+var_20], rcx
0x1800022cb  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800022d2  call    __raise_securityfailure
0x1800022d7  nop
0x1800022d8  add     rsp, 88h
0x1800022df  retn
```
