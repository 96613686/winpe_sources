# HResultException::HResultException(long)

- ea: `0x180006608`
- end: `0x18000667f`
- name: `??0HResultException@@QEAA@J@Z`
- size: `119`
- prototype: `HResultException *__fastcall(HResultException *__hidden this, int)`
- caller_count: `61`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180001760`
- `0x180001afc`
- `0x180001b78`
- `0x180001c48`
- `0x180002220`
- `0x180002320`
- `0x18000266c`
- `0x180003490`
- `0x180003818`
- `0x180003894`
- `0x180003b90`
- `0x180004260`
- `0x180004430`
- `0x180004a20`
- `0x180004b20`
- `0x180004d40`
- `0x180004dbc`
- `0x180004fc0`
- `0x18000515c`
- `0x180005b24`
- `0x180005c60`
- `0x180005ce4`
- `0x180005d60`
- `0x180005de4`
- `0x180005e60`
- `0x180005edc`
- `0x180005fbc`
- `0x180006068`
- `0x1800060f8`
- `0x18000617c`
- `0x180006208`
- `0x1800063f8`
- `0x180006474`
- `0x180006528`
- `0x1800065d4`
- `0x1800067e8`
- `0x180006af8`
- `0x18000cc94`
- `0x18000cd38`
- `0x18000cdc4`
- `0x18000ce50`
- `0x18000cefc`
- `0x18000d420`
- `0x18000d800`
- `0x18000da04`
- `0x18000db4c`
- `0x18000dcc8`
- `0x18000dda4`
- `0x18000de90`
- `0x18000e0d8`

## callees

- `0x1800046dc`

## import_xrefs

- `ntdll!RtlCaptureStackBackTrace` at `0x180006660`
- `ntdll!RtlCaptureStackBackTrace` at `0x180006660`

## pseudocode

```c
HResultException *__fastcall HResultException::HResultException(HResultException *this, int a2)
{
  __int64 v3; // rbx

  wil::ResultException::ResultException(this, a2);
  *(_QWORD *)this = &Win32Exception::`vftable';
  v3 = 136LL * g_NetSetupNextExceptionTrace;
  g_NetSetupNextExceptionTrace = ((_BYTE)g_NetSetupNextExceptionTrace + 1) & 3;
  *(_DWORD *)((char *)&g_NetSetupExceptionTraces + v3) = RtlCaptureStackBackTrace(
                                                           1u,
                                                           0x10u,
                                                           (PVOID *)((char *)&g_NetSetupExceptionTraces + v3 + 8),
                                                           0);
  return this;
}

```

## disassembly

```asm
0x180006608  mov     [rsp+arg_0], rbx
0x18000660d  mov     [rsp+arg_8], rsi
0x180006612  push    rdi
0x180006613  sub     rsp, 20h
0x180006617  mov     rdi, rcx
0x18000661a  call    ??0ResultException@wil@@QEAA@J@Z; wil::ResultException::ResultException(long)
0x18000661f  mov     ecx, 1; FramesToSkip
0x180006624  lea     rax, ??_7Win32Exception@@6B@; const Win32Exception::`vftable'
0x18000662b  mov     [rdi], rax
0x18000662e  lea     rsi, ?g_NetSetupExceptionTraces@@3PAUNetSetupExceptionTrace@@A; NetSetupExceptionTrace near * g_NetSetupExceptionTraces
0x180006635  mov     eax, cs:?g_NetSetupNextExceptionTrace@@3KC; ulong volatile g_NetSetupNextExceptionTrace
0x18000663b  lea     r8, [rsi+8]
0x18000663f  imul    rbx, rax, 88h
0x180006646  mov     eax, cs:?g_NetSetupNextExceptionTrace@@3KC; ulong volatile g_NetSetupNextExceptionTrace
0x18000664c  lea     edx, [rcx+0Fh]; FramesToCapture
0x18000664f  add     eax, ecx
0x180006651  add     r8, rbx; BackTrace
0x180006654  and     eax, 3
0x180006657  xor     r9d, r9d; BackTraceHash
0x18000665a  mov     cs:?g_NetSetupNextExceptionTrace@@3KC, eax; ulong volatile g_NetSetupNextExceptionTrace
0x180006660  call    cs:__imp_RtlCaptureStackBackTrace
0x180006666  movzx   eax, ax
0x180006669  mov     [rbx+rsi], eax
0x18000666c  mov     rax, rdi
0x18000666f  mov     rbx, [rsp+28h+arg_0]
0x180006674  mov     rsi, [rsp+28h+arg_8]
0x180006679  add     rsp, 20h
0x18000667d  pop     rdi
0x18000667e  retn
```
