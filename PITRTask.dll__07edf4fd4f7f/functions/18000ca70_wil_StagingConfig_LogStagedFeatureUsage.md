# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000ca70`
- end: `0x18000cae8`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: `HMODULE __fastcall(unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000ca70`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cabb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cabb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ca9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ca9f`

## string_xrefs

- `0x18000ca98`: `kernelbase.dll`

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
0x18000ca70  push    rbx
0x18000ca72  push    rbp
0x18000ca73  push    rsi
0x18000ca74  push    rdi
0x18000ca75  sub     rsp, 28h
0x18000ca79  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000ca80  mov     dil, r8b
0x18000ca83  mov     esi, edx
0x18000ca85  mov     ebp, ecx
0x18000ca87  test    rbx, rbx
0x18000ca8a  jnz     short loc_18000CAD0
0x18000ca8c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000ca93  test    rax, rax
0x18000ca96  jnz     short loc_18000CAB1
0x18000ca98  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000ca9f  call    cs:__imp_GetModuleHandleW
0x18000caa5  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000caac  test    rax, rax
0x18000caaf  jz      short loc_18000CAC4
0x18000cab1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000cab8  mov     rcx, rax; hModule
0x18000cabb  call    cs:__imp_GetProcAddress
0x18000cac1  mov     rbx, rax
0x18000cac4  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000cacb  test    rbx, rbx
0x18000cace  jz      short loc_18000CADF
0x18000cad0  mov     r8b, dil
0x18000cad3  mov     edx, esi
0x18000cad5  mov     ecx, ebp
0x18000cad7  mov     rax, rbx
0x18000cada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cadf  add     rsp, 28h
0x18000cae3  pop     rdi
0x18000cae4  pop     rsi
0x18000cae5  pop     rbp
0x18000cae6  pop     rbx
0x18000cae7  retn
```
