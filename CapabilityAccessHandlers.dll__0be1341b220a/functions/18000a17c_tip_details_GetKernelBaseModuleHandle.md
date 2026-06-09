# tip_details_GetKernelBaseModuleHandle

- ea: `0x18000a17c`
- end: `0x18000a1a5`
- name: `tip_details_GetKernelBaseModuleHandle`
- size: `41`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a068`
- `0x18000a0b4`
- `0x18000a100`
- `0x18000d178`
- `0x18000ed24`

## callees

- `0x18000a17c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a193`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a193`

## string_xrefs

- `0x18000a18c`: `kernelbase.dll`

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
0x18000a17c  sub     rsp, 28h
0x18000a180  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18000a187  test    rax, rax
0x18000a18a  jnz     short loc_18000A1A0
0x18000a18c  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a193  call    cs:__imp_GetModuleHandleW
0x18000a199  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18000a1a0  add     rsp, 28h
0x18000a1a4  retn
```
