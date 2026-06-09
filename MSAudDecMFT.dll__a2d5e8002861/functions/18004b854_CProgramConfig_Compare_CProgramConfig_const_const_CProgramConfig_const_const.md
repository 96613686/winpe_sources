# CProgramConfig_Compare(CProgramConfig const * const,CProgramConfig const * const)

- ea: `0x18004b854`
- end: `0x18004b9c0`
- name: `?CProgramConfig_Compare@@YAHQEBUCProgramConfig@@0@Z`
- size: `364`
- prototype: `__int64 __fastcall(const struct CProgramConfig *const, const struct CProgramConfig *const)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800069ec`
- `0x180010838`
- `0x180012bf8`
- `0x180048018`

## callees

- `0x18004b854`
- `0x180096060`

## pseudocode

```c
__int64 __fastcall CProgramConfig_Compare(const struct CProgramConfig *const a1, const struct CProgramConfig *const a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  int v6; // r10d
  int v7; // r11d
  int v8; // r8d
  int v9; // eax
  int v10; // r10d
  int v11; // r11d
  int i; // r8d
  int v13; // eax
  int v14; // r10d
  int v15; // r11d
  int j; // r8d

  v4 = 0;
  if ( memcmp_0(a1, a2, 0x1D1u) )
  {
    v4 = -1;
    if ( *((_BYTE *)a1 + 462) == *((_BYTE *)a2 + 462) )
    {
      v5 = *((unsigned __int8 *)a1 + 3);
      if ( (_BYTE)v5 == *((_BYTE *)a2 + 3) )
      {
        v6 = 0;
        v7 = 0;
        v8 = 0;
        v4 = 1;
        while ( v8 < v5 )
        {
          if ( *((_BYTE *)a1 + v8 + 48) != *((_BYTE *)a2 + v8 + 48) )
          {
            v4 = 2;
            break;
          }
          v6 += (*((_BYTE *)a1 + v8 + 16) != 0) + 1;
          v7 += (*((_BYTE *)a2 + v8++ + 16) != 0) + 1;
        }
        if ( v6 != v7 )
          v4 = 2;
      }
      else
      {
        v4 = 2;
      }
      v9 = *((unsigned __int8 *)a1 + 4);
      if ( (_BYTE)v9 == *((_BYTE *)a2 + 4) )
      {
        v10 = 0;
        v11 = 0;
        for ( i = 0; i < v9; ++i )
        {
          if ( *((_BYTE *)a1 + i + 96) != *((_BYTE *)a2 + i + 96) )
          {
            v4 = 2;
            break;
          }
          v10 += (*((_BYTE *)a1 + i + 64) != 0) + 1;
          v11 += (*((_BYTE *)a2 + i + 64) != 0) + 1;
        }
        if ( v10 != v11 )
          v4 = 2;
      }
      else
      {
        v4 = 2;
      }
      v13 = *((unsigned __int8 *)a1 + 5);
      if ( (_BYTE)v13 == *((_BYTE *)a2 + 5) )
      {
        v14 = 0;
        v15 = 0;
        for ( j = 0; j < v13; ++j )
        {
          if ( *((_BYTE *)a1 + j + 144) != *((_BYTE *)a2 + j + 144) )
          {
            v4 = 2;
            break;
          }
          v14 += (*((_BYTE *)a1 + j + 112) != 0) + 1;
          v15 += (*((_BYTE *)a2 + j + 112) != 0) + 1;
        }
        if ( v14 != v15 )
          v4 = 2;
      }
      else
      {
        v4 = 2;
      }
      if ( *((_BYTE *)a1 + 6) != *((_BYTE *)a2 + 6) )
        return 2;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18004b854  push    rbx
0x18004b856  push    rbp
0x18004b857  push    rsi
0x18004b858  push    rdi
0x18004b859  sub     rsp, 28h
0x18004b85d  mov     r8d, 1D1h; Size
0x18004b863  mov     rdi, rdx
0x18004b866  mov     rsi, rcx
0x18004b869  xor     ebx, ebx
0x18004b86b  call    memcmp_0
0x18004b870  test    eax, eax
0x18004b872  jz      loc_18004B9B4
0x18004b878  mov     al, [rdi+1CEh]
0x18004b87e  or      ebx, 0FFFFFFFFh
0x18004b881  cmp     [rsi+1CEh], al
0x18004b887  jnz     loc_18004B9B4
0x18004b88d  movzx   eax, byte ptr [rsi+3]
0x18004b891  cmp     al, [rdi+3]
0x18004b894  jz      short loc_18004B89D
0x18004b896  lea     edx, [rbx+3]
0x18004b899  mov     ebx, edx
0x18004b89b  jmp     short loc_18004B8F3
0x18004b89d  xor     r10d, r10d
0x18004b8a0  xor     r11d, r11d
0x18004b8a3  xor     r8d, r8d
0x18004b8a6  mov     ebx, 1
0x18004b8ab  mov     ebp, eax
0x18004b8ad  mov     edx, 2
0x18004b8b2  cmp     r8d, ebp
0x18004b8b5  jge     short loc_18004B8ED
0x18004b8b7  movsxd  r9, r8d
0x18004b8ba  mov     al, [r9+rdi+30h]
0x18004b8bf  cmp     [r9+rsi+30h], al
0x18004b8c4  jnz     short loc_18004B8EB
0x18004b8c6  mov     al, [r9+rsi+10h]
0x18004b8cb  neg     al
0x18004b8cd  mov     al, [r9+rdi+10h]
0x18004b8d2  sbb     ecx, ecx
0x18004b8d4  neg     ecx
0x18004b8d6  inc     ecx
0x18004b8d8  add     r10d, ecx
0x18004b8db  neg     al
0x18004b8dd  sbb     ecx, ecx
0x18004b8df  neg     ecx
0x18004b8e1  inc     ecx
0x18004b8e3  add     r11d, ecx
0x18004b8e6  inc     r8d
0x18004b8e9  jmp     short loc_18004B8AD
0x18004b8eb  mov     ebx, edx
0x18004b8ed  cmp     r10d, r11d
0x18004b8f0  cmovnz  ebx, edx
0x18004b8f3  movzx   eax, byte ptr [rsi+4]
0x18004b8f7  cmp     al, [rdi+4]
0x18004b8fa  jz      short loc_18004B900
0x18004b8fc  mov     ebx, edx
0x18004b8fe  jmp     short loc_18004B94C
0x18004b900  xor     r10d, r10d
0x18004b903  xor     r11d, r11d
0x18004b906  xor     r8d, r8d
0x18004b909  mov     ebp, eax
0x18004b90b  cmp     r8d, ebp
0x18004b90e  jge     short loc_18004B946
0x18004b910  movsxd  r9, r8d
0x18004b913  mov     al, [r9+rdi+60h]
0x18004b918  cmp     [r9+rsi+60h], al
0x18004b91d  jnz     short loc_18004B944
0x18004b91f  mov     al, [r9+rsi+40h]
0x18004b924  neg     al
0x18004b926  mov     al, [r9+rdi+40h]
0x18004b92b  sbb     ecx, ecx
0x18004b92d  neg     ecx
0x18004b92f  inc     ecx
0x18004b931  add     r10d, ecx
0x18004b934  neg     al
0x18004b936  sbb     ecx, ecx
0x18004b938  neg     ecx
0x18004b93a  inc     ecx
0x18004b93c  add     r11d, ecx
0x18004b93f  inc     r8d
0x18004b942  jmp     short loc_18004B90B
0x18004b944  mov     ebx, edx
0x18004b946  cmp     r10d, r11d
0x18004b949  cmovnz  ebx, edx
0x18004b94c  movzx   eax, byte ptr [rsi+5]
0x18004b950  cmp     al, [rdi+5]
0x18004b953  jz      short loc_18004B959
0x18004b955  mov     ebx, edx
0x18004b957  jmp     short loc_18004B9AB
0x18004b959  xor     r10d, r10d
0x18004b95c  xor     r11d, r11d
0x18004b95f  xor     r8d, r8d
0x18004b962  mov     ebp, eax
0x18004b964  cmp     r8d, ebp
0x18004b967  jge     short loc_18004B9A5
0x18004b969  movsxd  r9, r8d
0x18004b96c  mov     al, [r9+rdi+90h]
0x18004b974  cmp     [r9+rsi+90h], al
0x18004b97c  jnz     short loc_18004B9A3
0x18004b97e  mov     al, [r9+rsi+70h]
0x18004b983  neg     al
0x18004b985  mov     al, [r9+rdi+70h]
0x18004b98a  sbb     ecx, ecx
0x18004b98c  neg     ecx
0x18004b98e  inc     ecx
0x18004b990  add     r10d, ecx
0x18004b993  neg     al
0x18004b995  sbb     ecx, ecx
0x18004b997  neg     ecx
0x18004b999  inc     ecx
0x18004b99b  add     r11d, ecx
0x18004b99e  inc     r8d
0x18004b9a1  jmp     short loc_18004B964
0x18004b9a3  mov     ebx, edx
0x18004b9a5  cmp     r10d, r11d
0x18004b9a8  cmovnz  ebx, edx
0x18004b9ab  mov     cl, [rdi+6]
0x18004b9ae  cmp     [rsi+6], cl
0x18004b9b1  cmovnz  ebx, edx
0x18004b9b4  mov     eax, ebx
0x18004b9b6  add     rsp, 28h
0x18004b9ba  pop     rdi
0x18004b9bb  pop     rsi
0x18004b9bc  pop     rbp
0x18004b9bd  pop     rbx
0x18004b9be  retn
```
