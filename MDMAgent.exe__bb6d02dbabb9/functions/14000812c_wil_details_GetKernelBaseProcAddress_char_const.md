# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x14000812c`
- end: `0x14000818a`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140007b30`

## callees

- `0x14000812c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000814e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000814e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000816c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000816c`

## string_xrefs

- `0x140008145`: `kernelbase.dll`

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
0x14000812c  mov     [rsp+arg_0], rbx
0x140008131  push    rdi
0x140008132  sub     rsp, 20h
0x140008136  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000813d  mov     rdi, rcx
0x140008140  test    rax, rax
0x140008143  jnz     short loc_140008166
0x140008145  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000814c  xor     ebx, ebx
0x14000814e  call    cs:__imp_GetModuleHandleW
0x140008155  nop     dword ptr [rax+rax+00h]
0x14000815a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140008161  test    rax, rax
0x140008164  jz      short loc_14000817B
0x140008166  mov     rdx, rdi; lpProcName
0x140008169  mov     rcx, rax; hModule
0x14000816c  call    cs:__imp_GetProcAddress
0x140008173  nop     dword ptr [rax+rax+00h]
0x140008178  mov     rbx, rax
0x14000817b  mov     rax, rbx
0x14000817e  mov     rbx, [rsp+28h+arg_0]
0x140008183  add     rsp, 20h
0x140008187  pop     rdi
0x140008188  retn
```
