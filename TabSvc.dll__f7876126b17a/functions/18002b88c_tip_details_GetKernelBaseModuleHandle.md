# tip_details_GetKernelBaseModuleHandle

- ea: `0x18002b88c`
- end: `0x18002b8b5`
- name: `tip_details_GetKernelBaseModuleHandle`
- size: `41`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800144fc`
- `0x180019314`
- `0x180028f78`
- `0x18002b2bc`
- `0x18002b308`

## callees

- `0x18002b88c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002b8a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002b8a3`

## string_xrefs

- `0x18002b89c`: `kernelbase.dll`

## pseudocode

```c
HMODULE tip_details_GetKernelBaseModuleHandle()
{
  HMODULE result; // rax

  result = (HMODULE)g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    result = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = (__int64)result;
  }
  return result;
}

```

## disassembly

```asm
0x18002b88c  sub     rsp, 28h
0x18002b890  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18002b897  test    rax, rax
0x18002b89a  jnz     short loc_18002B8B0
0x18002b89c  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002b8a3  call    cs:__imp_GetModuleHandleW
0x18002b8a9  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18002b8b0  add     rsp, 28h
0x18002b8b4  retn
```
