# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180013070`
- end: `0x1800130c6`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `86`
- prototype: `FARPROC __fastcall(unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180012c88`
- `0x180013070`
- `0x18001b010`

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
0x180013070  mov     [rsp+arg_0], rbx
0x180013075  mov     [rsp+arg_8], rsi
0x18001307a  push    rdi
0x18001307b  sub     rsp, 20h
0x18001307f  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180013086  mov     bl, r8b
0x180013089  mov     edi, edx
0x18001308b  mov     esi, ecx
0x18001308d  test    rax, rax
0x180013090  jnz     short loc_1800130AA
0x180013092  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180013099  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x18001309e  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x1800130a5  test    rax, rax
0x1800130a8  jz      short loc_1800130B6
0x1800130aa  mov     r8b, bl
0x1800130ad  mov     edx, edi
0x1800130af  mov     ecx, esi
0x1800130b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130b6  mov     rbx, [rsp+28h+arg_0]
0x1800130bb  mov     rsi, [rsp+28h+arg_8]
0x1800130c0  add     rsp, 20h
0x1800130c4  pop     rdi
0x1800130c5  retn
```
