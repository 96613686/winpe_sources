# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x14000ae40`
- end: `0x14000aeb8`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: `HMODULE __fastcall(unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x14000ae40`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000ae8b`
- `KERNEL32!GetProcAddress` at `0x14000ae8b`
- `KERNEL32!GetModuleHandleW` at `0x14000ae6f`
- `KERNEL32!GetModuleHandleW` at `0x14000ae6f`

## string_xrefs

- `0x14000ae68`: `kernelbase.dll`

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
0x14000ae40  push    rbx
0x14000ae42  push    rbp
0x14000ae43  push    rsi
0x14000ae44  push    rdi
0x14000ae45  sub     rsp, 28h
0x14000ae49  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x14000ae50  mov     dil, r8b
0x14000ae53  mov     esi, edx
0x14000ae55  mov     ebp, ecx
0x14000ae57  test    rbx, rbx
0x14000ae5a  jnz     short loc_14000AEA0
0x14000ae5c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000ae63  test    rax, rax
0x14000ae66  jnz     short loc_14000AE81
0x14000ae68  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000ae6f  call    cs:__imp_GetModuleHandleW
0x14000ae75  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000ae7c  test    rax, rax
0x14000ae7f  jz      short loc_14000AE94
0x14000ae81  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x14000ae88  mov     rcx, rax; hModule
0x14000ae8b  call    cs:__imp_GetProcAddress
0x14000ae91  mov     rbx, rax
0x14000ae94  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x14000ae9b  test    rbx, rbx
0x14000ae9e  jz      short loc_14000AEAF
0x14000aea0  mov     r8b, dil
0x14000aea3  mov     edx, esi
0x14000aea5  mov     ecx, ebp
0x14000aea7  mov     rax, rbx
0x14000aeaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aeaf  add     rsp, 28h
0x14000aeb3  pop     rdi
0x14000aeb4  pop     rsi
0x14000aeb5  pop     rbp
0x14000aeb6  pop     rbx
0x14000aeb7  retn
```
