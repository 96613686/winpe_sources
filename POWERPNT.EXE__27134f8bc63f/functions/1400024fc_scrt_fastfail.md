# __scrt_fastfail

- ea: `0x1400024fc`
- end: `0x140002647`
- name: `__scrt_fastfail`
- size: `331`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140001ac0`
- `0x140001d40`
- `0x140002248`

## callees

- `0x140002352`
- `0x1400024f0`
- `0x1400024fc`

## import_xrefs

- `KERNEL32!RtlCaptureContext` at `0x140002545`
- `KERNEL32!RtlCaptureContext` at `0x140002545`
- `KERNEL32!RtlLookupFunctionEntry` at `0x14000255f`
- `KERNEL32!RtlLookupFunctionEntry` at `0x14000255f`
- `KERNEL32!RtlVirtualUnwind` at `0x1400025a3`
- `KERNEL32!RtlVirtualUnwind` at `0x1400025a3`
- `KERNEL32!IsDebuggerPresent` at `0x1400025f7`
- `KERNEL32!IsDebuggerPresent` at `0x1400025f7`
- `KERNEL32!UnhandledExceptionFilter` at `0x14000261f`
- `KERNEL32!UnhandledExceptionFilter` at `0x14000261f`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140002614`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140002614`
- `KERNEL32!IsProcessorFeaturePresent` at `0x140002518`
- `KERNEL32!IsProcessorFeaturePresent` at `0x140002518`

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
  _CONTEXT ContextRecord; // [rsp+F0h] [rbp-10h] BYREF
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
0x1400024fc  mov     [rsp-8+arg_0], rbx
0x140002501  push    rbp
0x140002502  lea     rbp, [rsp-4C0h]
0x14000250a  sub     rsp, 5C0h
0x140002511  mov     ebx, ecx
0x140002513  mov     ecx, 17h; ProcessorFeature
0x140002518  call    cs:__imp_IsProcessorFeaturePresent
0x14000251e  test    eax, eax
0x140002520  jz      short loc_140002526
0x140002522  mov     ecx, ebx
0x140002524  int     29h; Win8: RtlFailFast(ecx)
0x140002526  mov     ecx, 3
0x14000252b  call    __crt_debugger_hook
0x140002530  xor     edx, edx; Val
0x140002532  lea     rcx, [rbp+4C0h+ContextRecord]; void *
0x140002536  mov     r8d, 4D0h; Size
0x14000253c  call    memset_0
0x140002541  lea     rcx, [rbp+4C0h+ContextRecord]; ContextRecord
0x140002545  call    cs:__imp_RtlCaptureContext
0x14000254b  mov     rbx, [rbp+4C0h+ContextRecord.Rip]
0x140002552  lea     rdx, [rbp+4C0h+ImageBase]; ImageBase
0x140002559  mov     rcx, rbx; ControlPc
0x14000255c  xor     r8d, r8d; HistoryTable
0x14000255f  call    cs:__imp_RtlLookupFunctionEntry
0x140002565  test    rax, rax
0x140002568  jz      short loc_1400025A9
0x14000256a  mov     rdx, [rbp+4C0h+ImageBase]; ImageBase
0x140002571  lea     rcx, [rbp+4C0h+arg_10]
0x140002578  mov     [rsp+5C0h+ContextPointers], 0; ContextPointers
0x140002581  mov     r9, rax; FunctionEntry
0x140002584  mov     [rsp+5C0h+EstablisherFrame], rcx; EstablisherFrame
0x140002589  mov     r8, rbx; ControlPc
0x14000258c  lea     rcx, [rbp+4C0h+arg_18]
0x140002593  mov     [rsp+5C0h+HandlerData], rcx; HandlerData
0x140002598  lea     rcx, [rbp+4C0h+ContextRecord]
0x14000259c  mov     [rsp+5C0h+var_5A0], rcx; ContextRecord
0x1400025a1  xor     ecx, ecx; HandlerType
0x1400025a3  call    cs:__imp_RtlVirtualUnwind
0x1400025a9  mov     rax, [rbp+4C8h]
0x1400025b0  lea     rcx, [rsp+5C0h+var_570]; void *
0x1400025b5  mov     [rbp+4C0h+ContextRecord.Rip], rax
0x1400025bc  xor     edx, edx; Val
0x1400025be  lea     rax, [rbp+4C8h]
0x1400025c5  mov     r8d, 98h; Size
0x1400025cb  add     rax, 8
0x1400025cf  mov     [rbp+4C0h+ContextRecord.Rsp], rax
0x1400025d6  call    memset_0
0x1400025db  mov     rax, [rbp+4C8h]
0x1400025e2  mov     [rsp+5C0h+var_560], rax
0x1400025e7  mov     [rsp+5C0h+var_570], 40000015h
0x1400025ef  mov     [rsp+5C0h+var_56C], 1
0x1400025f7  call    cs:__imp_IsDebuggerPresent
0x1400025fd  mov     ebx, eax
0x1400025ff  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140002601  lea     rax, [rsp+5C0h+var_570]
0x140002606  mov     [rsp+5C0h+ExceptionInfo.ExceptionRecord], rax
0x14000260b  lea     rax, [rbp+4C0h+ContextRecord]
0x14000260f  mov     [rsp+5C0h+ExceptionInfo.ContextRecord], rax
0x140002614  call    cs:__imp_SetUnhandledExceptionFilter
0x14000261a  lea     rcx, [rsp+5C0h+ExceptionInfo]; ExceptionInfo
0x14000261f  call    cs:__imp_UnhandledExceptionFilter
0x140002625  test    eax, eax
0x140002627  jnz     short loc_140002636
0x140002629  cmp     ebx, 1
0x14000262c  jz      short loc_140002636
0x14000262e  lea     ecx, [rax+3]
0x140002631  call    __crt_debugger_hook
0x140002636  mov     rbx, [rsp+5C0h+arg_0]
0x14000263e  add     rsp, 5C0h
0x140002645  pop     rbp
0x140002646  retn
```
