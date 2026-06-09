# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180016750`
- end: `0x1800167c8`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180016750`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001679b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001679b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001677f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001677f`

## string_xrefs

- `0x180016778`: `kernelbase.dll`

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
0x180016750  push    rbx
0x180016752  push    rbp
0x180016753  push    rsi
0x180016754  push    rdi
0x180016755  sub     rsp, 28h
0x180016759  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180016760  mov     dil, r8b
0x180016763  mov     esi, edx
0x180016765  mov     ebp, ecx
0x180016767  test    rbx, rbx
0x18001676a  jnz     short loc_1800167B0
0x18001676c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180016773  test    rax, rax
0x180016776  jnz     short loc_180016791
0x180016778  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001677f  call    cs:__imp_GetModuleHandleW
0x180016785  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001678c  test    rax, rax
0x18001678f  jz      short loc_1800167A4
0x180016791  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180016798  mov     rcx, rax; hModule
0x18001679b  call    cs:__imp_GetProcAddress
0x1800167a1  mov     rbx, rax
0x1800167a4  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x1800167ab  test    rbx, rbx
0x1800167ae  jz      short loc_1800167BF
0x1800167b0  mov     r8b, dil
0x1800167b3  mov     edx, esi
0x1800167b5  mov     ecx, ebp
0x1800167b7  mov     rax, rbx
0x1800167ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167bf  add     rsp, 28h
0x1800167c3  pop     rdi
0x1800167c4  pop     rsi
0x1800167c5  pop     rbp
0x1800167c6  pop     rbx
0x1800167c7  retn
```
