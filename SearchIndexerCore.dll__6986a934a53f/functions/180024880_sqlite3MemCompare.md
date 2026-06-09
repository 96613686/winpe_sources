# sqlite3MemCompare

- ea: `0x180024880`
- end: `0x180024b53`
- name: `sqlite3MemCompare`
- size: `723`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800286a4`
- `0x18005737c`
- `0x180089500`
- `0x1800895c0`
- `0x180089d40`

## callees

- `0x1800232b0`
- `0x180024880`
- `0x180024d90`
- `0x180024dd0`
- `0x180025640`
- `0x180092b48`
- `0x1800b0010`

## pseudocode

```c
__int64 __fastcall sqlite3MemCompare(__int64 a1, __int64 a2, __int64 a3)
{
  __int16 v3; // r11
  __int16 v5; // bx
  char v6; // r10
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rax
  unsigned int v13; // ebx
  __int128 v15; // [rsp+30h] [rbp-29h] BYREF
  __int128 v16; // [rsp+40h] [rbp-19h]
  __int128 v17; // [rsp+50h] [rbp-9h]
  __int64 v18; // [rsp+60h] [rbp+7h]
  __int128 v19; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v20; // [rsp+78h] [rbp+1Fh]
  __int64 v21; // [rsp+80h] [rbp+27h]
  __int128 v22; // [rsp+88h] [rbp+2Fh]
  __int64 v23; // [rsp+98h] [rbp+3Fh]

  v3 = *(_WORD *)(a2 + 20);
  v5 = *(_WORD *)(a1 + 20);
  v6 = v5 | v3;
  if ( (((unsigned __int8)v5 | (unsigned __int8)v3) & 1) != 0 )
    return (v3 & 1) - (v5 & 1u);
  if ( (v6 & 0x2C) != 0 )
  {
    if ( ((unsigned __int8)v5 & (unsigned __int8)v3 & 0x24) != 0 )
    {
      if ( *(_QWORD *)a1 < *(_QWORD *)a2 )
        return 0xFFFFFFFFLL;
      if ( *(_QWORD *)a1 > *(_QWORD *)a2 )
        return 1;
    }
    else
    {
      if ( ((unsigned __int8)v5 & (unsigned __int8)v3 & 8) == 0 )
      {
        if ( (v5 & 0x24) != 0 )
        {
          if ( (v3 & 8) != 0 )
            return sqlite3IntFloatCompare(*(_QWORD *)a1);
          if ( (v3 & 0x24) != 0 && *(_QWORD *)a1 >= *(_QWORD *)a2 )
            return *(_QWORD *)a1 > *(_QWORD *)a2;
        }
        else
        {
          if ( (v5 & 8) == 0 )
            return 1;
          if ( (v3 & 0x24) != 0 )
            return (unsigned int)-sqlite3IntFloatCompare(*(_QWORD *)a2);
        }
        return 0xFFFFFFFFLL;
      }
      if ( *(double *)a2 > *(double *)a1 )
        return 0xFFFFFFFFLL;
      if ( *(double *)a1 > *(double *)a2 )
        return 1;
    }
    return 0;
  }
  if ( (v6 & 2) == 0 )
    return sqlite3BlobCompare();
  if ( (v5 & 2) == 0 )
    return 1;
  if ( (v3 & 2) == 0 )
    return 0xFFFFFFFFLL;
  if ( !a3 )
    return sqlite3BlobCompare();
  if ( *(_BYTE *)(a1 + 22) == *(_BYTE *)(a3 + 8) )
  {
    return (*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(a3 + 24))(
             *(_QWORD *)(a3 + 16),
             *(unsigned int *)(a1 + 16),
             *(_QWORD *)(a1 + 8),
             *(unsigned int *)(a2 + 16),
             *(_QWORD *)(a2 + 8));
  }
  else
  {
    v18 = 0;
    v16 = 0;
    v23 = 0;
    v8 = *(_QWORD *)(a1 + 24);
    v20 = 0x100000000LL;
    WORD2(v16) = 1;
    v17 = 0;
    *((_QWORD *)&v16 + 1) = v8;
    v22 = 0;
    v21 = v8;
    v15 = 0;
    LODWORD(v17) = 0;
    v19 = 0;
    LODWORD(v22) = 0;
    sqlite3VdbeMemShallowCopy(&v15, a1, 0x4000);
    sqlite3VdbeMemShallowCopy(&v19, a2, 0x4000);
    v9 = *(unsigned __int8 *)(a3 + 8);
    if ( (WORD2(v16) & 0x202) == 0x202 && BYTE6(v16) == (_BYTE)v9 )
    {
      v10 = *((_QWORD *)&v15 + 1);
    }
    else if ( (BYTE4(v16) & 1) != 0 )
    {
      v10 = 0;
    }
    else
    {
      v10 = valueToText(&v15, v9);
    }
    v11 = *(unsigned __int8 *)(a3 + 8);
    if ( (WORD2(v20) & 0x202) == 0x202 && BYTE6(v20) == (_BYTE)v11 )
    {
      v12 = *((_QWORD *)&v19 + 1);
    }
    else if ( (v20 & 0x100000000LL) != 0 )
    {
      v12 = 0;
    }
    else
    {
      v12 = valueToText(&v19, v11);
    }
    if ( v10 && v12 )
      v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, __int64))(a3 + 24))(
              *(_QWORD *)(a3 + 16),
              (unsigned int)v16,
              v10,
              (unsigned int)v20,
              v12);
    else
      v13 = 0;
    if ( (_DWORD)v17 )
      vdbeMemClear(&v15);
    if ( (_DWORD)v22 )
      vdbeMemClear(&v19);
  }
  return v13;
}

```

## disassembly

```asm
0x180024880  mov     [rsp-8+arg_8], rbx
0x180024885  mov     [rsp-8+arg_10], rsi
0x18002488a  push    rbp
0x18002488b  push    rdi
0x18002488c  push    r14
0x18002488e  lea     rbp, [rsp-47h]
0x180024893  sub     rsp, 0A0h
0x18002489a  movzx   r11d, word ptr [rdx+14h]
0x18002489f  mov     rdi, r8
0x1800248a2  movzx   ebx, word ptr [rcx+14h]
0x1800248a6  mov     r10d, r11d
0x1800248a9  or      r10d, ebx
0x1800248ac  mov     r14, rdx
0x1800248af  mov     rsi, rcx
0x1800248b2  test    r10b, 1
0x1800248b6  jnz     loc_180024A3D
0x1800248bc  test    r10b, 2Ch
0x1800248c0  jnz     loc_180024AC1
0x1800248c6  test    r10b, 2
0x1800248ca  jz      loc_180024A80
0x1800248d0  test    bl, 2
0x1800248d3  jz      loc_180024AD9
0x1800248d9  test    r11b, 2
0x1800248dd  jz      loc_180024AB7
0x1800248e3  test    r8, r8
0x1800248e6  jz      loc_180024A80
0x1800248ec  movzx   eax, byte ptr [r8+8]
0x1800248f1  cmp     [rcx+16h], al
0x1800248f4  jz      loc_180024A87
0x1800248fa  xorps   xmm0, xmm0
0x1800248fd  mov     [rsp+0B0h+arg_0], r15
0x180024905  xor     eax, eax
0x180024907  xorps   xmm1, xmm1
0x18002490a  mov     ecx, 1
0x18002490f  mov     [rbp+57h+var_50], rax
0x180024913  movups  [rbp+57h+var_70], xmm0
0x180024917  mov     [rbp+57h+var_18], rax
0x18002491b  xor     r15d, r15d
0x18002491e  mov     rax, [rsi+18h]
0x180024922  mov     r8d, 4000h
0x180024928  movups  [rbp+57h+var_38], xmm1
0x18002492c  mov     word ptr [rbp+57h+var_70+4], cx
0x180024930  mov     rdx, rsi
0x180024933  mov     word ptr [rbp+57h+var_38+4], cx
0x180024937  lea     rcx, [rbp+57h+var_80]
0x18002493b  movups  [rbp+57h+var_60], xmm0
0x18002493f  mov     qword ptr [rbp+57h+var_70+8], rax
0x180024943  movups  [rbp+57h+var_28], xmm1
0x180024947  mov     qword ptr [rbp+57h+var_38+8], rax
0x18002494b  movups  [rbp+57h+var_80], xmm0
0x18002494f  mov     dword ptr [rbp+57h+var_60], r15d
0x180024953  movups  [rbp+57h+var_48], xmm1
0x180024957  mov     dword ptr [rbp+57h+var_28], r15d
0x18002495b  call    sqlite3VdbeMemShallowCopy
0x180024960  mov     r8d, 4000h
0x180024966  lea     rcx, [rbp+57h+var_48]
0x18002496a  mov     rdx, r14
0x18002496d  call    sqlite3VdbeMemShallowCopy
0x180024972  movzx   ecx, word ptr [rbp+57h+var_70+4]
0x180024976  mov     esi, 202h
0x18002497b  movzx   edx, byte ptr [rdi+8]
0x18002497f  movzx   eax, cx
0x180024982  and     ax, si
0x180024985  cmp     ax, si
0x180024988  jz      loc_180024A4C
0x18002498e  test    cl, 1
0x180024991  jnz     loc_180024A70
0x180024997  lea     rcx, [rbp+57h+var_80]
0x18002499b  call    valueToText
0x1800249a0  mov     rbx, rax
0x1800249a3  movzx   eax, word ptr [rbp+57h+var_38+4]
0x1800249a7  movzx   edx, byte ptr [rdi+8]
0x1800249ab  movzx   ecx, ax
0x1800249ae  and     cx, si
0x1800249b1  cmp     cx, si
0x1800249b4  jz      loc_180024A5E
0x1800249ba  test    al, 1
0x1800249bc  jnz     loc_180024A78
0x1800249c2  lea     rcx, [rbp+57h+var_48]
0x1800249c6  call    valueToText
0x1800249cb  test    rbx, rbx
0x1800249ce  jz      loc_180024AAF
0x1800249d4  test    rax, rax
0x1800249d7  jz      loc_180024AAF
0x1800249dd  mov     r9d, dword ptr [rbp+57h+var_38]
0x1800249e1  mov     r8, rbx
0x1800249e4  mov     edx, dword ptr [rbp+57h+var_70]
0x1800249e7  mov     rcx, [rdi+10h]
0x1800249eb  mov     [rsp+0B0h+var_90], rax
0x1800249f0  mov     rax, [rdi+18h]
0x1800249f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249f9  mov     ebx, eax
0x1800249fb  cmp     dword ptr [rbp+57h+var_60], 0
0x1800249ff  mov     r15, [rsp+0B0h+arg_0]
0x180024a07  jz      short loc_180024A12
0x180024a09  lea     rcx, [rbp+57h+var_80]
0x180024a0d  call    vdbeMemClear
0x180024a12  cmp     dword ptr [rbp+57h+var_28], 0
0x180024a16  jnz     short loc_180024A32
0x180024a18  mov     eax, ebx
0x180024a1a  lea     r11, [rsp+0B0h+var_10]
0x180024a22  mov     rbx, [r11+28h]
0x180024a26  mov     rsi, [r11+30h]
0x180024a2a  mov     rsp, r11
0x180024a2d  pop     r14
0x180024a2f  pop     rdi
0x180024a30  pop     rbp
0x180024a31  retn
0x180024a32  lea     rcx, [rbp+57h+var_48]
0x180024a36  call    vdbeMemClear
0x180024a3b  jmp     short loc_180024A18
0x180024a3d  and     r11d, 1
0x180024a41  and     ebx, 1
0x180024a44  sub     r11d, ebx
0x180024a47  mov     eax, r11d
0x180024a4a  jmp     short loc_180024A1A
0x180024a4c  cmp     byte ptr [rbp+57h+var_70+6], dl
0x180024a4f  jnz     loc_18002498E
0x180024a55  mov     rbx, qword ptr [rbp+57h+var_80+8]
0x180024a59  jmp     loc_1800249A3
0x180024a5e  cmp     byte ptr [rbp+57h+var_38+6], dl
0x180024a61  jnz     loc_1800249BA
0x180024a67  mov     rax, qword ptr [rbp+57h+var_48+8]
0x180024a6b  jmp     loc_1800249CB
0x180024a70  mov     rbx, r15
0x180024a73  jmp     loc_1800249A3
0x180024a78  mov     rax, r15
0x180024a7b  jmp     loc_1800249CB
0x180024a80  call    sqlite3BlobCompare
0x180024a85  jmp     short loc_180024A1A
0x180024a87  mov     rcx, [rdx+8]
0x180024a8b  mov     r9d, [rdx+10h]
0x180024a8f  mov     r8, [rsi+8]
0x180024a93  mov     edx, [rsi+10h]
0x180024a96  mov     rax, [rdi+18h]
0x180024a9a  mov     [rsp+0B0h+var_90], rcx
0x180024a9f  mov     rcx, [rdi+10h]
0x180024aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024aa8  mov     ebx, eax
0x180024aaa  jmp     loc_180024A18
0x180024aaf  mov     ebx, r15d
0x180024ab2  jmp     loc_1800249FB
0x180024ab7  mov     eax, 0FFFFFFFFh
0x180024abc  jmp     loc_180024A1A
0x180024ac1  movzx   ecx, r11w
0x180024ac5  movzx   eax, bx
0x180024ac8  and     ecx, eax
0x180024aca  test    cl, 24h
0x180024acd  jz      short loc_180024AE3
0x180024acf  mov     rax, [rdx]
0x180024ad2  cmp     [rsi], rax
0x180024ad5  jl      short loc_180024AB7
0x180024ad7  jle     short loc_180024B2A
0x180024ad9  mov     eax, 1
0x180024ade  jmp     loc_180024A1A
0x180024ae3  test    cl, 8
0x180024ae6  jz      short loc_180024AFE
0x180024ae8  movsd   xmm0, qword ptr [rdx]
0x180024aec  movsd   xmm1, qword ptr [rsi]
0x180024af0  comisd  xmm0, xmm1
0x180024af4  ja      short loc_180024AB7
0x180024af6  comisd  xmm1, xmm0
0x180024afa  jbe     short loc_180024B2A
0x180024afc  jmp     short loc_180024AD9
0x180024afe  test    bl, 24h
0x180024b01  jz      short loc_180024B31
0x180024b03  test    r11b, 8
0x180024b07  jz      short loc_180024B1A
0x180024b09  movsd   xmm1, qword ptr [rdx]
0x180024b0d  mov     rcx, [rsi]
0x180024b10  call    sqlite3IntFloatCompare
0x180024b15  jmp     loc_180024A1A
0x180024b1a  test    r11b, 24h
0x180024b1e  jz      short loc_180024AB7
0x180024b20  mov     rax, [rdx]
0x180024b23  cmp     [rsi], rax
0x180024b26  jl      short loc_180024AB7
0x180024b28  jg      short loc_180024AD9
0x180024b2a  xor     eax, eax
0x180024b2c  jmp     loc_180024A1A
0x180024b31  test    bl, 8
0x180024b34  jz      short loc_180024AD9
0x180024b36  test    r11b, 24h
0x180024b3a  jz      loc_180024AB7
0x180024b40  movsd   xmm1, qword ptr [rsi]
0x180024b44  mov     rcx, [rdx]
0x180024b47  call    sqlite3IntFloatCompare
0x180024b4c  neg     eax
0x180024b4e  jmp     loc_180024A1A
```
