# __report_gsfailure

- ea: `0x180001700`
- end: `0x1800018a0`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800032e0`

## callees

- `0x1800016c0`
- `0x180001700`

## import_xrefs

- `ntdll!RtlVirtualUnwind` at `0x1800017ac`
- `ntdll!RtlVirtualUnwind` at `0x1800017ac`
- `ntdll!RtlLookupFunctionEntry` at `0x18000175f`
- `ntdll!RtlLookupFunctionEntry` at `0x18000175f`
- `ntdll!RtlCaptureContext` at `0x180001740`
- `ntdll!RtlCaptureContext` at `0x180001740`

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
  qword_1800060C0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_1800060B0 = -1073740791;
  dword_1800060B4 = 1;
  dword_1800060C8 = 3;
  qword_1800060D0[0] = 2;
  qword_1800060D0[1] = _security_cookie;
  qword_1800060D0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001700  mov     [rsp+arg_0], rcx
0x180001705  sub     rsp, 88h
0x18000170c  mov     [rsp+88h+ControlPc], 0
0x180001715  mov     [rsp+88h+var_30], 0
0x18000171e  mov     [rsp+88h+FunctionEntry], 0
0x180001727  mov     [rsp+88h+var_28], 0
0x180001730  mov     [rsp+88h+ImageBase], 0
0x180001739  lea     rcx, ContextRecord; ContextRecord
0x180001740  call    cs:__imp_RtlCaptureContext
0x180001746  mov     rax, cs:ContextRecord.Rip
0x18000174d  mov     [rsp+88h+ControlPc], rax
0x180001752  xor     r8d, r8d; HistoryTable
0x180001755  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000175a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000175f  call    cs:__imp_RtlLookupFunctionEntry
0x180001765  mov     [rsp+88h+FunctionEntry], rax
0x18000176a  cmp     [rsp+88h+FunctionEntry], 0
0x180001770  jz      short loc_1800017B5
0x180001772  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000177b  lea     rax, [rsp+88h+var_30]
0x180001780  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180001785  lea     rax, [rsp+88h+var_28]
0x18000178a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000178f  lea     rax, ContextRecord
0x180001796  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x18000179b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x1800017a0  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x1800017a5  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800017aa  xor     ecx, ecx; HandlerType
0x1800017ac  call    cs:__imp_RtlVirtualUnwind
0x1800017b2  nop
0x1800017b3  jmp     short loc_1800017D8
0x1800017b5  mov     rax, cs:ContextRecord.Rsp
0x1800017bc  mov     rax, [rax]
0x1800017bf  mov     cs:ContextRecord.Rip, rax
0x1800017c6  mov     rax, cs:ContextRecord.Rsp
0x1800017cd  add     rax, 8
0x1800017d1  mov     cs:ContextRecord.Rsp, rax
0x1800017d8  mov     rax, cs:ContextRecord.Rip
0x1800017df  mov     cs:qword_1800060C0, rax
0x1800017e6  mov     rax, [rsp+88h+arg_0]
0x1800017ee  mov     cs:ContextRecord.Rcx, rax
0x1800017f5  mov     cs:dword_1800060B0, 0C0000409h
0x1800017ff  mov     cs:dword_1800060B4, 1
0x180001809  mov     cs:dword_1800060C8, 3
0x180001813  mov     eax, 8
0x180001818  imul    rax, 0
0x18000181c  lea     rcx, qword_1800060D0
0x180001823  mov     qword ptr [rcx+rax], 2
0x18000182b  mov     eax, 8
0x180001830  imul    rax, 1
0x180001834  lea     rcx, qword_1800060D0
0x18000183b  mov     rdx, cs:__security_cookie
0x180001842  mov     [rcx+rax], rdx
0x180001846  mov     eax, 8
0x18000184b  imul    rax, 2
0x18000184f  lea     rcx, qword_1800060D0
0x180001856  mov     rdx, cs:__security_cookie_complement
0x18000185d  mov     [rcx+rax], rdx
0x180001861  mov     eax, 8
0x180001866  imul    rax, 0
0x18000186a  mov     rcx, cs:__security_cookie
0x180001871  mov     [rsp+rax+88h+var_20], rcx
0x180001876  mov     eax, 8
0x18000187b  imul    rax, 1
0x18000187f  mov     rcx, cs:__security_cookie_complement
0x180001886  mov     [rsp+rax+88h+var_20], rcx
0x18000188b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001892  call    __raise_securityfailure
0x180001897  nop
0x180001898  add     rsp, 88h
0x18000189f  retn
```
