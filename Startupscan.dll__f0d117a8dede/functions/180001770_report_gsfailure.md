# __report_gsfailure

- ea: `0x180001770`
- end: `0x180001910`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004130`

## callees

- `0x180001730`
- `0x180001770`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800017b0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800017b0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x1800017cf`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x1800017cf`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000181c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000181c`

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
  qword_180009100 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_1800090F0 = -1073740791;
  dword_1800090F4 = 1;
  dword_180009108 = 3;
  qword_180009110[0] = 2;
  qword_180009110[1] = _security_cookie;
  qword_180009110[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001770  mov     [rsp+arg_0], rcx
0x180001775  sub     rsp, 88h
0x18000177c  mov     [rsp+88h+ControlPc], 0
0x180001785  mov     [rsp+88h+var_30], 0
0x18000178e  mov     [rsp+88h+FunctionEntry], 0
0x180001797  mov     [rsp+88h+var_28], 0
0x1800017a0  mov     [rsp+88h+ImageBase], 0
0x1800017a9  lea     rcx, ContextRecord; ContextRecord
0x1800017b0  call    cs:__imp_RtlCaptureContext
0x1800017b6  mov     rax, cs:ContextRecord.Rip
0x1800017bd  mov     [rsp+88h+ControlPc], rax
0x1800017c2  xor     r8d, r8d; HistoryTable
0x1800017c5  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800017ca  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x1800017cf  call    cs:__imp_RtlLookupFunctionEntry
0x1800017d5  mov     [rsp+88h+FunctionEntry], rax
0x1800017da  cmp     [rsp+88h+FunctionEntry], 0
0x1800017e0  jz      short loc_180001825
0x1800017e2  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x1800017eb  lea     rax, [rsp+88h+var_30]
0x1800017f0  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x1800017f5  lea     rax, [rsp+88h+var_28]
0x1800017fa  mov     [rsp+88h+HandlerData], rax; HandlerData
0x1800017ff  lea     rax, ContextRecord
0x180001806  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x18000180b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180001810  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180001815  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000181a  xor     ecx, ecx; HandlerType
0x18000181c  call    cs:__imp_RtlVirtualUnwind
0x180001822  nop
0x180001823  jmp     short loc_180001848
0x180001825  mov     rax, cs:ContextRecord.Rsp
0x18000182c  mov     rax, [rax]
0x18000182f  mov     cs:ContextRecord.Rip, rax
0x180001836  mov     rax, cs:ContextRecord.Rsp
0x18000183d  add     rax, 8
0x180001841  mov     cs:ContextRecord.Rsp, rax
0x180001848  mov     rax, cs:ContextRecord.Rip
0x18000184f  mov     cs:qword_180009100, rax
0x180001856  mov     rax, [rsp+88h+arg_0]
0x18000185e  mov     cs:ContextRecord.Rcx, rax
0x180001865  mov     cs:dword_1800090F0, 0C0000409h
0x18000186f  mov     cs:dword_1800090F4, 1
0x180001879  mov     cs:dword_180009108, 3
0x180001883  mov     eax, 8
0x180001888  imul    rax, 0
0x18000188c  lea     rcx, qword_180009110
0x180001893  mov     qword ptr [rcx+rax], 2
0x18000189b  mov     eax, 8
0x1800018a0  imul    rax, 1
0x1800018a4  lea     rcx, qword_180009110
0x1800018ab  mov     rdx, cs:__security_cookie
0x1800018b2  mov     [rcx+rax], rdx
0x1800018b6  mov     eax, 8
0x1800018bb  imul    rax, 2
0x1800018bf  lea     rcx, qword_180009110
0x1800018c6  mov     rdx, cs:__security_cookie_complement
0x1800018cd  mov     [rcx+rax], rdx
0x1800018d1  mov     eax, 8
0x1800018d6  imul    rax, 0
0x1800018da  mov     rcx, cs:__security_cookie
0x1800018e1  mov     [rsp+rax+88h+var_20], rcx
0x1800018e6  mov     eax, 8
0x1800018eb  imul    rax, 1
0x1800018ef  mov     rcx, cs:__security_cookie_complement
0x1800018f6  mov     [rsp+rax+88h+var_20], rcx
0x1800018fb  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001902  call    __raise_securityfailure
0x180001907  nop
0x180001908  add     rsp, 88h
0x18000190f  retn
```
