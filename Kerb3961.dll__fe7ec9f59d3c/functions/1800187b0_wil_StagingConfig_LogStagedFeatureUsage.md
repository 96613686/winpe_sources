# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x1800187b0`
- end: `0x180018828`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x1800187b0`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800187fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800187fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800187df`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800187df`

## string_xrefs

- `0x1800187d8`: `kernelbase.dll`

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
0x1800187b0  push    rbx
0x1800187b2  push    rbp
0x1800187b3  push    rsi
0x1800187b4  push    rdi
0x1800187b5  sub     rsp, 28h
0x1800187b9  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x1800187c0  mov     dil, r8b
0x1800187c3  mov     esi, edx
0x1800187c5  mov     ebp, ecx
0x1800187c7  test    rbx, rbx
0x1800187ca  jnz     short loc_180018810
0x1800187cc  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800187d3  test    rax, rax
0x1800187d6  jnz     short loc_1800187F1
0x1800187d8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800187df  call    cs:__imp_GetModuleHandleW
0x1800187e5  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800187ec  test    rax, rax
0x1800187ef  jz      short loc_180018804
0x1800187f1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x1800187f8  mov     rcx, rax; hModule
0x1800187fb  call    cs:__imp_GetProcAddress
0x180018801  mov     rbx, rax
0x180018804  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18001880b  test    rbx, rbx
0x18001880e  jz      short loc_18001881F
0x180018810  mov     r8b, dil
0x180018813  mov     edx, esi
0x180018815  mov     ecx, ebp
0x180018817  mov     rax, rbx
0x18001881a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001881f  add     rsp, 28h
0x180018823  pop     rdi
0x180018824  pop     rsi
0x180018825  pop     rbp
0x180018826  pop     rbx
0x180018827  retn
```
