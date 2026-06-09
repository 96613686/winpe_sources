# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000baa0`
- end: `0x18000bb18`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: `HMODULE __fastcall(unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000baa0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000baeb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000baeb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bacf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bacf`

## string_xrefs

- `0x18000bac8`: `kernelbase.dll`

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
0x18000baa0  push    rbx
0x18000baa2  push    rbp
0x18000baa3  push    rsi
0x18000baa4  push    rdi
0x18000baa5  sub     rsp, 28h
0x18000baa9  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000bab0  mov     dil, r8b
0x18000bab3  mov     esi, edx
0x18000bab5  mov     ebp, ecx
0x18000bab7  test    rbx, rbx
0x18000baba  jnz     short loc_18000BB00
0x18000babc  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000bac3  test    rax, rax
0x18000bac6  jnz     short loc_18000BAE1
0x18000bac8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000bacf  call    cs:__imp_GetModuleHandleW
0x18000bad5  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000badc  test    rax, rax
0x18000badf  jz      short loc_18000BAF4
0x18000bae1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000bae8  mov     rcx, rax; hModule
0x18000baeb  call    cs:__imp_GetProcAddress
0x18000baf1  mov     rbx, rax
0x18000baf4  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000bafb  test    rbx, rbx
0x18000bafe  jz      short loc_18000BB0F
0x18000bb00  mov     r8b, dil
0x18000bb03  mov     edx, esi
0x18000bb05  mov     ecx, ebp
0x18000bb07  mov     rax, rbx
0x18000bb0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb0f  add     rsp, 28h
0x18000bb13  pop     rdi
0x18000bb14  pop     rsi
0x18000bb15  pop     rbp
0x18000bb16  pop     rbx
0x18000bb17  retn
```
