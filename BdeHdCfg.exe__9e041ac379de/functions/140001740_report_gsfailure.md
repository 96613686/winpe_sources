# __report_gsfailure

- ea: `0x140001740`
- end: `0x1400018e0`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004460`

## callees

- `0x140001700`
- `0x140001740`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x14000179f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x14000179f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x140001780`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x140001780`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x1400017ec`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x1400017ec`

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
  qword_1400090F0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_1400090E0 = -1073740791;
  dword_1400090E4 = 1;
  dword_1400090F8 = 3;
  qword_140009100[0] = 2;
  qword_140009100[1] = _security_cookie;
  qword_140009100[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x140001740  mov     [rsp+arg_0], rcx
0x140001745  sub     rsp, 88h
0x14000174c  mov     [rsp+88h+ControlPc], 0
0x140001755  mov     [rsp+88h+var_30], 0
0x14000175e  mov     [rsp+88h+FunctionEntry], 0
0x140001767  mov     [rsp+88h+var_28], 0
0x140001770  mov     [rsp+88h+ImageBase], 0
0x140001779  lea     rcx, ContextRecord; ContextRecord
0x140001780  call    cs:__imp_RtlCaptureContext
0x140001786  mov     rax, cs:ContextRecord.Rip
0x14000178d  mov     [rsp+88h+ControlPc], rax
0x140001792  xor     r8d, r8d; HistoryTable
0x140001795  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x14000179a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x14000179f  call    cs:__imp_RtlLookupFunctionEntry
0x1400017a5  mov     [rsp+88h+FunctionEntry], rax
0x1400017aa  cmp     [rsp+88h+FunctionEntry], 0
0x1400017b0  jz      short loc_1400017F5
0x1400017b2  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x1400017bb  lea     rax, [rsp+88h+var_30]
0x1400017c0  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x1400017c5  lea     rax, [rsp+88h+var_28]
0x1400017ca  mov     [rsp+88h+HandlerData], rax; HandlerData
0x1400017cf  lea     rax, ContextRecord
0x1400017d6  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x1400017db  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x1400017e0  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x1400017e5  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x1400017ea  xor     ecx, ecx; HandlerType
0x1400017ec  call    cs:__imp_RtlVirtualUnwind
0x1400017f2  nop
0x1400017f3  jmp     short loc_140001818
0x1400017f5  mov     rax, cs:ContextRecord.Rsp
0x1400017fc  mov     rax, [rax]
0x1400017ff  mov     cs:ContextRecord.Rip, rax
0x140001806  mov     rax, cs:ContextRecord.Rsp
0x14000180d  add     rax, 8
0x140001811  mov     cs:ContextRecord.Rsp, rax
0x140001818  mov     rax, cs:ContextRecord.Rip
0x14000181f  mov     cs:qword_1400090F0, rax
0x140001826  mov     rax, [rsp+88h+arg_0]
0x14000182e  mov     cs:ContextRecord.Rcx, rax
0x140001835  mov     cs:dword_1400090E0, 0C0000409h
0x14000183f  mov     cs:dword_1400090E4, 1
0x140001849  mov     cs:dword_1400090F8, 3
0x140001853  mov     eax, 8
0x140001858  imul    rax, 0
0x14000185c  lea     rcx, qword_140009100
0x140001863  mov     qword ptr [rcx+rax], 2
0x14000186b  mov     eax, 8
0x140001870  imul    rax, 1
0x140001874  lea     rcx, qword_140009100
0x14000187b  mov     rdx, cs:__security_cookie
0x140001882  mov     [rcx+rax], rdx
0x140001886  mov     eax, 8
0x14000188b  imul    rax, 2
0x14000188f  lea     rcx, qword_140009100
0x140001896  mov     rdx, cs:__security_cookie_complement
0x14000189d  mov     [rcx+rax], rdx
0x1400018a1  mov     eax, 8
0x1400018a6  imul    rax, 0
0x1400018aa  mov     rcx, cs:__security_cookie
0x1400018b1  mov     [rsp+rax+88h+var_20], rcx
0x1400018b6  mov     eax, 8
0x1400018bb  imul    rax, 1
0x1400018bf  mov     rcx, cs:__security_cookie_complement
0x1400018c6  mov     [rsp+rax+88h+var_20], rcx
0x1400018cb  lea     rcx, ExceptionInfo; ExceptionInfo
0x1400018d2  call    __raise_securityfailure
0x1400018d7  nop
0x1400018d8  add     rsp, 88h
0x1400018df  retn
```
