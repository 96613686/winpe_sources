# std::_Ref_count<IPxlatInterfaceMgr>::_Delete_this(void)

- ea: `0x18000c160`
- end: `0x18000c17f`
- name: `?_Delete_this@?$_Ref_count@VIPxlatInterfaceMgr@@@std@@EEAAXXZ`
- size: `31`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c160`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall std::_Ref_count<IPxlatInterfaceMgr>::_Delete_this(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, 1);
  return result;
}

```

## disassembly

```asm
0x18000c160  sub     rsp, 28h
0x18000c164  test    rcx, rcx
0x18000c167  jz      short loc_18000C17A
0x18000c169  mov     rax, [rcx]
0x18000c16c  mov     edx, 1
0x18000c171  mov     rax, [rax+10h]
0x18000c175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c17a  add     rsp, 28h
0x18000c17e  retn
```
