# CGeodeticRelationScanner::ClassifyTheJunction(void)

- ea: `0x100461040`
- end: `0x100461115`
- name: `?ClassifyTheJunction@CGeodeticRelationScanner@@MEAAXXZ`
- size: `213`
- prototype: `void __fastcall(CGeodeticRelationScanner *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path`

## callees

- `0x100461040`

## pseudocode

```c
void __fastcall CGeodeticRelationScanner::ClassifyTheJunction(CGeodeticRelationScanner *this)
{
  __int64 v1; // rax
  __int64 v3; // r8
  __int64 v4; // rcx

  v1 = *((_QWORD *)this + 38);
  if ( v1 )
  {
    do
    {
      if ( (*(_WORD *)(v1 + 72) & 0x2600) == 0 )
        break;
      v1 = *(_QWORD *)(v1 + 24);
    }
    while ( v1 );
    while ( v1 )
    {
      v3 = *(_WORD *)(v1 + 72) & 1;
      if ( (*(_WORD *)(v1 + 72) & 0x4840) != 0 )
      {
        ++*((_DWORD *)this + v3 + 143);
      }
      else
      {
        if ( (*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 8) + 24LL) + 104LL) & qword_10049A070) != 0 )
        {
          v4 = (unsigned int)(1 - v3);
          if ( *((_DWORD *)this + v4 + 143) )
            *((_BYTE *)this + v4 + 604) = 1;
        }
        *((_BYTE *)this + v3 + 568) = 1;
      }
      v1 = *(_QWORD *)(v1 + 24);
      if ( !v1 )
        break;
      do
      {
        if ( (*(_WORD *)(v1 + 72) & 0x2600) == 0 )
          break;
        v1 = *(_QWORD *)(v1 + 24);
      }
      while ( v1 );
    }
  }
}

```

## disassembly

```asm
0x100461040  sub     rsp, 8
0x100461044  mov     rax, [rcx+130h]
0x10046104b  xor     r11d, r11d
0x10046104e  mov     r9, rcx
0x100461051  mov     r10d, 2600h
0x100461057  test    rax, rax
0x10046105a  jz      loc_100461110
0x100461060  movzx   edx, word ptr [rax+48h]
0x100461064  and     dx, r10w
0x100461068  cmp     r11w, dx
0x10046106c  jz      short loc_100461077
0x10046106e  mov     rax, [rax+18h]
0x100461072  test    rax, rax
0x100461075  jnz     short loc_100461060
0x100461077  test    rax, rax
0x10046107a  jz      loc_100461110
0x100461080  mov     [rsp+8+var_8], rbx
0x100461084  mov     ebx, 4840h
0x100461089  nop     dword ptr [rax+00000000h]
0x100461090  movzx   ecx, word ptr [rax+48h]
0x100461094  mov     r8d, ecx
0x100461097  and     r8d, 1
0x10046109b  test    bx, cx
0x10046109e  jz      short loc_1004610AA
0x1004610a0  inc     dword ptr [r9+r8*4+23Ch]
0x1004610a8  jmp     short loc_1004610E3
0x1004610aa  mov     rcx, [rax+8]
0x1004610ae  mov     rdx, [rcx+18h]
0x1004610b2  mov     rcx, [rdx+68h]
0x1004610b6  test    cs:qword_10049A070, rcx
0x1004610bd  jz      short loc_1004610DA
0x1004610bf  mov     ecx, 1
0x1004610c4  sub     ecx, r8d
0x1004610c7  cmp     [r9+rcx*4+23Ch], r11d
0x1004610cf  jz      short loc_1004610DA
0x1004610d1  mov     byte ptr [rcx+r9+25Ch], 1
0x1004610da  mov     byte ptr [r8+r9+238h], 1
0x1004610e3  mov     rax, [rax+18h]
0x1004610e7  mov     ecx, r8d
0x1004610ea  test    rax, rax
0x1004610ed  jz      short loc_10046110C
0x1004610ef  nop
0x1004610f0  movzx   ecx, word ptr [rax+48h]
0x1004610f4  and     cx, r10w
0x1004610f8  cmp     r11w, cx
0x1004610fc  jz      short loc_100461107
0x1004610fe  mov     rax, [rax+18h]
0x100461102  test    rax, rax
0x100461105  jnz     short loc_1004610F0
0x100461107  test    rax, rax
0x10046110a  jnz     short loc_100461090
0x10046110c  mov     rbx, [rsp+8+var_8]
0x100461110  add     rsp, 8
0x100461114  retn
```
