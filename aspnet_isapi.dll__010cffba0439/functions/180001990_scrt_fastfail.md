# __scrt_fastfail

- ea: `0x180001990`
- end: `0x180001adb`
- name: `__scrt_fastfail`
- size: `331`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800011a0`
- `0x1800012b8`
- `0x18000180c`

## callees

- `0x180001988`
- `0x180001990`
- `0x180001eac`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x1800019ac`
- `KERNEL32!IsProcessorFeaturePresent` at `0x1800019ac`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001aa9`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001aa9`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001ab4`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001ab4`
- `KERNEL32!IsDebuggerPresent` at `0x180001a88`
- `KERNEL32!IsDebuggerPresent` at `0x180001a88`
- `KERNEL32!RtlVirtualUnwind` at `0x180001a34`
- `KERNEL32!RtlVirtualUnwind` at `0x180001a34`
- `KERNEL32!RtlLookupFunctionEntry` at `0x1800019f3`
- `KERNEL32!RtlLookupFunctionEntry` at `0x1800019f3`
- `KERNEL32!RtlCaptureContext` at `0x1800019d9`
- `KERNEL32!RtlCaptureContext` at `0x1800019d9`

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
0x180001990  mov     [rsp-8+arg_0], rbx
0x180001995  push    rbp
0x180001996  lea     rbp, [rsp-4C0h]
0x18000199e  sub     rsp, 5C0h
0x1800019a5  mov     ebx, ecx
0x1800019a7  mov     ecx, 17h; ProcessorFeature
0x1800019ac  call    cs:__imp_IsProcessorFeaturePresent
0x1800019b2  test    eax, eax
0x1800019b4  jz      short loc_1800019BA
0x1800019b6  mov     ecx, ebx
0x1800019b8  int     29h; Win8: RtlFailFast(ecx)
0x1800019ba  mov     ecx, 3
0x1800019bf  call    __crt_debugger_hook
0x1800019c4  xor     edx, edx; Val
0x1800019c6  lea     rcx, [rbp+4C0h+ContextRecord]; void *
0x1800019ca  mov     r8d, 4D0h; Size
0x1800019d0  call    memset_0
0x1800019d5  lea     rcx, [rbp+4C0h+ContextRecord]; ContextRecord
0x1800019d9  call    cs:__imp_RtlCaptureContext
0x1800019df  mov     rbx, [rbp+4C0h+ContextRecord.Rip]
0x1800019e6  lea     rdx, [rbp+4C0h+ImageBase]; ImageBase
0x1800019ed  mov     rcx, rbx; ControlPc
0x1800019f0  xor     r8d, r8d; HistoryTable
0x1800019f3  call    cs:__imp_RtlLookupFunctionEntry
0x1800019f9  test    rax, rax
0x1800019fc  jz      short loc_180001A3A
0x1800019fe  and     [rsp+5C0h+var_588], 0
0x180001a04  lea     rcx, [rbp+4C0h+arg_10]
0x180001a0b  mov     rdx, [rbp+4C0h+ImageBase]; ImageBase
0x180001a12  mov     r9, rax; FunctionEntry
0x180001a15  mov     [rsp+5C0h+EstablisherFrame], rcx; EstablisherFrame
0x180001a1a  mov     r8, rbx; ControlPc
0x180001a1d  lea     rcx, [rbp+4C0h+arg_18]
0x180001a24  mov     [rsp+5C0h+HandlerData], rcx; HandlerData
0x180001a29  lea     rcx, [rbp+4C0h+ContextRecord]
0x180001a2d  mov     [rsp+5C0h+var_5A0], rcx; ContextRecord
0x180001a32  xor     ecx, ecx; HandlerType
0x180001a34  call    cs:__imp_RtlVirtualUnwind
0x180001a3a  mov     rax, [rbp+4C8h]
0x180001a41  lea     rcx, [rsp+5C0h+var_570]; void *
0x180001a46  mov     [rbp+4C0h+ContextRecord.Rip], rax
0x180001a4d  xor     edx, edx; Val
0x180001a4f  lea     rax, [rbp+4C8h]
0x180001a56  mov     r8d, 98h; Size
0x180001a5c  add     rax, 8
0x180001a60  mov     [rbp+4C0h+ContextRecord.Rsp], rax
0x180001a67  call    memset_0
0x180001a6c  mov     rax, [rbp+4C8h]
0x180001a73  mov     [rsp+5C0h+var_560], rax
0x180001a78  mov     [rsp+5C0h+var_570], 40000015h
0x180001a80  mov     [rsp+5C0h+var_56C], 1
0x180001a88  call    cs:__imp_IsDebuggerPresent
0x180001a8e  cmp     eax, 1
0x180001a91  lea     rax, [rsp+5C0h+var_570]
0x180001a96  mov     [rsp+5C0h+ExceptionInfo.ExceptionRecord], rax
0x180001a9b  lea     rax, [rbp+4C0h+ContextRecord]
0x180001a9f  setz    bl
0x180001aa2  mov     [rsp+5C0h+ExceptionInfo.ContextRecord], rax
0x180001aa7  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001aa9  call    cs:__imp_SetUnhandledExceptionFilter
0x180001aaf  lea     rcx, [rsp+5C0h+ExceptionInfo]; ExceptionInfo
0x180001ab4  call    cs:__imp_UnhandledExceptionFilter
0x180001aba  test    eax, eax
0x180001abc  jnz     short loc_180001ACA
0x180001abe  test    bl, bl
0x180001ac0  jnz     short loc_180001ACA
0x180001ac2  lea     ecx, [rax+3]
0x180001ac5  call    __crt_debugger_hook
0x180001aca  mov     rbx, [rsp+5C0h+arg_0]
0x180001ad2  add     rsp, 5C0h
0x180001ad9  pop     rbp
0x180001ada  retn
```
