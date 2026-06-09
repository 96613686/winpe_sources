# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x140013570`
- end: `0x1400135c6`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140006b48`
- `0x140013570`
- `0x14001c010`

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
0x140013570  mov     [rsp+arg_0], rbx
0x140013575  mov     [rsp+arg_8], rsi
0x14001357a  push    rdi
0x14001357b  sub     rsp, 20h
0x14001357f  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x140013586  mov     bl, r8b
0x140013589  mov     edi, edx
0x14001358b  mov     esi, ecx
0x14001358d  test    rax, rax
0x140013590  jnz     short loc_1400135AA
0x140013592  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x140013599  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x14001359e  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x1400135a5  test    rax, rax
0x1400135a8  jz      short loc_1400135B6
0x1400135aa  mov     r8b, bl
0x1400135ad  mov     edx, edi
0x1400135af  mov     ecx, esi
0x1400135b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400135b6  mov     rbx, [rsp+28h+arg_0]
0x1400135bb  mov     rsi, [rsp+28h+arg_8]
0x1400135c0  add     rsp, 20h
0x1400135c4  pop     rdi
0x1400135c5  retn
```
