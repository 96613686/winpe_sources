# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000fae0`
- end: `0x18000fb38`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000fae0`
- `0x18001340c`
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
0x18000fae0  mov     [rsp+arg_0], rbx
0x18000fae5  mov     [rsp+arg_8], rsi
0x18000faea  push    rdi
0x18000faeb  sub     rsp, 20h
0x18000faef  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000faf6  mov     bl, r8b
0x18000faf9  mov     edi, edx
0x18000fafb  mov     esi, ecx
0x18000fafd  test    rax, rax
0x18000fb00  jz      short loc_18000FB1E
0x18000fb02  mov     r8b, bl
0x18000fb05  mov     edx, edi
0x18000fb07  mov     ecx, esi
0x18000fb09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb0e  mov     rbx, [rsp+28h+arg_0]
0x18000fb13  mov     rsi, [rsp+28h+arg_8]
0x18000fb18  add     rsp, 20h
0x18000fb1c  pop     rdi
0x18000fb1d  retn
0x18000fb1e  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000fb25  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x18000fb2a  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x18000fb31  test    rax, rax
0x18000fb34  jz      short loc_18000FB0E
0x18000fb36  jmp     short loc_18000FB02
```
