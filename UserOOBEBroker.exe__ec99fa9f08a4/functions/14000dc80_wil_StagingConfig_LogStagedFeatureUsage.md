# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x14000dc80`
- end: `0x14000dcf8`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x14000dc80`
- `0x14000f010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000dccb`
- `KERNEL32!GetProcAddress` at `0x14000dccb`
- `KERNEL32!GetModuleHandleW` at `0x14000dcaf`
- `KERNEL32!GetModuleHandleW` at `0x14000dcaf`

## string_xrefs

- `0x14000dca8`: `kernelbase.dll`

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
0x14000dc80  push    rbx
0x14000dc82  push    rbp
0x14000dc83  push    rsi
0x14000dc84  push    rdi
0x14000dc85  sub     rsp, 28h
0x14000dc89  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x14000dc90  mov     dil, r8b
0x14000dc93  mov     esi, edx
0x14000dc95  mov     ebp, ecx
0x14000dc97  test    rbx, rbx
0x14000dc9a  jnz     short loc_14000DCE0
0x14000dc9c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000dca3  test    rax, rax
0x14000dca6  jnz     short loc_14000DCC1
0x14000dca8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000dcaf  call    cs:__imp_GetModuleHandleW
0x14000dcb5  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000dcbc  test    rax, rax
0x14000dcbf  jz      short loc_14000DCD4
0x14000dcc1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x14000dcc8  mov     rcx, rax; hModule
0x14000dccb  call    cs:__imp_GetProcAddress
0x14000dcd1  mov     rbx, rax
0x14000dcd4  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x14000dcdb  test    rbx, rbx
0x14000dcde  jz      short loc_14000DCEF
0x14000dce0  mov     r8b, dil
0x14000dce3  mov     edx, esi
0x14000dce5  mov     ecx, ebp
0x14000dce7  mov     rax, rbx
0x14000dcea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dcef  add     rsp, 28h
0x14000dcf3  pop     rdi
0x14000dcf4  pop     rsi
0x14000dcf5  pop     rbp
0x14000dcf6  pop     rbx
0x14000dcf7  retn
```
