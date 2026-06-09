# tip_details_GetKernelBaseModuleHandle

- ea: `0x18001d36c`
- end: `0x18001d395`
- name: `tip_details_GetKernelBaseModuleHandle`
- size: `41`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180016660`
- `0x1800176d0`
- `0x180019f74`
- `0x18001d050`
- `0x18001d09c`
- `0x18001d0e8`
- `0x18002d810`

## callees

- `0x18001d36c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d383`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d383`

## string_xrefs

- `0x18001d37c`: `kernelbase.dll`

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
0x18001d36c  sub     rsp, 28h
0x18001d370  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18001d377  test    rax, rax
0x18001d37a  jnz     short loc_18001D390
0x18001d37c  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001d383  call    cs:__imp_GetModuleHandleW
0x18001d389  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18001d390  add     rsp, 28h
0x18001d394  retn
```
