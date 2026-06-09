# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000e870`
- end: `0x18000e8e8`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: `HMODULE __fastcall(unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000e870`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e8bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e8bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e89f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e89f`

## string_xrefs

- `0x18000e898`: `kernelbase.dll`

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
0x18000e870  push    rbx
0x18000e872  push    rbp
0x18000e873  push    rsi
0x18000e874  push    rdi
0x18000e875  sub     rsp, 28h
0x18000e879  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000e880  mov     dil, r8b
0x18000e883  mov     esi, edx
0x18000e885  mov     ebp, ecx
0x18000e887  test    rbx, rbx
0x18000e88a  jnz     short loc_18000E8D0
0x18000e88c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000e893  test    rax, rax
0x18000e896  jnz     short loc_18000E8B1
0x18000e898  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000e89f  call    cs:__imp_GetModuleHandleW
0x18000e8a5  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000e8ac  test    rax, rax
0x18000e8af  jz      short loc_18000E8C4
0x18000e8b1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000e8b8  mov     rcx, rax; hModule
0x18000e8bb  call    cs:__imp_GetProcAddress
0x18000e8c1  mov     rbx, rax
0x18000e8c4  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000e8cb  test    rbx, rbx
0x18000e8ce  jz      short loc_18000E8DF
0x18000e8d0  mov     r8b, dil
0x18000e8d3  mov     edx, esi
0x18000e8d5  mov     ecx, ebp
0x18000e8d7  mov     rax, rbx
0x18000e8da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8df  add     rsp, 28h
0x18000e8e3  pop     rdi
0x18000e8e4  pop     rsi
0x18000e8e5  pop     rbp
0x18000e8e6  pop     rbx
0x18000e8e7  retn
```
