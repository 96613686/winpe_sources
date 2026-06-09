# TransformResourceRecursiveOldCompatible

- ea: `0x180006a60`
- end: `0x180006b8f`
- name: `TransformResourceRecursiveOldCompatible`
- size: `303`
- prototype: `void __fastcall(__int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006858`
- `0x180006a60`

## callees

- `0x180004cc4`
- `0x180006a60`

## pseudocode

```c
void __fastcall TransformResourceRecursiveOldCompatible(__int64 a1, unsigned __int64 a2)
{
  int *v3; // rdi
  unsigned int v4; // eax
  int v5; // eax
  int i; // esi
  __int64 v7; // rdx
  __int64 v8; // rax
  unsigned __int64 v9; // rcx
  unsigned int *v10; // r11
  int NewRvaFromRiftTable; // eax
  _DWORD *v12; // r11
  int v13; // eax
  int v14; // r11d
  int v15; // eax
  int v16; // r11d

  if ( a2 >= *(_QWORD *)(a1 + 40) && a2 < *(_QWORD *)(a1 + 16) )
  {
    v3 = (int *)(a2 + 16);
    if ( a2 + 16 < *(_QWORD *)(a1 + 16) )
    {
      v4 = *(_DWORD *)(a1 + 28) + 16;
      *(_DWORD *)(a1 + 28) = v4;
      if ( v4 <= *(_DWORD *)(a1 + 24) )
      {
        v5 = *(_DWORD *)(a1 + 32);
        if ( *(_DWORD *)(a2 + 4) != v5 )
          *(_DWORD *)(a2 + 4) = v5;
        for ( i = *(unsigned __int16 *)(a2 + 12) + *(unsigned __int16 *)(a2 + 14); i; --i )
        {
          v7 = *(_QWORD *)(a1 + 16);
          if ( (unsigned __int64)v3 >= v7 - 8 )
            break;
          v8 = (unsigned int)v3[1];
          v9 = *(_QWORD *)(a1 + 8);
          if ( (int)v8 >= 0 )
          {
            v10 = (unsigned int *)(v9 + v8);
            if ( v9 + v8 > v9 && (unsigned __int64)v10 < v7 - 16 )
            {
              *(_DWORD *)(a1 + 28) += v10[1];
              if ( *(_DWORD *)(a1 + 28) > *(_DWORD *)(a1 + 24) )
                return;
              NewRvaFromRiftTable = GetNewRvaFromRiftTable(*(int **)a1, *v10);
              if ( *v12 != NewRvaFromRiftTable )
                *v12 = NewRvaFromRiftTable;
            }
          }
          else
          {
            TransformResourceRecursiveOldCompatible(a1, v9 + (v8 & 0x7FFFFFFF));
          }
          v13 = GetNewRvaFromRiftTable(*(int **)a1, (v3[1] & 0x7FFFFFFFu) + *(_DWORD *)(a1 + 48)) - *(_DWORD *)(a1 + 52);
          if ( v14 != v13 )
            v3[1] ^= (v3[1] ^ v13) & 0x7FFFFFFF;
          if ( *v3 < 0 )
          {
            v15 = GetNewRvaFromRiftTable(*(int **)a1, (*v3 & 0x7FFFFFFFu) + *(_DWORD *)(a1 + 48)) - *(_DWORD *)(a1 + 52);
            if ( v16 != v15 )
              *v3 ^= (*v3 ^ v15) & 0x7FFFFFFF;
          }
          *(_DWORD *)(a1 + 28) += 8;
          if ( *(_DWORD *)(a1 + 28) > *(_DWORD *)(a1 + 24) )
            break;
          v3 += 2;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180006a60  push    rbx
0x180006a62  push    rbp
0x180006a63  push    rsi
0x180006a64  push    rdi
0x180006a65  sub     rsp, 28h
0x180006a69  mov     rbx, rcx
0x180006a6c  cmp     rdx, [rcx+28h]
0x180006a70  jb      loc_180006B86
0x180006a76  cmp     rdx, [rcx+10h]
0x180006a7a  jnb     loc_180006B86
0x180006a80  lea     rdi, [rdx+10h]
0x180006a84  cmp     rdi, [rcx+10h]
0x180006a88  jnb     loc_180006B86
0x180006a8e  mov     eax, [rcx+1Ch]
0x180006a91  add     eax, 10h
0x180006a94  mov     [rcx+1Ch], eax
0x180006a97  cmp     eax, [rcx+18h]
0x180006a9a  ja      loc_180006B86
0x180006aa0  mov     eax, [rcx+20h]
0x180006aa3  cmp     [rdx+4], eax
0x180006aa6  jz      short loc_180006AAB
0x180006aa8  mov     [rdx+4], eax
0x180006aab  movzx   esi, word ptr [rdx+0Eh]
0x180006aaf  movzx   eax, word ptr [rdx+0Ch]
0x180006ab3  add     esi, eax
0x180006ab5  jz      loc_180006B86
0x180006abb  mov     ebp, 7FFFFFFFh
0x180006ac0  mov     rdx, [rbx+10h]
0x180006ac4  lea     rax, [rdx-8]
0x180006ac8  cmp     rdi, rax
0x180006acb  jnb     loc_180006B86
0x180006ad1  mov     eax, [rdi+4]
0x180006ad4  mov     rcx, [rbx+8]
0x180006ad8  test    eax, eax
0x180006ada  jns     short loc_180006AED
0x180006adc  and     rax, rbp
0x180006adf  lea     rdx, [rcx+rax]
0x180006ae3  mov     rcx, rbx
0x180006ae6  call    TransformResourceRecursiveOldCompatible
0x180006aeb  jmp     short loc_180006B21
0x180006aed  lea     r11, [rcx+rax]
0x180006af1  cmp     r11, rcx
0x180006af4  jbe     short loc_180006B21
0x180006af6  lea     rax, [rdx-10h]
0x180006afa  cmp     r11, rax
0x180006afd  jnb     short loc_180006B21
0x180006aff  mov     eax, [r11+4]
0x180006b03  add     [rbx+1Ch], eax
0x180006b06  mov     eax, [rbx+1Ch]
0x180006b09  cmp     eax, [rbx+18h]
0x180006b0c  ja      short loc_180006B86
0x180006b0e  mov     edx, [r11]
0x180006b11  mov     rcx, [rbx]
0x180006b14  call    GetNewRvaFromRiftTable
0x180006b19  cmp     [r11], eax
0x180006b1c  jz      short loc_180006B21
0x180006b1e  mov     [r11], eax
0x180006b21  mov     edx, [rbx+30h]
0x180006b24  mov     r11d, [rdi+4]
0x180006b28  mov     rcx, [rbx]
0x180006b2b  and     r11d, ebp
0x180006b2e  add     edx, r11d
0x180006b31  call    GetNewRvaFromRiftTable
0x180006b36  sub     eax, [rbx+34h]
0x180006b39  cmp     r11d, eax
0x180006b3c  jz      short loc_180006B46
0x180006b3e  xor     eax, [rdi+4]
0x180006b41  and     eax, ebp
0x180006b43  xor     [rdi+4], eax
0x180006b46  cmp     dword ptr [rdi], 0
0x180006b49  jge     short loc_180006B6D
0x180006b4b  mov     edx, [rbx+30h]
0x180006b4e  mov     r11d, [rdi]
0x180006b51  mov     rcx, [rbx]
0x180006b54  and     r11d, ebp
0x180006b57  add     edx, r11d
0x180006b5a  call    GetNewRvaFromRiftTable
0x180006b5f  sub     eax, [rbx+34h]
0x180006b62  cmp     r11d, eax
0x180006b65  jz      short loc_180006B6D
0x180006b67  xor     eax, [rdi]
0x180006b69  and     eax, ebp
0x180006b6b  xor     [rdi], eax
0x180006b6d  add     dword ptr [rbx+1Ch], 8
0x180006b71  mov     eax, [rbx+1Ch]
0x180006b74  cmp     eax, [rbx+18h]
0x180006b77  ja      short loc_180006B86
0x180006b79  add     rdi, 8
0x180006b7d  add     esi, 0FFFFFFFFh
0x180006b80  jnz     loc_180006AC0
0x180006b86  add     rsp, 28h
0x180006b8a  pop     rdi
0x180006b8b  pop     rsi
0x180006b8c  pop     rbp
0x180006b8d  pop     rbx
0x180006b8e  retn
```
