# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180009048`
- end: `0x180009099`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005fa0`

## callees

- `0x180009048`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000906a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000906a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009082`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009082`

## string_xrefs

- `0x180009061`: `kernelbase.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetKernelBaseProcAddress(LPCSTR lpProcName)
{
  HMODULE ModuleHandleW; // rax
  __int64 v3; // rbx

  ModuleHandleW = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle )
    return GetProcAddress(ModuleHandleW, lpProcName);
  v3 = 0;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = ModuleHandleW;
  if ( ModuleHandleW )
    return GetProcAddress(ModuleHandleW, lpProcName);
  return (FARPROC)v3;
}

```

## disassembly

```asm
0x180009048  mov     [rsp+arg_0], rbx
0x18000904d  push    rdi
0x18000904e  sub     rsp, 20h
0x180009052  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009059  mov     rdi, rcx
0x18000905c  test    rax, rax
0x18000905f  jnz     short loc_18000907C
0x180009061  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180009068  xor     ebx, ebx
0x18000906a  call    cs:__imp_GetModuleHandleW
0x180009070  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009077  test    rax, rax
0x18000907a  jz      short loc_18000908B
0x18000907c  mov     rdx, rdi; lpProcName
0x18000907f  mov     rcx, rax; hModule
0x180009082  call    cs:__imp_GetProcAddress
0x180009088  mov     rbx, rax
0x18000908b  mov     rax, rbx
0x18000908e  mov     rbx, [rsp+28h+arg_0]
0x180009093  add     rsp, 20h
0x180009097  pop     rdi
0x180009098  retn
```
