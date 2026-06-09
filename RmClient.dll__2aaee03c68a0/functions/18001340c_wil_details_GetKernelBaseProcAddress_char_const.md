# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18001340c`
- end: `0x18001345d`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000fae0`
- `0x180016ca0`

## callees

- `0x18001340c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001342e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001342e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013446`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013446`

## string_xrefs

- `0x180013425`: `kernelbase.dll`

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
0x18001340c  mov     [rsp+arg_0], rbx
0x180013411  push    rdi
0x180013412  sub     rsp, 20h
0x180013416  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001341d  mov     rdi, rcx
0x180013420  test    rax, rax
0x180013423  jnz     short loc_180013440
0x180013425  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001342c  xor     ebx, ebx
0x18001342e  call    cs:__imp_GetModuleHandleW
0x180013434  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001343b  test    rax, rax
0x18001343e  jz      short loc_18001344F
0x180013440  mov     rdx, rdi; lpProcName
0x180013443  mov     rcx, rax; hModule
0x180013446  call    cs:__imp_GetProcAddress
0x18001344c  mov     rbx, rax
0x18001344f  mov     rax, rbx
0x180013452  mov     rbx, [rsp+28h+arg_0]
0x180013457  add     rsp, 20h
0x18001345b  pop     rdi
0x18001345c  retn
```
