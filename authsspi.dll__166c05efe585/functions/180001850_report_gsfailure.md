# __report_gsfailure

- ea: `0x180001850`
- end: `0x1800019f0`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008ba0`

## callees

- `0x18000180c`
- `0x180001850`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x180001890`
- `ntdll!RtlCaptureContext` at `0x180001890`
- `ntdll!RtlLookupFunctionEntry` at `0x1800018af`
- `ntdll!RtlLookupFunctionEntry` at `0x1800018af`
- `ntdll!RtlVirtualUnwind` at `0x1800018fc`
- `ntdll!RtlVirtualUnwind` at `0x1800018fc`

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
  qword_18000E0C0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18000E0B0 = -1073740791;
  dword_18000E0B4 = 1;
  dword_18000E0C8 = 3;
  qword_18000E0D0[0] = 2;
  qword_18000E0D0[1] = _security_cookie;
  qword_18000E0D0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001850  mov     [rsp+arg_0], rcx
0x180001855  sub     rsp, 88h
0x18000185c  mov     [rsp+88h+ControlPc], 0
0x180001865  mov     [rsp+88h+var_30], 0
0x18000186e  mov     [rsp+88h+FunctionEntry], 0
0x180001877  mov     [rsp+88h+var_28], 0
0x180001880  mov     [rsp+88h+ImageBase], 0
0x180001889  lea     rcx, ContextRecord; ContextRecord
0x180001890  call    cs:__imp_RtlCaptureContext
0x180001896  mov     rax, cs:ContextRecord.Rip
0x18000189d  mov     [rsp+88h+ControlPc], rax
0x1800018a2  xor     r8d, r8d; HistoryTable
0x1800018a5  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800018aa  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x1800018af  call    cs:__imp_RtlLookupFunctionEntry
0x1800018b5  mov     [rsp+88h+FunctionEntry], rax
0x1800018ba  cmp     [rsp+88h+FunctionEntry], 0
0x1800018c0  jz      short loc_180001905
0x1800018c2  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x1800018cb  lea     rax, [rsp+88h+var_30]
0x1800018d0  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x1800018d5  lea     rax, [rsp+88h+var_28]
0x1800018da  mov     [rsp+88h+HandlerData], rax; HandlerData
0x1800018df  lea     rax, ContextRecord
0x1800018e6  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x1800018eb  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x1800018f0  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x1800018f5  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800018fa  xor     ecx, ecx; HandlerType
0x1800018fc  call    cs:__imp_RtlVirtualUnwind
0x180001902  nop
0x180001903  jmp     short loc_180001928
0x180001905  mov     rax, cs:ContextRecord.Rsp
0x18000190c  mov     rax, [rax]
0x18000190f  mov     cs:ContextRecord.Rip, rax
0x180001916  mov     rax, cs:ContextRecord.Rsp
0x18000191d  add     rax, 8
0x180001921  mov     cs:ContextRecord.Rsp, rax
0x180001928  mov     rax, cs:ContextRecord.Rip
0x18000192f  mov     cs:qword_18000E0C0, rax
0x180001936  mov     rax, [rsp+88h+arg_0]
0x18000193e  mov     cs:ContextRecord.Rcx, rax
0x180001945  mov     cs:dword_18000E0B0, 0C0000409h
0x18000194f  mov     cs:dword_18000E0B4, 1
0x180001959  mov     cs:dword_18000E0C8, 3
0x180001963  mov     eax, 8
0x180001968  imul    rax, 0
0x18000196c  lea     rcx, qword_18000E0D0
0x180001973  mov     qword ptr [rcx+rax], 2
0x18000197b  mov     eax, 8
0x180001980  imul    rax, 1
0x180001984  lea     rcx, qword_18000E0D0
0x18000198b  mov     rdx, cs:__security_cookie
0x180001992  mov     [rcx+rax], rdx
0x180001996  mov     eax, 8
0x18000199b  imul    rax, 2
0x18000199f  lea     rcx, qword_18000E0D0
0x1800019a6  mov     rdx, cs:__security_cookie_complement
0x1800019ad  mov     [rcx+rax], rdx
0x1800019b1  mov     eax, 8
0x1800019b6  imul    rax, 0
0x1800019ba  mov     rcx, cs:__security_cookie
0x1800019c1  mov     [rsp+rax+88h+var_20], rcx
0x1800019c6  mov     eax, 8
0x1800019cb  imul    rax, 1
0x1800019cf  mov     rcx, cs:__security_cookie_complement
0x1800019d6  mov     [rsp+rax+88h+var_20], rcx
0x1800019db  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800019e2  call    __raise_securityfailure
0x1800019e7  nop
0x1800019e8  add     rsp, 88h
0x1800019ef  retn
```
