# __report_gsfailure

- ea: `0x180004af0`
- end: `0x180004c90`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006570`

## callees

- `0x180004ab4`
- `0x180004af0`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x180004b4f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x180004b4f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180004b30`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180004b30`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x180004b9c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x180004b9c`

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
  qword_18000C0E0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18000C0D0 = -1073740791;
  dword_18000C0D4 = 1;
  dword_18000C0E8 = 3;
  qword_18000C0F0[0] = 2;
  qword_18000C0F0[1] = _security_cookie;
  qword_18000C0F0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180004af0  mov     [rsp+arg_0], rcx
0x180004af5  sub     rsp, 88h
0x180004afc  mov     [rsp+88h+ControlPc], 0
0x180004b05  mov     [rsp+88h+var_30], 0
0x180004b0e  mov     [rsp+88h+FunctionEntry], 0
0x180004b17  mov     [rsp+88h+var_28], 0
0x180004b20  mov     [rsp+88h+ImageBase], 0
0x180004b29  lea     rcx, ContextRecord; ContextRecord
0x180004b30  call    cs:__imp_RtlCaptureContext
0x180004b36  mov     rax, cs:ContextRecord.Rip
0x180004b3d  mov     [rsp+88h+ControlPc], rax
0x180004b42  xor     r8d, r8d; HistoryTable
0x180004b45  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x180004b4a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x180004b4f  call    cs:__imp_RtlLookupFunctionEntry
0x180004b55  mov     [rsp+88h+FunctionEntry], rax
0x180004b5a  cmp     [rsp+88h+FunctionEntry], 0
0x180004b60  jz      short loc_180004BA5
0x180004b62  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x180004b6b  lea     rax, [rsp+88h+var_30]
0x180004b70  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180004b75  lea     rax, [rsp+88h+var_28]
0x180004b7a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x180004b7f  lea     rax, ContextRecord
0x180004b86  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x180004b8b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180004b90  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180004b95  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x180004b9a  xor     ecx, ecx; HandlerType
0x180004b9c  call    cs:__imp_RtlVirtualUnwind
0x180004ba2  nop
0x180004ba3  jmp     short loc_180004BC8
0x180004ba5  mov     rax, cs:ContextRecord.Rsp
0x180004bac  mov     rax, [rax]
0x180004baf  mov     cs:ContextRecord.Rip, rax
0x180004bb6  mov     rax, cs:ContextRecord.Rsp
0x180004bbd  add     rax, 8
0x180004bc1  mov     cs:ContextRecord.Rsp, rax
0x180004bc8  mov     rax, cs:ContextRecord.Rip
0x180004bcf  mov     cs:qword_18000C0E0, rax
0x180004bd6  mov     rax, [rsp+88h+arg_0]
0x180004bde  mov     cs:ContextRecord.Rcx, rax
0x180004be5  mov     cs:dword_18000C0D0, 0C0000409h
0x180004bef  mov     cs:dword_18000C0D4, 1
0x180004bf9  mov     cs:dword_18000C0E8, 3
0x180004c03  mov     eax, 8
0x180004c08  imul    rax, 0
0x180004c0c  lea     rcx, qword_18000C0F0
0x180004c13  mov     qword ptr [rcx+rax], 2
0x180004c1b  mov     eax, 8
0x180004c20  imul    rax, 1
0x180004c24  lea     rcx, qword_18000C0F0
0x180004c2b  mov     rdx, cs:__security_cookie
0x180004c32  mov     [rcx+rax], rdx
0x180004c36  mov     eax, 8
0x180004c3b  imul    rax, 2
0x180004c3f  lea     rcx, qword_18000C0F0
0x180004c46  mov     rdx, cs:__security_cookie_complement
0x180004c4d  mov     [rcx+rax], rdx
0x180004c51  mov     eax, 8
0x180004c56  imul    rax, 0
0x180004c5a  mov     rcx, cs:__security_cookie
0x180004c61  mov     [rsp+rax+88h+var_20], rcx
0x180004c66  mov     eax, 8
0x180004c6b  imul    rax, 1
0x180004c6f  mov     rcx, cs:__security_cookie_complement
0x180004c76  mov     [rsp+rax+88h+var_20], rcx
0x180004c7b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180004c82  call    __raise_securityfailure
0x180004c87  nop
0x180004c88  add     rsp, 88h
0x180004c8f  retn
```
