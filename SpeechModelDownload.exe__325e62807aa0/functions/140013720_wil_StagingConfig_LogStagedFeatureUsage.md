# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x140013720`
- end: `0x140013798`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x140013720`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001374f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001374f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001376b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001376b`

## string_xrefs

- `0x140013748`: `kernelbase.dll`

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
0x140013720  push    rbx
0x140013722  push    rbp
0x140013723  push    rsi
0x140013724  push    rdi
0x140013725  sub     rsp, 28h
0x140013729  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x140013730  mov     dil, r8b
0x140013733  mov     esi, edx
0x140013735  mov     ebp, ecx
0x140013737  test    rbx, rbx
0x14001373a  jnz     short loc_140013780
0x14001373c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140013743  test    rax, rax
0x140013746  jnz     short loc_140013761
0x140013748  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14001374f  call    cs:__imp_GetModuleHandleW
0x140013755  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14001375c  test    rax, rax
0x14001375f  jz      short loc_140013774
0x140013761  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x140013768  mov     rcx, rax; hModule
0x14001376b  call    cs:__imp_GetProcAddress
0x140013771  mov     rbx, rax
0x140013774  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x14001377b  test    rbx, rbx
0x14001377e  jz      short loc_14001378F
0x140013780  mov     r8b, dil
0x140013783  mov     edx, esi
0x140013785  mov     ecx, ebp
0x140013787  mov     rax, rbx
0x14001378a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001378f  add     rsp, 28h
0x140013793  pop     rdi
0x140013794  pop     rsi
0x140013795  pop     rbp
0x140013796  pop     rbx
0x140013797  retn
```
