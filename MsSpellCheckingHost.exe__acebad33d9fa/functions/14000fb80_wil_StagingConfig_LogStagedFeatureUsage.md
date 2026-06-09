# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x14000fb80`
- end: `0x14000fbf8`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: `HMODULE __fastcall(unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x14000fb80`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000fbaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000fbaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000fbcb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000fbcb`

## string_xrefs

- `0x14000fba8`: `kernelbase.dll`

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
0x14000fb80  push    rbx
0x14000fb82  push    rbp
0x14000fb83  push    rsi
0x14000fb84  push    rdi
0x14000fb85  sub     rsp, 28h
0x14000fb89  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x14000fb90  mov     dil, r8b
0x14000fb93  mov     esi, edx
0x14000fb95  mov     ebp, ecx
0x14000fb97  test    rbx, rbx
0x14000fb9a  jnz     short loc_14000FBE0
0x14000fb9c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000fba3  test    rax, rax
0x14000fba6  jnz     short loc_14000FBC1
0x14000fba8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000fbaf  call    cs:__imp_GetModuleHandleW
0x14000fbb5  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000fbbc  test    rax, rax
0x14000fbbf  jz      short loc_14000FBD4
0x14000fbc1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x14000fbc8  mov     rcx, rax; hModule
0x14000fbcb  call    cs:__imp_GetProcAddress
0x14000fbd1  mov     rbx, rax
0x14000fbd4  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x14000fbdb  test    rbx, rbx
0x14000fbde  jz      short loc_14000FBEF
0x14000fbe0  mov     r8b, dil
0x14000fbe3  mov     edx, esi
0x14000fbe5  mov     ecx, ebp
0x14000fbe7  mov     rax, rbx
0x14000fbea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fbef  add     rsp, 28h
0x14000fbf3  pop     rdi
0x14000fbf4  pop     rsi
0x14000fbf5  pop     rbp
0x14000fbf6  pop     rbx
0x14000fbf7  retn
```
