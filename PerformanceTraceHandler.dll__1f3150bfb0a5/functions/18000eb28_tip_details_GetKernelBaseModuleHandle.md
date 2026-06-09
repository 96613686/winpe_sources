# tip_details_GetKernelBaseModuleHandle

- ea: `0x18000eb28`
- end: `0x18000eb51`
- name: `tip_details_GetKernelBaseModuleHandle`
- size: `41`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d0fc`
- `0x18000ea90`
- `0x18000eadc`
- `0x180012ec0`
- `0x180013540`

## callees

- `0x18000eb28`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000eb3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000eb3f`

## string_xrefs

- `0x18000eb38`: `kernelbase.dll`

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
0x18000eb28  sub     rsp, 28h
0x18000eb2c  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18000eb33  test    rax, rax
0x18000eb36  jnz     short loc_18000EB4C
0x18000eb38  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000eb3f  call    cs:__imp_GetModuleHandleW
0x18000eb45  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18000eb4c  add     rsp, 28h
0x18000eb50  retn
```
