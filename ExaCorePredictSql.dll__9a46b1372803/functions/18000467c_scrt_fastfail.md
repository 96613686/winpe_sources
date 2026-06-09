# __scrt_fastfail

- ea: `0x18000467c`
- end: `0x1800047c1`
- name: `__scrt_fastfail`
- size: `325`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180003d20`
- `0x180003fd0`
- `0x1800040fc`

## callees

- `0x18000467c`
- `0x180004966`
- `0x1800049b4`

## import_xrefs

- `KERNEL32!RtlLookupFunctionEntry` at `0x1800046db`
- `KERNEL32!RtlLookupFunctionEntry` at `0x1800046db`
- `KERNEL32!RtlVirtualUnwind` at `0x18000471c`
- `KERNEL32!RtlVirtualUnwind` at `0x18000471c`
- `KERNEL32!UnhandledExceptionFilter` at `0x18000479c`
- `KERNEL32!UnhandledExceptionFilter` at `0x18000479c`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180004791`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180004791`
- `KERNEL32!IsDebuggerPresent` at `0x180004770`
- `KERNEL32!IsDebuggerPresent` at `0x180004770`
- `KERNEL32!RtlCaptureContext` at `0x1800046c1`
- `KERNEL32!RtlCaptureContext` at `0x1800046c1`

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
  struct _CONTEXT ContextRecord; // [rsp+F0h] [rbp-10h] BYREF
  DWORD64 retaddr; // [rsp+5C8h] [rbp+4C8h]
  __int64 v11; // [rsp+5D0h] [rbp+4D0h] BYREF
  unsigned __int64 ImageBase; // [rsp+5D8h] [rbp+4D8h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+5E0h] [rbp+4E0h] BYREF
  PVOID HandlerData; // [rsp+5E8h] [rbp+4E8h] BYREF

  if ( IsProcessorFeaturePresent_0(0x17u) )
    __fastfail(a1);
  _scrt_debugger_hook_flag = 0;
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
  if ( !result )
  {
    result = -v4;
    _scrt_debugger_hook_flag &= result;
  }
  return result;
}

```

## disassembly

```asm
0x18000467c  mov     [rsp-8+arg_0], rbx
0x180004681  push    rbp
0x180004682  lea     rbp, [rsp-4C0h]
0x18000468a  sub     rsp, 5C0h
0x180004691  mov     ebx, ecx
0x180004693  mov     ecx, 17h; ProcessorFeature
0x180004698  call    IsProcessorFeaturePresent_0
0x18000469d  test    eax, eax
0x18000469f  jz      short loc_1800046A5
0x1800046a1  mov     ecx, ebx
0x1800046a3  int     29h; Win8: RtlFailFast(ecx)
0x1800046a5  and     cs:__scrt_debugger_hook_flag, 0
0x1800046ac  lea     rcx, [rbp+4C0h+ContextRecord]; void *
0x1800046b0  xor     edx, edx; Val
0x1800046b2  mov     r8d, 4D0h; Size
0x1800046b8  call    memset_0
0x1800046bd  lea     rcx, [rbp+4C0h+ContextRecord]; ContextRecord
0x1800046c1  call    cs:__imp_RtlCaptureContext
0x1800046c7  mov     rbx, [rbp+4C0h+ContextRecord.Rip]
0x1800046ce  lea     rdx, [rbp+4C0h+ImageBase]; ImageBase
0x1800046d5  mov     rcx, rbx; ControlPc
0x1800046d8  xor     r8d, r8d; HistoryTable
0x1800046db  call    cs:__imp_RtlLookupFunctionEntry
0x1800046e1  test    rax, rax
0x1800046e4  jz      short loc_180004722
0x1800046e6  and     [rsp+5C0h+var_588], 0
0x1800046ec  lea     rcx, [rbp+4C0h+arg_10]
0x1800046f3  mov     rdx, [rbp+4C0h+ImageBase]; ImageBase
0x1800046fa  mov     r9, rax; FunctionEntry
0x1800046fd  mov     [rsp+5C0h+EstablisherFrame], rcx; EstablisherFrame
0x180004702  mov     r8, rbx; ControlPc
0x180004705  lea     rcx, [rbp+4C0h+arg_18]
0x18000470c  mov     [rsp+5C0h+HandlerData], rcx; HandlerData
0x180004711  lea     rcx, [rbp+4C0h+ContextRecord]
0x180004715  mov     [rsp+5C0h+var_5A0], rcx; ContextRecord
0x18000471a  xor     ecx, ecx; HandlerType
0x18000471c  call    cs:__imp_RtlVirtualUnwind
0x180004722  mov     rax, [rbp+4C8h]
0x180004729  lea     rcx, [rsp+5C0h+var_570]; void *
0x18000472e  mov     [rbp+4C0h+ContextRecord.Rip], rax
0x180004735  xor     edx, edx; Val
0x180004737  lea     rax, [rbp+4C8h]
0x18000473e  mov     r8d, 98h; Size
0x180004744  add     rax, 8
0x180004748  mov     [rbp+4C0h+ContextRecord.Rsp], rax
0x18000474f  call    memset_0
0x180004754  mov     rax, [rbp+4C8h]
0x18000475b  mov     [rsp+5C0h+var_560], rax
0x180004760  mov     [rsp+5C0h+var_570], 40000015h
0x180004768  mov     [rsp+5C0h+var_56C], 1
0x180004770  call    cs:__imp_IsDebuggerPresent
0x180004776  cmp     eax, 1
0x180004779  lea     rax, [rsp+5C0h+var_570]
0x18000477e  mov     [rsp+5C0h+ExceptionInfo.ExceptionRecord], rax
0x180004783  lea     rax, [rbp+4C0h+ContextRecord]
0x180004787  setz    bl
0x18000478a  mov     [rsp+5C0h+ExceptionInfo.ContextRecord], rax
0x18000478f  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180004791  call    cs:__imp_SetUnhandledExceptionFilter
0x180004797  lea     rcx, [rsp+5C0h+ExceptionInfo]; ExceptionInfo
0x18000479c  call    cs:__imp_UnhandledExceptionFilter
0x1800047a2  test    eax, eax
0x1800047a4  jnz     short loc_1800047B0
0x1800047a6  neg     bl
0x1800047a8  sbb     eax, eax
0x1800047aa  and     cs:__scrt_debugger_hook_flag, eax
0x1800047b0  mov     rbx, [rsp+5C0h+arg_0]
0x1800047b8  add     rsp, 5C0h
0x1800047bf  pop     rbp
0x1800047c0  retn
```
