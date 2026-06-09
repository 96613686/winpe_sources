# tip_details_GetKernelBaseModuleHandle

- ea: `0x1800265a8`
- end: `0x1800265d1`
- name: `tip_details_GetKernelBaseModuleHandle`
- size: `41`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180025af0`
- `0x180026424`
- `0x180026470`
- `0x1800264e0`
- `0x18002652c`

## callees

- `0x1800265a8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800265bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800265bf`

## string_xrefs

- `0x1800265b8`: `kernelbase.dll`

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
0x1800265a8  sub     rsp, 28h
0x1800265ac  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800265b3  test    rax, rax
0x1800265b6  jnz     short loc_1800265CC
0x1800265b8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800265bf  call    cs:__imp_GetModuleHandleW
0x1800265c5  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800265cc  add     rsp, 28h
0x1800265d0  retn
```
