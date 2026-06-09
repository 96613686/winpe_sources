# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000d030`
- end: `0x18000d0a8`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000d030`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000d05f`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000d05f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000d07b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000d07b`

## string_xrefs

- `0x18000d058`: `kernelbase.dll`

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
0x18000d030  push    rbx
0x18000d032  push    rbp
0x18000d033  push    rsi
0x18000d034  push    rdi
0x18000d035  sub     rsp, 28h
0x18000d039  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000d040  mov     dil, r8b
0x18000d043  mov     esi, edx
0x18000d045  mov     ebp, ecx
0x18000d047  test    rbx, rbx
0x18000d04a  jnz     short loc_18000D090
0x18000d04c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000d053  test    rax, rax
0x18000d056  jnz     short loc_18000D071
0x18000d058  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000d05f  call    cs:__imp_GetModuleHandleW
0x18000d065  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000d06c  test    rax, rax
0x18000d06f  jz      short loc_18000D084
0x18000d071  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000d078  mov     rcx, rax; hModule
0x18000d07b  call    cs:__imp_GetProcAddress
0x18000d081  mov     rbx, rax
0x18000d084  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000d08b  test    rbx, rbx
0x18000d08e  jz      short loc_18000D09F
0x18000d090  mov     r8b, dil
0x18000d093  mov     edx, esi
0x18000d095  mov     ecx, ebp
0x18000d097  mov     rax, rbx
0x18000d09a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d09f  add     rsp, 28h
0x18000d0a3  pop     rdi
0x18000d0a4  pop     rsi
0x18000d0a5  pop     rbp
0x18000d0a6  pop     rbx
0x18000d0a7  retn
```
