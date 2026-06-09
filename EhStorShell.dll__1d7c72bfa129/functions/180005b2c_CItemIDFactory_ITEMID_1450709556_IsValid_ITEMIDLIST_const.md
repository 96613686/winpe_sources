# CItemIDFactory<_ITEMID,1450709556>::_IsValid(_ITEMIDLIST const *)

- ea: `0x180005b2c`
- end: `0x180005b5a`
- name: `?_IsValid@?$CItemIDFactory@U_ITEMID@@$0FGHIBCDE@@@CAPEFBUCHILDITEMID@1@PEFBU_ITEMIDLIST@@@Z`
- size: `46`
- prototype: `unsigned __int16 *__fastcall(unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800048e0`
- `0x180004cd0`
- `0x180005ab8`
- `0x180006890`
- `0x1800094a0`

## callees

- `0x180005b2c`

## pseudocode

```c
unsigned __int16 *__fastcall CItemIDFactory<_ITEMID,1450709556>::_IsValid(unsigned __int16 *a1)
{
  if ( a1 && *a1 >= 0x1Au && *(_DWORD *)(a1 + 3) == 1450709556 && *a1 >= (unsigned __int64)a1[5] + 26 )
    return a1;
  else
    return 0;
}

```

## disassembly

```asm
0x180005b2c  test    rcx, rcx
0x180005b2f  jz      short loc_180005B57
0x180005b31  mov     eax, 1Ah
0x180005b36  cmp     [rcx], ax
0x180005b39  jb      short loc_180005B57
0x180005b3b  cmp     dword ptr [rcx+6], 56781234h
0x180005b42  jnz     short loc_180005B57
0x180005b44  movzx   edx, word ptr [rcx+0Ah]
0x180005b48  add     rdx, rax
0x180005b4b  movzx   eax, word ptr [rcx]
0x180005b4e  cmp     rax, rdx
0x180005b51  jb      short loc_180005B57
0x180005b53  mov     rax, rcx
0x180005b56  retn
0x180005b57  xor     eax, eax
0x180005b59  retn
```
