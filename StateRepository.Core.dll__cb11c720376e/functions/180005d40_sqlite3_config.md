# sqlite3_config

- ea: `0x180005d40`
- end: `0x180006149`
- name: `sqlite3_config`
- size: `1033`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005c78`
- `0x180005d40`
- `0x18000c250`
- `0x18005e8ec`

## callees

- `0x180005d40`
- `0x18005e8ec`
- `0x180060134`

## pseudocode

```c
__int64 __fastcall sqlite3_config(int a1, __int64 a2, unsigned __int64 a3, int a4)
{
  unsigned int v5; // ebx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  __int64 v11; // rcx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  __int64 v19; // rcx
  __int64 v20; // rax
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx

  if ( dword_1800B5784 && ((unsigned int)a1 > 0x3F || ((1LL << a1) & 0x1010000) == 0) )
    return sqlite3ReportError(21, 181552, "misuse");
  v5 = 0;
  if ( a1 > 16 )
  {
    if ( a1 > 24 )
    {
      v21 = a1 - 25;
      if ( !v21 )
      {
        dword_1800B5780 = a2;
        return v5;
      }
      v22 = v21 - 1;
      if ( !v22 )
      {
        dword_1800B564C = a2;
        return v5;
      }
      v23 = v22 - 1;
      if ( !v23 )
      {
        byte_1800B5638 = a2;
        return v5;
      }
      v24 = v23 - 2;
      if ( !v24 )
      {
        qword_1800B57B8 = a2;
        return v5;
      }
      if ( v24 == 1 )
      {
        *(_DWORD *)a2 = 0;
        return v5;
      }
    }
    else
    {
      if ( a1 == 24 )
      {
        *(_DWORD *)a2 = 272;
        return v5;
      }
      v15 = a1 - 17;
      if ( !v15 )
      {
        byte_1800B5636 = a2;
        return v5;
      }
      v16 = v15 - 1;
      if ( !v16 )
      {
        xmmword_1800B56D8 = *(_OWORD *)a2;
        xmmword_1800B56E8 = *(_OWORD *)(a2 + 16);
        xmmword_1800B56F8 = *(_OWORD *)(a2 + 32);
        xmmword_1800B5708 = *(_OWORD *)(a2 + 48);
        xmmword_1800B5718 = *(_OWORD *)(a2 + 64);
        xmmword_1800B5728 = *(_OWORD *)(a2 + 80);
        qword_1800B5738 = *(_QWORD *)(a2 + 96);
        return v5;
      }
      v17 = v16 - 1;
      if ( !v17 )
      {
        if ( !(_QWORD)xmmword_1800B56E8 )
          sqlite3_config(18, qword_18009B2F0);
        *(_OWORD *)a2 = xmmword_1800B56D8;
        *(_OWORD *)(a2 + 16) = xmmword_1800B56E8;
        *(_OWORD *)(a2 + 32) = xmmword_1800B56F8;
        *(_OWORD *)(a2 + 48) = xmmword_1800B5708;
        *(_OWORD *)(a2 + 64) = xmmword_1800B5718;
        *(_OWORD *)(a2 + 80) = xmmword_1800B5728;
        *(_QWORD *)(a2 + 96) = qword_1800B5738;
        return v5;
      }
      v18 = v17 - 1;
      if ( !v18 )
      {
        byte_1800B5637 = a2;
        return v5;
      }
      if ( v18 == 2 )
      {
        v19 = a3;
        if ( a3 > 0x7FFF0000 )
          v19 = 2147418112;
        v20 = 0;
        if ( a2 >= 0 )
          v20 = a2;
        qword_1800B5760 = v19;
        if ( v20 <= v19 )
          v19 = v20;
        qword_1800B5758 = v19;
        return v5;
      }
    }
    return 1;
  }
  if ( a1 == 16 )
  {
    qword_1800B57A8 = a2;
    qword_1800B57B0 = a3;
    return v5;
  }
  if ( a1 <= 9 )
  {
    if ( a1 == 9 )
    {
      dword_1800B5630 = a2;
      return v5;
    }
    v6 = a1 - 1;
    if ( !v6 )
    {
      word_1800B5634 = 0;
      return v5;
    }
    v7 = v6 - 1;
    if ( !v7 )
    {
      word_1800B5634 = 1;
      return v5;
    }
    v8 = v7 - 1;
    if ( !v8 )
    {
      word_1800B5634 = 257;
      return v5;
    }
    v9 = v8 - 1;
    if ( !v9 )
    {
      qword_1800B5650 = *(_QWORD *)a2;
      xmmword_1800B5658 = *(_OWORD *)(a2 + 8);
      *(_OWORD *)&xmmword_1800B5668 = *(_OWORD *)(a2 + 24);
      xmmword_1800B5678 = *(_OWORD *)(a2 + 40);
      qword_1800B5688 = *(_QWORD *)(a2 + 56);
      return v5;
    }
    v10 = v9 - 1;
    if ( !v10 )
    {
      v11 = qword_1800B5650;
      if ( !qword_1800B5650 )
      {
        sqlite3MemSetDefault(0, 0, 1);
        v11 = qword_1800B5650;
      }
      *(_QWORD *)a2 = v11;
      *(_OWORD *)(a2 + 8) = xmmword_1800B5658;
      *(_OWORD *)(a2 + 24) = *(_OWORD *)&xmmword_1800B5668;
      *(_OWORD *)(a2 + 40) = xmmword_1800B5678;
      *(_QWORD *)(a2 + 56) = qword_1800B5688;
      return v5;
    }
    if ( v10 == 2 )
    {
      qword_1800B5768 = a2;
      dword_1800B5770 = a3;
      dword_1800B5774 = a4;
      return v5;
    }
    return 1;
  }
  v12 = a1 - 10;
  if ( !v12 )
  {
    xmmword_1800B5690 = *(_OWORD *)a2;
    xmmword_1800B56A0 = *(_OWORD *)(a2 + 16);
    xmmword_1800B56B0 = *(_OWORD *)(a2 + 32);
    xmmword_1800B56C0 = *(_OWORD *)(a2 + 48);
    qword_1800B56D0 = *(_QWORD *)(a2 + 64);
    return v5;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    *(_OWORD *)a2 = xmmword_1800B5690;
    *(_OWORD *)(a2 + 16) = xmmword_1800B56A0;
    *(_OWORD *)(a2 + 32) = xmmword_1800B56B0;
    *(_OWORD *)(a2 + 48) = xmmword_1800B56C0;
    *(_QWORD *)(a2 + 64) = qword_1800B56D0;
    return v5;
  }
  v14 = v13 - 2;
  if ( !v14 )
  {
    dword_1800B5644 = a2;
    dword_1800B5648 = a3;
    return v5;
  }
  if ( v14 != 1 )
    return 1;
  return v5;
}

```

## disassembly

```asm
0x180005d40  mov     rax, rsp
0x180005d43  mov     [rax+8], ecx
0x180005d46  mov     [rax+10h], rdx
0x180005d4a  mov     [rax+18h], r8
0x180005d4e  mov     [rax+20h], r9
0x180005d52  push    rbx
0x180005d53  push    rdi
0x180005d54  sub     rsp, 38h
0x180005d58  xor     edx, edx
0x180005d5a  cmp     cs:dword_1800B5784, edx
0x180005d60  lea     r8d, [rdx+1]
0x180005d64  jz      short loc_180005D94
0x180005d66  cmp     ecx, 3Fh ; '?'
0x180005d69  ja      short loc_180005D79
0x180005d6b  mov     eax, r8d
0x180005d6e  shl     rax, cl
0x180005d71  test    rax, 1010000h
0x180005d77  jnz     short loc_180005D94
0x180005d79  lea     r8, aMisuse; "misuse"
0x180005d80  mov     edx, 2C530h
0x180005d85  mov     ecx, 15h
0x180005d8a  call    sqlite3ReportError
0x180005d8f  jmp     loc_180006142
0x180005d94  lea     rdi, [rsp+48h+arg_8]
0x180005d99  mov     ebx, edx
0x180005d9b  cmp     ecx, 10h
0x180005d9e  jg      loc_180005FA1
0x180005da4  jz      loc_180005F87
0x180005daa  cmp     ecx, 9
0x180005dad  jg      loc_180005ED1
0x180005db3  jz      loc_180005EC4
0x180005db9  sub     ecx, r8d
0x180005dbc  jz      loc_180005EB8
0x180005dc2  sub     ecx, r8d
0x180005dc5  jz      loc_180005EAB
0x180005dcb  sub     ecx, r8d
0x180005dce  jz      loc_180005E9D
0x180005dd4  sub     ecx, r8d
0x180005dd7  jz      loc_180005E5D
0x180005ddd  sub     ecx, r8d
0x180005de0  jz      short loc_180005E0C
0x180005de2  cmp     ecx, 2
0x180005de5  jnz     loc_180005EE9
0x180005deb  mov     rax, [rdi]
0x180005dee  mov     cs:qword_1800B5768, rax
0x180005df5  mov     eax, [rdi+8]
0x180005df8  mov     cs:dword_1800B5770, eax
0x180005dfe  mov     eax, [rdi+10h]
0x180005e01  mov     cs:dword_1800B5774, eax
0x180005e07  jmp     loc_180006140
0x180005e0c  mov     rcx, cs:qword_1800B5650
0x180005e13  test    rcx, rcx
0x180005e16  jnz     short loc_180005E24
0x180005e18  call    sqlite3MemSetDefault
0x180005e1d  mov     rcx, cs:qword_1800B5650
0x180005e24  mov     rax, [rdi]
0x180005e27  mov     [rax], rcx
0x180005e2a  movups  xmm0, cs:xmmword_1800B5658
0x180005e31  movups  xmmword ptr [rax+8], xmm0
0x180005e35  movups  xmm1, cs:xmmword_1800B5668
0x180005e3c  movups  xmmword ptr [rax+18h], xmm1
0x180005e40  movups  xmm0, cs:xmmword_1800B5678
0x180005e47  movups  xmmword ptr [rax+28h], xmm0
0x180005e4b  movsd   xmm1, cs:qword_1800B5688
0x180005e53  movsd   qword ptr [rax+38h], xmm1
0x180005e58  jmp     loc_180006140
0x180005e5d  mov     rcx, [rdi]
0x180005e60  mov     rax, [rcx]
0x180005e63  mov     cs:qword_1800B5650, rax
0x180005e6a  movups  xmm0, xmmword ptr [rcx+8]
0x180005e6e  movups  cs:xmmword_1800B5658, xmm0
0x180005e75  movups  xmm1, xmmword ptr [rcx+18h]
0x180005e79  movups  cs:xmmword_1800B5668, xmm1
0x180005e80  movups  xmm0, xmmword ptr [rcx+28h]
0x180005e84  movups  cs:xmmword_1800B5678, xmm0
0x180005e8b  movsd   xmm1, qword ptr [rcx+38h]
0x180005e90  movsd   cs:qword_1800B5688, xmm1
0x180005e98  jmp     loc_180006140
0x180005e9d  mov     cs:word_1800B5634, 101h
0x180005ea6  jmp     loc_180006140
0x180005eab  mov     cs:word_1800B5634, r8w
0x180005eb3  jmp     loc_180006140
0x180005eb8  mov     cs:word_1800B5634, dx
0x180005ebf  jmp     loc_180006140
0x180005ec4  mov     eax, [rdi]
0x180005ec6  mov     cs:dword_1800B5630, eax
0x180005ecc  jmp     loc_180006140
0x180005ed1  sub     ecx, 0Ah
0x180005ed4  jz      short loc_180005F47
0x180005ed6  sub     ecx, r8d
0x180005ed9  jz      short loc_180005F07
0x180005edb  sub     ecx, 2
0x180005ede  jz      short loc_180005EF1
0x180005ee0  sub     ecx, r8d
0x180005ee3  jz      loc_180006140
0x180005ee9  mov     ebx, r8d
0x180005eec  jmp     loc_180006140
0x180005ef1  mov     eax, [rdi]
0x180005ef3  mov     cs:dword_1800B5644, eax
0x180005ef9  mov     eax, [rdi+8]
0x180005efc  mov     cs:dword_1800B5648, eax
0x180005f02  jmp     loc_180006140
0x180005f07  movaps  xmm0, cs:xmmword_1800B5690
0x180005f0e  mov     rax, [rdi]
0x180005f11  movups  xmmword ptr [rax], xmm0
0x180005f14  movaps  xmm1, cs:xmmword_1800B56A0
0x180005f1b  movups  xmmword ptr [rax+10h], xmm1
0x180005f1f  movaps  xmm0, cs:xmmword_1800B56B0
0x180005f26  movups  xmmword ptr [rax+20h], xmm0
0x180005f2a  movaps  xmm1, cs:xmmword_1800B56C0
0x180005f31  movups  xmmword ptr [rax+30h], xmm1
0x180005f35  movsd   xmm0, cs:qword_1800B56D0
0x180005f3d  movsd   qword ptr [rax+40h], xmm0
0x180005f42  jmp     loc_180006140
0x180005f47  mov     rax, [rdi]
0x180005f4a  movups  xmm0, xmmword ptr [rax]
0x180005f4d  movaps  cs:xmmword_1800B5690, xmm0
0x180005f54  movups  xmm1, xmmword ptr [rax+10h]
0x180005f58  movaps  cs:xmmword_1800B56A0, xmm1
0x180005f5f  movups  xmm0, xmmword ptr [rax+20h]
0x180005f63  movaps  cs:xmmword_1800B56B0, xmm0
0x180005f6a  movups  xmm1, xmmword ptr [rax+30h]
0x180005f6e  movaps  cs:xmmword_1800B56C0, xmm1
0x180005f75  movsd   xmm0, qword ptr [rax+40h]
0x180005f7a  movsd   cs:qword_1800B56D0, xmm0
0x180005f82  jmp     loc_180006140
0x180005f87  mov     rcx, [rdi+8]
0x180005f8b  mov     rax, [rdi]
0x180005f8e  mov     cs:qword_1800B57A8, rax
0x180005f95  mov     cs:qword_1800B57B0, rcx
0x180005f9c  jmp     loc_180006140
0x180005fa1  cmp     ecx, 18h
0x180005fa4  jg      loc_1800060F4
0x180005faa  jz      loc_1800060E9
0x180005fb0  sub     ecx, 11h
0x180005fb3  jz      loc_1800060DF
0x180005fb9  sub     ecx, r8d
0x180005fbc  jz      loc_18000608C
0x180005fc2  sub     ecx, r8d
0x180005fc5  jz      short loc_18000601C
0x180005fc7  sub     ecx, r8d
0x180005fca  jz      short loc_18000600F
0x180005fcc  cmp     ecx, 2
0x180005fcf  jnz     loc_180005EE9
0x180005fd5  mov     rcx, [rdi+8]
0x180005fd9  mov     eax, 7FFF0000h
0x180005fde  test    rcx, rcx
0x180005fe1  js      short loc_180005FE8
0x180005fe3  cmp     rcx, rax
0x180005fe6  jle     short loc_180005FEB
0x180005fe8  mov     rcx, rax
0x180005feb  cmp     [rdi], rdx
0x180005fee  mov     rax, rdx
0x180005ff1  cmovge  rax, [rdi]
0x180005ff5  cmp     rax, rcx
0x180005ff8  mov     cs:qword_1800B5760, rcx
0x180005fff  cmovle  rcx, rax
0x180006003  mov     cs:qword_1800B5758, rcx
0x18000600a  jmp     loc_180006140
0x18000600f  mov     al, [rdi]
0x180006011  mov     cs:byte_1800B5637, al
0x180006017  jmp     loc_180006140
0x18000601c  cmp     qword ptr cs:xmmword_1800B56E8, rdx
0x180006023  jnz     short loc_180006036
0x180006025  lea     rdx, qword_18009B2F0
0x18000602c  mov     ecx, 12h
0x180006031  call    sqlite3_config
0x180006036  movups  xmm0, cs:xmmword_1800B56D8
0x18000603d  mov     rax, [rdi]
0x180006040  movups  xmmword ptr [rax], xmm0
0x180006043  movups  xmm1, cs:xmmword_1800B56E8
0x18000604a  movups  xmmword ptr [rax+10h], xmm1
0x18000604e  movups  xmm0, cs:xmmword_1800B56F8
0x180006055  movups  xmmword ptr [rax+20h], xmm0
0x180006059  movups  xmm1, cs:xmmword_1800B5708
0x180006060  movups  xmmword ptr [rax+30h], xmm1
0x180006064  movups  xmm0, cs:xmmword_1800B5718
0x18000606b  movups  xmmword ptr [rax+40h], xmm0
0x18000606f  movups  xmm1, cs:xmmword_1800B5728
0x180006076  movups  xmmword ptr [rax+50h], xmm1
0x18000607a  movsd   xmm0, cs:qword_1800B5738
0x180006082  movsd   qword ptr [rax+60h], xmm0
0x180006087  jmp     loc_180006140
0x18000608c  mov     rax, [rdi]
0x18000608f  movups  xmm0, xmmword ptr [rax]
0x180006092  movups  cs:xmmword_1800B56D8, xmm0
0x180006099  movups  xmm1, xmmword ptr [rax+10h]
0x18000609d  movups  cs:xmmword_1800B56E8, xmm1
0x1800060a4  movups  xmm0, xmmword ptr [rax+20h]
0x1800060a8  movups  cs:xmmword_1800B56F8, xmm0
0x1800060af  movups  xmm1, xmmword ptr [rax+30h]
0x1800060b3  movups  cs:xmmword_1800B5708, xmm1
0x1800060ba  movups  xmm0, xmmword ptr [rax+40h]
0x1800060be  movups  cs:xmmword_1800B5718, xmm0
0x1800060c5  movups  xmm1, xmmword ptr [rax+50h]
0x1800060c9  movups  cs:xmmword_1800B5728, xmm1
0x1800060d0  movsd   xmm0, qword ptr [rax+60h]
0x1800060d5  movsd   cs:qword_1800B5738, xmm0
0x1800060dd  jmp     short loc_180006140
0x1800060df  mov     al, [rdi]
0x1800060e1  mov     cs:byte_1800B5636, al
0x1800060e7  jmp     short loc_180006140
0x1800060e9  mov     rax, [rdi]
0x1800060ec  mov     dword ptr [rax], 110h
0x1800060f2  jmp     short loc_180006140
0x1800060f4  sub     ecx, 19h
0x1800060f7  jz      short loc_180006138
0x1800060f9  sub     ecx, r8d
0x1800060fc  jz      short loc_18000612E
0x1800060fe  sub     ecx, r8d
0x180006101  jz      short loc_180006124
0x180006103  sub     ecx, 2
0x180006106  jz      short loc_180006118
0x180006108  cmp     ecx, r8d
0x18000610b  jnz     loc_180005EE9
0x180006111  mov     rax, [rdi]
0x180006114  mov     [rax], edx
0x180006116  jmp     short loc_180006140
0x180006118  mov     rax, [rdi]
0x18000611b  mov     cs:qword_1800B57B8, rax
0x180006122  jmp     short loc_180006140
0x180006124  mov     al, [rdi]
0x180006126  mov     cs:byte_1800B5638, al
0x18000612c  jmp     short loc_180006140
0x18000612e  mov     eax, [rdi]
0x180006130  mov     cs:dword_1800B564C, eax
0x180006136  jmp     short loc_180006140
0x180006138  mov     ecx, [rdi]
0x18000613a  mov     cs:dword_1800B5780, ecx
0x180006140  mov     eax, ebx
0x180006142  add     rsp, 38h
0x180006146  pop     rdi
0x180006147  pop     rbx
0x180006148  retn
```
