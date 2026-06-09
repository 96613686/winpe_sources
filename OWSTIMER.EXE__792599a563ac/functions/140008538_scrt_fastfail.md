# __scrt_fastfail

- ea: `0x140008538`
- end: `0x140008682`
- name: `__scrt_fastfail`
- size: `330`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140007de0`
- `0x140007ecc`
- `0x1400082a0`

## callees

- `0x140008530`
- `0x140008538`
- `0x1400089fa`
- `0x140008a9b`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14000862f`
- `KERNEL32!IsDebuggerPresent` at `0x14000862f`
- `KERNEL32!RtlCaptureContext` at `0x140008580`
- `KERNEL32!RtlCaptureContext` at `0x140008580`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140008650`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140008650`
- `KERNEL32!UnhandledExceptionFilter` at `0x14000865b`
- `KERNEL32!UnhandledExceptionFilter` at `0x14000865b`
- `KERNEL32!RtlVirtualUnwind` at `0x1400085db`
- `KERNEL32!RtlVirtualUnwind` at `0x1400085db`
- `KERNEL32!RtlLookupFunctionEntry` at `0x14000859a`
- `KERNEL32!RtlLookupFunctionEntry` at `0x14000859a`

## pseudocode

```c
LONG __fastcall _scrt_fastfail(unsigned int a1)
{
  ULONG64 Rip; // rbx
  struct _IMAGE_RUNTIME_FUNCTION_ENTRY *v3; // rax
  bool v4; // bl
  LONG result; // eax
  _EXCEPTION_POINTERS ExceptionInfo; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v7[20]; // [rsp+50h] [rbp-B0h] BYREF
  struct _CONTEXT ContextRecord; // [rsp+F0h] [rbp-10h] BYREF
  DWORD64 retaddr; // [rsp+5C8h] [rbp+4C8h]
  __int64 v10; // [rsp+5D0h] [rbp+4D0h] BYREF
  unsigned __int64 ImageBase; // [rsp+5D8h] [rbp+4D8h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+5E0h] [rbp+4E0h] BYREF
  PVOID HandlerData; // [rsp+5E8h] [rbp+4E8h] BYREF

  if ( IsProcessorFeaturePresent(0x17u) )
    __fastfail(a1);
  sub_140008530(3);
  memset(&ContextRecord, 0, sizeof(ContextRecord));
  RtlCaptureContext(&ContextRecord);
  Rip = ContextRecord.Rip;
  v3 = RtlLookupFunctionEntry(ContextRecord.Rip, &ImageBase, 0);
  if ( v3 )
    RtlVirtualUnwind(0, ImageBase, Rip, v3, &ContextRecord, &HandlerData, &EstablisherFrame, 0);
  ContextRecord.Rip = retaddr;
  ContextRecord.Rsp = (DWORD64)&v10;
  memset(v7, 0, 0x98u);
  v7[2] = retaddr;
  v7[0] = 0x140000015LL;
  ExceptionInfo.ExceptionRecord = (PEXCEPTION_RECORD)v7;
  v4 = IsDebuggerPresent();
  ExceptionInfo.ContextRecord = &ContextRecord;
  SetUnhandledExceptionFilter(0);
  result = UnhandledExceptionFilter(&ExceptionInfo);
  if ( !result && !v4 )
    return sub_140008530(3);
  return result;
}

```

## disassembly

```asm
0x140008538  mov     [rsp-8+arg_0], rbx
0x14000853d  push    rbp
0x14000853e  lea     rbp, [rsp-4C0h]
0x140008546  sub     rsp, 5C0h
0x14000854d  mov     ebx, ecx
0x14000854f  mov     ecx, 17h; ProcessorFeature
0x140008554  call    IsProcessorFeaturePresent
0x140008559  test    eax, eax
0x14000855b  jz      short loc_140008561
0x14000855d  mov     ecx, ebx
0x14000855f  int     29h; Win8: RtlFailFast(ecx)
0x140008561  mov     ecx, 3
0x140008566  call    sub_140008530
0x14000856b  xor     edx, edx; Val
0x14000856d  lea     rcx, [rbp+4C0h+ContextRecord]; void *
0x140008571  mov     r8d, 4D0h; Size
0x140008577  call    memset
0x14000857c  lea     rcx, [rbp+4C0h+ContextRecord]; ContextRecord
0x140008580  call    cs:RtlCaptureContext
0x140008586  mov     rbx, [rbp+4C0h+ContextRecord.Rip]
0x14000858d  lea     rdx, [rbp+4C0h+ImageBase]; ImageBase
0x140008594  mov     rcx, rbx; ControlPc
0x140008597  xor     r8d, r8d; HistoryTable
0x14000859a  call    cs:RtlLookupFunctionEntry
0x1400085a0  test    rax, rax
0x1400085a3  jz      short loc_1400085E1
0x1400085a5  and     [rsp+5C0h+var_588], 0
0x1400085ab  lea     rcx, [rbp+4C0h+arg_10]
0x1400085b2  mov     rdx, [rbp+4C0h+ImageBase]; ImageBase
0x1400085b9  mov     r9, rax; FunctionEntry
0x1400085bc  mov     [rsp+5C0h+EstablisherFrame], rcx; EstablisherFrame
0x1400085c1  mov     r8, rbx; ControlPc
0x1400085c4  lea     rcx, [rbp+4C0h+arg_18]
0x1400085cb  mov     [rsp+5C0h+HandlerData], rcx; HandlerData
0x1400085d0  lea     rcx, [rbp+4C0h+ContextRecord]
0x1400085d4  mov     [rsp+5C0h+var_5A0], rcx; ContextRecord
0x1400085d9  xor     ecx, ecx; HandlerType
0x1400085db  call    cs:RtlVirtualUnwind
0x1400085e1  mov     rax, [rbp+4C8h]
0x1400085e8  lea     rcx, [rsp+5C0h+var_570]; void *
0x1400085ed  mov     [rbp+4C0h+ContextRecord.Rip], rax
0x1400085f4  xor     edx, edx; Val
0x1400085f6  lea     rax, [rbp+4C8h]
0x1400085fd  mov     r8d, 98h; Size
0x140008603  add     rax, 8
0x140008607  mov     [rbp+4C0h+ContextRecord.Rsp], rax
0x14000860e  call    memset
0x140008613  mov     rax, [rbp+4C8h]
0x14000861a  mov     [rsp+5C0h+var_560], rax
0x14000861f  mov     [rsp+5C0h+var_570], 40000015h
0x140008627  mov     [rsp+5C0h+var_56C], 1
0x14000862f  call    cs:IsDebuggerPresent
0x140008635  cmp     eax, 1
0x140008638  lea     rax, [rsp+5C0h+var_570]
0x14000863d  mov     [rsp+5C0h+ExceptionInfo.ExceptionRecord], rax
0x140008642  lea     rax, [rbp+4C0h+ContextRecord]
0x140008646  setz    bl
0x140008649  mov     [rsp+5C0h+ExceptionInfo.ContextRecord], rax
0x14000864e  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140008650  call    cs:SetUnhandledExceptionFilter
0x140008656  lea     rcx, [rsp+5C0h+ExceptionInfo]; ExceptionInfo
0x14000865b  call    cs:UnhandledExceptionFilter
0x140008661  test    eax, eax
0x140008663  jnz     short loc_140008671
0x140008665  test    bl, bl
0x140008667  jnz     short loc_140008671
0x140008669  lea     ecx, [rax+3]
0x14000866c  call    sub_140008530
0x140008671  mov     rbx, [rsp+5C0h+arg_0]
0x140008679  add     rsp, 5C0h
0x140008680  pop     rbp
0x140008681  retn
```
