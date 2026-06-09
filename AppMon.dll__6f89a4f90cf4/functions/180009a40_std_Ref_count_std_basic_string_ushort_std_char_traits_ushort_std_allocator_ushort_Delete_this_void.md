# std::_Ref_count<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>::_Delete_this(void)

- ea: `0x180009a40`
- end: `0x180009a5f`
- name: `?_Delete_this@?$_Ref_count@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@EEAAXXZ`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009a40`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall std::_Ref_count<std::wstring>::_Delete_this(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, 1);
  return result;
}

```

## disassembly

```asm
0x180009a40  sub     rsp, 28h
0x180009a44  test    rcx, rcx
0x180009a47  jz      short loc_180009A5A
0x180009a49  mov     rax, [rcx]
0x180009a4c  mov     edx, 1
0x180009a51  mov     rax, [rax+10h]
0x180009a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a5a  add     rsp, 28h
0x180009a5e  retn
```
