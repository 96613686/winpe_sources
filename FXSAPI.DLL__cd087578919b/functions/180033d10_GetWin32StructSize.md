# GetWin32StructSize

- ea: `0x180033d10`
- end: `0x180033d3f`
- name: `GetWin32StructSize`
- size: `47`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180010ce0`
- `0x180011640`
- `0x1800118e0`
- `0x180012570`
- `0x1800130f0`
- `0x180014030`
- `0x180024730`
- `0x180024900`

## callees

- `0x180033c2c`

## pseudocode

```c
__int64 __fastcall GetWin32StructSize(_DWORD *a1)
{
  int ShrinkedSize; // eax
  unsigned int v2; // ecx
  unsigned __int64 v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  ShrinkedSize = GetShrinkedSize(a1, &v4);
  v2 = v4;
  if ( !ShrinkedSize )
    return (unsigned int)-1;
  return v2;
}

```

## disassembly

```asm
0x180033d10  sub     rsp, 28h
0x180033d14  lea     rdx, [rsp+28h+arg_8]
0x180033d19  mov     [rsp+28h+arg_8], 0
0x180033d22  call    GetShrinkedSize
0x180033d27  mov     rcx, [rsp+28h+arg_8]
0x180033d2c  test    eax, eax
0x180033d2e  mov     edx, 0FFFFFFFFh
0x180033d33  cmovz   rcx, rdx
0x180033d37  mov     eax, ecx
0x180033d39  add     rsp, 28h
0x180033d3d  retn
```
