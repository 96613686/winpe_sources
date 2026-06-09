# InitMicDiagnostic(void)

- ea: `0x18000683c`
- end: `0x18000688e`
- name: `?InitMicDiagnostic@@YAJXZ`
- size: `82`
- prototype: `__int64(void)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006d60`
- `0x180006dd0`
- `0x180006e40`
- `0x180006eb0`
- `0x180006f20`
- `0x180006fc0`
- `0x180007020`
- `0x1800070d0`

## callees

- `0x180005b08`
- `0x18000683c`

## import_xrefs

- `KERNEL32!InitOnceExecuteOnce` at `0x18000685e`
- `KERNEL32!InitOnceExecuteOnce` at `0x18000685e`

## pseudocode

```c
__int64 InitMicDiagnostic(void)
{
  const char *v0; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( g_pSpeechDiagnostic || InitOnceExecuteOnce(&g_initOnce, InitOnceHandler, 0, 0) )
    return 0;
  else
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x3F,
             (unsigned int)"base\\diagnosis\\pdi\\scripteddiag\\packages\\speech\\speechdiagnosticutil\\speechdiagnosticutil.cpp",
             v0);
}

```

## disassembly

```asm
0x18000683c  sub     rsp, 28h
0x180006840  cmp     cs:?g_pSpeechDiagnostic@@3PEAUISpeechMicDiagnostic@SpeechMicDiagnostic@@EA, 0; SpeechMicDiagnostic::ISpeechMicDiagnostic * g_pSpeechDiagnostic
0x180006848  jnz     short loc_180006886
0x18000684a  xor     r9d, r9d; Context
0x18000684d  lea     rdx, InitOnceHandler; InitFn
0x180006854  xor     r8d, r8d; Parameter
0x180006857  lea     rcx, ?g_initOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18000685e  call    cs:__imp_InitOnceExecuteOnce
0x180006865  nop     dword ptr [rax+rax+00h]
0x18000686a  test    eax, eax
0x18000686c  jnz     short loc_180006886
0x18000686e  mov     rcx, [rsp+28h]; this
0x180006873  lea     r8, aBaseDiagnosisP; "base\\diagnosis\\pdi\\scripteddiag\\pac"...
0x18000687a  lea     edx, [rax+3Fh]; void *
0x18000687d  add     rsp, 28h
0x180006881  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006886  xor     eax, eax
0x180006888  add     rsp, 28h
0x18000688c  retn
```
