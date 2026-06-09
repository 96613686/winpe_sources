# __report_gsfailure

- ea: `0x140002220`
- end: `0x1400023c0`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004360`

## callees

- `0x1400021dc`
- `0x140002220`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x14000227f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x14000227f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x1400022cc`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x1400022cc`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x140002260`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x140002260`

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
  qword_14000C260 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_14000C250 = -1073740791;
  dword_14000C254 = 1;
  dword_14000C268 = 3;
  qword_14000C270[0] = 2;
  qword_14000C270[1] = _security_cookie;
  qword_14000C270[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x140002220  mov     [rsp+arg_0], rcx
0x140002225  sub     rsp, 88h
0x14000222c  mov     [rsp+88h+ControlPc], 0
0x140002235  mov     [rsp+88h+var_30], 0
0x14000223e  mov     [rsp+88h+FunctionEntry], 0
0x140002247  mov     [rsp+88h+var_28], 0
0x140002250  mov     [rsp+88h+ImageBase], 0
0x140002259  lea     rcx, ContextRecord; ContextRecord
0x140002260  call    cs:__imp_RtlCaptureContext
0x140002266  mov     rax, cs:ContextRecord.Rip
0x14000226d  mov     [rsp+88h+ControlPc], rax
0x140002272  xor     r8d, r8d; HistoryTable
0x140002275  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x14000227a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x14000227f  call    cs:__imp_RtlLookupFunctionEntry
0x140002285  mov     [rsp+88h+FunctionEntry], rax
0x14000228a  cmp     [rsp+88h+FunctionEntry], 0
0x140002290  jz      short loc_1400022D5
0x140002292  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x14000229b  lea     rax, [rsp+88h+var_30]
0x1400022a0  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x1400022a5  lea     rax, [rsp+88h+var_28]
0x1400022aa  mov     [rsp+88h+HandlerData], rax; HandlerData
0x1400022af  lea     rax, ContextRecord
0x1400022b6  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x1400022bb  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x1400022c0  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x1400022c5  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x1400022ca  xor     ecx, ecx; HandlerType
0x1400022cc  call    cs:__imp_RtlVirtualUnwind
0x1400022d2  nop
0x1400022d3  jmp     short loc_1400022F8
0x1400022d5  mov     rax, cs:ContextRecord.Rsp
0x1400022dc  mov     rax, [rax]
0x1400022df  mov     cs:ContextRecord.Rip, rax
0x1400022e6  mov     rax, cs:ContextRecord.Rsp
0x1400022ed  add     rax, 8
0x1400022f1  mov     cs:ContextRecord.Rsp, rax
0x1400022f8  mov     rax, cs:ContextRecord.Rip
0x1400022ff  mov     cs:qword_14000C260, rax
0x140002306  mov     rax, [rsp+88h+arg_0]
0x14000230e  mov     cs:ContextRecord.Rcx, rax
0x140002315  mov     cs:dword_14000C250, 0C0000409h
0x14000231f  mov     cs:dword_14000C254, 1
0x140002329  mov     cs:dword_14000C268, 3
0x140002333  mov     eax, 8
0x140002338  imul    rax, 0
0x14000233c  lea     rcx, qword_14000C270
0x140002343  mov     qword ptr [rcx+rax], 2
0x14000234b  mov     eax, 8
0x140002350  imul    rax, 1
0x140002354  lea     rcx, qword_14000C270
0x14000235b  mov     rdx, cs:__security_cookie
0x140002362  mov     [rcx+rax], rdx
0x140002366  mov     eax, 8
0x14000236b  imul    rax, 2
0x14000236f  lea     rcx, qword_14000C270
0x140002376  mov     rdx, cs:__security_cookie_complement
0x14000237d  mov     [rcx+rax], rdx
0x140002381  mov     eax, 8
0x140002386  imul    rax, 0
0x14000238a  mov     rcx, cs:__security_cookie
0x140002391  mov     [rsp+rax+88h+var_20], rcx
0x140002396  mov     eax, 8
0x14000239b  imul    rax, 1
0x14000239f  mov     rcx, cs:__security_cookie_complement
0x1400023a6  mov     [rsp+rax+88h+var_20], rcx
0x1400023ab  lea     rcx, ExceptionInfo; ExceptionInfo
0x1400023b2  call    __raise_securityfailure
0x1400023b7  nop
0x1400023b8  add     rsp, 88h
0x1400023bf  retn
```
