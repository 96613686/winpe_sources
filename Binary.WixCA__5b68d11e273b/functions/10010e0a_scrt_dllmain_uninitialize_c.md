# ___scrt_dllmain_uninitialize_c

- ea: `0x10010e0a`
- end: `0x10010e2d`
- name: `___scrt_dllmain_uninitialize_c`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1001088e`

## callees

- `0x10010e0a`
- `0x10011376`
- `0x100163a4`
- `0x100163c9`
- `0x100169f7`

## pseudocode

```c
void __scrt_dllmain_uninitialize_c()
{
  if ( __scrt_is_ucrt_dll_in_use() )
  {
    _execute_onexit_table(&Table);
  }
  else if ( !sub_100163C9() )
  {
    _cexit();
  }
}

```

## disassembly

```asm
0x10010e0a  call    ___scrt_is_ucrt_dll_in_use
0x10010e0f  test    eax, eax
0x10010e11  jz      short loc_10010E1F
0x10010e13  push    offset Table; Table
0x10010e18  call    __execute_onexit_table
0x10010e1d  pop     ecx
0x10010e1e  retn
0x10010e1f  call    sub_100163C9
0x10010e24  test    eax, eax
0x10010e26  jz      __cexit
0x10010e2c  retn
```
