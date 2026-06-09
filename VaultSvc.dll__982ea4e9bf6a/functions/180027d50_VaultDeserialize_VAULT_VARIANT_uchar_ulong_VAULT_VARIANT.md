# VaultDeserialize<_VAULT_VARIANT>(uchar * &,ulong &,_VAULT_VARIANT &)

- ea: `0x180027d50`
- end: `0x180028068`
- name: `??$VaultDeserialize@U_VAULT_VARIANT@@@@YAKAEAPEAEAEAKAEAU_VAULT_VARIANT@@@Z`
- size: `792`
- prototype: `__int64 __fastcall(_QWORD *, int *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001aa28`
- `0x18001cc1c`

## callees

- `0x180027d50`
- `0x18002f340`
- `0x18004b43c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027dd9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027e8f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027dd9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027e8f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180027e6a`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180027e6a`

## pseudocode

```c
__int64 __fastcall VaultDeserialize<_VAULT_VARIANT>(_QWORD *a1, int *a2, __int64 a3)
{
  _DWORD *v3; // r9
  _QWORD *v6; // rdx
  int v7; // r14d
  int v8; // eax
  _WORD *v9; // rbp
  unsigned int v10; // r13d
  unsigned int v11; // eax
  HLOCAL v12; // rax
  unsigned int v13; // r15d
  SIZE_T v14; // rsi
  char *v15; // rbp
  unsigned int i; // ebx
  HLOCAL v17; // rax
  unsigned int v18; // r14d
  unsigned int v20; // eax
  unsigned int Source2; // [rsp+78h] [rbp+10h] BYREF
  __int64 v23; // [rsp+80h] [rbp+18h]
  _DWORD *v24; // [rsp+88h] [rbp+20h] BYREF

  v23 = a3;
  v3 = (_DWORD *)*a1;
  v6 = a1;
  v7 = *a2;
  if ( (unsigned int)*a2 < 4 )
    return 122;
  v8 = *v3;
  v9 = v3 + 1;
  *(_DWORD *)a3 = *v3;
  v10 = v7 - 4;
  v24 = v3 + 1;
  Source2 = v7 - 4;
  if ( v8 == 7 )
  {
    v13 = 0;
    LOWORD(Source2) = 0;
    if ( v10 < 4 )
    {
      v13 = 122;
    }
    else
    {
      v14 = *(unsigned int *)v9;
      v10 = v7 - 8;
      v15 = (char *)(v3 + 2);
      if ( (unsigned int)v14 < 2 )
      {
        *(_QWORD *)(a3 + 8) = 0;
      }
      else if ( (unsigned int)v14 > v7 - 8 )
      {
        v13 = 122;
      }
      else if ( (v14 & 1) != 0 )
      {
LABEL_25:
        v13 = 1358;
      }
      else
      {
        for ( i = 0; ; i += 2 )
        {
          if ( i >= (unsigned int)v14 )
            goto LABEL_24;
          if ( RtlCompareMemory(&v15[i], &Source2, 2u) == 2 )
            break;
        }
        if ( i != v14 - 2 )
        {
LABEL_24:
          v6 = a1;
          goto LABEL_25;
        }
        v17 = LocalAlloc(0x40u, v14);
        *(_QWORD *)(v23 + 8) = v17;
        if ( v17 )
        {
          memcpy_0(v17, v15, v14);
          v6 = a1;
          v10 -= v14;
        }
        else
        {
          v6 = a1;
          v13 = 14;
        }
      }
    }
  }
  else
  {
    if ( v8 != 8 )
    {
      switch ( v8 )
      {
        case 0:
          v20 = VaultDeserialize<unsigned char>(&v24, &Source2, (_BYTE *)(a3 + 8));
          v6 = a1;
          v13 = v20;
          v10 = Source2;
          goto LABEL_21;
        case 1:
        case 2:
          if ( v10 >= 2 )
          {
            v10 = v7 - 6;
            *(_WORD *)(a3 + 8) = *v9;
            v13 = 0;
          }
          else
          {
            v13 = 122;
          }
          goto LABEL_21;
        case 3:
        case 4:
          if ( v10 >= 4 )
          {
            v10 = v7 - 8;
            v13 = 0;
            *(_DWORD *)(a3 + 8) = *(_DWORD *)v9;
          }
          else
          {
            v13 = 122;
          }
          goto LABEL_21;
        case 5:
          if ( v10 >= 8 )
          {
            v10 = v7 - 12;
            *(_QWORD *)(a3 + 8) = *(_QWORD *)v9;
            v13 = 0;
          }
          else
          {
            v13 = 122;
          }
          goto LABEL_21;
        case 6:
          if ( v10 < 0x10 )
          {
            v13 = 122;
          }
          else
          {
            v10 = v7 - 20;
            v13 = 0;
            *(_OWORD *)(a3 + 8) = *(_OWORD *)v9;
          }
          goto LABEL_21;
        case 10:
          break;
        default:
          return 87;
      }
    }
    *(_OWORD *)(a3 + 8) = 0;
    if ( v10 < 4 )
    {
      v13 = 122;
    }
    else
    {
      v11 = *(_DWORD *)v9;
      *(_DWORD *)(a3 + 8) = *(_DWORD *)v9;
      v10 = v7 - 8;
      if ( v11 > v7 - 8 )
      {
        v13 = 122;
      }
      else
      {
        if ( !v11 )
        {
LABEL_9:
          v13 = 0;
          goto LABEL_21;
        }
        v12 = LocalAlloc(0x40u, v11);
        *(_QWORD *)(a3 + 16) = v12;
        if ( v12 )
        {
          memcpy_0(v12, v9 + 2, *(unsigned int *)(a3 + 8));
          v10 -= *(_DWORD *)(a3 + 8);
          v6 = a1;
          goto LABEL_9;
        }
        v6 = a1;
        v13 = 14;
      }
    }
  }
LABEL_21:
  if ( !v13 )
  {
    v18 = v7 - v10;
    *v6 += v18;
    *a2 -= v18;
    return 0;
  }
  return v13;
}

```

## disassembly

```asm
0x180027d50  mov     r11, rsp
0x180027d53  mov     [r11+18h], r8
0x180027d57  mov     [r11+8], rcx
0x180027d5b  push    rbx
0x180027d5c  push    rbp
0x180027d5d  push    rdi
0x180027d5e  push    r12
0x180027d60  push    r13
0x180027d62  push    r14
0x180027d64  push    r15
0x180027d66  sub     rsp, 30h
0x180027d6a  mov     r9, [rcx]
0x180027d6d  mov     r12, rdx
0x180027d70  mov     rdi, r8
0x180027d73  mov     rdx, rcx
0x180027d76  mov     r14d, [r12]
0x180027d7a  cmp     r14d, 4
0x180027d7e  jb      loc_180027F49
0x180027d84  movsxd  rax, dword ptr [r9]
0x180027d87  lea     rbp, [r9+4]
0x180027d8b  mov     [r8], eax
0x180027d8e  lea     r13d, [r14-4]
0x180027d92  mov     [r11+20h], rbp
0x180027d96  mov     [r11+10h], r13d
0x180027d9a  cmp     eax, 7
0x180027d9d  jz      short loc_180027E0D
0x180027d9f  cmp     eax, 8
0x180027da2  jnz     loc_180027F01
0x180027da8  xorps   xmm0, xmm0; jumptable 0000000180027F1C case 10
0x180027dab  movups  xmmword ptr [rdi+8], xmm0
0x180027daf  cmp     r13d, 4
0x180027db3  jb      loc_180027FFC
0x180027db9  mov     eax, [rbp+0]
0x180027dbc  lea     ebx, [r13-4]
0x180027dc0  mov     [rdi+8], eax
0x180027dc3  mov     r13d, ebx
0x180027dc6  cmp     eax, ebx
0x180027dc8  ja      loc_180028007
0x180027dce  test    eax, eax
0x180027dd0  jz      short loc_180027E05
0x180027dd2  mov     edx, eax; uBytes
0x180027dd4  mov     ecx, 40h ; '@'; uFlags
0x180027dd9  call    cs:__imp_LocalAlloc
0x180027ddf  mov     [rdi+10h], rax
0x180027de3  test    rax, rax
0x180027de6  jz      loc_180028012
0x180027dec  mov     r8d, [rdi+8]; Size
0x180027df0  lea     rdx, [rbp+4]; Src
0x180027df4  mov     rcx, rax; void *
0x180027df7  call    memcpy_0
0x180027dfc  sub     r13d, [rdi+8]
0x180027e00  mov     rdx, [rsp+68h+arg_0]
0x180027e05  xor     r15d, r15d
0x180027e08  jmp     loc_180027EC5
0x180027e0d  xor     r15d, r15d
0x180027e10  mov     word ptr [rsp+68h+Source2], r15w
0x180027e16  cmp     r13d, 4
0x180027e1a  jb      loc_180028022
0x180027e20  mov     [rsp+68h+var_40], rsi
0x180027e25  lea     eax, [r13-4]
0x180027e29  mov     esi, [rbp+0]
0x180027e2c  mov     r13d, eax
0x180027e2f  add     rbp, 4
0x180027e33  cmp     esi, 2
0x180027e36  jb      loc_180027EFB
0x180027e3c  cmp     esi, eax
0x180027e3e  ja      loc_18002802D
0x180027e44  test    sil, 1
0x180027e48  jnz     loc_180027EF3
0x180027e4e  mov     ebx, r15d
0x180027e51  cmp     ebx, esi
0x180027e53  jnb     loc_180027EEE
0x180027e59  mov     edi, ebx
0x180027e5b  lea     rdx, [rsp+68h+Source2]; Source2
0x180027e60  mov     r8d, 2; Length
0x180027e66  lea     rcx, [rdi+rbp]; Source1
0x180027e6a  call    cs:__imp_RtlCompareMemory
0x180027e70  cmp     rax, 2
0x180027e74  jz      short loc_180027E7B
0x180027e76  add     ebx, 2
0x180027e79  jmp     short loc_180027E51
0x180027e7b  lea     rax, [rsi-2]
0x180027e7f  mov     rbx, rsi
0x180027e82  cmp     rdi, rax
0x180027e85  jnz     short loc_180027EEE
0x180027e87  mov     rdx, rbx; uBytes
0x180027e8a  mov     ecx, 40h ; '@'; uFlags
0x180027e8f  call    cs:__imp_LocalAlloc
0x180027e95  mov     rcx, [rsp+68h+arg_10]
0x180027e9d  mov     [rcx+8], rax
0x180027ea1  test    rax, rax
0x180027ea4  jz      loc_180027F39
0x180027eaa  mov     r8, rbx; Size
0x180027ead  mov     rdx, rbp; Src
0x180027eb0  mov     rcx, rax; void *
0x180027eb3  call    memcpy_0
0x180027eb8  mov     rdx, [rsp+68h+arg_0]
0x180027ebd  sub     r13d, esi
0x180027ec0  mov     rsi, [rsp+68h+var_40]
0x180027ec5  test    r15d, r15d
0x180027ec8  jnz     short loc_180027EE9
0x180027eca  sub     r14d, r13d
0x180027ecd  mov     eax, r14d
0x180027ed0  add     [rdx], rax
0x180027ed3  sub     [r12], eax
0x180027ed7  xor     eax, eax
0x180027ed9  add     rsp, 30h
0x180027edd  pop     r15
0x180027edf  pop     r14
0x180027ee1  pop     r13
0x180027ee3  pop     r12
0x180027ee5  pop     rdi
0x180027ee6  pop     rbp
0x180027ee7  pop     rbx
0x180027ee8  retn
0x180027ee9  mov     eax, r15d
0x180027eec  jmp     short loc_180027ED9
0x180027eee  mov     rdx, [rsp+68h+arg_0]
0x180027ef3  mov     r15d, 54Eh
0x180027ef9  jmp     short loc_180027EC0
0x180027efb  mov     [r8+8], r15
0x180027eff  jmp     short loc_180027EC0
0x180027f01  cmp     eax, 0Bh; switch 12 cases
0x180027f04  ja      def_180027F1C; jumptable 0000000180027F1C default case, cases 7-9,11
0x180027f0a  lea     r8, __ImageBase
0x180027f11  mov     ecx, ds:(jpt_180027F1C - 180000000h)[r8+rax*4]
0x180027f19  add     rcx, r8
0x180027f1c  jmp     rcx; switch jump
0x180027f1e  cmp     r13d, 10h; jumptable 0000000180027F1C case 6
0x180027f22  jb      loc_180027FE6
0x180027f28  movups  xmm0, xmmword ptr [rbp+0]
0x180027f2c  add     r13d, 0FFFFFFF0h
0x180027f30  xor     r15d, r15d
0x180027f33  movups  xmmword ptr [rdi+8], xmm0
0x180027f37  jmp     short loc_180027EC5
0x180027f39  mov     rdx, [rsp+68h+arg_0]
0x180027f3e  mov     r15d, 0Eh
0x180027f44  jmp     loc_180027EC0
0x180027f49  mov     r15d, 7Ah ; 'z'
0x180027f4f  jmp     short loc_180027EE9
0x180027f51  cmp     r13d, 2; jumptable 0000000180027F1C cases 1,2
0x180027f55  jnb     short loc_180027F62
0x180027f57  mov     r15d, 7Ah ; 'z'
0x180027f5d  jmp     loc_180027EC5
0x180027f62  movzx   eax, word ptr [rbp+0]
0x180027f66  add     r13d, 0FFFFFFFEh
0x180027f6a  mov     [rdi+8], ax
0x180027f6e  xor     r15d, r15d
0x180027f71  jmp     loc_180027EC5
0x180027f76  cmp     r13d, 4; jumptable 0000000180027F1C cases 3,4
0x180027f7a  jnb     short loc_180027F87
0x180027f7c  mov     r15d, 7Ah ; 'z'
0x180027f82  jmp     loc_180027EC5
0x180027f87  mov     eax, [rbp+0]
0x180027f8a  add     r13d, 0FFFFFFFCh
0x180027f8e  xor     r15d, r15d
0x180027f91  mov     [rdi+8], eax
0x180027f94  jmp     loc_180027EC5
0x180027f99  cmp     r13d, 8; jumptable 0000000180027F1C case 5
0x180027f9d  jnb     short loc_180027FAA
0x180027f9f  mov     r15d, 7Ah ; 'z'
0x180027fa5  jmp     loc_180027EC5
0x180027faa  mov     rax, [rbp+0]
0x180027fae  add     r13d, 0FFFFFFF8h
0x180027fb2  mov     [rdi+8], rax
0x180027fb6  xor     r15d, r15d
0x180027fb9  jmp     loc_180027EC5
0x180027fbe  lea     r8, [rdi+8]; jumptable 0000000180027F1C case 0
0x180027fc2  lea     rdx, [rsp+68h+Source2]
0x180027fc7  lea     rcx, [rsp+68h+arg_18]
0x180027fcf  call    ??$VaultDeserialize@E@@YAKAEAPEAEAEAKAEAE@Z; VaultDeserialize<uchar>(uchar * &,ulong &,uchar &)
0x180027fd4  mov     rdx, [rsp+68h+arg_0]
0x180027fd9  mov     r15d, eax
0x180027fdc  mov     r13d, [rsp+68h+Source2]
0x180027fe1  jmp     loc_180027EC5
0x180027fe6  mov     r15d, 7Ah ; 'z'
0x180027fec  jmp     loc_180027EC5
0x180027ff1  mov     r15d, 57h ; 'W'; jumptable 0000000180027F1C default case, cases 7-9,11
0x180027ff7  jmp     loc_180027EE9
0x180027ffc  mov     r15d, 7Ah ; 'z'
0x180028002  jmp     loc_180027EC5
0x180028007  mov     r15d, 7Ah ; 'z'
0x18002800d  jmp     loc_180027EC5
0x180028012  mov     rdx, [rsp+68h+arg_0]
0x180028017  mov     r15d, 0Eh
0x18002801d  jmp     loc_180027EC5
0x180028022  mov     r15d, 7Ah ; 'z'
0x180028028  jmp     loc_180027EC5
0x18002802d  mov     r15d, 7Ah ; 'z'
0x180028033  jmp     loc_180027EC0
```
