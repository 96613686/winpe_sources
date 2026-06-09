# CspUpdateCursorAfterRedraw

- ea: `0x140021e64`
- end: `0x140021f0b`
- name: `CspUpdateCursorAfterRedraw`
- size: `167`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140021be0`
- `0x140021cf0`
- `0x140021e10`

## callees

- `0x140021e64`

## pseudocode

```c
__int16 __fastcall CspUpdateCursorAfterRedraw(__int64 a1, __int64 a2)
{
  __int64 v2; // r8
  __int16 v3; // cx
  __int16 result; // ax
  __int16 v5; // ax
  __int16 v6; // dx

  v2 = *(_QWORD *)(a1 + 96);
  v3 = *(_WORD *)(v2 + 52);
  if ( *(_WORD *)(a2 + 72) == v3 )
  {
    result = *(_WORD *)(v2 + 54);
    if ( *(_WORD *)(a2 + 74) == result )
      return result;
  }
  v5 = *(_WORD *)(v2 + 68) - *(_WORD *)(v2 + 64) + 1;
  v6 = *(_WORD *)(v2 + 70) - *(_WORD *)(v2 + 66) + 1;
  if ( v3 < *(__int16 *)(v2 + 64) )
  {
    *(_WORD *)(v2 + 68) = v3 + *(_WORD *)(v2 + 68) - *(_WORD *)(v2 + 64);
LABEL_7:
    *(_WORD *)(v2 + 64) = v3;
    *(_BYTE *)(v2 + 44) = 1;
    goto LABEL_8;
  }
  if ( v3 > *(__int16 *)(v2 + 68) )
  {
    *(_WORD *)(v2 + 68) = v3;
    v3 = v3 - v5 + 1;
    goto LABEL_7;
  }
LABEL_8:
  result = *(_WORD *)(v2 + 54);
  if ( result >= *(__int16 *)(v2 + 66) )
  {
    if ( result <= *(__int16 *)(v2 + 70) )
      return result;
    *(_WORD *)(v2 + 70) = result;
    result = result - v6 + 1;
  }
  else
  {
    *(_WORD *)(v2 + 70) = result + v6 - 1;
  }
  *(_WORD *)(v2 + 66) = result;
  *(_BYTE *)(v2 + 44) = 1;
  return result;
}

```

## disassembly

```asm
0x140021e64  mov     r8, [rcx+60h]
0x140021e68  movzx   ecx, word ptr [r8+34h]
0x140021e6d  cmp     [rdx+48h], cx
0x140021e71  jnz     short loc_140021E82
0x140021e73  movzx   eax, word ptr [r8+36h]
0x140021e78  cmp     [rdx+4Ah], ax
0x140021e7c  jz      locret_140021F0A
0x140021e82  movzx   eax, word ptr [r8+44h]
0x140021e87  mov     r10w, 1
0x140021e8c  sub     ax, [r8+40h]
0x140021e91  movzx   edx, word ptr [r8+46h]
0x140021e96  add     ax, r10w
0x140021e9a  sub     dx, [r8+42h]
0x140021e9f  add     dx, r10w
0x140021ea3  cmp     cx, [r8+40h]
0x140021ea8  jge     short loc_140021EB8
0x140021eaa  add     ax, cx
0x140021ead  sub     ax, r10w
0x140021eb1  mov     [r8+44h], ax
0x140021eb6  jmp     short loc_140021ECB
0x140021eb8  cmp     cx, [r8+44h]
0x140021ebd  jle     short loc_140021ED4
0x140021ebf  mov     [r8+44h], cx
0x140021ec4  sub     cx, ax
0x140021ec7  add     cx, r10w
0x140021ecb  mov     [r8+40h], cx
0x140021ed0  mov     [r8+2Ch], r10b
0x140021ed4  movzx   eax, word ptr [r8+36h]
0x140021ed9  cmp     ax, [r8+42h]
0x140021ede  jge     short loc_140021EEE
0x140021ee0  add     dx, ax
0x140021ee3  sub     dx, r10w
0x140021ee7  mov     [r8+46h], dx
0x140021eec  jmp     short loc_140021F01
0x140021eee  cmp     ax, [r8+46h]
0x140021ef3  jle     short locret_140021F0A
0x140021ef5  mov     [r8+46h], ax
0x140021efa  sub     ax, dx
0x140021efd  add     ax, r10w
0x140021f01  mov     [r8+42h], ax
0x140021f06  mov     [r8+2Ch], r10b
0x140021f0a  retn
```
