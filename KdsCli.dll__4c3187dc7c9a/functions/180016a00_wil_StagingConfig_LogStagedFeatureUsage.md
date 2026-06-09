# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180016a00`
- end: `0x180016a78`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180016a00`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016a2f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016a2f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016a4b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016a4b`

## string_xrefs

- `0x180016a28`: `kernelbase.dll`

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
0x180016a00  push    rbx
0x180016a02  push    rbp
0x180016a03  push    rsi
0x180016a04  push    rdi
0x180016a05  sub     rsp, 28h
0x180016a09  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180016a10  mov     dil, r8b
0x180016a13  mov     esi, edx
0x180016a15  mov     ebp, ecx
0x180016a17  test    rbx, rbx
0x180016a1a  jnz     short loc_180016A60
0x180016a1c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180016a23  test    rax, rax
0x180016a26  jnz     short loc_180016A41
0x180016a28  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180016a2f  call    cs:__imp_GetModuleHandleW
0x180016a35  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180016a3c  test    rax, rax
0x180016a3f  jz      short loc_180016A54
0x180016a41  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180016a48  mov     rcx, rax; hModule
0x180016a4b  call    cs:__imp_GetProcAddress
0x180016a51  mov     rbx, rax
0x180016a54  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x180016a5b  test    rbx, rbx
0x180016a5e  jz      short loc_180016A6F
0x180016a60  mov     r8b, dil
0x180016a63  mov     edx, esi
0x180016a65  mov     ecx, ebp
0x180016a67  mov     rax, rbx
0x180016a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a6f  add     rsp, 28h
0x180016a73  pop     rdi
0x180016a74  pop     rsi
0x180016a75  pop     rbp
0x180016a76  pop     rbx
0x180016a77  retn
```
