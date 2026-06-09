# __report_gsfailure

- ea: `0x1800016f0`
- end: `0x180001890`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005f60`

## callees

- `0x1800016a8`
- `0x1800016f0`

## import_xrefs

- `KERNEL32!RtlVirtualUnwind` at `0x18000179c`
- `KERNEL32!RtlVirtualUnwind` at `0x18000179c`
- `KERNEL32!RtlLookupFunctionEntry` at `0x18000174f`
- `KERNEL32!RtlLookupFunctionEntry` at `0x18000174f`
- `KERNEL32!RtlCaptureContext` at `0x180001730`
- `KERNEL32!RtlCaptureContext` at `0x180001730`

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
  qword_18000B280 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18000B270 = -1073740791;
  dword_18000B274 = 1;
  dword_18000B288 = 3;
  qword_18000B290[0] = 2;
  qword_18000B290[1] = _security_cookie;
  qword_18000B290[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1800016f0  mov     [rsp+arg_0], rcx
0x1800016f5  sub     rsp, 88h
0x1800016fc  mov     [rsp+88h+ControlPc], 0
0x180001705  mov     [rsp+88h+var_30], 0
0x18000170e  mov     [rsp+88h+FunctionEntry], 0
0x180001717  mov     [rsp+88h+var_28], 0
0x180001720  mov     [rsp+88h+ImageBase], 0
0x180001729  lea     rcx, ContextRecord; ContextRecord
0x180001730  call    cs:__imp_RtlCaptureContext
0x180001736  mov     rax, cs:ContextRecord.Rip
0x18000173d  mov     [rsp+88h+ControlPc], rax
0x180001742  xor     r8d, r8d; HistoryTable
0x180001745  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000174a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000174f  call    cs:__imp_RtlLookupFunctionEntry
0x180001755  mov     [rsp+88h+FunctionEntry], rax
0x18000175a  cmp     [rsp+88h+FunctionEntry], 0
0x180001760  jz      short loc_1800017A5
0x180001762  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000176b  lea     rax, [rsp+88h+var_30]
0x180001770  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180001775  lea     rax, [rsp+88h+var_28]
0x18000177a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000177f  lea     rax, ContextRecord
0x180001786  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x18000178b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180001790  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180001795  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000179a  xor     ecx, ecx; HandlerType
0x18000179c  call    cs:__imp_RtlVirtualUnwind
0x1800017a2  nop
0x1800017a3  jmp     short loc_1800017C8
0x1800017a5  mov     rax, cs:ContextRecord.Rsp
0x1800017ac  mov     rax, [rax]
0x1800017af  mov     cs:ContextRecord.Rip, rax
0x1800017b6  mov     rax, cs:ContextRecord.Rsp
0x1800017bd  add     rax, 8
0x1800017c1  mov     cs:ContextRecord.Rsp, rax
0x1800017c8  mov     rax, cs:ContextRecord.Rip
0x1800017cf  mov     cs:qword_18000B280, rax
0x1800017d6  mov     rax, [rsp+88h+arg_0]
0x1800017de  mov     cs:ContextRecord.Rcx, rax
0x1800017e5  mov     cs:dword_18000B270, 0C0000409h
0x1800017ef  mov     cs:dword_18000B274, 1
0x1800017f9  mov     cs:dword_18000B288, 3
0x180001803  mov     eax, 8
0x180001808  imul    rax, 0
0x18000180c  lea     rcx, qword_18000B290
0x180001813  mov     qword ptr [rcx+rax], 2
0x18000181b  mov     eax, 8
0x180001820  imul    rax, 1
0x180001824  lea     rcx, qword_18000B290
0x18000182b  mov     rdx, cs:__security_cookie
0x180001832  mov     [rcx+rax], rdx
0x180001836  mov     eax, 8
0x18000183b  imul    rax, 2
0x18000183f  lea     rcx, qword_18000B290
0x180001846  mov     rdx, cs:__security_cookie_complement
0x18000184d  mov     [rcx+rax], rdx
0x180001851  mov     eax, 8
0x180001856  imul    rax, 0
0x18000185a  mov     rcx, cs:__security_cookie
0x180001861  mov     [rsp+rax+88h+var_20], rcx
0x180001866  mov     eax, 8
0x18000186b  imul    rax, 1
0x18000186f  mov     rcx, cs:__security_cookie_complement
0x180001876  mov     [rsp+rax+88h+var_20], rcx
0x18000187b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001882  call    __raise_securityfailure
0x180001887  nop
0x180001888  add     rsp, 88h
0x18000188f  retn
```
