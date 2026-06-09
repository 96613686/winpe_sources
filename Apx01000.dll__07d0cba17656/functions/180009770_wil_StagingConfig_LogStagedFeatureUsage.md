# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180009770`
- end: `0x1800097e8`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180009770`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000979f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000979f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800097bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800097bb`

## string_xrefs

- `0x180009798`: `kernelbase.dll`

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
0x180009770  push    rbx
0x180009772  push    rbp
0x180009773  push    rsi
0x180009774  push    rdi
0x180009775  sub     rsp, 28h
0x180009779  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180009780  mov     dil, r8b
0x180009783  mov     esi, edx
0x180009785  mov     ebp, ecx
0x180009787  test    rbx, rbx
0x18000978a  jnz     short loc_1800097D0
0x18000978c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009793  test    rax, rax
0x180009796  jnz     short loc_1800097B1
0x180009798  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000979f  call    cs:__imp_GetModuleHandleW
0x1800097a5  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800097ac  test    rax, rax
0x1800097af  jz      short loc_1800097C4
0x1800097b1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x1800097b8  mov     rcx, rax; hModule
0x1800097bb  call    cs:__imp_GetProcAddress
0x1800097c1  mov     rbx, rax
0x1800097c4  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x1800097cb  test    rbx, rbx
0x1800097ce  jz      short loc_1800097DF
0x1800097d0  mov     r8b, dil
0x1800097d3  mov     edx, esi
0x1800097d5  mov     ecx, ebp
0x1800097d7  mov     rax, rbx
0x1800097da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097df  add     rsp, 28h
0x1800097e3  pop     rdi
0x1800097e4  pop     rsi
0x1800097e5  pop     rbp
0x1800097e6  pop     rbx
0x1800097e7  retn
```
