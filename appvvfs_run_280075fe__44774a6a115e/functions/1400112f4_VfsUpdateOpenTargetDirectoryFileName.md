# VfsUpdateOpenTargetDirectoryFileName

- ea: `0x1400112f4`
- end: `0x14001139a`
- name: `VfsUpdateOpenTargetDirectoryFileName`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140004d1c`

## callees

- `0x1400112f4`

## pseudocode

```c
unsigned __int16 __fastcall VfsUpdateOpenTargetDirectoryFileName(__int64 a1)
{
  unsigned __int16 v2; // cx
  unsigned __int16 result; // ax
  __int64 v4; // r8
  unsigned __int16 v5; // dx
  unsigned __int16 v6; // dx
  unsigned __int16 v7; // r11
  __int16 v8; // cx
  __int64 v9; // r8

  v2 = *(_WORD *)(a1 + 88);
  result = v2 >> 1;
  if ( v2 >> 1 )
  {
    v4 = *(_QWORD *)(a1 + 96);
    v5 = --result;
    if ( *(_WORD *)(v4 + 2LL * result) == 92 )
    {
      if ( result <= 1u )
        return result;
      v5 = result - 1;
    }
    if ( v5 )
    {
      while ( 1 )
      {
        result = v5;
        if ( *(_WORD *)(v4 + 2LL * v5) == 92 )
          break;
        if ( !--v5 )
          return result;
      }
      v6 = v5 + 1;
      if ( v6 )
      {
        v7 = 0;
        v8 = v2 - 2 * v6;
        result = -2;
        *(_WORD *)(a1 + 88) = v8;
        if ( (v8 & 0xFFFE) != 0 )
        {
          do
          {
            v9 = v7++;
            *(_WORD *)(*(_QWORD *)(a1 + 96) + 2 * v9) = *(_WORD *)(*(_QWORD *)(a1 + 96) + 2 * v9 + 2LL * v6);
            result = *(_WORD *)(a1 + 88) >> 1;
          }
          while ( v7 < result );
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400112f4  mov     r9, rcx
0x1400112f7  movzx   ecx, word ptr [rcx+58h]
0x1400112fb  movzx   eax, cx
0x1400112fe  shr     ax, 1
0x140011301  jz      locret_140011399
0x140011307  mov     r8, [r9+60h]
0x14001130b  dec     ax
0x14001130e  movzx   edx, ax
0x140011311  mov     r11d, 0FFFFh
0x140011317  cmp     word ptr [r8+rdx*2], 5Ch ; '\'
0x14001131d  jnz     short loc_140011328
0x14001131f  cmp     edx, 1
0x140011322  jbe     short locret_140011399
0x140011324  add     dx, r11w
0x140011328  xor     r10d, r10d
0x14001132b  test    dx, dx
0x14001132e  jz      short locret_140011399
0x140011330  movzx   eax, dx
0x140011333  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x140011339  jz      short loc_140011343
0x14001133b  add     dx, r11w
0x14001133f  jnz     short loc_140011330
0x140011341  retn
0x140011343  inc     dx
0x140011346  test    dx, dx
0x140011349  jz      short locret_140011399
0x14001134b  movzx   eax, dx
0x14001134e  mov     r11d, r10d
0x140011351  add     ax, ax
0x140011354  sub     cx, ax
0x140011357  mov     eax, 0FFFEh
0x14001135c  mov     [r9+58h], cx
0x140011361  and     cx, ax
0x140011364  cmp     r10w, cx
0x140011368  jnb     short locret_140011399
0x14001136a  movzx   r10d, dx
0x14001136e  add     r10, r10
0x140011371  mov     rdx, [r9+60h]
0x140011375  movzx   r8d, r11w
0x140011379  inc     r11w
0x14001137d  lea     rax, [rdx+r8*2]
0x140011381  movzx   ecx, word ptr [rax+r10]
0x140011386  mov     [rdx+r8*2], cx
0x14001138b  movzx   eax, word ptr [r9+58h]
0x140011390  shr     ax, 1
0x140011393  cmp     r11w, ax
0x140011397  jb      short loc_140011371
0x140011399  retn
```
