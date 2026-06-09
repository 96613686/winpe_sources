# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180015f70`
- end: `0x180015fe8`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180015f70`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015f9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015f9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015fbb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015fbb`

## string_xrefs

- `0x180015f98`: `kernelbase.dll`

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
0x180015f70  push    rbx
0x180015f72  push    rbp
0x180015f73  push    rsi
0x180015f74  push    rdi
0x180015f75  sub     rsp, 28h
0x180015f79  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180015f80  mov     dil, r8b
0x180015f83  mov     esi, edx
0x180015f85  mov     ebp, ecx
0x180015f87  test    rbx, rbx
0x180015f8a  jnz     short loc_180015FD0
0x180015f8c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180015f93  test    rax, rax
0x180015f96  jnz     short loc_180015FB1
0x180015f98  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180015f9f  call    cs:__imp_GetModuleHandleW
0x180015fa5  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180015fac  test    rax, rax
0x180015faf  jz      short loc_180015FC4
0x180015fb1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180015fb8  mov     rcx, rax; hModule
0x180015fbb  call    cs:__imp_GetProcAddress
0x180015fc1  mov     rbx, rax
0x180015fc4  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x180015fcb  test    rbx, rbx
0x180015fce  jz      short loc_180015FDF
0x180015fd0  mov     r8b, dil
0x180015fd3  mov     edx, esi
0x180015fd5  mov     ecx, ebp
0x180015fd7  mov     rax, rbx
0x180015fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fdf  add     rsp, 28h
0x180015fe3  pop     rdi
0x180015fe4  pop     rsi
0x180015fe5  pop     rbp
0x180015fe6  pop     rbx
0x180015fe7  retn
```
