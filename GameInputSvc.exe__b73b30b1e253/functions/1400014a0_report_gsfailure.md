# __report_gsfailure

- ea: `0x1400014a0`
- end: `0x140001617`
- name: `__report_gsfailure`
- size: `375`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007750`

## callees

- `0x1400014a0`
- `0x1400016dc`
- `0x1400016e8`
- `0x1400016f4`
- `0x140001700`
- `0x14000170c`

## pseudocode

```c
void __cdecl __noreturn _report_gsfailure(uintptr_t StackCookie)
{
  struct _RUNTIME_FUNCTION *FunctionEntry; // [rsp+40h] [rbp-48h]
  DWORD64 ControlPc; // [rsp+48h] [rbp-40h]
  unsigned __int64 ImageBase; // [rsp+50h] [rbp-38h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+58h] [rbp-30h] BYREF
  PVOID HandlerData[5]; // [rsp+60h] [rbp-28h] BYREF
  DWORD64 retaddr; // [rsp+88h] [rbp+0h]
  uintptr_t v7; // [rsp+90h] [rbp+8h] BYREF

  v7 = StackCookie;
  EstablisherFrame = 0;
  HandlerData[0] = 0;
  ImageBase = 0;
  RtlCaptureContext_0(&ContextRecord);
  ControlPc = ContextRecord.Rip;
  FunctionEntry = RtlLookupFunctionEntry_0(ContextRecord.Rip, &ImageBase, 0);
  if ( FunctionEntry )
  {
    RtlVirtualUnwind_0(0, ImageBase, ControlPc, FunctionEntry, &ContextRecord, HandlerData, &EstablisherFrame, 0);
  }
  else
  {
    ContextRecord.Rip = retaddr;
    ContextRecord.Rsp = (DWORD64)&v7;
  }
  qword_14000E090 = ContextRecord.Rip;
  ContextRecord.Rcx = v7;
  dword_14000E080 = -1073740791;
  dword_14000E084 = 1;
  dword_14000E098 = 1;
  qword_14000E0A0[0] = 2;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  RtlUnhandledExceptionFilter_0((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
  NtTerminateProcess_0((HANDLE)0xFFFFFFFFFFFFFFFFLL, -1073740791);
}

```

## disassembly

```asm
0x1400014a0  mov     [rsp+arg_0], rcx
0x1400014a5  sub     rsp, 88h
0x1400014ac  mov     [rsp+88h+ControlPc], 0
0x1400014b5  mov     [rsp+88h+var_30], 0
0x1400014be  mov     [rsp+88h+FunctionEntry], 0
0x1400014c7  mov     [rsp+88h+var_28], 0
0x1400014d0  mov     [rsp+88h+ImageBase], 0
0x1400014d9  lea     rcx, ContextRecord; ContextRecord
0x1400014e0  call    RtlCaptureContext_0
0x1400014e5  mov     rax, cs:ContextRecord.Rip
0x1400014ec  mov     [rsp+88h+ControlPc], rax
0x1400014f1  xor     r8d, r8d; HistoryTable
0x1400014f4  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x1400014f9  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x1400014fe  call    RtlLookupFunctionEntry_0
0x140001503  mov     [rsp+88h+FunctionEntry], rax
0x140001508  cmp     [rsp+88h+FunctionEntry], 0
0x14000150e  jz      short loc_140001552
0x140001510  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x140001519  lea     rax, [rsp+88h+var_30]
0x14000151e  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x140001523  lea     rax, [rsp+88h+var_28]
0x140001528  mov     [rsp+88h+HandlerData], rax; HandlerData
0x14000152d  lea     rax, ContextRecord
0x140001534  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x140001539  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x14000153e  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x140001543  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x140001548  xor     ecx, ecx; HandlerType
0x14000154a  call    RtlVirtualUnwind_0
0x14000154f  nop
0x140001550  jmp     short loc_140001574
0x140001552  mov     rax, [rsp+88h]
0x14000155a  mov     cs:ContextRecord.Rip, rax
0x140001561  lea     rax, [rsp+88h]
0x140001569  add     rax, 8
0x14000156d  mov     cs:ContextRecord.Rsp, rax
0x140001574  mov     rax, cs:ContextRecord.Rip
0x14000157b  mov     cs:qword_14000E090, rax
0x140001582  mov     rax, [rsp+88h+arg_0]
0x14000158a  mov     cs:ContextRecord.Rcx, rax
0x140001591  mov     cs:dword_14000E080, 0C0000409h
0x14000159b  mov     cs:dword_14000E084, 1
0x1400015a5  mov     cs:dword_14000E098, 1
0x1400015af  mov     eax, 8
0x1400015b4  imul    rax, 0
0x1400015b8  lea     rcx, qword_14000E0A0
0x1400015bf  mov     qword ptr [rcx+rax], 2
0x1400015c7  mov     eax, 8
0x1400015cc  imul    rax, 0
0x1400015d0  mov     rcx, cs:__security_cookie
0x1400015d7  mov     [rsp+rax+88h+var_20], rcx
0x1400015dc  mov     eax, 8
0x1400015e1  imul    rax, 1
0x1400015e5  mov     rcx, cs:__security_cookie_complement
0x1400015ec  mov     [rsp+rax+88h+var_20], rcx
0x1400015f1  lea     rcx, ExceptionInfo; ExceptionInfo
0x1400015f8  call    RtlUnhandledExceptionFilter_0
0x1400015fd  mov     edx, 0C0000409h; ExitStatus
0x140001602  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140001609  call    NtTerminateProcess_0
0x14000160e  nop
0x14000160f  add     rsp, 88h
0x140001616  retn
```
