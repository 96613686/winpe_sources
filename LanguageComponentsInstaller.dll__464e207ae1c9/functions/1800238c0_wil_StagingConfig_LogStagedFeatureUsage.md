# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x1800238c0`
- end: `0x180023938`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x1800238c0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002390b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002390b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800238ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800238ef`

## string_xrefs

- `0x1800238e8`: `kernelbase.dll`

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
0x1800238c0  push    rbx
0x1800238c2  push    rbp
0x1800238c3  push    rsi
0x1800238c4  push    rdi
0x1800238c5  sub     rsp, 28h
0x1800238c9  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x1800238d0  mov     dil, r8b
0x1800238d3  mov     esi, edx
0x1800238d5  mov     ebp, ecx
0x1800238d7  test    rbx, rbx
0x1800238da  jnz     short loc_180023920
0x1800238dc  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800238e3  test    rax, rax
0x1800238e6  jnz     short loc_180023901
0x1800238e8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800238ef  call    cs:__imp_GetModuleHandleW
0x1800238f5  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800238fc  test    rax, rax
0x1800238ff  jz      short loc_180023914
0x180023901  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180023908  mov     rcx, rax; hModule
0x18002390b  call    cs:__imp_GetProcAddress
0x180023911  mov     rbx, rax
0x180023914  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18002391b  test    rbx, rbx
0x18002391e  jz      short loc_18002392F
0x180023920  mov     r8b, dil
0x180023923  mov     edx, esi
0x180023925  mov     ecx, ebp
0x180023927  mov     rax, rbx
0x18002392a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002392f  add     rsp, 28h
0x180023933  pop     rdi
0x180023934  pop     rsi
0x180023935  pop     rbp
0x180023936  pop     rbx
0x180023937  retn
```
