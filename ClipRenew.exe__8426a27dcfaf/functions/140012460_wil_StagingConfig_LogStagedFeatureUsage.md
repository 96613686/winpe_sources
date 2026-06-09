# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x140012460`
- end: `0x1400124d8`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: `HMODULE __fastcall(unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x140012460`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400124ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400124ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001248f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001248f`

## string_xrefs

- `0x140012488`: `kernelbase.dll`

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
0x140012460  push    rbx
0x140012462  push    rbp
0x140012463  push    rsi
0x140012464  push    rdi
0x140012465  sub     rsp, 28h
0x140012469  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x140012470  mov     dil, r8b
0x140012473  mov     esi, edx
0x140012475  mov     ebp, ecx
0x140012477  test    rbx, rbx
0x14001247a  jnz     short loc_1400124C0
0x14001247c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140012483  test    rax, rax
0x140012486  jnz     short loc_1400124A1
0x140012488  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14001248f  call    cs:__imp_GetModuleHandleW
0x140012495  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14001249c  test    rax, rax
0x14001249f  jz      short loc_1400124B4
0x1400124a1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x1400124a8  mov     rcx, rax; hModule
0x1400124ab  call    cs:__imp_GetProcAddress
0x1400124b1  mov     rbx, rax
0x1400124b4  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x1400124bb  test    rbx, rbx
0x1400124be  jz      short loc_1400124CF
0x1400124c0  mov     r8b, dil
0x1400124c3  mov     edx, esi
0x1400124c5  mov     ecx, ebp
0x1400124c7  mov     rax, rbx
0x1400124ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400124cf  add     rsp, 28h
0x1400124d3  pop     rdi
0x1400124d4  pop     rsi
0x1400124d5  pop     rbp
0x1400124d6  pop     rbx
0x1400124d7  retn
```
