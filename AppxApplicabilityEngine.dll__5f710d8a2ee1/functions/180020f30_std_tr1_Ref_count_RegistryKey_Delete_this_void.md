# std::tr1::_Ref_count<RegistryKey>::_Delete_this(void)

- ea: `0x180020f30`
- end: `0x180020f4f`
- name: `?_Delete_this@?$_Ref_count@VRegistryKey@@@tr1@std@@EEAAXXZ`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180020f30`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall std::tr1::_Ref_count<RegistryKey>::_Delete_this(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, 1);
  return result;
}

```

## disassembly

```asm
0x180020f30  sub     rsp, 28h
0x180020f34  test    rcx, rcx
0x180020f37  jz      short loc_180020F4A
0x180020f39  mov     rax, [rcx]
0x180020f3c  mov     edx, 1
0x180020f41  mov     rax, [rax+10h]
0x180020f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f4a  add     rsp, 28h
0x180020f4e  retn
```
