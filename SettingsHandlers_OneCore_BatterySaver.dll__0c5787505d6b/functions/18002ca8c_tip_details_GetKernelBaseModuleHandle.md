# tip_details_GetKernelBaseModuleHandle

- ea: `0x18002ca8c`
- end: `0x18002cab5`
- name: `tip_details_GetKernelBaseModuleHandle`
- size: `41`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002c8ac`
- `0x18002c8f8`
- `0x18002c968`
- `0x18002c9b4`
- `0x18003a350`

## callees

- `0x18002ca8c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002caa3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002caa3`

## string_xrefs

- `0x18002ca9c`: `kernelbase.dll`

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
0x18002ca8c  sub     rsp, 28h
0x18002ca90  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18002ca97  test    rax, rax
0x18002ca9a  jnz     short loc_18002CAB0
0x18002ca9c  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002caa3  call    cs:__imp_GetModuleHandleW
0x18002caa9  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18002cab0  add     rsp, 28h
0x18002cab4  retn
```
