# std::_Ref_count_obj<__ExceptionPtr>::_Delete_this(void)

- ea: `0x40ca70`
- end: `0x40ca8e`
- name: `?_Delete_this@?$_Ref_count_obj@V__ExceptionPtr@@@std@@EAEXXZ`
- size: `30`
- prototype: `int __thiscall(void *this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x402330`
- `0x40ca70`

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
0x40ca70  push    edi
0x40ca71  mov     edi, ecx
0x40ca73  test    edi, edi
0x40ca75  jz      short loc_40CA8C
0x40ca77  mov     eax, [edi]
0x40ca79  push    esi
0x40ca7a  push    1
0x40ca7c  mov     esi, [eax+8]
0x40ca7f  mov     ecx, esi
0x40ca81  call    ds:___guard_check_icall_fptr
0x40ca87  mov     ecx, edi
0x40ca89  call    esi
0x40ca8b  pop     esi
0x40ca8c  pop     edi
0x40ca8d  retn
```
