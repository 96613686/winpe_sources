# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180008718`
- end: `0x180008769`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800081c8`
- `0x18001db80`

## callees

- `0x180008718`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008752`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008752`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000873a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000873a`

## string_xrefs

- `0x180008731`: `kernelbase.dll`

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
0x180008718  mov     [rsp+arg_0], rbx
0x18000871d  push    rdi
0x18000871e  sub     rsp, 20h
0x180008722  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008729  mov     rdi, rcx
0x18000872c  test    rax, rax
0x18000872f  jnz     short loc_18000874C
0x180008731  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180008738  xor     ebx, ebx
0x18000873a  call    cs:__imp_GetModuleHandleW
0x180008740  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008747  test    rax, rax
0x18000874a  jz      short loc_18000875B
0x18000874c  mov     rdx, rdi; lpProcName
0x18000874f  mov     rcx, rax; hModule
0x180008752  call    cs:__imp_GetProcAddress
0x180008758  mov     rbx, rax
0x18000875b  mov     rax, rbx
0x18000875e  mov     rbx, [rsp+28h+arg_0]
0x180008763  add     rsp, 20h
0x180008767  pop     rdi
0x180008768  retn
```
