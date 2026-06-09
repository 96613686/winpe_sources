# tip_details_GetKernelBaseModuleHandle

- ea: `0x18001bc7c`
- end: `0x18001bca5`
- name: `tip_details_GetKernelBaseModuleHandle`
- size: `41`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001b2b8`
- `0x18001ba9c`
- `0x18001bae8`
- `0x18001bb58`
- `0x18001bba4`

## callees

- `0x18001bc7c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bc93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bc93`

## string_xrefs

- `0x18001bc8c`: `kernelbase.dll`

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
0x18001bc7c  sub     rsp, 28h
0x18001bc80  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18001bc87  test    rax, rax
0x18001bc8a  jnz     short loc_18001BCA0
0x18001bc8c  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001bc93  call    cs:__imp_GetModuleHandleW
0x18001bc99  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18001bca0  add     rsp, 28h
0x18001bca4  retn
```
