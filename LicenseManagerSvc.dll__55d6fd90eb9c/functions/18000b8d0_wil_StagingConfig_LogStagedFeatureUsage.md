# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000b8d0`
- end: `0x18000b926`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180007898`
- `0x18000b8d0`
- `0x180018010`

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
0x18000b8d0  mov     [rsp+arg_0], rbx
0x18000b8d5  mov     [rsp+arg_8], rsi
0x18000b8da  push    rdi
0x18000b8db  sub     rsp, 20h
0x18000b8df  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000b8e6  mov     bl, r8b
0x18000b8e9  mov     edi, edx
0x18000b8eb  mov     esi, ecx
0x18000b8ed  test    rax, rax
0x18000b8f0  jnz     short loc_18000B90A
0x18000b8f2  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000b8f9  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x18000b8fe  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x18000b905  test    rax, rax
0x18000b908  jz      short loc_18000B916
0x18000b90a  mov     r8b, bl
0x18000b90d  mov     edx, edi
0x18000b90f  mov     ecx, esi
0x18000b911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b916  mov     rbx, [rsp+28h+arg_0]
0x18000b91b  mov     rsi, [rsp+28h+arg_8]
0x18000b920  add     rsp, 20h
0x18000b924  pop     rdi
0x18000b925  retn
```
