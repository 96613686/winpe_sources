# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180012490`
- end: `0x180012508`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180012490`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800124db`
- `KERNEL32!GetProcAddress` at `0x1800124db`
- `KERNEL32!GetModuleHandleW` at `0x1800124bf`
- `KERNEL32!GetModuleHandleW` at `0x1800124bf`

## string_xrefs

- `0x1800124b8`: `kernelbase.dll`

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
0x180012490  push    rbx
0x180012492  push    rbp
0x180012493  push    rsi
0x180012494  push    rdi
0x180012495  sub     rsp, 28h
0x180012499  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x1800124a0  mov     dil, r8b
0x1800124a3  mov     esi, edx
0x1800124a5  mov     ebp, ecx
0x1800124a7  test    rbx, rbx
0x1800124aa  jnz     short loc_1800124F0
0x1800124ac  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800124b3  test    rax, rax
0x1800124b6  jnz     short loc_1800124D1
0x1800124b8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800124bf  call    cs:__imp_GetModuleHandleW
0x1800124c5  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800124cc  test    rax, rax
0x1800124cf  jz      short loc_1800124E4
0x1800124d1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x1800124d8  mov     rcx, rax; hModule
0x1800124db  call    cs:__imp_GetProcAddress
0x1800124e1  mov     rbx, rax
0x1800124e4  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x1800124eb  test    rbx, rbx
0x1800124ee  jz      short loc_1800124FF
0x1800124f0  mov     r8b, dil
0x1800124f3  mov     edx, esi
0x1800124f5  mov     ecx, ebp
0x1800124f7  mov     rax, rbx
0x1800124fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124ff  add     rsp, 28h
0x180012503  pop     rdi
0x180012504  pop     rsi
0x180012505  pop     rbp
0x180012506  pop     rbx
0x180012507  retn
```
