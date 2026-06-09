# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180009a20`
- end: `0x180009a98`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180009a20`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009a6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009a6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009a4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009a4f`

## string_xrefs

- `0x180009a48`: `kernelbase.dll`

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
0x180009a20  push    rbx
0x180009a22  push    rbp
0x180009a23  push    rsi
0x180009a24  push    rdi
0x180009a25  sub     rsp, 28h
0x180009a29  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180009a30  mov     dil, r8b
0x180009a33  mov     esi, edx
0x180009a35  mov     ebp, ecx
0x180009a37  test    rbx, rbx
0x180009a3a  jnz     short loc_180009A80
0x180009a3c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009a43  test    rax, rax
0x180009a46  jnz     short loc_180009A61
0x180009a48  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180009a4f  call    cs:__imp_GetModuleHandleW
0x180009a55  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009a5c  test    rax, rax
0x180009a5f  jz      short loc_180009A74
0x180009a61  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180009a68  mov     rcx, rax; hModule
0x180009a6b  call    cs:__imp_GetProcAddress
0x180009a71  mov     rbx, rax
0x180009a74  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x180009a7b  test    rbx, rbx
0x180009a7e  jz      short loc_180009A8F
0x180009a80  mov     r8b, dil
0x180009a83  mov     edx, esi
0x180009a85  mov     ecx, ebp
0x180009a87  mov     rax, rbx
0x180009a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a8f  add     rsp, 28h
0x180009a93  pop     rdi
0x180009a94  pop     rsi
0x180009a95  pop     rbp
0x180009a96  pop     rbx
0x180009a97  retn
```
