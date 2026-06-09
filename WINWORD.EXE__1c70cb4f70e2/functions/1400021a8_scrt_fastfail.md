# __scrt_fastfail

- ea: `0x1400021a8`
- end: `0x1400022f3`
- name: `__scrt_fastfail`
- size: `331`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400017f0`
- `0x1400018dc`
- `0x140001af8`

## callees

- `0x14000219c`
- `0x1400021a8`
- `0x14000274e`

## import_xrefs

- `KERNEL32!RtlVirtualUnwind` at `0x14000224f`
- `KERNEL32!RtlVirtualUnwind` at `0x14000224f`
- `KERNEL32!RtlLookupFunctionEntry` at `0x14000220b`
- `KERNEL32!RtlLookupFunctionEntry` at `0x14000220b`
- `KERNEL32!RtlCaptureContext` at `0x1400021f1`
- `KERNEL32!RtlCaptureContext` at `0x1400021f1`
- `KERNEL32!UnhandledExceptionFilter` at `0x1400022cb`
- `KERNEL32!UnhandledExceptionFilter` at `0x1400022cb`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1400022c0`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1400022c0`
- `KERNEL32!IsProcessorFeaturePresent` at `0x1400021c4`
- `KERNEL32!IsProcessorFeaturePresent` at `0x1400021c4`
- `KERNEL32!IsDebuggerPresent` at `0x1400022a3`
- `KERNEL32!IsDebuggerPresent` at `0x1400022a3`

## pseudocode

```c
LONG __fastcall _scrt_fastfail(unsigned int a1)
{
  ULONG64 Rip; // rbx
  struct _IMAGE_RUNTIME_FUNCTION_ENTRY *v3; // rax
  BOOL v4; // ebx
  LONG result; // eax
  _EXCEPTION_POINTERS ExceptionInfo; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v7[4]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD64 v8; // [rsp+60h] [rbp-A0h]
  struct _CONTEXT ContextRecord; // [rsp+F0h] [rbp-10h] BYREF
  DWORD64 retaddr; // [rsp+5C8h] [rbp+4C8h]
  __int64 v11; // [rsp+5D0h] [rbp+4D0h] BYREF
  unsigned __int64 ImageBase; // [rsp+5D8h] [rbp+4D8h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+5E0h] [rbp+4E0h] BYREF
  PVOID HandlerData; // [rsp+5E8h] [rbp+4E8h] BYREF

  if ( IsProcessorFeaturePresent(0x17u) )
    __fastfail(a1);
  _crt_debugger_hook(3);
  memset_0(&ContextRecord, 0, sizeof(ContextRecord));
  RtlCaptureContext(&ContextRecord);
  Rip = ContextRecord.Rip;
  v3 = RtlLookupFunctionEntry(ContextRecord.Rip, &ImageBase, 0);
  if ( v3 )
    RtlVirtualUnwind(0, ImageBase, Rip, v3, &ContextRecord, &HandlerData, &EstablisherFrame, 0);
  ContextRecord.Rip = retaddr;
  ContextRecord.Rsp = (DWORD64)&v11;
  memset_0(v7, 0, 0x98u);
  v8 = retaddr;
  v7[0] = 1073741845;
  v7[1] = 1;
  v4 = IsDebuggerPresent();
  ExceptionInfo.ExceptionRecord = (PEXCEPTION_RECORD)v7;
  ExceptionInfo.ContextRecord = &ContextRecord;
  SetUnhandledExceptionFilter(0);
  result = UnhandledExceptionFilter(&ExceptionInfo);
  if ( !result && !v4 )
    return _crt_debugger_hook(3);
  return result;
}

```

## disassembly

```asm
0x1400021a8  mov     [rsp-8+arg_0], rbx
0x1400021ad  push    rbp
0x1400021ae  lea     rbp, [rsp-4C0h]
0x1400021b6  sub     rsp, 5C0h
0x1400021bd  mov     ebx, ecx
0x1400021bf  mov     ecx, 17h; ProcessorFeature
0x1400021c4  call    cs:__imp_IsProcessorFeaturePresent
0x1400021ca  test    eax, eax
0x1400021cc  jz      short loc_1400021D2
0x1400021ce  mov     ecx, ebx
0x1400021d0  int     29h; Win8: RtlFailFast(ecx)
0x1400021d2  mov     ecx, 3
0x1400021d7  call    __crt_debugger_hook
0x1400021dc  xor     edx, edx; Val
0x1400021de  lea     rcx, [rbp+4C0h+ContextRecord]; void *
0x1400021e2  mov     r8d, 4D0h; Size
0x1400021e8  call    memset_0
0x1400021ed  lea     rcx, [rbp+4C0h+ContextRecord]; ContextRecord
0x1400021f1  call    cs:__imp_RtlCaptureContext
0x1400021f7  mov     rbx, [rbp+4C0h+ContextRecord.Rip]
0x1400021fe  lea     rdx, [rbp+4C0h+ImageBase]; ImageBase
0x140002205  mov     rcx, rbx; ControlPc
0x140002208  xor     r8d, r8d; HistoryTable
0x14000220b  call    cs:__imp_RtlLookupFunctionEntry
0x140002211  test    rax, rax
0x140002214  jz      short loc_140002255
0x140002216  mov     rdx, [rbp+4C0h+ImageBase]; ImageBase
0x14000221d  lea     rcx, [rbp+4C0h+arg_10]
0x140002224  mov     [rsp+5C0h+ContextPointers], 0; ContextPointers
0x14000222d  mov     r9, rax; FunctionEntry
0x140002230  mov     [rsp+5C0h+EstablisherFrame], rcx; EstablisherFrame
0x140002235  mov     r8, rbx; ControlPc
0x140002238  lea     rcx, [rbp+4C0h+arg_18]
0x14000223f  mov     [rsp+5C0h+HandlerData], rcx; HandlerData
0x140002244  lea     rcx, [rbp+4C0h+ContextRecord]
0x140002248  mov     [rsp+5C0h+var_5A0], rcx; ContextRecord
0x14000224d  xor     ecx, ecx; HandlerType
0x14000224f  call    cs:__imp_RtlVirtualUnwind
0x140002255  mov     rax, [rbp+4C8h]
0x14000225c  lea     rcx, [rsp+5C0h+var_570]; void *
0x140002261  mov     [rbp+4C0h+ContextRecord.Rip], rax
0x140002268  xor     edx, edx; Val
0x14000226a  lea     rax, [rbp+4C8h]
0x140002271  mov     r8d, 98h; Size
0x140002277  add     rax, 8
0x14000227b  mov     [rbp+4C0h+ContextRecord.Rsp], rax
0x140002282  call    memset_0
0x140002287  mov     rax, [rbp+4C8h]
0x14000228e  mov     [rsp+5C0h+var_560], rax
0x140002293  mov     [rsp+5C0h+var_570], 40000015h
0x14000229b  mov     [rsp+5C0h+var_56C], 1
0x1400022a3  call    cs:__imp_IsDebuggerPresent
0x1400022a9  mov     ebx, eax
0x1400022ab  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1400022ad  lea     rax, [rsp+5C0h+var_570]
0x1400022b2  mov     [rsp+5C0h+ExceptionInfo.ExceptionRecord], rax
0x1400022b7  lea     rax, [rbp+4C0h+ContextRecord]
0x1400022bb  mov     [rsp+5C0h+ExceptionInfo.ContextRecord], rax
0x1400022c0  call    cs:__imp_SetUnhandledExceptionFilter
0x1400022c6  lea     rcx, [rsp+5C0h+ExceptionInfo]; ExceptionInfo
0x1400022cb  call    cs:__imp_UnhandledExceptionFilter
0x1400022d1  test    eax, eax
0x1400022d3  jnz     short loc_1400022E2
0x1400022d5  cmp     ebx, 1
0x1400022d8  jz      short loc_1400022E2
0x1400022da  lea     ecx, [rax+3]
0x1400022dd  call    __crt_debugger_hook
0x1400022e2  mov     rbx, [rsp+5C0h+arg_0]
0x1400022ea  add     rsp, 5C0h
0x1400022f1  pop     rbp
0x1400022f2  retn
```
