# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180009bf0`
- end: `0x180009c68`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180009bf0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009c1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009c1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009c3b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009c3b`

## string_xrefs

- `0x180009c18`: `kernelbase.dll`

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
0x180009bf0  push    rbx
0x180009bf2  push    rbp
0x180009bf3  push    rsi
0x180009bf4  push    rdi
0x180009bf5  sub     rsp, 28h
0x180009bf9  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180009c00  mov     dil, r8b
0x180009c03  mov     esi, edx
0x180009c05  mov     ebp, ecx
0x180009c07  test    rbx, rbx
0x180009c0a  jnz     short loc_180009C50
0x180009c0c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009c13  test    rax, rax
0x180009c16  jnz     short loc_180009C31
0x180009c18  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180009c1f  call    cs:__imp_GetModuleHandleW
0x180009c25  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009c2c  test    rax, rax
0x180009c2f  jz      short loc_180009C44
0x180009c31  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180009c38  mov     rcx, rax; hModule
0x180009c3b  call    cs:__imp_GetProcAddress
0x180009c41  mov     rbx, rax
0x180009c44  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x180009c4b  test    rbx, rbx
0x180009c4e  jz      short loc_180009C5F
0x180009c50  mov     r8b, dil
0x180009c53  mov     edx, esi
0x180009c55  mov     ecx, ebp
0x180009c57  mov     rax, rbx
0x180009c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c5f  add     rsp, 28h
0x180009c63  pop     rdi
0x180009c64  pop     rsi
0x180009c65  pop     rbp
0x180009c66  pop     rbx
0x180009c67  retn
```
