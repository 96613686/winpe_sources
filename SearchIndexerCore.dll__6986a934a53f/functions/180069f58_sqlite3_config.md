# sqlite3_config

- ea: `0x180069f58`
- end: `0x18006a377`
- name: `sqlite3_config`
- size: `1055`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18004b508`
- `0x180069d50`
- `0x180069f40`
- `0x180069f58`

## callees

- `0x1800257e0`
- `0x180069f40`
- `0x180069f58`

## pseudocode

```c
__int64 __fastcall sqlite3_config(int a1, __int64 a2, unsigned __int64 a3, int a4)
{
  unsigned int v4; // ebx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  __int64 v10; // rcx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  __int64 v18; // rcx
  __int64 v19; // rax
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx

  if ( dword_1800D09C4 && ((unsigned int)a1 > 0x3F || ((1LL << a1) & 0x1010000) == 0) )
  {
    v4 = 21;
    sqlite3_log(
      21,
      "%s at line %d of [%.10s]",
      "misuse",
      180664,
      "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
    return v4;
  }
  v4 = 0;
  if ( a1 > 16 )
  {
    if ( a1 > 24 )
    {
      v20 = a1 - 25;
      if ( !v20 )
      {
        dword_1800D09C0 = a2;
        return v4;
      }
      v21 = v20 - 1;
      if ( !v21 )
      {
        dword_1800D088C = a2;
        return v4;
      }
      v22 = v21 - 1;
      if ( !v22 )
      {
        byte_1800D0878 = a2;
        return v4;
      }
      v23 = v22 - 2;
      if ( !v23 )
      {
        qword_1800D09F8 = a2;
        return v4;
      }
      if ( v23 == 1 )
      {
        *(_DWORD *)a2 = 0;
        return v4;
      }
      return 1;
    }
    if ( a1 == 24 )
    {
      *(_DWORD *)a2 = 272;
      return v4;
    }
    v14 = a1 - 17;
    if ( !v14 )
    {
      byte_1800D0876 = a2;
      return v4;
    }
    v15 = v14 - 1;
    if ( !v15 )
    {
      *(_OWORD *)&qword_1800D0918 = *(_OWORD *)a2;
      xmmword_1800D0928 = *(_OWORD *)(a2 + 16);
      xmmword_1800D0938 = *(_OWORD *)(a2 + 32);
      xmmword_1800D0948 = *(_OWORD *)(a2 + 48);
      xmmword_1800D0958 = *(_OWORD *)(a2 + 64);
      xmmword_1800D0968 = *(_OWORD *)(a2 + 80);
      qword_1800D0978 = *(_QWORD *)(a2 + 96);
      return v4;
    }
    v16 = v15 - 1;
    if ( v16 )
    {
      v17 = v16 - 1;
      if ( !v17 )
      {
        byte_1800D0877 = a2;
        return v4;
      }
      if ( v17 != 2 )
        return 1;
      v18 = a3;
      if ( a3 > 0x7FFF0000 )
        v18 = 2147418112;
      v19 = 0;
      if ( a2 >= 0 )
        v19 = a2;
      qword_1800D09A0 = v18;
      if ( v19 <= v18 )
        v18 = v19;
      qword_1800D0998 = v18;
    }
    else
    {
      if ( !(_QWORD)xmmword_1800D0928 )
        sqlite3_config(18, qword_1800B1AF0, 1);
      *(_OWORD *)a2 = *(_OWORD *)&qword_1800D0918;
      *(_OWORD *)(a2 + 16) = xmmword_1800D0928;
      *(_OWORD *)(a2 + 32) = xmmword_1800D0938;
      *(_OWORD *)(a2 + 48) = xmmword_1800D0948;
      *(_OWORD *)(a2 + 64) = xmmword_1800D0958;
      *(_OWORD *)(a2 + 80) = xmmword_1800D0968;
      *(_QWORD *)(a2 + 96) = qword_1800D0978;
    }
  }
  else
  {
    if ( a1 == 16 )
    {
      qword_1800D09E8 = a2;
      qword_1800D09F0 = a3;
      return v4;
    }
    if ( a1 > 9 )
    {
      v11 = a1 - 10;
      if ( !v11 )
      {
        xmmword_1800D08D0 = *(_OWORD *)a2;
        xmmword_1800D08E0 = *(_OWORD *)(a2 + 16);
        xmmword_1800D08F0 = *(_OWORD *)(a2 + 32);
        xmmword_1800D0900 = *(_OWORD *)(a2 + 48);
        qword_1800D0910 = *(_QWORD *)(a2 + 64);
        return v4;
      }
      v12 = v11 - 1;
      if ( !v12 )
      {
        *(_OWORD *)a2 = xmmword_1800D08D0;
        *(_OWORD *)(a2 + 16) = xmmword_1800D08E0;
        *(_OWORD *)(a2 + 32) = xmmword_1800D08F0;
        *(_OWORD *)(a2 + 48) = xmmword_1800D0900;
        *(_QWORD *)(a2 + 64) = qword_1800D0910;
        return v4;
      }
      v13 = v12 - 2;
      if ( !v13 )
      {
        dword_1800D0884 = a2;
        dword_1800D0888 = a3;
        return v4;
      }
      if ( v13 != 1 )
        return 1;
    }
    else
    {
      if ( a1 == 9 )
      {
        dword_1800D0870 = a2;
        return v4;
      }
      v5 = a1 - 1;
      if ( !v5 )
      {
        word_1800D0874 = 0;
        return v4;
      }
      v6 = v5 - 1;
      if ( !v6 )
      {
        word_1800D0874 = 1;
        return v4;
      }
      v7 = v6 - 1;
      if ( !v7 )
      {
        word_1800D0874 = 257;
        return v4;
      }
      v8 = v7 - 1;
      if ( !v8 )
      {
        qword_1800D0890 = *(_QWORD *)a2;
        xmmword_1800D0898 = *(_OWORD *)(a2 + 8);
        xmmword_1800D08A8 = *(_OWORD *)(a2 + 24);
        xmmword_1800D08B8 = *(_OWORD *)(a2 + 40);
        qword_1800D08C8 = *(_QWORD *)(a2 + 56);
        return v4;
      }
      v9 = v8 - 1;
      if ( v9 )
      {
        if ( v9 == 2 )
        {
          qword_1800D09A8 = a2;
          dword_1800D09B0 = a3;
          dword_1800D09B4 = a4;
          return v4;
        }
        return 1;
      }
      v10 = qword_1800D0890;
      if ( !qword_1800D0890 )
      {
        sqlite3MemSetDefault(0, 0, 1);
        v10 = qword_1800D0890;
      }
      *(_QWORD *)a2 = v10;
      *(_OWORD *)(a2 + 8) = xmmword_1800D0898;
      *(_OWORD *)(a2 + 24) = xmmword_1800D08A8;
      *(_OWORD *)(a2 + 40) = xmmword_1800D08B8;
      *(_QWORD *)(a2 + 56) = qword_1800D08C8;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180069f58  mov     rax, rsp
0x180069f5b  mov     [rax+8], ecx
0x180069f5e  mov     [rax+10h], rdx
0x180069f62  mov     [rax+18h], r8
0x180069f66  mov     [rax+20h], r9
0x180069f6a  push    rbx
0x180069f6b  push    rdi
0x180069f6c  sub     rsp, 48h
0x180069f70  xor     edx, edx
0x180069f72  cmp     cs:dword_1800D09C4, edx
0x180069f78  lea     r8d, [rdx+1]
0x180069f7c  jz      short loc_180069FC2
0x180069f7e  cmp     ecx, 3Fh ; '?'
0x180069f81  ja      short loc_180069F91
0x180069f83  mov     eax, r8d
0x180069f86  shl     rax, cl
0x180069f89  test    rax, 1010000h
0x180069f8f  jnz     short loc_180069FC2
0x180069f91  lea     rax, a20240523134606+14h; "18a3cf29885901ce73120761875ccdd0e3704e3"...
0x180069f98  mov     ebx, 15h
0x180069f9d  mov     ecx, ebx
0x180069f9f  mov     [rsp+58h+var_38], rax
0x180069fa4  mov     r9d, 2C1B8h
0x180069faa  lea     r8, aMisuse; "misuse"
0x180069fb1  lea     rdx, aSAtLineDOf10s; "%s at line %d of [%.10s]"
0x180069fb8  call    sqlite3_log
0x180069fbd  jmp     loc_18006A36E
0x180069fc2  lea     rdi, [rsp+58h+arg_8]
0x180069fc7  mov     ebx, edx
0x180069fc9  cmp     ecx, 10h
0x180069fcc  jg      loc_18006A1CF
0x180069fd2  jz      loc_18006A1B5
0x180069fd8  cmp     ecx, 9
0x180069fdb  jg      loc_18006A0FF
0x180069fe1  jz      loc_18006A0F2
0x180069fe7  sub     ecx, r8d
0x180069fea  jz      loc_18006A0E6
0x180069ff0  sub     ecx, r8d
0x180069ff3  jz      loc_18006A0D9
0x180069ff9  sub     ecx, r8d
0x180069ffc  jz      loc_18006A0CB
0x18006a002  sub     ecx, r8d
0x18006a005  jz      loc_18006A08B
0x18006a00b  sub     ecx, r8d
0x18006a00e  jz      short loc_18006A03A
0x18006a010  cmp     ecx, 2
0x18006a013  jnz     loc_18006A117
0x18006a019  mov     rax, [rdi]
0x18006a01c  mov     cs:qword_1800D09A8, rax
0x18006a023  mov     eax, [rdi+8]
0x18006a026  mov     cs:dword_1800D09B0, eax
0x18006a02c  mov     eax, [rdi+10h]
0x18006a02f  mov     cs:dword_1800D09B4, eax
0x18006a035  jmp     loc_18006A36E
0x18006a03a  mov     rcx, cs:qword_1800D0890
0x18006a041  test    rcx, rcx
0x18006a044  jnz     short loc_18006A052
0x18006a046  call    sqlite3MemSetDefault
0x18006a04b  mov     rcx, cs:qword_1800D0890
0x18006a052  mov     rax, [rdi]
0x18006a055  mov     [rax], rcx
0x18006a058  movups  xmm0, cs:xmmword_1800D0898
0x18006a05f  movups  xmmword ptr [rax+8], xmm0
0x18006a063  movups  xmm1, cs:xmmword_1800D08A8
0x18006a06a  movups  xmmword ptr [rax+18h], xmm1
0x18006a06e  movups  xmm0, cs:xmmword_1800D08B8
0x18006a075  movups  xmmword ptr [rax+28h], xmm0
0x18006a079  movsd   xmm1, cs:qword_1800D08C8
0x18006a081  movsd   qword ptr [rax+38h], xmm1
0x18006a086  jmp     loc_18006A36E
0x18006a08b  mov     rcx, [rdi]
0x18006a08e  mov     rax, [rcx]
0x18006a091  mov     cs:qword_1800D0890, rax
0x18006a098  movups  xmm0, xmmword ptr [rcx+8]
0x18006a09c  movups  cs:xmmword_1800D0898, xmm0
0x18006a0a3  movups  xmm1, xmmword ptr [rcx+18h]
0x18006a0a7  movups  cs:xmmword_1800D08A8, xmm1
0x18006a0ae  movups  xmm0, xmmword ptr [rcx+28h]
0x18006a0b2  movups  cs:xmmword_1800D08B8, xmm0
0x18006a0b9  movsd   xmm1, qword ptr [rcx+38h]
0x18006a0be  movsd   cs:qword_1800D08C8, xmm1
0x18006a0c6  jmp     loc_18006A36E
0x18006a0cb  mov     cs:word_1800D0874, 101h
0x18006a0d4  jmp     loc_18006A36E
0x18006a0d9  mov     cs:word_1800D0874, r8w
0x18006a0e1  jmp     loc_18006A36E
0x18006a0e6  mov     cs:word_1800D0874, dx
0x18006a0ed  jmp     loc_18006A36E
0x18006a0f2  mov     eax, [rdi]
0x18006a0f4  mov     cs:dword_1800D0870, eax
0x18006a0fa  jmp     loc_18006A36E
0x18006a0ff  sub     ecx, 0Ah
0x18006a102  jz      short loc_18006A175
0x18006a104  sub     ecx, r8d
0x18006a107  jz      short loc_18006A135
0x18006a109  sub     ecx, 2
0x18006a10c  jz      short loc_18006A11F
0x18006a10e  sub     ecx, r8d
0x18006a111  jz      loc_18006A36E
0x18006a117  mov     ebx, r8d
0x18006a11a  jmp     loc_18006A36E
0x18006a11f  mov     eax, [rdi]
0x18006a121  mov     cs:dword_1800D0884, eax
0x18006a127  mov     eax, [rdi+8]
0x18006a12a  mov     cs:dword_1800D0888, eax
0x18006a130  jmp     loc_18006A36E
0x18006a135  movaps  xmm0, cs:xmmword_1800D08D0
0x18006a13c  mov     rax, [rdi]
0x18006a13f  movups  xmmword ptr [rax], xmm0
0x18006a142  movaps  xmm1, cs:xmmword_1800D08E0
0x18006a149  movups  xmmword ptr [rax+10h], xmm1
0x18006a14d  movaps  xmm0, cs:xmmword_1800D08F0
0x18006a154  movups  xmmword ptr [rax+20h], xmm0
0x18006a158  movaps  xmm1, cs:xmmword_1800D0900
0x18006a15f  movups  xmmword ptr [rax+30h], xmm1
0x18006a163  movsd   xmm0, cs:qword_1800D0910
0x18006a16b  movsd   qword ptr [rax+40h], xmm0
0x18006a170  jmp     loc_18006A36E
0x18006a175  mov     rax, [rdi]
0x18006a178  movups  xmm0, xmmword ptr [rax]
0x18006a17b  movaps  cs:xmmword_1800D08D0, xmm0
0x18006a182  movups  xmm1, xmmword ptr [rax+10h]
0x18006a186  movaps  cs:xmmword_1800D08E0, xmm1
0x18006a18d  movups  xmm0, xmmword ptr [rax+20h]
0x18006a191  movaps  cs:xmmword_1800D08F0, xmm0
0x18006a198  movups  xmm1, xmmword ptr [rax+30h]
0x18006a19c  movaps  cs:xmmword_1800D0900, xmm1
0x18006a1a3  movsd   xmm0, qword ptr [rax+40h]
0x18006a1a8  movsd   cs:qword_1800D0910, xmm0
0x18006a1b0  jmp     loc_18006A36E
0x18006a1b5  mov     rcx, [rdi+8]
0x18006a1b9  mov     rax, [rdi]
0x18006a1bc  mov     cs:qword_1800D09E8, rax
0x18006a1c3  mov     cs:qword_1800D09F0, rcx
0x18006a1ca  jmp     loc_18006A36E
0x18006a1cf  cmp     ecx, 18h
0x18006a1d2  jg      loc_18006A322
0x18006a1d8  jz      loc_18006A317
0x18006a1de  sub     ecx, 11h
0x18006a1e1  jz      loc_18006A30D
0x18006a1e7  sub     ecx, r8d
0x18006a1ea  jz      loc_18006A2BA
0x18006a1f0  sub     ecx, r8d
0x18006a1f3  jz      short loc_18006A24A
0x18006a1f5  sub     ecx, r8d
0x18006a1f8  jz      short loc_18006A23D
0x18006a1fa  cmp     ecx, 2
0x18006a1fd  jnz     loc_18006A117
0x18006a203  mov     rcx, [rdi+8]
0x18006a207  mov     eax, 7FFF0000h
0x18006a20c  test    rcx, rcx
0x18006a20f  js      short loc_18006A216
0x18006a211  cmp     rcx, rax
0x18006a214  jle     short loc_18006A219
0x18006a216  mov     rcx, rax
0x18006a219  cmp     [rdi], rdx
0x18006a21c  mov     rax, rdx
0x18006a21f  cmovge  rax, [rdi]
0x18006a223  cmp     rax, rcx
0x18006a226  mov     cs:qword_1800D09A0, rcx
0x18006a22d  cmovle  rcx, rax
0x18006a231  mov     cs:qword_1800D0998, rcx
0x18006a238  jmp     loc_18006A36E
0x18006a23d  mov     al, [rdi]
0x18006a23f  mov     cs:byte_1800D0877, al
0x18006a245  jmp     loc_18006A36E
0x18006a24a  cmp     qword ptr cs:xmmword_1800D0928, rdx
0x18006a251  jnz     short loc_18006A264
0x18006a253  lea     rdx, qword_1800B1AF0
0x18006a25a  mov     ecx, 12h
0x18006a25f  call    sqlite3_config
0x18006a264  movups  xmm0, xmmword ptr cs:qword_1800D0918
0x18006a26b  mov     rax, [rdi]
0x18006a26e  movups  xmmword ptr [rax], xmm0
0x18006a271  movups  xmm1, cs:xmmword_1800D0928
0x18006a278  movups  xmmword ptr [rax+10h], xmm1
0x18006a27c  movups  xmm0, cs:xmmword_1800D0938
0x18006a283  movups  xmmword ptr [rax+20h], xmm0
0x18006a287  movups  xmm1, cs:xmmword_1800D0948
0x18006a28e  movups  xmmword ptr [rax+30h], xmm1
0x18006a292  movups  xmm0, cs:xmmword_1800D0958
0x18006a299  movups  xmmword ptr [rax+40h], xmm0
0x18006a29d  movups  xmm1, cs:xmmword_1800D0968
0x18006a2a4  movups  xmmword ptr [rax+50h], xmm1
0x18006a2a8  movsd   xmm0, cs:qword_1800D0978
0x18006a2b0  movsd   qword ptr [rax+60h], xmm0
0x18006a2b5  jmp     loc_18006A36E
0x18006a2ba  mov     rax, [rdi]
0x18006a2bd  movups  xmm0, xmmword ptr [rax]
0x18006a2c0  movups  xmmword ptr cs:qword_1800D0918, xmm0
0x18006a2c7  movups  xmm1, xmmword ptr [rax+10h]
0x18006a2cb  movups  cs:xmmword_1800D0928, xmm1
0x18006a2d2  movups  xmm0, xmmword ptr [rax+20h]
0x18006a2d6  movups  cs:xmmword_1800D0938, xmm0
0x18006a2dd  movups  xmm1, xmmword ptr [rax+30h]
0x18006a2e1  movups  cs:xmmword_1800D0948, xmm1
0x18006a2e8  movups  xmm0, xmmword ptr [rax+40h]
0x18006a2ec  movups  cs:xmmword_1800D0958, xmm0
0x18006a2f3  movups  xmm1, xmmword ptr [rax+50h]
0x18006a2f7  movups  cs:xmmword_1800D0968, xmm1
0x18006a2fe  movsd   xmm0, qword ptr [rax+60h]
0x18006a303  movsd   cs:qword_1800D0978, xmm0
0x18006a30b  jmp     short loc_18006A36E
0x18006a30d  mov     al, [rdi]
0x18006a30f  mov     cs:byte_1800D0876, al
0x18006a315  jmp     short loc_18006A36E
0x18006a317  mov     rax, [rdi]
0x18006a31a  mov     dword ptr [rax], 110h
0x18006a320  jmp     short loc_18006A36E
0x18006a322  sub     ecx, 19h
0x18006a325  jz      short loc_18006A366
0x18006a327  sub     ecx, r8d
0x18006a32a  jz      short loc_18006A35C
0x18006a32c  sub     ecx, r8d
0x18006a32f  jz      short loc_18006A352
0x18006a331  sub     ecx, 2
0x18006a334  jz      short loc_18006A346
0x18006a336  cmp     ecx, r8d
0x18006a339  jnz     loc_18006A117
0x18006a33f  mov     rax, [rdi]
0x18006a342  mov     [rax], edx
0x18006a344  jmp     short loc_18006A36E
0x18006a346  mov     rax, [rdi]
0x18006a349  mov     cs:qword_1800D09F8, rax
0x18006a350  jmp     short loc_18006A36E
0x18006a352  mov     al, [rdi]
0x18006a354  mov     cs:byte_1800D0878, al
0x18006a35a  jmp     short loc_18006A36E
0x18006a35c  mov     eax, [rdi]
0x18006a35e  mov     cs:dword_1800D088C, eax
0x18006a364  jmp     short loc_18006A36E
0x18006a366  mov     ecx, [rdi]
0x18006a368  mov     cs:dword_1800D09C0, ecx
0x18006a36e  mov     eax, ebx
0x18006a370  add     rsp, 48h
0x18006a374  pop     rdi
0x18006a375  pop     rbx
0x18006a376  retn
```
