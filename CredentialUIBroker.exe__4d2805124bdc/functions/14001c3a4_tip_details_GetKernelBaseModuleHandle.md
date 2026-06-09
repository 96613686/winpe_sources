# tip_details_GetKernelBaseModuleHandle

- ea: `0x14001c3a4`
- end: `0x14001c3cd`
- name: `tip_details_GetKernelBaseModuleHandle`
- size: `41`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400190b8`
- `0x14001b938`
- `0x14001c1a4`
- `0x14001c1f0`
- `0x14001c23c`

## callees

- `0x14001c3a4`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14001c3bb`
- `KERNEL32!GetModuleHandleW` at `0x14001c3bb`

## string_xrefs

- `0x14001c3b4`: `kernelbase.dll`

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
0x14001c3a4  sub     rsp, 28h
0x14001c3a8  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x14001c3af  test    rax, rax
0x14001c3b2  jnz     short loc_14001C3C8
0x14001c3b4  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14001c3bb  call    cs:__imp_GetModuleHandleW
0x14001c3c1  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x14001c3c8  add     rsp, 28h
0x14001c3cc  retn
```
