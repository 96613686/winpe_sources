# __scrt_fastfail

- ea: `0x180003df8`
- end: `0x180003f43`
- name: `__scrt_fastfail`
- size: `331`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800032e0`
- `0x1800033f8`
- `0x1800035f0`
- `0x180003c20`

## callees

- `0x180003df0`
- `0x180003df8`
- `0x1800042f6`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x180003e14`
- `KERNEL32!IsProcessorFeaturePresent` at `0x180003e14`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180003f11`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180003f11`
- `KERNEL32!UnhandledExceptionFilter` at `0x180003f1c`
- `KERNEL32!UnhandledExceptionFilter` at `0x180003f1c`
- `KERNEL32!IsDebuggerPresent` at `0x180003ef0`
- `KERNEL32!IsDebuggerPresent` at `0x180003ef0`
- `KERNEL32!RtlCaptureContext` at `0x180003e41`
- `KERNEL32!RtlCaptureContext` at `0x180003e41`
- `KERNEL32!RtlVirtualUnwind` at `0x180003e9c`
- `KERNEL32!RtlVirtualUnwind` at `0x180003e9c`
- `KERNEL32!RtlLookupFunctionEntry` at `0x180003e5b`
- `KERNEL32!RtlLookupFunctionEntry` at `0x180003e5b`

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
0x180003df8  mov     [rsp-8+arg_0], rbx
0x180003dfd  push    rbp
0x180003dfe  lea     rbp, [rsp-4C0h]
0x180003e06  sub     rsp, 5C0h
0x180003e0d  mov     ebx, ecx
0x180003e0f  mov     ecx, 17h; ProcessorFeature
0x180003e14  call    cs:__imp_IsProcessorFeaturePresent
0x180003e1a  test    eax, eax
0x180003e1c  jz      short loc_180003E22
0x180003e1e  mov     ecx, ebx
0x180003e20  int     29h; Win8: RtlFailFast(ecx)
0x180003e22  mov     ecx, 3
0x180003e27  call    __crt_debugger_hook
0x180003e2c  xor     edx, edx; Val
0x180003e2e  lea     rcx, [rbp+4C0h+ContextRecord]; void *
0x180003e32  mov     r8d, 4D0h; Size
0x180003e38  call    memset_0
0x180003e3d  lea     rcx, [rbp+4C0h+ContextRecord]; ContextRecord
0x180003e41  call    cs:__imp_RtlCaptureContext
0x180003e47  mov     rbx, [rbp+4C0h+ContextRecord.Rip]
0x180003e4e  lea     rdx, [rbp+4C0h+ImageBase]; ImageBase
0x180003e55  mov     rcx, rbx; ControlPc
0x180003e58  xor     r8d, r8d; HistoryTable
0x180003e5b  call    cs:__imp_RtlLookupFunctionEntry
0x180003e61  test    rax, rax
0x180003e64  jz      short loc_180003EA2
0x180003e66  and     [rsp+5C0h+var_588], 0
0x180003e6c  lea     rcx, [rbp+4C0h+arg_10]
0x180003e73  mov     rdx, [rbp+4C0h+ImageBase]; ImageBase
0x180003e7a  mov     r9, rax; FunctionEntry
0x180003e7d  mov     [rsp+5C0h+EstablisherFrame], rcx; EstablisherFrame
0x180003e82  mov     r8, rbx; ControlPc
0x180003e85  lea     rcx, [rbp+4C0h+arg_18]
0x180003e8c  mov     [rsp+5C0h+HandlerData], rcx; HandlerData
0x180003e91  lea     rcx, [rbp+4C0h+ContextRecord]
0x180003e95  mov     [rsp+5C0h+var_5A0], rcx; ContextRecord
0x180003e9a  xor     ecx, ecx; HandlerType
0x180003e9c  call    cs:__imp_RtlVirtualUnwind
0x180003ea2  mov     rax, [rbp+4C8h]
0x180003ea9  lea     rcx, [rsp+5C0h+var_570]; void *
0x180003eae  mov     [rbp+4C0h+ContextRecord.Rip], rax
0x180003eb5  xor     edx, edx; Val
0x180003eb7  lea     rax, [rbp+4C8h]
0x180003ebe  mov     r8d, 98h; Size
0x180003ec4  add     rax, 8
0x180003ec8  mov     [rbp+4C0h+ContextRecord.Rsp], rax
0x180003ecf  call    memset_0
0x180003ed4  mov     rax, [rbp+4C8h]
0x180003edb  mov     [rsp+5C0h+var_560], rax
0x180003ee0  mov     [rsp+5C0h+var_570], 40000015h
0x180003ee8  mov     [rsp+5C0h+var_56C], 1
0x180003ef0  call    cs:__imp_IsDebuggerPresent
0x180003ef6  cmp     eax, 1
0x180003ef9  lea     rax, [rsp+5C0h+var_570]
0x180003efe  mov     [rsp+5C0h+ExceptionInfo.ExceptionRecord], rax
0x180003f03  lea     rax, [rbp+4C0h+ContextRecord]
0x180003f07  setz    bl
0x180003f0a  mov     [rsp+5C0h+ExceptionInfo.ContextRecord], rax
0x180003f0f  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180003f11  call    cs:__imp_SetUnhandledExceptionFilter
0x180003f17  lea     rcx, [rsp+5C0h+ExceptionInfo]; ExceptionInfo
0x180003f1c  call    cs:__imp_UnhandledExceptionFilter
0x180003f22  test    eax, eax
0x180003f24  jnz     short loc_180003F32
0x180003f26  test    bl, bl
0x180003f28  jnz     short loc_180003F32
0x180003f2a  lea     ecx, [rax+3]
0x180003f2d  call    __crt_debugger_hook
0x180003f32  mov     rbx, [rsp+5C0h+arg_0]
0x180003f3a  add     rsp, 5C0h
0x180003f41  pop     rbp
0x180003f42  retn
```
