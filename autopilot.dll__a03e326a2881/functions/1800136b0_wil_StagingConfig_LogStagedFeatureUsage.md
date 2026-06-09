# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x1800136b0`
- end: `0x180013728`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x1800136b0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800136df`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800136df`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800136fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800136fb`

## string_xrefs

- `0x1800136d8`: `kernelbase.dll`

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
0x1800136b0  push    rbx
0x1800136b2  push    rbp
0x1800136b3  push    rsi
0x1800136b4  push    rdi
0x1800136b5  sub     rsp, 28h
0x1800136b9  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x1800136c0  mov     dil, r8b
0x1800136c3  mov     esi, edx
0x1800136c5  mov     ebp, ecx
0x1800136c7  test    rbx, rbx
0x1800136ca  jnz     short loc_180013710
0x1800136cc  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800136d3  test    rax, rax
0x1800136d6  jnz     short loc_1800136F1
0x1800136d8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800136df  call    cs:__imp_GetModuleHandleW
0x1800136e5  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800136ec  test    rax, rax
0x1800136ef  jz      short loc_180013704
0x1800136f1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x1800136f8  mov     rcx, rax; hModule
0x1800136fb  call    cs:__imp_GetProcAddress
0x180013701  mov     rbx, rax
0x180013704  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18001370b  test    rbx, rbx
0x18001370e  jz      short loc_18001371F
0x180013710  mov     r8b, dil
0x180013713  mov     edx, esi
0x180013715  mov     ecx, ebp
0x180013717  mov     rax, rbx
0x18001371a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001371f  add     rsp, 28h
0x180013723  pop     rdi
0x180013724  pop     rsi
0x180013725  pop     rbp
0x180013726  pop     rbx
0x180013727  retn
```
