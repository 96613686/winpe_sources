# std::_Ref_count<XinputHid::XInputHidDevice>::_Delete_this(void)

- ea: `0x180010e50`
- end: `0x180010e6f`
- name: `?_Delete_this@?$_Ref_count@UXInputHidDevice@XinputHid@@@std@@EEAAXXZ`
- size: `31`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180010e50`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall std::_Ref_count<XinputHid::XInputHidDevice>::_Delete_this(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, 1);
  return result;
}

```

## disassembly

```asm
0x180010e50  sub     rsp, 28h
0x180010e54  test    rcx, rcx
0x180010e57  jz      short loc_180010E6A
0x180010e59  mov     rax, [rcx]
0x180010e5c  mov     edx, 1
0x180010e61  mov     rax, [rax+10h]
0x180010e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e6a  add     rsp, 28h
0x180010e6e  retn
```
