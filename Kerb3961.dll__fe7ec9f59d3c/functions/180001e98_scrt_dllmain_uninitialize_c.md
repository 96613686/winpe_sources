# __scrt_dllmain_uninitialize_c

- ea: `0x180001e98`
- end: `0x180001ec8`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001b28`

## callees

- `0x180001e98`
- `0x18000259c`
- `0x180002880`
- `0x1800028a4`
- `0x180007fa0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  Kerb3961::RC4_4757 *v0; // rcx
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = Kerb3961::RC4_4757::GetCipherSessionKeyBitmask(v0);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180001e98  sub     rsp, 28h
0x180001e9c  call    __scrt_is_ucrt_dll_in_use
0x180001ea1  test    eax, eax
0x180001ea3  jz      short loc_180001EB5
0x180001ea5  lea     rcx, Table; Table
0x180001eac  add     rsp, 28h
0x180001eb0  jmp     _execute_onexit_table
0x180001eb5  call    ?GetCipherSessionKeyBitmask@RC4_4757@Kerb3961@@EEAAIXZ; Kerb3961::RC4_4757::GetCipherSessionKeyBitmask(void)
0x180001eba  test    eax, eax
0x180001ebc  jnz     short loc_180001EC3
0x180001ebe  call    _o__cexit_0
0x180001ec3  add     rsp, 28h
0x180001ec7  retn
```
