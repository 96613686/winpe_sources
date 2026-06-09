# BfpWalkPath

- ea: `0x14001ba10`
- end: `0x14001baee`
- name: `BfpWalkPath`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001b280`

## callees

- `0x14001ba10`

## pseudocode

```c
__int64 __fastcall BfpWalkPath(__int64 a1, unsigned __int16 a2, __int64 a3)
{
  __int64 v4; // r10
  __int64 v5; // r9
  unsigned __int16 v6; // dx
  unsigned __int16 v7; // ax
  __int64 v8; // r8
  __int64 v9; // rax
  unsigned __int16 v10; // dx
  bool v11; // zf
  unsigned __int8 v12; // r9
  __int64 v13; // r10
  __int16 v14; // ax

  if ( *(_WORD *)a3 )
  {
    v8 = *(_QWORD *)(a1 + 8);
    v9 = (*(_QWORD *)(a3 + 8) - v8) >> 1;
    v10 = *(_WORD *)a1 >> 1;
    v11 = (_WORD)v9 == v10;
    if ( (unsigned __int16)v9 >= v10 )
    {
LABEL_8:
      if ( v11 )
      {
        *(_QWORD *)(a3 + 8) = 0;
        *(_WORD *)(a3 + 2) = 0;
        *(_WORD *)a3 = 0;
        return 0;
      }
    }
    else
    {
      while ( *(_WORD *)(v8 + 2LL * (unsigned __int16)v9) != 92 )
      {
        LOWORD(v9) = v9 + 1;
        v11 = (_WORD)v9 == v10;
        if ( (unsigned __int16)v9 >= v10 )
          goto LABEL_8;
      }
    }
    v7 = v9 + 1;
  }
  else
  {
    v4 = *(_QWORD *)(a1 + 8);
    v5 = a2 >> 1;
    v6 = v5 + 1;
    if ( *(_WORD *)(v4 + 2 * v5) != 92 )
      v6 = v5;
    v7 = v6;
    *(_QWORD *)(a3 + 8) = v4 + 2LL * v6;
  }
  v12 = 0;
  v13 = v7;
  while ( v7 < (unsigned __int16)(*(_WORD *)a1 >> 1) )
  {
    if ( *(_WORD *)(*(_QWORD *)(a1 + 8) + 2LL * v7) == 92 )
    {
      v12 = 1;
      break;
    }
    ++v7;
  }
  v14 = 2 * (v7 - v13);
  *(_QWORD *)(a3 + 8) = *(_QWORD *)(a1 + 8) + 2 * v13;
  *(_WORD *)(a3 + 2) = v14;
  *(_WORD *)a3 = v14;
  return v12;
}

```

## disassembly

```asm
0x14001ba10  mov     [rsp+arg_0], rbx
0x14001ba15  cmp     word ptr [r8], 0
0x14001ba1a  mov     rbx, r8
0x14001ba1d  mov     r11, rcx
0x14001ba20  jnz     short loc_14001BA49
0x14001ba22  mov     r10, [rcx+8]
0x14001ba26  shr     dx, 1
0x14001ba29  movzx   r9d, dx
0x14001ba2d  cmp     word ptr [r10+r9*2], 5Ch ; '\'
0x14001ba33  lea     edx, [r9+1]
0x14001ba37  cmovnz  dx, r9w
0x14001ba3c  movzx   eax, dx
0x14001ba3f  lea     rcx, [r10+rax*2]
0x14001ba43  mov     [r8+8], rcx
0x14001ba47  jmp     short loc_14001BA7A
0x14001ba49  mov     r8, [rcx+8]
0x14001ba4d  mov     rax, [rbx+8]
0x14001ba51  movzx   edx, word ptr [rcx]
0x14001ba54  sub     rax, r8
0x14001ba57  sar     rax, 1
0x14001ba5a  shr     dx, 1
0x14001ba5d  cmp     ax, dx
0x14001ba60  jnb     short loc_14001BA75
0x14001ba62  movzx   ecx, ax
0x14001ba65  cmp     word ptr [r8+rcx*2], 5Ch ; '\'
0x14001ba6b  jz      short loc_14001BA77
0x14001ba6d  inc     ax
0x14001ba70  cmp     ax, dx
0x14001ba73  jb      short loc_14001BA62
0x14001ba75  jz      short loc_14001BAD1
0x14001ba77  inc     ax
0x14001ba7a  movzx   r8d, word ptr [r11]
0x14001ba7e  xor     r9b, r9b
0x14001ba81  shr     r8w, 1
0x14001ba85  movzx   r10d, ax
0x14001ba89  nop     dword ptr [rax+00000000h]
0x14001ba90  cmp     ax, r8w
0x14001ba94  jnb     short loc_14001BAAC
0x14001ba96  mov     rcx, [r11+8]
0x14001ba9a  movzx   edx, ax
0x14001ba9d  cmp     word ptr [rcx+rdx*2], 5Ch ; '\'
0x14001baa2  jz      short loc_14001BAA9
0x14001baa4  inc     ax
0x14001baa7  jmp     short loc_14001BA90
0x14001baa9  mov     r9b, 1
0x14001baac  mov     rcx, [r11+8]
0x14001bab0  sub     ax, r10w
0x14001bab4  add     ax, ax
0x14001bab7  lea     rcx, [rcx+r10*2]
0x14001babb  mov     [rbx+8], rcx
0x14001babf  mov     [rbx+2], ax
0x14001bac3  mov     [rbx], ax
0x14001bac6  movzx   eax, r9b
0x14001baca  mov     rbx, [rsp+arg_0]
0x14001bacf  retn
0x14001bad1  xor     eax, eax
0x14001bad3  xor     ecx, ecx
0x14001bad5  mov     [rbx+8], rcx
0x14001bad9  xor     r9b, r9b
0x14001badc  mov     [rbx+2], ax
0x14001bae0  mov     [rbx], ax
0x14001bae3  movzx   eax, r9b
0x14001bae7  mov     rbx, [rsp+arg_0]
0x14001baec  retn
```
