# MsvpAvlGet

- ea: `0x180009c00`
- end: `0x180009c60`
- name: `MsvpAvlGet`
- size: `96`
- prototype: `int *__fastcall(int *, int, unsigned int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180009b50`
- `0x180009c70`
- `0x180009d10`
- `0x180009dc0`
- `0x180009df0`
- `0x180009e70`
- `0x180009f00`

## callees

- `0x180009c00`

## pseudocode

```c
int *__fastcall MsvpAvlGet(int *a1, int a2, unsigned int a3)
{
  int *v3; // r9
  int i; // eax

  v3 = a1;
  if ( a3 >= 4 )
  {
    for ( i = *a1; (int)a3 > 0 && a3 >= (unsigned __int64)HIWORD(i) + 4; i = *v3 )
    {
      if ( (unsigned __int16)i == a2 )
        return v3;
      if ( !(_WORD)i )
        return 0;
      a3 = a3 - HIWORD(i) - 4;
      if ( a3 < 4 )
        return 0;
      v3 = (int *)((char *)v3 + HIWORD(i) + 4);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180009c00  mov     [rsp+arg_0], rbx
0x180009c05  mov     r11d, edx
0x180009c08  mov     r9, rcx
0x180009c0b  cmp     r8d, 4
0x180009c0f  jb      short loc_180009C53
0x180009c11  mov     eax, [rcx]
0x180009c13  jmp     short loc_180009C4E
0x180009c15  mov     ecx, eax
0x180009c17  shr     ecx, 10h
0x180009c1a  movzx   r10d, cx
0x180009c1e  mov     ecx, r8d
0x180009c21  lea     rdx, [r10+4]
0x180009c25  cmp     rcx, rdx
0x180009c28  jb      short loc_180009C53
0x180009c2a  movzx   ecx, ax
0x180009c2d  cmp     ecx, r11d
0x180009c30  jz      short loc_180009C5B
0x180009c32  test    ax, ax
0x180009c35  jz      short loc_180009C53
0x180009c37  sub     r8d, r10d
0x180009c3a  add     r8d, 0FFFFFFFCh
0x180009c3e  cmp     r8d, 4
0x180009c42  jb      short loc_180009C53
0x180009c44  add     r9, 4
0x180009c48  add     r9, r10
0x180009c4b  mov     eax, [r9]
0x180009c4e  test    r8d, r8d
0x180009c51  jg      short loc_180009C15
0x180009c53  xor     eax, eax
0x180009c55  mov     rbx, [rsp+arg_0]
0x180009c5a  retn
0x180009c5b  mov     rax, r9
0x180009c5e  jmp     short loc_180009C55
```
