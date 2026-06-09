# std::_Ref_count_obj<__ExceptionPtr>::_Delete_this(void)

- ea: `0x40ab90`
- end: `0x40abae`
- name: `?_Delete_this@?$_Ref_count_obj@V__ExceptionPtr@@@std@@EAEXXZ`
- size: `30`
- prototype: `int __thiscall(void *this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x407eb0`
- `0x40ab90`

## pseudocode

```c
int __thiscall std::_Ref_count_obj<__ExceptionPtr>::_Delete_this(void *this)
{
  int result; // eax

  if ( this )
    return (*(int (__thiscall **)(void *, int))(*(_DWORD *)this + 8))(this, 1);
  return result;
}

```

## disassembly

```asm
0x40ab90  push    edi
0x40ab91  mov     edi, ecx
0x40ab93  test    edi, edi
0x40ab95  jz      short loc_40ABAC
0x40ab97  mov     eax, [edi]
0x40ab99  push    esi
0x40ab9a  push    1
0x40ab9c  mov     esi, [eax+8]
0x40ab9f  mov     ecx, esi
0x40aba1  call    ds:___guard_check_icall_fptr
0x40aba7  mov     ecx, edi
0x40aba9  call    esi
0x40abab  pop     esi
0x40abac  pop     edi
0x40abad  retn
```
