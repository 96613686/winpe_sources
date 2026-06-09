# std::_Ref_count_obj2<Settings>::_Delete_this(void)

- ea: `0x18000fa50`
- end: `0x18000fa6f`
- name: `?_Delete_this@?$_Ref_count_obj2@VSettings@@@std@@EEAAXXZ`
- size: `31`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000fa50`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_obj2<Settings>::_Delete_this(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, 1);
  return result;
}

```

## disassembly

```asm
0x18000fa50  sub     rsp, 28h
0x18000fa54  test    rcx, rcx
0x18000fa57  jz      short loc_18000FA6A
0x18000fa59  mov     rax, [rcx]
0x18000fa5c  mov     edx, 1
0x18000fa61  mov     rax, [rax+10h]
0x18000fa65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa6a  add     rsp, 28h
0x18000fa6e  retn
```
