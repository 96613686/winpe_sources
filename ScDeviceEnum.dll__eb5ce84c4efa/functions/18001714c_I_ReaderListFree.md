# I_ReaderListFree

- ea: `0x18001714c`
- end: `0x180017170`
- name: `I_ReaderListFree`
- size: `36`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cb00`
- `0x18001ac5c`
- `0x18001ad14`
- `0x18001ba4c`
- `0x18001c158`

## callees

- `0x18001714c`
- `0x180017178`

## pseudocode

```c
__int64 __fastcall I_ReaderListFree(_QWORD *a1)
{
  _QWORD *v1; // rbx
  __int64 result; // rax

  if ( a1 )
  {
    do
    {
      v1 = (_QWORD *)a1[30];
      result = I_ReaderListFreeItem(a1);
      a1 = v1;
    }
    while ( v1 );
  }
  return result;
}

```

## disassembly

```asm
0x18001714c  test    rcx, rcx
0x18001714f  jz      short locret_18001716F
0x180017151  push    rbx
0x180017152  sub     rsp, 20h
0x180017156  mov     rbx, [rcx+0F0h]
0x18001715d  call    I_ReaderListFreeItem
0x180017162  mov     rcx, rbx
0x180017165  test    rbx, rbx
0x180017168  jnz     short loc_180017156
0x18001716a  add     rsp, 20h
0x18001716e  pop     rbx
0x18001716f  retn
```
