# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000a2e0`
- end: `0x18000a336`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180009df8`
- `0x18000a2e0`
- `0x18001c010`

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
0x18000a2e0  mov     [rsp+arg_0], rbx
0x18000a2e5  mov     [rsp+arg_8], rsi
0x18000a2ea  push    rdi
0x18000a2eb  sub     rsp, 20h
0x18000a2ef  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000a2f6  mov     bl, r8b
0x18000a2f9  mov     edi, edx
0x18000a2fb  mov     esi, ecx
0x18000a2fd  test    rax, rax
0x18000a300  jnz     short loc_18000A31A
0x18000a302  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000a309  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x18000a30e  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x18000a315  test    rax, rax
0x18000a318  jz      short loc_18000A326
0x18000a31a  mov     r8b, bl
0x18000a31d  mov     edx, edi
0x18000a31f  mov     ecx, esi
0x18000a321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a326  mov     rbx, [rsp+28h+arg_0]
0x18000a32b  mov     rsi, [rsp+28h+arg_8]
0x18000a330  add     rsp, 20h
0x18000a334  pop     rdi
0x18000a335  retn
```
