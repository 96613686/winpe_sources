# _std::shared_ptr_CConfigSource_::_Resetp_CConfigSource__::_1_::catch$1

- ea: `0x180011a3e`
- end: `0x180011a55`
- name: `_std::shared_ptr_CConfigSource_::_Resetp_CConfigSource__::_1_::catch$1`
- size: `23`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180010e2c`

## pseudocode

```c
void __noreturn std::shared_ptr_CConfigSource_::_Resetp_CConfigSource__::_1_::catch_1()
{
  throw;
}

```

## disassembly

```asm
0x180011a3e  mov     [rsp+arg_8], rdx
0x180011a43  push    rbp
0x180011a44  sub     rsp, 20h
0x180011a48  mov     rbp, rdx
0x180011a4b  xor     edx, edx; pThrowInfo
0x180011a4d  xor     ecx, ecx; pExceptionObject
0x180011a4f  call    _CxxThrowException_0
```
