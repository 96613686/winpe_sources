# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180010dc0`
- end: `0x180010e5c`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180010dc0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010e1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010e1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010dfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010dfa`

## string_xrefs

- `0x180010df3`: `kernelbase.dll`

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
0x180010dc0  mov     [rsp+arg_0], rbx
0x180010dc5  mov     [rsp+arg_8], rbp
0x180010dca  mov     [rsp+arg_10], rsi
0x180010dcf  push    rdi
0x180010dd0  sub     rsp, 20h
0x180010dd4  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180010ddb  mov     dil, r8b
0x180010dde  mov     esi, edx
0x180010de0  mov     ebp, ecx
0x180010de2  test    rbx, rbx
0x180010de5  jnz     short loc_180010E37
0x180010de7  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180010dee  test    rax, rax
0x180010df1  jnz     short loc_180010E12
0x180010df3  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180010dfa  call    cs:__imp_GetModuleHandleW
0x180010e01  nop     dword ptr [rax+rax+00h]
0x180010e06  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180010e0d  test    rax, rax
0x180010e10  jz      short loc_180010E2B
0x180010e12  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180010e19  mov     rcx, rax; hModule
0x180010e1c  call    cs:__imp_GetProcAddress
0x180010e23  nop     dword ptr [rax+rax+00h]
0x180010e28  mov     rbx, rax
0x180010e2b  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x180010e32  test    rbx, rbx
0x180010e35  jz      short loc_180010E46
0x180010e37  mov     r8b, dil
0x180010e3a  mov     edx, esi
0x180010e3c  mov     ecx, ebp
0x180010e3e  mov     rax, rbx
0x180010e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e46  mov     rbx, [rsp+28h+arg_0]
0x180010e4b  mov     rbp, [rsp+28h+arg_8]
0x180010e50  mov     rsi, [rsp+28h+arg_10]
0x180010e55  add     rsp, 20h
0x180010e59  pop     rdi
0x180010e5a  retn
```
