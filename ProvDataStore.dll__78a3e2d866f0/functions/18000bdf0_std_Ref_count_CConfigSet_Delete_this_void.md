# std::_Ref_count<CConfigSet>::_Delete_this(void)

- ea: `0x18000bdf0`
- end: `0x18000be0f`
- name: `?_Delete_this@?$_Ref_count@VCConfigSet@@@std@@EEAAXXZ`
- size: `31`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000bdf0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall std::_Ref_count<CConfigSet>::_Delete_this(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, 1);
  return result;
}

```

## disassembly

```asm
0x18000bdf0  sub     rsp, 28h
0x18000bdf4  test    rcx, rcx
0x18000bdf7  jz      short loc_18000BE0A
0x18000bdf9  mov     rax, [rcx]
0x18000bdfc  mov     edx, 1
0x18000be01  mov     rax, [rax+10h]
0x18000be05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be0a  add     rsp, 28h
0x18000be0e  retn
```
