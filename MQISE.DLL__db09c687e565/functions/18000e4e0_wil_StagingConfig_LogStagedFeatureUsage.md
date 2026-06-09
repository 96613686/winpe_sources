# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000e4e0`
- end: `0x18000e558`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000e4e0`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000e50f`
- `KERNEL32!GetModuleHandleW` at `0x18000e50f`
- `KERNEL32!GetProcAddress` at `0x18000e52b`
- `KERNEL32!GetProcAddress` at `0x18000e52b`

## string_xrefs

- `0x18000e508`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HMODULE __fastcall wil_StagingConfig_LogStagedFeatureUsage(unsigned int a1, unsigned int a2, __int64 a3)
{
  char v3; // di
  __int64 (__fastcall *v6)(_QWORD, _QWORD, _QWORD); // rbx
  HMODULE result; // rax

  v3 = a3;
  v6 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))g_wil_details_pfnLogStagedFeatureUsage;
  if ( g_wil_details_pfnLogStagedFeatureUsage )
    goto LABEL_6;
  result = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle
    || (result = GetModuleHandleW(L"kernelbase.dll"),
        (`wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = result) != 0) )
  {
    result = (HMODULE)GetProcAddress(result, "LogStagedFeatureUsage");
    v6 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))result;
  }
  g_wil_details_pfnLogStagedFeatureUsage = (__int64)v6;
  if ( v6 )
  {
LABEL_6:
    LOBYTE(a3) = v3;
    return (HMODULE)v6(a1, a2, a3);
  }
  return result;
}

```

## disassembly

```asm
0x18000e4e0  push    rbx
0x18000e4e2  push    rbp
0x18000e4e3  push    rsi
0x18000e4e4  push    rdi
0x18000e4e5  sub     rsp, 28h
0x18000e4e9  mov     dil, r8b
0x18000e4ec  mov     esi, edx
0x18000e4ee  mov     ebp, ecx
0x18000e4f0  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000e4f7  test    rbx, rbx
0x18000e4fa  jnz     short loc_18000E540
0x18000e4fc  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000e503  test    rax, rax
0x18000e506  jnz     short loc_18000E521
0x18000e508  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000e50f  call    cs:__imp_GetModuleHandleW
0x18000e515  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000e51c  test    rax, rax
0x18000e51f  jz      short loc_18000E534
0x18000e521  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000e528  mov     rcx, rax; hModule
0x18000e52b  call    cs:__imp_GetProcAddress
0x18000e531  mov     rbx, rax
0x18000e534  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000e53b  test    rbx, rbx
0x18000e53e  jz      short loc_18000E54F
0x18000e540  mov     r8b, dil
0x18000e543  mov     edx, esi
0x18000e545  mov     ecx, ebp
0x18000e547  mov     rax, rbx
0x18000e54a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e54f  add     rsp, 28h
0x18000e553  pop     rdi
0x18000e554  pop     rsi
0x18000e555  pop     rbp
0x18000e556  pop     rbx
0x18000e557  retn
```
