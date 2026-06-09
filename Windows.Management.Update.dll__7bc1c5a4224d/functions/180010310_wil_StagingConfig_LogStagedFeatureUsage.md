# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180010310`
- end: `0x180010388`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180010310`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001033f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001033f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001035b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001035b`

## string_xrefs

- `0x180010338`: `kernelbase.dll`

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
0x180010310  push    rbx
0x180010312  push    rbp
0x180010313  push    rsi
0x180010314  push    rdi
0x180010315  sub     rsp, 28h
0x180010319  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180010320  mov     dil, r8b
0x180010323  mov     esi, edx
0x180010325  mov     ebp, ecx
0x180010327  test    rbx, rbx
0x18001032a  jnz     short loc_180010370
0x18001032c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180010333  test    rax, rax
0x180010336  jnz     short loc_180010351
0x180010338  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001033f  call    cs:__imp_GetModuleHandleW
0x180010345  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001034c  test    rax, rax
0x18001034f  jz      short loc_180010364
0x180010351  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180010358  mov     rcx, rax; hModule
0x18001035b  call    cs:__imp_GetProcAddress
0x180010361  mov     rbx, rax
0x180010364  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18001036b  test    rbx, rbx
0x18001036e  jz      short loc_18001037F
0x180010370  mov     r8b, dil
0x180010373  mov     edx, esi
0x180010375  mov     ecx, ebp
0x180010377  mov     rax, rbx
0x18001037a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001037f  add     rsp, 28h
0x180010383  pop     rdi
0x180010384  pop     rsi
0x180010385  pop     rbp
0x180010386  pop     rbx
0x180010387  retn
```
