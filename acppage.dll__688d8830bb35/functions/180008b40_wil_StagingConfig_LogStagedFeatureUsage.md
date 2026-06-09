# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180008b40`
- end: `0x180008bb8`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180008b40`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180008b6f`
- `KERNEL32!GetModuleHandleW` at `0x180008b6f`
- `KERNEL32!GetProcAddress` at `0x180008b8b`
- `KERNEL32!GetProcAddress` at `0x180008b8b`

## string_xrefs

- `0x180008b68`: `kernelbase.dll`

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
0x180008b40  push    rbx
0x180008b42  push    rbp
0x180008b43  push    rsi
0x180008b44  push    rdi
0x180008b45  sub     rsp, 28h
0x180008b49  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180008b50  mov     dil, r8b
0x180008b53  mov     esi, edx
0x180008b55  mov     ebp, ecx
0x180008b57  test    rbx, rbx
0x180008b5a  jnz     short loc_180008BA0
0x180008b5c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008b63  test    rax, rax
0x180008b66  jnz     short loc_180008B81
0x180008b68  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180008b6f  call    cs:__imp_GetModuleHandleW
0x180008b75  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008b7c  test    rax, rax
0x180008b7f  jz      short loc_180008B94
0x180008b81  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180008b88  mov     rcx, rax; hModule
0x180008b8b  call    cs:__imp_GetProcAddress
0x180008b91  mov     rbx, rax
0x180008b94  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x180008b9b  test    rbx, rbx
0x180008b9e  jz      short loc_180008BAF
0x180008ba0  mov     r8b, dil
0x180008ba3  mov     edx, esi
0x180008ba5  mov     ecx, ebp
0x180008ba7  mov     rax, rbx
0x180008baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008baf  add     rsp, 28h
0x180008bb3  pop     rdi
0x180008bb4  pop     rsi
0x180008bb5  pop     rbp
0x180008bb6  pop     rbx
0x180008bb7  retn
```
