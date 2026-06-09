# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000ac30`
- end: `0x18000aca8`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000ac30`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ac7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ac7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ac5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ac5f`

## string_xrefs

- `0x18000ac58`: `kernelbase.dll`

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
0x18000ac30  push    rbx
0x18000ac32  push    rbp
0x18000ac33  push    rsi
0x18000ac34  push    rdi
0x18000ac35  sub     rsp, 28h
0x18000ac39  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000ac40  mov     dil, r8b
0x18000ac43  mov     esi, edx
0x18000ac45  mov     ebp, ecx
0x18000ac47  test    rbx, rbx
0x18000ac4a  jnz     short loc_18000AC90
0x18000ac4c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000ac53  test    rax, rax
0x18000ac56  jnz     short loc_18000AC71
0x18000ac58  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000ac5f  call    cs:__imp_GetModuleHandleW
0x18000ac65  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000ac6c  test    rax, rax
0x18000ac6f  jz      short loc_18000AC84
0x18000ac71  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000ac78  mov     rcx, rax; hModule
0x18000ac7b  call    cs:__imp_GetProcAddress
0x18000ac81  mov     rbx, rax
0x18000ac84  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000ac8b  test    rbx, rbx
0x18000ac8e  jz      short loc_18000AC9F
0x18000ac90  mov     r8b, dil
0x18000ac93  mov     edx, esi
0x18000ac95  mov     ecx, ebp
0x18000ac97  mov     rax, rbx
0x18000ac9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac9f  add     rsp, 28h
0x18000aca3  pop     rdi
0x18000aca4  pop     rsi
0x18000aca5  pop     rbp
0x18000aca6  pop     rbx
0x18000aca7  retn
```
