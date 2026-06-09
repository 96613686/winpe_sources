# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180014a40`
- end: `0x180014a96`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180014444`
- `0x180014a40`
- `0x180029010`

## pseudocode

```c
FARPROC __fastcall wil_StagingConfig_LogStagedFeatureUsage(unsigned int a1, unsigned int a2, __int64 a3)
{
  FARPROC result; // rax
  char v4; // bl

  result = (FARPROC)g_wil_details_pfnLogStagedFeatureUsage;
  v4 = a3;
  if ( g_wil_details_pfnLogStagedFeatureUsage
    || (result = wil_details_GetKernelBaseProcAddress("LogStagedFeatureUsage"),
        (g_wil_details_pfnLogStagedFeatureUsage = (__int64)result) != 0) )
  {
    LOBYTE(a3) = v4;
    return (FARPROC)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))result)(a1, a2, a3);
  }
  return result;
}

```

## disassembly

```asm
0x180014a40  mov     [rsp+arg_0], rbx
0x180014a45  mov     [rsp+arg_8], rsi
0x180014a4a  push    rdi
0x180014a4b  sub     rsp, 20h
0x180014a4f  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180014a56  mov     bl, r8b
0x180014a59  mov     edi, edx
0x180014a5b  mov     esi, ecx
0x180014a5d  test    rax, rax
0x180014a60  jnz     short loc_180014A7A
0x180014a62  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180014a69  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x180014a6e  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x180014a75  test    rax, rax
0x180014a78  jz      short loc_180014A86
0x180014a7a  mov     r8b, bl
0x180014a7d  mov     edx, edi
0x180014a7f  mov     ecx, esi
0x180014a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a86  mov     rbx, [rsp+28h+arg_0]
0x180014a8b  mov     rsi, [rsp+28h+arg_8]
0x180014a90  add     rsp, 20h
0x180014a94  pop     rdi
0x180014a95  retn
```
