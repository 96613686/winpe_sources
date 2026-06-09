# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000ba50`
- end: `0x18000bac8`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000ba50`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ba7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ba7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ba9b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ba9b`

## string_xrefs

- `0x18000ba78`: `kernelbase.dll`

## pseudocode

```c
HMODULE __fastcall wil_StagingConfig_LogStagedFeatureUsage(unsigned int a1, unsigned int a2, __int64 a3)
{
  __int64 (__fastcall *v3)(_QWORD, _QWORD, _QWORD); // rbx
  char v4; // di
  HMODULE result; // rax

  v3 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))g_wil_details_pfnLogStagedFeatureUsage;
  v4 = a3;
  if ( g_wil_details_pfnLogStagedFeatureUsage )
    goto LABEL_6;
  result = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle
    || (result = GetModuleHandleW(L"kernelbase.dll"),
        (`wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = result) != 0) )
  {
    result = (HMODULE)GetProcAddress(result, "LogStagedFeatureUsage");
    v3 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))result;
  }
  g_wil_details_pfnLogStagedFeatureUsage = (__int64)v3;
  if ( v3 )
  {
LABEL_6:
    LOBYTE(a3) = v4;
    return (HMODULE)v3(a1, a2, a3);
  }
  return result;
}

```

## disassembly

```asm
0x18000ba50  push    rbx
0x18000ba52  push    rbp
0x18000ba53  push    rsi
0x18000ba54  push    rdi
0x18000ba55  sub     rsp, 28h
0x18000ba59  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000ba60  mov     dil, r8b
0x18000ba63  mov     esi, edx
0x18000ba65  mov     ebp, ecx
0x18000ba67  test    rbx, rbx
0x18000ba6a  jnz     short loc_18000BAB0
0x18000ba6c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000ba73  test    rax, rax
0x18000ba76  jnz     short loc_18000BA91
0x18000ba78  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000ba7f  call    cs:__imp_GetModuleHandleW
0x18000ba85  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000ba8c  test    rax, rax
0x18000ba8f  jz      short loc_18000BAA4
0x18000ba91  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000ba98  mov     rcx, rax; hModule
0x18000ba9b  call    cs:__imp_GetProcAddress
0x18000baa1  mov     rbx, rax
0x18000baa4  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000baab  test    rbx, rbx
0x18000baae  jz      short loc_18000BABF
0x18000bab0  mov     r8b, dil
0x18000bab3  mov     edx, esi
0x18000bab5  mov     ecx, ebp
0x18000bab7  mov     rax, rbx
0x18000baba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000babf  add     rsp, 28h
0x18000bac3  pop     rdi
0x18000bac4  pop     rsi
0x18000bac5  pop     rbp
0x18000bac6  pop     rbx
0x18000bac7  retn
```
