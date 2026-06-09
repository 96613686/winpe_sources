# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180030df0`
- end: `0x180030e68`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: `HMODULE __fastcall(unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180030df0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030e3b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030e3b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030e1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030e1f`

## string_xrefs

- `0x180030e18`: `kernelbase.dll`

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
0x180030df0  push    rbx
0x180030df2  push    rbp
0x180030df3  push    rsi
0x180030df4  push    rdi
0x180030df5  sub     rsp, 28h
0x180030df9  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180030e00  mov     dil, r8b
0x180030e03  mov     esi, edx
0x180030e05  mov     ebp, ecx
0x180030e07  test    rbx, rbx
0x180030e0a  jnz     short loc_180030E50
0x180030e0c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180030e13  test    rax, rax
0x180030e16  jnz     short loc_180030E31
0x180030e18  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180030e1f  call    cs:__imp_GetModuleHandleW
0x180030e25  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180030e2c  test    rax, rax
0x180030e2f  jz      short loc_180030E44
0x180030e31  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180030e38  mov     rcx, rax; hModule
0x180030e3b  call    cs:__imp_GetProcAddress
0x180030e41  mov     rbx, rax
0x180030e44  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x180030e4b  test    rbx, rbx
0x180030e4e  jz      short loc_180030E5F
0x180030e50  mov     r8b, dil
0x180030e53  mov     edx, esi
0x180030e55  mov     ecx, ebp
0x180030e57  mov     rax, rbx
0x180030e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e5f  add     rsp, 28h
0x180030e63  pop     rdi
0x180030e64  pop     rsi
0x180030e65  pop     rbp
0x180030e66  pop     rbx
0x180030e67  retn
```
