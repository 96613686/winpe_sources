# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x140009290`
- end: `0x140009308`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: `HMODULE __fastcall(unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x140009290`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400092bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400092bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400092db`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400092db`

## string_xrefs

- `0x1400092b8`: `kernelbase.dll`

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
0x140009290  push    rbx
0x140009292  push    rbp
0x140009293  push    rsi
0x140009294  push    rdi
0x140009295  sub     rsp, 28h
0x140009299  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x1400092a0  mov     dil, r8b
0x1400092a3  mov     esi, edx
0x1400092a5  mov     ebp, ecx
0x1400092a7  test    rbx, rbx
0x1400092aa  jnz     short loc_1400092F0
0x1400092ac  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1400092b3  test    rax, rax
0x1400092b6  jnz     short loc_1400092D1
0x1400092b8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1400092bf  call    cs:__imp_GetModuleHandleW
0x1400092c5  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1400092cc  test    rax, rax
0x1400092cf  jz      short loc_1400092E4
0x1400092d1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x1400092d8  mov     rcx, rax; hModule
0x1400092db  call    cs:__imp_GetProcAddress
0x1400092e1  mov     rbx, rax
0x1400092e4  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x1400092eb  test    rbx, rbx
0x1400092ee  jz      short loc_1400092FF
0x1400092f0  mov     r8b, dil
0x1400092f3  mov     edx, esi
0x1400092f5  mov     ecx, ebp
0x1400092f7  mov     rax, rbx
0x1400092fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400092ff  add     rsp, 28h
0x140009303  pop     rdi
0x140009304  pop     rsi
0x140009305  pop     rbp
0x140009306  pop     rbx
0x140009307  retn
```
