# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180012e70`
- end: `0x180012ee8`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180012e70`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012ebb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012ebb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012e9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012e9f`

## string_xrefs

- `0x180012e98`: `kernelbase.dll`

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
0x180012e70  push    rbx
0x180012e72  push    rbp
0x180012e73  push    rsi
0x180012e74  push    rdi
0x180012e75  sub     rsp, 28h
0x180012e79  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180012e80  mov     dil, r8b
0x180012e83  mov     esi, edx
0x180012e85  mov     ebp, ecx
0x180012e87  test    rbx, rbx
0x180012e8a  jnz     short loc_180012ED0
0x180012e8c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180012e93  test    rax, rax
0x180012e96  jnz     short loc_180012EB1
0x180012e98  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180012e9f  call    cs:__imp_GetModuleHandleW
0x180012ea5  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180012eac  test    rax, rax
0x180012eaf  jz      short loc_180012EC4
0x180012eb1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180012eb8  mov     rcx, rax; hModule
0x180012ebb  call    cs:__imp_GetProcAddress
0x180012ec1  mov     rbx, rax
0x180012ec4  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x180012ecb  test    rbx, rbx
0x180012ece  jz      short loc_180012EDF
0x180012ed0  mov     r8b, dil
0x180012ed3  mov     edx, esi
0x180012ed5  mov     ecx, ebp
0x180012ed7  mov     rax, rbx
0x180012eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012edf  add     rsp, 28h
0x180012ee3  pop     rdi
0x180012ee4  pop     rsi
0x180012ee5  pop     rbp
0x180012ee6  pop     rbx
0x180012ee7  retn
```
