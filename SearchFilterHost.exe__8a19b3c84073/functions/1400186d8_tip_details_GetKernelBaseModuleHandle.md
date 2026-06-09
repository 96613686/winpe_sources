# tip_details_GetKernelBaseModuleHandle

- ea: `0x1400186d8`
- end: `0x140018701`
- name: `tip_details_GetKernelBaseModuleHandle`
- size: `41`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400184c0`
- `0x14001850c`
- `0x1400185a0`
- `0x140018610`
- `0x14001865c`

## callees

- `0x1400186d8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400186ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400186ef`

## string_xrefs

- `0x1400186e8`: `kernelbase.dll`

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
0x1400186d8  sub     rsp, 28h
0x1400186dc  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1400186e3  test    rax, rax
0x1400186e6  jnz     short loc_1400186FC
0x1400186e8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1400186ef  call    cs:__imp_GetModuleHandleW
0x1400186f5  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1400186fc  add     rsp, 28h
0x140018700  retn
```
