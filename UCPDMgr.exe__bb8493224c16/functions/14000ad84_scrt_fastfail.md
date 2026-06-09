# __scrt_fastfail

- ea: `0x14000ad84`
- end: `0x14000aef0`
- name: `__scrt_fastfail`
- size: `364`
- prototype: `LONG __fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000a434`
- `0x14000a660`
- `0x14000a750`

## callees

- `0x14000ad70`
- `0x14000ad84`
- `0x14000f550`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14000aea0`
- `KERNEL32!IsDebuggerPresent` at `0x14000aea0`
- `KERNEL32!IsProcessorFeaturePresent` at `0x14000ada0`
- `KERNEL32!IsProcessorFeaturePresent` at `0x14000ada0`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14000aebd`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14000aebd`
- `KERNEL32!UnhandledExceptionFilter` at `0x14000aec8`
- `KERNEL32!UnhandledExceptionFilter` at `0x14000aec8`
- `KERNEL32!RtlVirtualUnwind` at `0x14000ae4c`
- `KERNEL32!RtlVirtualUnwind` at `0x14000ae4c`
- `KERNEL32!RtlLookupFunctionEntry` at `0x14000adf2`
- `KERNEL32!RtlLookupFunctionEntry` at `0x14000adf2`
- `KERNEL32!RtlCaptureContext` at `0x14000adcd`
- `KERNEL32!RtlCaptureContext` at `0x14000adcd`

## pseudocode

```c
LONG __fastcall _scrt_fastfail(unsigned int a1)
{
  ULONG64 Rip; // rbx
  struct _IMAGE_RUNTIME_FUNCTION_ENTRY *v3; // rax
  BOOL v4; // ebx
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
  _crt_debugger_hook(3);
  memset(&ContextRecord, 0, sizeof(ContextRecord));
  RtlCaptureContext(&ContextRecord);
  Rip = ContextRecord.Rip;
  ImageBase = 0;
  v3 = RtlLookupFunctionEntry(ContextRecord.Rip, &ImageBase, 0);
  if ( v3 )
  {
    EstablisherFrame = 0;
    HandlerData = 0;
    RtlVirtualUnwind(0, ImageBase, Rip, v3, &ContextRecord, &HandlerData, &EstablisherFrame, 0);
  }
  ContextRecord.Rip = retaddr;
  ContextRecord.Rsp = (DWORD64)&v10;
  memset(v7, 0, 0x98u);
  v7[2] = retaddr;
  v7[0] = 0x140000015LL;
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
0x14000ad84  mov     [rsp-8+arg_0], rbx
0x14000ad89  push    rbp
0x14000ad8a  lea     rbp, [rsp-4C0h]
0x14000ad92  sub     rsp, 5C0h
0x14000ad99  mov     ebx, ecx
0x14000ad9b  mov     ecx, 17h; ProcessorFeature
0x14000ada0  call    cs:__imp_IsProcessorFeaturePresent
0x14000ada6  test    eax, eax
0x14000ada8  jz      short loc_14000ADAE
0x14000adaa  mov     ecx, ebx
0x14000adac  int     29h; Win8: RtlFailFast(ecx)
0x14000adae  mov     ecx, 3
0x14000adb3  call    __crt_debugger_hook
0x14000adb8  xor     edx, edx; Val
0x14000adba  lea     rcx, [rbp+4C0h+ContextRecord]; void *
0x14000adbe  mov     r8d, 4D0h; Size
0x14000adc4  call    memset
0x14000adc9  lea     rcx, [rbp+4C0h+ContextRecord]; ContextRecord
0x14000adcd  call    cs:__imp_RtlCaptureContext
0x14000add3  mov     rbx, [rbp+4C0h+ContextRecord.Rip]
0x14000adda  lea     rdx, [rbp+4C0h+ImageBase]; ImageBase
0x14000ade1  mov     rcx, rbx; ControlPc
0x14000ade4  mov     [rbp+4C0h+ImageBase], 0
0x14000adef  xor     r8d, r8d; HistoryTable
0x14000adf2  call    cs:__imp_RtlLookupFunctionEntry
0x14000adf8  test    rax, rax
0x14000adfb  jz      short loc_14000AE52
0x14000adfd  mov     rdx, [rbp+4C0h+ImageBase]; ImageBase
0x14000ae04  lea     rcx, [rbp+4C0h+arg_10]
0x14000ae0b  mov     [rsp+5C0h+ContextPointers], 0; ContextPointers
0x14000ae14  mov     r9, rax; FunctionEntry
0x14000ae17  mov     [rsp+5C0h+EstablisherFrame], rcx; EstablisherFrame
0x14000ae1c  mov     r8, rbx; ControlPc
0x14000ae1f  lea     rcx, [rbp+4C0h+arg_18]
0x14000ae26  mov     [rbp+4C0h+arg_10], 0
0x14000ae31  mov     [rsp+5C0h+HandlerData], rcx; HandlerData
0x14000ae36  lea     rcx, [rbp+4C0h+ContextRecord]
0x14000ae3a  mov     [rsp+5C0h+var_5A0], rcx; ContextRecord
0x14000ae3f  xor     ecx, ecx; HandlerType
0x14000ae41  mov     [rbp+4C0h+arg_18], 0
0x14000ae4c  call    cs:__imp_RtlVirtualUnwind
0x14000ae52  mov     rax, [rbp+4C8h]
0x14000ae59  lea     rcx, [rsp+5C0h+var_570]; void *
0x14000ae5e  mov     [rbp+4C0h+ContextRecord.Rip], rax
0x14000ae65  xor     edx, edx; Val
0x14000ae67  lea     rax, [rbp+4C8h]
0x14000ae6e  mov     r8d, 98h; Size
0x14000ae74  add     rax, 8
0x14000ae78  mov     [rbp+4C0h+ContextRecord.Rsp], rax
0x14000ae7f  call    memset
0x14000ae84  mov     rax, [rbp+4C8h]
0x14000ae8b  mov     [rsp+5C0h+var_560], rax
0x14000ae90  mov     [rsp+5C0h+var_570], 40000015h
0x14000ae98  mov     [rsp+5C0h+var_56C], 1
0x14000aea0  call    cs:__imp_IsDebuggerPresent
0x14000aea6  mov     ebx, eax
0x14000aea8  xor     ecx, ecx; lpTopLevelExceptionFilter
0x14000aeaa  lea     rax, [rsp+5C0h+var_570]
0x14000aeaf  mov     [rsp+5C0h+ExceptionInfo.ExceptionRecord], rax
0x14000aeb4  lea     rax, [rbp+4C0h+ContextRecord]
0x14000aeb8  mov     [rsp+5C0h+ExceptionInfo.ContextRecord], rax
0x14000aebd  call    cs:__imp_SetUnhandledExceptionFilter
0x14000aec3  lea     rcx, [rsp+5C0h+ExceptionInfo]; ExceptionInfo
0x14000aec8  call    cs:__imp_UnhandledExceptionFilter
0x14000aece  test    eax, eax
0x14000aed0  jnz     short loc_14000AEDF
0x14000aed2  cmp     ebx, 1
0x14000aed5  jz      short loc_14000AEDF
0x14000aed7  lea     ecx, [rax+3]
0x14000aeda  call    __crt_debugger_hook
0x14000aedf  mov     rbx, [rsp+5C0h+arg_0]
0x14000aee7  add     rsp, 5C0h
0x14000aeee  pop     rbp
0x14000aeef  retn
```
