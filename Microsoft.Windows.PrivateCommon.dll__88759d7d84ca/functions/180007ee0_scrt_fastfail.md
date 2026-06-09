# __scrt_fastfail

- ea: `0x180007ee0`
- end: `0x18000802b`
- name: `__scrt_fastfail`
- size: `331`
- prototype: `LONG __fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007498`
- `0x1800076f0`
- `0x180007808`

## callees

- `0x180007ed4`
- `0x180007ee0`
- `0x18000b990`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180007fdb`
- `KERNEL32!IsDebuggerPresent` at `0x180007fdb`
- `KERNEL32!RtlCaptureContext` at `0x180007f29`
- `KERNEL32!RtlCaptureContext` at `0x180007f29`
- `KERNEL32!RtlLookupFunctionEntry` at `0x180007f43`
- `KERNEL32!RtlLookupFunctionEntry` at `0x180007f43`
- `KERNEL32!RtlVirtualUnwind` at `0x180007f87`
- `KERNEL32!RtlVirtualUnwind` at `0x180007f87`
- `KERNEL32!UnhandledExceptionFilter` at `0x180008003`
- `KERNEL32!UnhandledExceptionFilter` at `0x180008003`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180007ff8`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180007ff8`
- `KERNEL32!IsProcessorFeaturePresent` at `0x180007efc`
- `KERNEL32!IsProcessorFeaturePresent` at `0x180007efc`

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
  v3 = RtlLookupFunctionEntry(ContextRecord.Rip, &ImageBase, 0);
  if ( v3 )
    RtlVirtualUnwind(0, ImageBase, Rip, v3, &ContextRecord, &HandlerData, &EstablisherFrame, 0);
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
0x180007ee0  mov     [rsp-8+arg_0], rbx
0x180007ee5  push    rbp
0x180007ee6  lea     rbp, [rsp-4C0h]
0x180007eee  sub     rsp, 5C0h
0x180007ef5  mov     ebx, ecx
0x180007ef7  mov     ecx, 17h; ProcessorFeature
0x180007efc  call    cs:__imp_IsProcessorFeaturePresent
0x180007f02  test    eax, eax
0x180007f04  jz      short loc_180007F0A
0x180007f06  mov     ecx, ebx
0x180007f08  int     29h; Win8: RtlFailFast(ecx)
0x180007f0a  mov     ecx, 3
0x180007f0f  call    __crt_debugger_hook
0x180007f14  xor     edx, edx; Val
0x180007f16  lea     rcx, [rbp+4C0h+ContextRecord]; void *
0x180007f1a  mov     r8d, 4D0h; Size
0x180007f20  call    memset
0x180007f25  lea     rcx, [rbp+4C0h+ContextRecord]; ContextRecord
0x180007f29  call    cs:__imp_RtlCaptureContext
0x180007f2f  mov     rbx, [rbp+4C0h+ContextRecord.Rip]
0x180007f36  lea     rdx, [rbp+4C0h+ImageBase]; ImageBase
0x180007f3d  mov     rcx, rbx; ControlPc
0x180007f40  xor     r8d, r8d; HistoryTable
0x180007f43  call    cs:__imp_RtlLookupFunctionEntry
0x180007f49  test    rax, rax
0x180007f4c  jz      short loc_180007F8D
0x180007f4e  mov     rdx, [rbp+4C0h+ImageBase]; ImageBase
0x180007f55  lea     rcx, [rbp+4C0h+arg_10]
0x180007f5c  mov     [rsp+5C0h+ContextPointers], 0; ContextPointers
0x180007f65  mov     r9, rax; FunctionEntry
0x180007f68  mov     [rsp+5C0h+EstablisherFrame], rcx; EstablisherFrame
0x180007f6d  mov     r8, rbx; ControlPc
0x180007f70  lea     rcx, [rbp+4C0h+arg_18]
0x180007f77  mov     [rsp+5C0h+HandlerData], rcx; HandlerData
0x180007f7c  lea     rcx, [rbp+4C0h+ContextRecord]
0x180007f80  mov     [rsp+5C0h+var_5A0], rcx; ContextRecord
0x180007f85  xor     ecx, ecx; HandlerType
0x180007f87  call    cs:__imp_RtlVirtualUnwind
0x180007f8d  mov     rax, [rbp+4C8h]
0x180007f94  lea     rcx, [rsp+5C0h+var_570]; void *
0x180007f99  mov     [rbp+4C0h+ContextRecord.Rip], rax
0x180007fa0  xor     edx, edx; Val
0x180007fa2  lea     rax, [rbp+4C8h]
0x180007fa9  mov     r8d, 98h; Size
0x180007faf  add     rax, 8
0x180007fb3  mov     [rbp+4C0h+ContextRecord.Rsp], rax
0x180007fba  call    memset
0x180007fbf  mov     rax, [rbp+4C8h]
0x180007fc6  mov     [rsp+5C0h+var_560], rax
0x180007fcb  mov     [rsp+5C0h+var_570], 40000015h
0x180007fd3  mov     [rsp+5C0h+var_56C], 1
0x180007fdb  call    cs:__imp_IsDebuggerPresent
0x180007fe1  mov     ebx, eax
0x180007fe3  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180007fe5  lea     rax, [rsp+5C0h+var_570]
0x180007fea  mov     [rsp+5C0h+ExceptionInfo.ExceptionRecord], rax
0x180007fef  lea     rax, [rbp+4C0h+ContextRecord]
0x180007ff3  mov     [rsp+5C0h+ExceptionInfo.ContextRecord], rax
0x180007ff8  call    cs:__imp_SetUnhandledExceptionFilter
0x180007ffe  lea     rcx, [rsp+5C0h+ExceptionInfo]; ExceptionInfo
0x180008003  call    cs:__imp_UnhandledExceptionFilter
0x180008009  test    eax, eax
0x18000800b  jnz     short loc_18000801A
0x18000800d  cmp     ebx, 1
0x180008010  jz      short loc_18000801A
0x180008012  lea     ecx, [rax+3]
0x180008015  call    __crt_debugger_hook
0x18000801a  mov     rbx, [rsp+5C0h+arg_0]
0x180008022  add     rsp, 5C0h
0x180008029  pop     rbp
0x18000802a  retn
```
