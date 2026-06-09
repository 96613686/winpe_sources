# EnumOEMRUList

- ea: `0x18000df50`
- end: `0x18000e00a`
- name: `EnumOEMRUList`
- size: `186`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004640`
- `0x18000df50`

## import_xrefs

- `KERNEL32!RtlMoveMemory` at `0x18000dfc4`
- `KERNEL32!RtlMoveMemory` at `0x18000dfc4`

## pseudocode

```c
__int64 __fastcall EnumOEMRUList(__int64 a1, int a2, unsigned __int16 *a3, unsigned int a4)
{
  __int64 v4; // r11
  unsigned int v5; // edi
  __int64 v7; // rcx
  __int64 result; // rax
  bool v9; // zf
  __int64 v10; // rcx
  unsigned int *v11; // rdx
  __int64 v12; // rbx

  LODWORD(v4) = -1;
  v5 = a4;
  if ( !a1 )
    return (unsigned int)v4;
  v7 = *(_QWORD *)(a1 + 24);
  result = -1;
  do
    ++result;
  while ( *(_WORD *)(v7 + 2 * result) );
  if ( a2 >= 0 && a3 )
  {
    if ( a2 < (int)result )
    {
      v9 = (*(_BYTE *)a1 & 1) == 0;
      _mm_lfence();
      v10 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 24) + 2LL * a2);
      if ( v9 )
      {
        v12 = *(_QWORD *)(a1 + 8 * v10 - 744);
        if ( v12 )
        {
          StringCchCopyW(a3, (unsigned __int64)a4 >> 1, *(const unsigned __int16 **)(a1 + 8 * v10 - 744));
          do
            ++v4;
          while ( *(_WORD *)(v12 + 2 * v4) );
        }
      }
      else
      {
        v11 = *(unsigned int **)(a1 + 8 * v10 - 744);
        if ( v11 )
        {
          if ( *v11 < a4 )
            v5 = *v11;
          RtlMoveMemory(a3, v11 + 1, v5);
          LODWORD(v4) = v5;
        }
      }
    }
    return (unsigned int)v4;
  }
  return result;
}

```

## disassembly

```asm
0x18000df50  mov     [rsp+arg_0], rbx
0x18000df55  mov     [rsp+arg_8], rsi
0x18000df5a  push    rdi
0x18000df5b  sub     rsp, 20h
0x18000df5f  or      r11, 0FFFFFFFFFFFFFFFFh
0x18000df63  mov     edi, r9d
0x18000df66  xor     esi, esi
0x18000df68  mov     r9, r8
0x18000df6b  mov     r10, rcx
0x18000df6e  test    rcx, rcx
0x18000df71  jz      loc_18000DFF7
0x18000df77  mov     rcx, [rcx+18h]
0x18000df7b  mov     rax, r11
0x18000df7e  inc     rax
0x18000df81  cmp     [rcx+rax*2], si
0x18000df85  jnz     short loc_18000DF7E
0x18000df87  test    edx, edx
0x18000df89  js      short loc_18000DFFA
0x18000df8b  test    r9, r9
0x18000df8e  jz      short loc_18000DFFA
0x18000df90  cmp     edx, eax
0x18000df92  jge     short loc_18000DFF7
0x18000df94  test    byte ptr [r10], 1
0x18000df98  movsxd  rcx, edx
0x18000df9b  lfence
0x18000df9e  mov     rax, [r10+18h]
0x18000dfa2  movzx   ecx, word ptr [rax+rcx*2]
0x18000dfa6  jz      short loc_18000DFCF
0x18000dfa8  mov     rdx, [r10+rcx*8-2E8h]
0x18000dfb0  test    rdx, rdx
0x18000dfb3  jz      short loc_18000DFF7
0x18000dfb5  cmp     [rdx], edi
0x18000dfb7  mov     rcx, r9
0x18000dfba  cmovb   edi, [rdx]
0x18000dfbd  add     rdx, 4
0x18000dfc1  mov     r8d, edi
0x18000dfc4  call    cs:__imp_RtlMoveMemory
0x18000dfca  mov     r11d, edi
0x18000dfcd  jmp     short loc_18000DFF7
0x18000dfcf  mov     rbx, [r10+rcx*8-2E8h]
0x18000dfd7  test    rbx, rbx
0x18000dfda  jz      short loc_18000DFF7
0x18000dfdc  mov     rdx, rdi
0x18000dfdf  mov     r8, rbx; unsigned __int16 *
0x18000dfe2  shr     rdx, 1; unsigned __int64
0x18000dfe5  mov     rcx, r9; unsigned __int16 *
0x18000dfe8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000dfed  inc     r11
0x18000dff0  cmp     [rbx+r11*2], si
0x18000dff5  jnz     short loc_18000DFED
0x18000dff7  mov     eax, r11d
0x18000dffa  mov     rbx, [rsp+28h+arg_0]
0x18000dfff  mov     rsi, [rsp+28h+arg_8]
0x18000e004  add     rsp, 20h
0x18000e008  pop     rdi
0x18000e009  retn
```
