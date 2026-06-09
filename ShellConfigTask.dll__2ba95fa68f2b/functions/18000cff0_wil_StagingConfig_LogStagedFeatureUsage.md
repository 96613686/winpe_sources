# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000cff0`
- end: `0x18000d068`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000cff0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d01f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d01f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d03b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d03b`

## string_xrefs

- `0x18000d018`: `kernelbase.dll`

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
0x18000cff0  push    rbx
0x18000cff2  push    rbp
0x18000cff3  push    rsi
0x18000cff4  push    rdi
0x18000cff5  sub     rsp, 28h
0x18000cff9  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000d000  mov     dil, r8b
0x18000d003  mov     esi, edx
0x18000d005  mov     ebp, ecx
0x18000d007  test    rbx, rbx
0x18000d00a  jnz     short loc_18000D050
0x18000d00c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000d013  test    rax, rax
0x18000d016  jnz     short loc_18000D031
0x18000d018  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000d01f  call    cs:__imp_GetModuleHandleW
0x18000d025  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000d02c  test    rax, rax
0x18000d02f  jz      short loc_18000D044
0x18000d031  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000d038  mov     rcx, rax; hModule
0x18000d03b  call    cs:__imp_GetProcAddress
0x18000d041  mov     rbx, rax
0x18000d044  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000d04b  test    rbx, rbx
0x18000d04e  jz      short loc_18000D05F
0x18000d050  mov     r8b, dil
0x18000d053  mov     edx, esi
0x18000d055  mov     ecx, ebp
0x18000d057  mov     rax, rbx
0x18000d05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d05f  add     rsp, 28h
0x18000d063  pop     rdi
0x18000d064  pop     rsi
0x18000d065  pop     rbp
0x18000d066  pop     rbx
0x18000d067  retn
```
