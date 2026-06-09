# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x140007768`
- end: `0x1400077b9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140005050`

## callees

- `0x140007768`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400077a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400077a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000778a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000778a`

## string_xrefs

- `0x140007781`: `kernelbase.dll`

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
0x140007768  mov     [rsp+arg_0], rbx
0x14000776d  push    rdi
0x14000776e  sub     rsp, 20h
0x140007772  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140007779  mov     rdi, rcx
0x14000777c  test    rax, rax
0x14000777f  jnz     short loc_14000779C
0x140007781  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140007788  xor     ebx, ebx
0x14000778a  call    cs:__imp_GetModuleHandleW
0x140007790  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140007797  test    rax, rax
0x14000779a  jz      short loc_1400077AB
0x14000779c  mov     rdx, rdi; lpProcName
0x14000779f  mov     rcx, rax; hModule
0x1400077a2  call    cs:__imp_GetProcAddress
0x1400077a8  mov     rbx, rax
0x1400077ab  mov     rax, rbx
0x1400077ae  mov     rbx, [rsp+28h+arg_0]
0x1400077b3  add     rsp, 20h
0x1400077b7  pop     rdi
0x1400077b8  retn
```
