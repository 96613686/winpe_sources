# FwCopyCryptoSet

- ea: `0x180014b20`
- end: `0x180014eac`
- name: `FwCopyCryptoSet`
- size: `908`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800042c4`
- `0x180014b20`
- `0x180014eb4`
- `0x180014f80`
- `0x18001ffd4`

## import_xrefs

- `fwbase!FwAlloc` at `0x180014b43`
- `fwbase!FwAlloc` at `0x180014b43`
- `fwbase!FwStringCopy` at `0x180014b81`
- `fwbase!FwStringCopy` at `0x180014b9c`
- `fwbase!FwStringCopy` at `0x180014bb7`
- `fwbase!FwStringCopy` at `0x180014bd2`
- `fwbase!FwStringCopy` at `0x180014c4c`
- `fwbase!FwStringCopy` at `0x180014b81`
- `fwbase!FwStringCopy` at `0x180014b9c`
- `fwbase!FwStringCopy` at `0x180014bb7`
- `fwbase!FwStringCopy` at `0x180014bd2`
- `fwbase!FwStringCopy` at `0x180014c4c`
- `fwbase!FwAllocCheckSize` at `0x180014c13`
- `fwbase!FwAllocCheckSize` at `0x180014cbf`
- `fwbase!FwAllocCheckSize` at `0x180014c13`
- `fwbase!FwAllocCheckSize` at `0x180014cbf`

## pseudocode

```c
__int64 __fastcall FwCopyCryptoSet(__int64 a1, _QWORD *a2)
{
  void *v4; // rax
  int v5; // ebx
  unsigned int v7; // r10d
  unsigned int v8; // r11d
  __int64 v9; // r9
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  LPCOLESTR v13; // rcx
  __int64 v14; // rdx

  *a2 = 0;
  v4 = (void *)FwAlloc(96);
  *a2 = v4;
  if ( !v4 )
  {
    v5 = -2147024882;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_19;
    v14 = 123;
    goto LABEL_46;
  }
  memset_0(v4, 0, 0x60u);
  *(_WORD *)(*a2 + 8LL) = *(_WORD *)(a1 + 8);
  *(_DWORD *)(*a2 + 12LL) = *(_DWORD *)(a1 + 12);
  v5 = FwStringCopy(*(_QWORD *)(a1 + 16), *a2 + 16LL);
  if ( v5 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_19;
    v14 = 124;
    goto LABEL_46;
  }
  v5 = FwStringCopy(*(_QWORD *)(a1 + 24), *a2 + 24LL);
  if ( v5 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_19;
    v14 = 125;
    goto LABEL_46;
  }
  v5 = FwStringCopy(*(_QWORD *)(a1 + 32), *a2 + 32LL);
  if ( v5 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_19;
    v14 = 126;
    goto LABEL_46;
  }
  v5 = FwStringCopy(*(_QWORD *)(a1 + 40), *a2 + 40LL);
  if ( v5 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_19;
    v14 = 127;
    goto LABEL_46;
  }
  if ( *(_DWORD *)(a1 + 12) == 1 )
  {
    *(_WORD *)(*a2 + 48LL) = *(_WORD *)(a1 + 48);
    *(_DWORD *)(*a2 + 64LL) = *(_DWORD *)(a1 + 64);
    *(_DWORD *)(*a2 + 68LL) = *(_DWORD *)(a1 + 68);
    *(_DWORD *)(*a2 + 52LL) = *(_DWORD *)(a1 + 52);
    v5 = FwAllocCheckSize(16, *(unsigned int *)(a1 + 52), *a2 + 56LL);
    if ( v5 < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_19;
      v14 = 128;
      goto LABEL_46;
    }
    v7 = 0;
    v8 = *(_DWORD *)(a1 + 52);
    v9 = *(_QWORD *)(a1 + 56);
    v10 = *(_QWORD *)(*a2 + 56LL);
    if ( v8 )
    {
      v11 = 0;
      do
      {
        ++v7;
        v12 = 2 * v11++;
        *(_DWORD *)(v10 + 8 * v12) = *(_DWORD *)(v9 + 8 * v12);
        *(_DWORD *)(v10 + 8 * v12 + 4) = *(_DWORD *)(v9 + 8 * v12 + 4);
        *(_DWORD *)(v10 + 8 * v12 + 8) = *(_DWORD *)(v9 + 8 * v12 + 8);
      }
      while ( v7 < v8 );
    }
  }
  else if ( *(_DWORD *)(a1 + 12) == 2 )
  {
    *(_DWORD *)(*a2 + 48LL) = *(_DWORD *)(a1 + 48);
    *(_DWORD *)(*a2 + 52LL) = *(_DWORD *)(a1 + 52);
    v5 = FwAllocCheckSize(28, *(unsigned int *)(a1 + 52), *a2 + 56LL);
    if ( v5 < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_19;
      v14 = 130;
      goto LABEL_46;
    }
    v5 = FwCopyPhase2CryptoSets(
           *(struct _tag_FW_PHASE2_CRYPTO_SUITE **)(a1 + 56),
           *(struct _tag_FW_PHASE2_CRYPTO_SUITE **)(*a2 + 56LL),
           *(_DWORD *)(a1 + 52));
    if ( v5 < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_19;
      v14 = 131;
      goto LABEL_46;
    }
  }
  v5 = FwStringCopy(*(_QWORD *)(a1 + 80), *a2 + 80LL);
  if ( v5 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_19;
    v14 = 132;
LABEL_46:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, (unsigned int)v5);
LABEL_19:
    FwCryptoSetFree(*a2);
    *a2 = 0;
    return (unsigned int)v5;
  }
  *(_DWORD *)(*a2 + 72LL) = *(_DWORD *)(a1 + 72);
  *(_DWORD *)(*a2 + 88LL) = *(_DWORD *)(a1 + 88);
  *(_QWORD *)*a2 = 0;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180014b20  mov     [rsp+arg_0], rbx
0x180014b25  mov     [rsp+arg_8], rsi
0x180014b2a  push    rdi
0x180014b2b  sub     rsp, 20h
0x180014b2f  mov     rsi, rcx
0x180014b32  mov     qword ptr [rdx], 0
0x180014b39  mov     ebx, 60h ; '`'
0x180014b3e  mov     rdi, rdx
0x180014b41  mov     ecx, ebx
0x180014b43  call    cs:__imp_FwAlloc
0x180014b49  mov     [rdi], rax
0x180014b4c  test    rax, rax
0x180014b4f  jz      loc_180014D8F
0x180014b55  mov     r8d, ebx; Size
0x180014b58  xor     edx, edx; Val
0x180014b5a  mov     rcx, rax; void *
0x180014b5d  call    memset_0
0x180014b62  mov     rcx, [rdi]
0x180014b65  movzx   eax, word ptr [rsi+8]
0x180014b69  mov     [rcx+8], ax
0x180014b6d  mov     rcx, [rdi]
0x180014b70  mov     eax, [rsi+0Ch]
0x180014b73  mov     [rcx+0Ch], eax
0x180014b76  mov     rdx, [rdi]
0x180014b79  mov     rcx, [rsi+10h]
0x180014b7d  add     rdx, 10h
0x180014b81  call    cs:__imp_FwStringCopy
0x180014b87  mov     ebx, eax
0x180014b89  test    eax, eax
0x180014b8b  js      loc_180014D49
0x180014b91  mov     rdx, [rdi]
0x180014b94  mov     rcx, [rsi+18h]
0x180014b98  add     rdx, 18h
0x180014b9c  call    cs:__imp_FwStringCopy
0x180014ba2  mov     ebx, eax
0x180014ba4  test    eax, eax
0x180014ba6  js      loc_180014DB7
0x180014bac  mov     rdx, [rdi]
0x180014baf  mov     rcx, [rsi+20h]
0x180014bb3  add     rdx, 20h ; ' '
0x180014bb7  call    cs:__imp_FwStringCopy
0x180014bbd  mov     ebx, eax
0x180014bbf  test    eax, eax
0x180014bc1  js      loc_180014D1E
0x180014bc7  mov     rdx, [rdi]
0x180014bca  mov     rcx, [rsi+28h]
0x180014bce  add     rdx, 28h ; '('
0x180014bd2  call    cs:__imp_FwStringCopy
0x180014bd8  mov     ebx, eax
0x180014bda  test    eax, eax
0x180014bdc  js      loc_180014DF6
0x180014be2  cmp     dword ptr [rsi+0Ch], 1
0x180014be6  jz      loc_180014C8A
0x180014bec  cmp     dword ptr [rsi+0Ch], 2
0x180014bf0  jnz     short loc_180014C41
0x180014bf2  mov     rcx, [rdi]
0x180014bf5  mov     eax, [rsi+30h]
0x180014bf8  mov     [rcx+30h], eax
0x180014bfb  mov     rcx, [rdi]
0x180014bfe  mov     eax, [rsi+34h]
0x180014c01  mov     [rcx+34h], eax
0x180014c04  mov     ecx, 1Ch
0x180014c09  mov     r8, [rdi]
0x180014c0c  mov     edx, [rsi+34h]
0x180014c0f  add     r8, 38h ; '8'
0x180014c13  call    cs:__imp_FwAllocCheckSize
0x180014c19  mov     ebx, eax
0x180014c1b  test    eax, eax
0x180014c1d  js      loc_180014D6C
0x180014c23  mov     rdx, [rdi]
0x180014c26  mov     rcx, [rsi+38h]; struct _tag_FW_PHASE2_CRYPTO_SUITE *
0x180014c2a  mov     r8d, [rsi+34h]; unsigned int
0x180014c2e  mov     rdx, [rdx+38h]; struct _tag_FW_PHASE2_CRYPTO_SUITE *
0x180014c32  call    ?FwCopyPhase2CryptoSets@@YAJPEAU_tag_FW_PHASE2_CRYPTO_SUITE@@0K@Z; FwCopyPhase2CryptoSets(_tag_FW_PHASE2_CRYPTO_SUITE *,_tag_FW_PHASE2_CRYPTO_SUITE *,ulong)
0x180014c37  mov     ebx, eax
0x180014c39  test    eax, eax
0x180014c3b  js      loc_180014E46
0x180014c41  mov     rdx, [rdi]
0x180014c44  mov     rcx, [rsi+50h]
0x180014c48  add     rdx, 50h ; 'P'
0x180014c4c  call    cs:__imp_FwStringCopy
0x180014c52  mov     ebx, eax
0x180014c54  test    eax, eax
0x180014c56  js      loc_180014E6E
0x180014c5c  mov     eax, [rsi+48h]
0x180014c5f  mov     rcx, [rdi]
0x180014c62  mov     [rcx+48h], eax
0x180014c65  mov     eax, [rsi+58h]
0x180014c68  mov     rcx, [rdi]
0x180014c6b  mov     [rcx+58h], eax
0x180014c6e  mov     rax, [rdi]
0x180014c71  mov     qword ptr [rax], 0
0x180014c78  mov     rsi, [rsp+28h+arg_8]
0x180014c7d  mov     eax, ebx
0x180014c7f  mov     rbx, [rsp+28h+arg_0]
0x180014c84  add     rsp, 20h
0x180014c88  pop     rdi
0x180014c89  retn
0x180014c8a  mov     rcx, [rdi]
0x180014c8d  movzx   eax, word ptr [rsi+30h]
0x180014c91  mov     [rcx+30h], ax
0x180014c95  mov     ecx, 10h
0x180014c9a  mov     rdx, [rdi]
0x180014c9d  mov     eax, [rsi+40h]
0x180014ca0  mov     [rdx+40h], eax
0x180014ca3  mov     rdx, [rdi]
0x180014ca6  mov     eax, [rsi+44h]
0x180014ca9  mov     [rdx+44h], eax
0x180014cac  mov     rdx, [rdi]
0x180014caf  mov     eax, [rsi+34h]
0x180014cb2  mov     [rdx+34h], eax
0x180014cb5  mov     r8, [rdi]
0x180014cb8  mov     edx, [rsi+34h]
0x180014cbb  add     r8, 38h ; '8'
0x180014cbf  call    cs:__imp_FwAllocCheckSize
0x180014cc5  mov     ebx, eax
0x180014cc7  test    eax, eax
0x180014cc9  js      loc_180014E1E
0x180014ccf  mov     rax, [rdi]
0x180014cd2  xor     r10d, r10d
0x180014cd5  mov     r11d, [rsi+34h]
0x180014cd9  mov     r9, [rsi+38h]
0x180014cdd  mov     r8, [rax+38h]
0x180014ce1  test    r11d, r11d
0x180014ce4  jz      loc_180014C41
0x180014cea  xor     edx, edx
0x180014cec  mov     rcx, rdx
0x180014cef  inc     r10d
0x180014cf2  add     rcx, rcx
0x180014cf5  inc     rdx
0x180014cf8  mov     eax, [r9+rcx*8]
0x180014cfc  mov     [r8+rcx*8], eax
0x180014d00  mov     eax, [r9+rcx*8+4]
0x180014d05  mov     [r8+rcx*8+4], eax
0x180014d0a  mov     eax, [r9+rcx*8+8]
0x180014d0f  mov     [r8+rcx*8+8], eax
0x180014d14  cmp     r10d, r11d
0x180014d17  jb      short loc_180014CEC
0x180014d19  jmp     loc_180014C41
0x180014d1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d25  lea     rax, WPP_GLOBAL_Control
0x180014d2c  cmp     rcx, rax
0x180014d2f  jnz     loc_180014DE2
0x180014d35  mov     rcx, [rdi]
0x180014d38  call    FwCryptoSetFree
0x180014d3d  mov     qword ptr [rdi], 0
0x180014d44  jmp     loc_180014C78
0x180014d49  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d50  lea     rax, WPP_GLOBAL_Control
0x180014d57  cmp     rcx, rax
0x180014d5a  jz      short loc_180014D35
0x180014d5c  test    byte ptr [rcx+1Ch], 1
0x180014d60  jz      short loc_180014D35
0x180014d62  mov     edx, 7Ch ; '|'
0x180014d67  jmp     loc_180014E94
0x180014d6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d73  lea     rax, WPP_GLOBAL_Control
0x180014d7a  cmp     rcx, rax
0x180014d7d  jz      short loc_180014D35
0x180014d7f  test    byte ptr [rcx+1Ch], 1
0x180014d83  jz      short loc_180014D35
0x180014d85  mov     edx, 82h
0x180014d8a  jmp     loc_180014E94
0x180014d8f  mov     ebx, 8007000Eh
0x180014d94  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d9b  lea     rax, WPP_GLOBAL_Control
0x180014da2  cmp     rcx, rax
0x180014da5  jz      short loc_180014D35
0x180014da7  test    byte ptr [rcx+1Ch], 1
0x180014dab  jz      short loc_180014D35
0x180014dad  mov     edx, 7Bh ; '{'
0x180014db2  jmp     loc_180014E94
0x180014db7  mov     rcx, cs:WPP_GLOBAL_Control
0x180014dbe  lea     rax, WPP_GLOBAL_Control
0x180014dc5  cmp     rcx, rax
0x180014dc8  jz      loc_180014D35
0x180014dce  test    byte ptr [rcx+1Ch], 1
0x180014dd2  jz      loc_180014D35
0x180014dd8  mov     edx, 7Dh ; '}'
0x180014ddd  jmp     loc_180014E94
0x180014de2  test    byte ptr [rcx+1Ch], 1
0x180014de6  jz      loc_180014D35
0x180014dec  mov     edx, 7Eh ; '~'
0x180014df1  jmp     loc_180014E94
0x180014df6  mov     rcx, cs:WPP_GLOBAL_Control
0x180014dfd  lea     rax, WPP_GLOBAL_Control
0x180014e04  cmp     rcx, rax
0x180014e07  jz      loc_180014D35
0x180014e0d  test    byte ptr [rcx+1Ch], 1
0x180014e11  jz      loc_180014D35
0x180014e17  mov     edx, 7Fh
0x180014e1c  jmp     short loc_180014E94
0x180014e1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e25  lea     rax, WPP_GLOBAL_Control
0x180014e2c  cmp     rcx, rax
0x180014e2f  jz      loc_180014D35
0x180014e35  test    byte ptr [rcx+1Ch], 1
0x180014e39  jz      loc_180014D35
0x180014e3f  mov     edx, 80h
0x180014e44  jmp     short loc_180014E94
0x180014e46  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e4d  lea     rax, WPP_GLOBAL_Control
0x180014e54  cmp     rcx, rax
0x180014e57  jz      loc_180014D35
0x180014e5d  test    byte ptr [rcx+1Ch], 1
0x180014e61  jz      loc_180014D35
0x180014e67  mov     edx, 83h
0x180014e6c  jmp     short loc_180014E94
0x180014e6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e75  lea     rax, WPP_GLOBAL_Control
0x180014e7c  cmp     rcx, rax
0x180014e7f  jz      loc_180014D35
0x180014e85  test    byte ptr [rcx+1Ch], 1
0x180014e89  jz      loc_180014D35
0x180014e8f  mov     edx, 84h
0x180014e94  mov     rcx, [rcx+10h]
0x180014e98  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x180014e9f  mov     r9d, ebx
0x180014ea2  call    WPP_SF_d
0x180014ea7  jmp     loc_180014D35
```
