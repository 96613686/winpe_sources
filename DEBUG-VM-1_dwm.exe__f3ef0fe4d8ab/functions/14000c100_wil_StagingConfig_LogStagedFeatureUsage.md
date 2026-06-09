# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x14000c100`
- end: `0x14000c156`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x14000bc3c`
- `0x14000c100`
- `0x140010010`

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
0x14000c100  mov     [rsp+arg_0], rbx
0x14000c105  mov     [rsp+arg_8], rsi
0x14000c10a  push    rdi
0x14000c10b  sub     rsp, 20h
0x14000c10f  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x14000c116  mov     bl, r8b
0x14000c119  mov     edi, edx
0x14000c11b  mov     esi, ecx
0x14000c11d  test    rax, rax
0x14000c120  jnz     short loc_14000C13A
0x14000c122  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x14000c129  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x14000c12e  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x14000c135  test    rax, rax
0x14000c138  jz      short loc_14000C146
0x14000c13a  mov     r8b, bl
0x14000c13d  mov     edx, edi
0x14000c13f  mov     ecx, esi
0x14000c141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c146  mov     rbx, [rsp+28h+arg_0]
0x14000c14b  mov     rsi, [rsp+28h+arg_8]
0x14000c150  add     rsp, 20h
0x14000c154  pop     rdi
0x14000c155  retn
```
