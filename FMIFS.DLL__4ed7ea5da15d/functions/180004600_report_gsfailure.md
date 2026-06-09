# __report_gsfailure

- ea: `0x180004600`
- end: `0x1800047a0`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009780`

## callees

- `0x1800045c4`
- `0x180004600`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x180004640`
- `ntdll!RtlCaptureContext` at `0x180004640`
- `ntdll!RtlLookupFunctionEntry` at `0x18000465f`
- `ntdll!RtlLookupFunctionEntry` at `0x18000465f`
- `ntdll!RtlVirtualUnwind` at `0x1800046ac`
- `ntdll!RtlVirtualUnwind` at `0x1800046ac`

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
  qword_18000F1E0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18000F1D0 = -1073740791;
  dword_18000F1D4 = 1;
  dword_18000F1E8 = 3;
  qword_18000F1F0[0] = 2;
  qword_18000F1F0[1] = _security_cookie;
  qword_18000F1F0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180004600  mov     [rsp+arg_0], rcx
0x180004605  sub     rsp, 88h
0x18000460c  mov     [rsp+88h+ControlPc], 0
0x180004615  mov     [rsp+88h+var_30], 0
0x18000461e  mov     [rsp+88h+FunctionEntry], 0
0x180004627  mov     [rsp+88h+var_28], 0
0x180004630  mov     [rsp+88h+ImageBase], 0
0x180004639  lea     rcx, ContextRecord; ContextRecord
0x180004640  call    cs:__imp_RtlCaptureContext
0x180004646  mov     rax, cs:ContextRecord.Rip
0x18000464d  mov     [rsp+88h+ControlPc], rax
0x180004652  xor     r8d, r8d; HistoryTable
0x180004655  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000465a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000465f  call    cs:__imp_RtlLookupFunctionEntry
0x180004665  mov     [rsp+88h+FunctionEntry], rax
0x18000466a  cmp     [rsp+88h+FunctionEntry], 0
0x180004670  jz      short loc_1800046B5
0x180004672  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000467b  lea     rax, [rsp+88h+var_30]
0x180004680  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180004685  lea     rax, [rsp+88h+var_28]
0x18000468a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000468f  lea     rax, ContextRecord
0x180004696  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x18000469b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x1800046a0  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x1800046a5  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800046aa  xor     ecx, ecx; HandlerType
0x1800046ac  call    cs:__imp_RtlVirtualUnwind
0x1800046b2  nop
0x1800046b3  jmp     short loc_1800046D8
0x1800046b5  mov     rax, cs:ContextRecord.Rsp
0x1800046bc  mov     rax, [rax]
0x1800046bf  mov     cs:ContextRecord.Rip, rax
0x1800046c6  mov     rax, cs:ContextRecord.Rsp
0x1800046cd  add     rax, 8
0x1800046d1  mov     cs:ContextRecord.Rsp, rax
0x1800046d8  mov     rax, cs:ContextRecord.Rip
0x1800046df  mov     cs:qword_18000F1E0, rax
0x1800046e6  mov     rax, [rsp+88h+arg_0]
0x1800046ee  mov     cs:ContextRecord.Rcx, rax
0x1800046f5  mov     cs:dword_18000F1D0, 0C0000409h
0x1800046ff  mov     cs:dword_18000F1D4, 1
0x180004709  mov     cs:dword_18000F1E8, 3
0x180004713  mov     eax, 8
0x180004718  imul    rax, 0
0x18000471c  lea     rcx, qword_18000F1F0
0x180004723  mov     qword ptr [rcx+rax], 2
0x18000472b  mov     eax, 8
0x180004730  imul    rax, 1
0x180004734  lea     rcx, qword_18000F1F0
0x18000473b  mov     rdx, cs:__security_cookie
0x180004742  mov     [rcx+rax], rdx
0x180004746  mov     eax, 8
0x18000474b  imul    rax, 2
0x18000474f  lea     rcx, qword_18000F1F0
0x180004756  mov     rdx, cs:__security_cookie_complement
0x18000475d  mov     [rcx+rax], rdx
0x180004761  mov     eax, 8
0x180004766  imul    rax, 0
0x18000476a  mov     rcx, cs:__security_cookie
0x180004771  mov     [rsp+rax+88h+var_20], rcx
0x180004776  mov     eax, 8
0x18000477b  imul    rax, 1
0x18000477f  mov     rcx, cs:__security_cookie_complement
0x180004786  mov     [rsp+rax+88h+var_20], rcx
0x18000478b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180004792  call    __raise_securityfailure
0x180004797  nop
0x180004798  add     rsp, 88h
0x18000479f  retn
```
