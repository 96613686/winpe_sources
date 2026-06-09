# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x14000aa00`
- end: `0x14000aa78`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x14000aa00`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000aa2f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000aa2f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000aa4b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000aa4b`

## string_xrefs

- `0x14000aa28`: `kernelbase.dll`

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
0x14000aa00  push    rbx
0x14000aa02  push    rbp
0x14000aa03  push    rsi
0x14000aa04  push    rdi
0x14000aa05  sub     rsp, 28h
0x14000aa09  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x14000aa10  mov     dil, r8b
0x14000aa13  mov     esi, edx
0x14000aa15  mov     ebp, ecx
0x14000aa17  test    rbx, rbx
0x14000aa1a  jnz     short loc_14000AA60
0x14000aa1c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000aa23  test    rax, rax
0x14000aa26  jnz     short loc_14000AA41
0x14000aa28  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000aa2f  call    cs:__imp_GetModuleHandleW
0x14000aa35  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000aa3c  test    rax, rax
0x14000aa3f  jz      short loc_14000AA54
0x14000aa41  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x14000aa48  mov     rcx, rax; hModule
0x14000aa4b  call    cs:__imp_GetProcAddress
0x14000aa51  mov     rbx, rax
0x14000aa54  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x14000aa5b  test    rbx, rbx
0x14000aa5e  jz      short loc_14000AA6F
0x14000aa60  mov     r8b, dil
0x14000aa63  mov     edx, esi
0x14000aa65  mov     ecx, ebp
0x14000aa67  mov     rax, rbx
0x14000aa6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa6f  add     rsp, 28h
0x14000aa73  pop     rdi
0x14000aa74  pop     rsi
0x14000aa75  pop     rbp
0x14000aa76  pop     rbx
0x14000aa77  retn
```
