# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18003cd70`
- end: `0x18003cde8`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18003cd70`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003cd9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003cd9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003cdbb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003cdbb`

## string_xrefs

- `0x18003cd98`: `kernelbase.dll`

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
0x18003cd70  push    rbx
0x18003cd72  push    rbp
0x18003cd73  push    rsi
0x18003cd74  push    rdi
0x18003cd75  sub     rsp, 28h
0x18003cd79  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18003cd80  mov     dil, r8b
0x18003cd83  mov     esi, edx
0x18003cd85  mov     ebp, ecx
0x18003cd87  test    rbx, rbx
0x18003cd8a  jnz     short loc_18003CDD0
0x18003cd8c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18003cd93  test    rax, rax
0x18003cd96  jnz     short loc_18003CDB1
0x18003cd98  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18003cd9f  call    cs:__imp_GetModuleHandleW
0x18003cda5  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18003cdac  test    rax, rax
0x18003cdaf  jz      short loc_18003CDC4
0x18003cdb1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18003cdb8  mov     rcx, rax; hModule
0x18003cdbb  call    cs:__imp_GetProcAddress
0x18003cdc1  mov     rbx, rax
0x18003cdc4  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18003cdcb  test    rbx, rbx
0x18003cdce  jz      short loc_18003CDDF
0x18003cdd0  mov     r8b, dil
0x18003cdd3  mov     edx, esi
0x18003cdd5  mov     ecx, ebp
0x18003cdd7  mov     rax, rbx
0x18003cdda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cddf  add     rsp, 28h
0x18003cde3  pop     rdi
0x18003cde4  pop     rsi
0x18003cde5  pop     rbp
0x18003cde6  pop     rbx
0x18003cde7  retn
```
