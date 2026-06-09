# __scrt_fastfail

- ea: `0x140005eb0`
- end: `0x140005ffb`
- name: `__scrt_fastfail`
- size: `331`
- prototype: `LONG __fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140005810`
- `0x1400058fc`
- `0x140005bc8`

## callees

- `0x140005ea8`
- `0x140005eb0`
- `0x1400064a0`

## import_xrefs

- `KERNEL32!RtlCaptureContext` at `0x140005ef9`
- `KERNEL32!RtlCaptureContext` at `0x140005ef9`
- `KERNEL32!RtlLookupFunctionEntry` at `0x140005f13`
- `KERNEL32!RtlLookupFunctionEntry` at `0x140005f13`
- `KERNEL32!RtlVirtualUnwind` at `0x140005f54`
- `KERNEL32!RtlVirtualUnwind` at `0x140005f54`
- `KERNEL32!IsDebuggerPresent` at `0x140005fa8`
- `KERNEL32!IsDebuggerPresent` at `0x140005fa8`
- `KERNEL32!UnhandledExceptionFilter` at `0x140005fd4`
- `KERNEL32!UnhandledExceptionFilter` at `0x140005fd4`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140005fc9`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140005fc9`
- `KERNEL32!IsProcessorFeaturePresent` at `0x140005ecc`
- `KERNEL32!IsProcessorFeaturePresent` at `0x140005ecc`

## pseudocode

```c
LONG __fastcall _scrt_fastfail(unsigned int a1)
{
  ULONG64 Rip; // rbx
  struct _IMAGE_RUNTIME_FUNCTION_ENTRY *v3; // rax
  bool v4; // bl
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
  ExceptionInfo.ExceptionRecord = (PEXCEPTION_RECORD)v7;
  v4 = IsDebuggerPresent();
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
0x140005eb0  mov     [rsp-8+arg_0], rbx
0x140005eb5  push    rbp
0x140005eb6  lea     rbp, [rsp-4C0h]
0x140005ebe  sub     rsp, 5C0h
0x140005ec5  mov     ebx, ecx
0x140005ec7  mov     ecx, 17h; ProcessorFeature
0x140005ecc  call    cs:__imp_IsProcessorFeaturePresent
0x140005ed2  test    eax, eax
0x140005ed4  jz      short loc_140005EDA
0x140005ed6  mov     ecx, ebx
0x140005ed8  int     29h; Win8: RtlFailFast(ecx)
0x140005eda  mov     ecx, 3
0x140005edf  call    __crt_debugger_hook
0x140005ee4  xor     edx, edx; Val
0x140005ee6  lea     rcx, [rbp+4C0h+ContextRecord]; void *
0x140005eea  mov     r8d, 4D0h; Size
0x140005ef0  call    memset_0
0x140005ef5  lea     rcx, [rbp+4C0h+ContextRecord]; ContextRecord
0x140005ef9  call    cs:__imp_RtlCaptureContext
0x140005eff  mov     rbx, [rbp+4C0h+ContextRecord.Rip]
0x140005f06  lea     rdx, [rbp+4C0h+ImageBase]; ImageBase
0x140005f0d  mov     rcx, rbx; ControlPc
0x140005f10  xor     r8d, r8d; HistoryTable
0x140005f13  call    cs:__imp_RtlLookupFunctionEntry
0x140005f19  test    rax, rax
0x140005f1c  jz      short loc_140005F5A
0x140005f1e  and     [rsp+5C0h+var_588], 0
0x140005f24  lea     rcx, [rbp+4C0h+arg_10]
0x140005f2b  mov     rdx, [rbp+4C0h+ImageBase]; ImageBase
0x140005f32  mov     r9, rax; FunctionEntry
0x140005f35  mov     [rsp+5C0h+EstablisherFrame], rcx; EstablisherFrame
0x140005f3a  mov     r8, rbx; ControlPc
0x140005f3d  lea     rcx, [rbp+4C0h+arg_18]
0x140005f44  mov     [rsp+5C0h+HandlerData], rcx; HandlerData
0x140005f49  lea     rcx, [rbp+4C0h+ContextRecord]
0x140005f4d  mov     [rsp+5C0h+var_5A0], rcx; ContextRecord
0x140005f52  xor     ecx, ecx; HandlerType
0x140005f54  call    cs:__imp_RtlVirtualUnwind
0x140005f5a  mov     rax, [rbp+4C8h]
0x140005f61  lea     rcx, [rsp+5C0h+var_570]; void *
0x140005f66  mov     [rbp+4C0h+ContextRecord.Rip], rax
0x140005f6d  xor     edx, edx; Val
0x140005f6f  lea     rax, [rbp+4C8h]
0x140005f76  mov     r8d, 98h; Size
0x140005f7c  add     rax, 8
0x140005f80  mov     [rbp+4C0h+ContextRecord.Rsp], rax
0x140005f87  call    memset_0
0x140005f8c  mov     rax, [rbp+4C8h]
0x140005f93  mov     [rsp+5C0h+var_560], rax
0x140005f98  mov     [rsp+5C0h+var_570], 40000015h
0x140005fa0  mov     [rsp+5C0h+var_56C], 1
0x140005fa8  call    cs:__imp_IsDebuggerPresent
0x140005fae  cmp     eax, 1
0x140005fb1  lea     rax, [rsp+5C0h+var_570]
0x140005fb6  mov     [rsp+5C0h+ExceptionInfo.ExceptionRecord], rax
0x140005fbb  lea     rax, [rbp+4C0h+ContextRecord]
0x140005fbf  setz    bl
0x140005fc2  mov     [rsp+5C0h+ExceptionInfo.ContextRecord], rax
0x140005fc7  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140005fc9  call    cs:__imp_SetUnhandledExceptionFilter
0x140005fcf  lea     rcx, [rsp+5C0h+ExceptionInfo]; ExceptionInfo
0x140005fd4  call    cs:__imp_UnhandledExceptionFilter
0x140005fda  test    eax, eax
0x140005fdc  jnz     short loc_140005FEA
0x140005fde  test    bl, bl
0x140005fe0  jnz     short loc_140005FEA
0x140005fe2  lea     ecx, [rax+3]
0x140005fe5  call    __crt_debugger_hook
0x140005fea  mov     rbx, [rsp+5C0h+arg_0]
0x140005ff2  add     rsp, 5C0h
0x140005ff9  pop     rbp
0x140005ffa  retn
```
