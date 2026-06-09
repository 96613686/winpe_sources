# __report_gsfailure

- ea: `0x180001ba0`
- end: `0x180001d40`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006980`

## callees

- `0x180001b5c`
- `0x180001ba0`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x180001c4c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x180001c4c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180001be0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180001be0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x180001bff`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x180001bff`

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
  qword_18000C1A0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18000C190 = -1073740791;
  dword_18000C194 = 1;
  dword_18000C1A8 = 3;
  qword_18000C1B0[0] = 2;
  qword_18000C1B0[1] = _security_cookie;
  qword_18000C1B0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001ba0  mov     [rsp+arg_0], rcx
0x180001ba5  sub     rsp, 88h
0x180001bac  mov     [rsp+88h+ControlPc], 0
0x180001bb5  mov     [rsp+88h+var_30], 0
0x180001bbe  mov     [rsp+88h+FunctionEntry], 0
0x180001bc7  mov     [rsp+88h+var_28], 0
0x180001bd0  mov     [rsp+88h+ImageBase], 0
0x180001bd9  lea     rcx, ContextRecord; ContextRecord
0x180001be0  call    cs:__imp_RtlCaptureContext
0x180001be6  mov     rax, cs:ContextRecord.Rip
0x180001bed  mov     [rsp+88h+ControlPc], rax
0x180001bf2  xor     r8d, r8d; HistoryTable
0x180001bf5  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x180001bfa  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x180001bff  call    cs:__imp_RtlLookupFunctionEntry
0x180001c05  mov     [rsp+88h+FunctionEntry], rax
0x180001c0a  cmp     [rsp+88h+FunctionEntry], 0
0x180001c10  jz      short loc_180001C55
0x180001c12  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x180001c1b  lea     rax, [rsp+88h+var_30]
0x180001c20  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180001c25  lea     rax, [rsp+88h+var_28]
0x180001c2a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x180001c2f  lea     rax, ContextRecord
0x180001c36  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x180001c3b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180001c40  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180001c45  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x180001c4a  xor     ecx, ecx; HandlerType
0x180001c4c  call    cs:__imp_RtlVirtualUnwind
0x180001c52  nop
0x180001c53  jmp     short loc_180001C78
0x180001c55  mov     rax, cs:ContextRecord.Rsp
0x180001c5c  mov     rax, [rax]
0x180001c5f  mov     cs:ContextRecord.Rip, rax
0x180001c66  mov     rax, cs:ContextRecord.Rsp
0x180001c6d  add     rax, 8
0x180001c71  mov     cs:ContextRecord.Rsp, rax
0x180001c78  mov     rax, cs:ContextRecord.Rip
0x180001c7f  mov     cs:qword_18000C1A0, rax
0x180001c86  mov     rax, [rsp+88h+arg_0]
0x180001c8e  mov     cs:ContextRecord.Rcx, rax
0x180001c95  mov     cs:dword_18000C190, 0C0000409h
0x180001c9f  mov     cs:dword_18000C194, 1
0x180001ca9  mov     cs:dword_18000C1A8, 3
0x180001cb3  mov     eax, 8
0x180001cb8  imul    rax, 0
0x180001cbc  lea     rcx, qword_18000C1B0
0x180001cc3  mov     qword ptr [rcx+rax], 2
0x180001ccb  mov     eax, 8
0x180001cd0  imul    rax, 1
0x180001cd4  lea     rcx, qword_18000C1B0
0x180001cdb  mov     rdx, cs:__security_cookie
0x180001ce2  mov     [rcx+rax], rdx
0x180001ce6  mov     eax, 8
0x180001ceb  imul    rax, 2
0x180001cef  lea     rcx, qword_18000C1B0
0x180001cf6  mov     rdx, cs:__security_cookie_complement
0x180001cfd  mov     [rcx+rax], rdx
0x180001d01  mov     eax, 8
0x180001d06  imul    rax, 0
0x180001d0a  mov     rcx, cs:__security_cookie
0x180001d11  mov     [rsp+rax+88h+var_20], rcx
0x180001d16  mov     eax, 8
0x180001d1b  imul    rax, 1
0x180001d1f  mov     rcx, cs:__security_cookie_complement
0x180001d26  mov     [rsp+rax+88h+var_20], rcx
0x180001d2b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001d32  call    __raise_securityfailure
0x180001d37  nop
0x180001d38  add     rsp, 88h
0x180001d3f  retn
```
