# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180012290`
- end: `0x1800122e7`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1800058a4`
- `0x180012290`
- `0x18001e010`

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
0x180012290  mov     [rsp+arg_0], rbx
0x180012295  mov     [rsp+arg_8], rsi
0x18001229a  push    rdi
0x18001229b  sub     rsp, 20h
0x18001229f  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x1800122a6  mov     bl, r8b
0x1800122a9  mov     edi, edx
0x1800122ab  mov     esi, ecx
0x1800122ad  test    rax, rax
0x1800122b0  jnz     short loc_1800122CA
0x1800122b2  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x1800122b9  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x1800122be  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x1800122c5  test    rax, rax
0x1800122c8  jz      short loc_1800122D6
0x1800122ca  mov     r8b, bl
0x1800122cd  mov     edx, edi
0x1800122cf  mov     ecx, esi
0x1800122d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122d6  mov     rbx, [rsp+28h+arg_0]
0x1800122db  mov     rsi, [rsp+28h+arg_8]
0x1800122e0  add     rsp, 20h
0x1800122e4  pop     rdi
0x1800122e5  retn
```
