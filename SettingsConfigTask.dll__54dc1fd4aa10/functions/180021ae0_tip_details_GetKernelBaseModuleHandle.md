# tip_details_GetKernelBaseModuleHandle

- ea: `0x180021ae0`
- end: `0x180021b09`
- name: `tip_details_GetKernelBaseModuleHandle`
- size: `41`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001f700`
- `0x1800218c8`
- `0x180021914`
- `0x1800219a8`
- `0x180021a18`
- `0x180021a64`

## callees

- `0x180021ae0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021af7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021af7`

## string_xrefs

- `0x180021af0`: `kernelbase.dll`

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
0x180021ae0  sub     rsp, 28h
0x180021ae4  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180021aeb  test    rax, rax
0x180021aee  jnz     short loc_180021B04
0x180021af0  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180021af7  call    cs:__imp_GetModuleHandleW
0x180021afd  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180021b04  add     rsp, 28h
0x180021b08  retn
```
