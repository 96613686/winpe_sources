# avpriv_split_xiph_headers

- ea: `0x180022580`
- end: `0x18002269e`
- name: `avpriv_split_xiph_headers`
- size: `286`
- prototype: `__int64 __fastcall(_WORD *, int, int, _QWORD *, int *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800153f0`
- `0x1800158e0`
- `0x18001c530`

## callees

- `0x180022580`

## pseudocode

```c
__int64 __fastcall avpriv_split_xiph_headers(_WORD *a1, int a2, int a3, _QWORD *a4, int *a5)
{
  int *v5; // r11
  int v6; // ebx
  _WORD *v7; // r10
  int v8; // ecx
  _BYTE *v9; // r10
  int v10; // r8d
  __int64 v11; // rcx
  _DWORD *v12; // rbx
  int v13; // esi
  int v14; // edi

  v5 = a5;
  v6 = 6;
  v7 = a1;
  if ( a2 >= 6 && (unsigned __int16)__ROR2__(*a1, 8) == a3 )
  {
    v8 = 0;
    while ( 1 )
    {
      *v5 = (unsigned __int16)__ROR2__(*v7, 8);
      *a4 = v7 + 1;
      v7 = (_WORD *)((char *)v7 + *v5 + 2);
      if ( v6 > a2 - *v5 )
        break;
      v6 += *v5;
      ++v8;
      ++v5;
      ++a4;
      if ( v8 >= 3 )
        return 0;
    }
    return 3199971767LL;
  }
  if ( (unsigned int)(a2 - 3) <= 0x7FFFFDFC && *(_BYTE *)a1 == 2 )
  {
    v9 = (char *)a1 + 1;
    v10 = 3;
    v11 = 0;
    v12 = a5;
    v13 = 0;
    while ( 1 )
    {
      v14 = 0;
      *v12 = 0;
      while ( v10 < a2 && *v9 == 0xFF )
      {
        v14 += 255;
        v10 += 256;
        *v12 = v14;
        ++v9;
      }
      *v12 = v14 + (unsigned __int8)*v9;
      v10 += (unsigned __int8)*v9;
      if ( v10 > a2 )
        break;
      ++v13;
      ++v12;
      ++v9;
      if ( v13 >= 2 )
      {
        a5[2] = a2 - v10;
        *a4 = v9;
        do
        {
          a4[v11 + 1] = a4[v11] + a5[v11];
          ++v11;
        }
        while ( v11 < 2 );
        return 0;
      }
    }
    return 3199971767LL;
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180022580  mov     [rsp+arg_0], rbx
0x180022585  mov     [rsp+arg_8], rsi
0x18002258a  mov     [rsp+arg_10], rdi
0x18002258f  mov     r11, [rsp+arg_20]
0x180022594  mov     ebx, 6
0x180022599  mov     r10, rcx
0x18002259c  cmp     edx, ebx
0x18002259e  jl      short loc_1800225F4
0x1800225a0  movzx   eax, word ptr [rcx]
0x1800225a3  ror     ax, 8
0x1800225a7  movzx   eax, ax
0x1800225aa  cmp     eax, r8d
0x1800225ad  jnz     short loc_1800225F4
0x1800225af  xor     ecx, ecx
0x1800225b1  lea     r8d, [rbx-3]
0x1800225b5  movzx   eax, word ptr [r10]
0x1800225b9  ror     ax, 8
0x1800225bd  movzx   eax, ax
0x1800225c0  mov     [r11], eax
0x1800225c3  lea     rax, [r10+2]
0x1800225c7  mov     [r9], rax
0x1800225ca  movsxd  r10, dword ptr [r11]
0x1800225cd  add     r10, rax
0x1800225d0  mov     eax, edx
0x1800225d2  sub     eax, [r11]
0x1800225d5  cmp     ebx, eax
0x1800225d7  jg      loc_180022684
0x1800225dd  add     ebx, [r11]
0x1800225e0  inc     ecx
0x1800225e2  add     r11, 4
0x1800225e6  add     r9, 8
0x1800225ea  cmp     ecx, r8d
0x1800225ed  jl      short loc_1800225B5
0x1800225ef  jmp     loc_180022680
0x1800225f4  lea     eax, [rdx-3]
0x1800225f7  cmp     eax, 7FFFFDFCh
0x1800225fc  ja      loc_18002268B
0x180022602  cmp     byte ptr [rcx], 2
0x180022605  jnz     loc_18002268B
0x18002260b  inc     r10
0x18002260e  mov     r8d, 3
0x180022614  xor     ecx, ecx
0x180022616  mov     rbx, r11
0x180022619  mov     esi, ecx
0x18002261b  mov     edi, ecx
0x18002261d  mov     [rbx], ecx
0x18002261f  jmp     short loc_180022639
0x180022621  cmp     byte ptr [r10], 0FFh
0x180022625  jnz     short loc_18002263E
0x180022627  add     edi, 0FFh
0x18002262d  add     r8d, 100h
0x180022634  mov     [rbx], edi
0x180022636  inc     r10
0x180022639  cmp     r8d, edx
0x18002263c  jl      short loc_180022621
0x18002263e  movzx   eax, byte ptr [r10]
0x180022642  add     eax, edi
0x180022644  mov     [rbx], eax
0x180022646  movzx   eax, byte ptr [r10]
0x18002264a  add     r8d, eax
0x18002264d  cmp     r8d, edx
0x180022650  jg      short loc_180022684
0x180022652  inc     esi
0x180022654  add     rbx, 4
0x180022658  inc     r10
0x18002265b  cmp     esi, 2
0x18002265e  jl      short loc_18002261B
0x180022660  sub     edx, r8d
0x180022663  mov     [r11+8], edx
0x180022667  mov     [r9], r10
0x18002266a  movsxd  rax, dword ptr [r11+rcx*4]
0x18002266e  add     rax, [r9+rcx*8]
0x180022672  mov     [r9+rcx*8+8], rax
0x180022677  inc     rcx
0x18002267a  cmp     rcx, 2
0x18002267e  jl      short loc_18002266A
0x180022680  xor     eax, eax
0x180022682  jmp     short loc_18002268E
0x180022684  mov     eax, 0BEBBB1B7h
0x180022689  jmp     short loc_18002268E
0x18002268b  or      eax, 0FFFFFFFFh
0x18002268e  mov     rbx, [rsp+arg_0]
0x180022693  mov     rsi, [rsp+arg_8]
0x180022698  mov     rdi, [rsp+arg_10]
0x18002269d  retn
```
