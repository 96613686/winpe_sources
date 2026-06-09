# std::_Ref_count_obj2<CWMABuffer>::_Delete_this(void)

- ea: `0x18006d740`
- end: `0x18006d757`
- name: `?_Delete_this@?$_Ref_count_obj2@VCWMABuffer@@@std@@EEAAXXZ`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18006d740`
- `0x180085010`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_obj2<CWMABuffer>::_Delete_this(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, 1);
  return result;
}

```

## disassembly

```asm
0x18006d740  test    rcx, rcx
0x18006d743  jz      short locret_18006D756
0x18006d745  mov     rax, [rcx]
0x18006d748  mov     edx, 1
0x18006d74d  mov     rax, [rax+10h]
0x18006d751  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18006d756  retn
```
