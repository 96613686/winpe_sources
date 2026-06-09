# FindSubstituteEuro

- ea: `0x18000ff24`
- end: `0x180010239`
- name: `FindSubstituteEuro`
- size: `789`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e800`

## callees

- `0x180001ee0`
- `0x18000f4a8`
- `0x18000ff24`

## string_xrefs

- `0x18000ff69`: `Courier`
- `0x18000ff9b`: `Courier-Oblique`
- `0x18000ffd3`: `Courier-Bold`
- `0x180010005`: `Courier-BoldOblique`

## pseudocode

```c
__int64 __fastcall FindSubstituteEuro(__int64 a1, char a2, __int16 a3, __int16 a4)
{
  __int64 v4; // rdx
  bool v5; // zf
  __int64 v6; // rax
  _BYTE *v7; // r8
  const char *v8; // r9
  const char *v9; // r9
  const char *v10; // r9
  const char *v11; // r9
  __int64 v12; // rax
  const char *v13; // r9
  const char *v14; // r9
  const char *v15; // r9
  const char *v16; // r9
  __int64 v17; // rax
  const char *v18; // r9
  const char *v19; // r9
  const char *v20; // r9
  const char *v21; // r9
  _BYTE *v22; // rax
  _BYTE v24[64]; // [rsp+20h] [rbp-50h] BYREF

  if ( (a2 & 1) != 0 )
  {
    v4 = 60;
    v5 = a3 == 0;
    v6 = 2147483646;
    v7 = v24;
    if ( v5 )
    {
      if ( a4 )
      {
        v9 = "Courier-Oblique";
        do
        {
          if ( !v6 )
            break;
          if ( !*v9 )
            break;
          *v7++ = *v9++;
          --v6;
          --v4;
        }
        while ( v4 );
      }
      else
      {
        v8 = "Courier";
        do
        {
          if ( !v6 )
            break;
          if ( !*v8 )
            break;
          *v7++ = *v8++;
          --v6;
          --v4;
        }
        while ( v4 );
      }
    }
    else if ( a4 )
    {
      v11 = "Courier-BoldOblique";
      do
      {
        if ( !v6 )
          break;
        if ( !*v11 )
          break;
        *v7++ = *v11++;
        --v6;
        --v4;
      }
      while ( v4 );
    }
    else
    {
      v10 = "Courier-Bold";
      do
      {
        if ( !v6 )
          break;
        if ( !*v10 )
          break;
        *v7++ = *v10++;
        --v6;
        --v4;
      }
      while ( v4 );
    }
  }
  else if ( (a2 & 0x10) != 0 )
  {
    v12 = 2147483646;
    v5 = a3 == 0;
    v7 = v24;
    v4 = 60;
    if ( v5 )
    {
      if ( a4 )
      {
        v14 = "Times-Italic";
        do
        {
          if ( !v12 )
            break;
          if ( !*v14 )
            break;
          *v7++ = *v14++;
          --v12;
          --v4;
        }
        while ( v4 );
      }
      else
      {
        v13 = "Times-Roman";
        do
        {
          if ( !v12 )
            break;
          if ( !*v13 )
            break;
          *v7++ = *v13++;
          --v12;
          --v4;
        }
        while ( v4 );
      }
    }
    else if ( a4 )
    {
      v16 = "Times-BoldItalic";
      do
      {
        if ( !v12 )
          break;
        if ( !*v16 )
          break;
        *v7++ = *v16++;
        --v12;
        --v4;
      }
      while ( v4 );
    }
    else
    {
      v15 = "Times-Bold";
      do
      {
        if ( !v12 )
          break;
        if ( !*v15 )
          break;
        *v7++ = *v15++;
        --v12;
        --v4;
      }
      while ( v4 );
    }
  }
  else
  {
    if ( (a2 & 0x20) == 0 )
      return 0xFFFFFFFFLL;
    v17 = 2147483646;
    v5 = a3 == 0;
    v7 = v24;
    v4 = 60;
    if ( v5 )
    {
      if ( a4 )
      {
        v19 = "Helvetica-Oblique";
        do
        {
          if ( !v17 )
            break;
          if ( !*v19 )
            break;
          *v7++ = *v19++;
          --v17;
          --v4;
        }
        while ( v4 );
      }
      else
      {
        v18 = "Helvetica";
        do
        {
          if ( !v17 )
            break;
          if ( !*v18 )
            break;
          *v7++ = *v18++;
          --v17;
          --v4;
        }
        while ( v4 );
      }
    }
    else if ( a4 )
    {
      v21 = "Helvetica-BoldOblique";
      do
      {
        if ( !v17 )
          break;
        if ( !*v21 )
          break;
        *v7++ = *v21++;
        --v17;
        --v4;
      }
      while ( v4 );
    }
    else
    {
      v20 = "Helvetica-Bold";
      do
      {
        if ( !v17 )
          break;
        if ( !*v20 )
          break;
        *v7++ = *v20++;
        --v17;
        --v4;
      }
      while ( v4 );
    }
  }
  v22 = v7 - 1;
  if ( v4 )
    v22 = v7;
  *v22 = 0;
  return BSearchNameIndex(*(_QWORD *)(a1 + 3712), v24, v7, (unsigned int)(*(_DWORD *)(a1 + 3720) - 1));
}

```

## disassembly

```asm
0x18000ff24  mov     [rsp-8+arg_8], rbx
0x18000ff29  push    rbp
0x18000ff2a  mov     rbp, rsp
0x18000ff2d  sub     rsp, 70h
0x18000ff31  mov     rax, cs:__security_cookie
0x18000ff38  xor     rax, rsp
0x18000ff3b  mov     [rbp+var_10], rax
0x18000ff3f  mov     ebx, 1
0x18000ff44  mov     r11, rcx
0x18000ff47  test    bl, dl
0x18000ff49  jz      loc_180010037
0x18000ff4f  xor     ecx, ecx
0x18000ff51  lea     edx, [rbx+3Bh]
0x18000ff54  test    r8w, r8w
0x18000ff58  mov     eax, 7FFFFFFEh
0x18000ff5d  lea     r8, [rbp+var_50]
0x18000ff61  jnz     short loc_18000FFCD
0x18000ff63  test    r9w, r9w
0x18000ff67  jnz     short loc_18000FF9B
0x18000ff69  lea     r9, aCourier_0; "Courier"
0x18000ff70  test    rax, rax
0x18000ff73  jz      loc_1800101F3
0x18000ff79  mov     r10b, [r9]
0x18000ff7c  test    r10b, r10b
0x18000ff7f  jz      loc_1800101F3
0x18000ff85  mov     [r8], r10b
0x18000ff88  add     r9, rbx
0x18000ff8b  add     r8, rbx
0x18000ff8e  sub     rax, rbx
0x18000ff91  sub     rdx, rbx
0x18000ff94  jnz     short loc_18000FF70
0x18000ff96  jmp     loc_1800101F3
0x18000ff9b  lea     r9, aCourierOblique; "Courier-Oblique"
0x18000ffa2  test    rax, rax
0x18000ffa5  jz      loc_1800101F3
0x18000ffab  mov     r10b, [r9]
0x18000ffae  test    r10b, r10b
0x18000ffb1  jz      loc_1800101F3
0x18000ffb7  mov     [r8], r10b
0x18000ffba  add     r9, rbx
0x18000ffbd  add     r8, rbx
0x18000ffc0  sub     rax, rbx
0x18000ffc3  sub     rdx, rbx
0x18000ffc6  jnz     short loc_18000FFA2
0x18000ffc8  jmp     loc_1800101F3
0x18000ffcd  test    r9w, r9w
0x18000ffd1  jnz     short loc_180010005
0x18000ffd3  lea     r9, aCourierBold; "Courier-Bold"
0x18000ffda  test    rax, rax
0x18000ffdd  jz      loc_1800101F3
0x18000ffe3  mov     r10b, [r9]
0x18000ffe6  test    r10b, r10b
0x18000ffe9  jz      loc_1800101F3
0x18000ffef  mov     [r8], r10b
0x18000fff2  add     r9, rbx
0x18000fff5  add     r8, rbx
0x18000fff8  sub     rax, rbx
0x18000fffb  sub     rdx, rbx
0x18000fffe  jnz     short loc_18000FFDA
0x180010000  jmp     loc_1800101F3
0x180010005  lea     r9, aCourierBoldobl; "Courier-BoldOblique"
0x18001000c  test    rax, rax
0x18001000f  jz      loc_1800101F3
0x180010015  mov     r10b, [r9]
0x180010018  test    r10b, r10b
0x18001001b  jz      loc_1800101F3
0x180010021  mov     [r8], r10b
0x180010024  add     r9, rbx
0x180010027  add     r8, rbx
0x18001002a  sub     rax, rbx
0x18001002d  sub     rdx, rbx
0x180010030  jnz     short loc_18001000C
0x180010032  jmp     loc_1800101F3
0x180010037  test    dl, 10h
0x18001003a  jz      loc_180010128
0x180010040  xor     ecx, ecx
0x180010042  mov     eax, 7FFFFFFEh
0x180010047  test    r8w, r8w
0x18001004b  lea     r8, [rbp+var_50]
0x18001004f  lea     edx, [rcx+3Ch]
0x180010052  jnz     short loc_1800100BE
0x180010054  test    r9w, r9w
0x180010058  jnz     short loc_18001008C
0x18001005a  lea     r9, aTimesRoman; "Times-Roman"
0x180010061  test    rax, rax
0x180010064  jz      loc_1800101F3
0x18001006a  mov     r10b, [r9]
0x18001006d  test    r10b, r10b
0x180010070  jz      loc_1800101F3
0x180010076  mov     [r8], r10b
0x180010079  add     r9, rbx
0x18001007c  add     r8, rbx
0x18001007f  sub     rax, rbx
0x180010082  sub     rdx, rbx
0x180010085  jnz     short loc_180010061
0x180010087  jmp     loc_1800101F3
0x18001008c  lea     r9, aTimesItalic; "Times-Italic"
0x180010093  test    rax, rax
0x180010096  jz      loc_1800101F3
0x18001009c  mov     r10b, [r9]
0x18001009f  test    r10b, r10b
0x1800100a2  jz      loc_1800101F3
0x1800100a8  mov     [r8], r10b
0x1800100ab  add     r9, rbx
0x1800100ae  add     r8, rbx
0x1800100b1  sub     rax, rbx
0x1800100b4  sub     rdx, rbx
0x1800100b7  jnz     short loc_180010093
0x1800100b9  jmp     loc_1800101F3
0x1800100be  test    r9w, r9w
0x1800100c2  jnz     short loc_1800100F6
0x1800100c4  lea     r9, aTimesBold; "Times-Bold"
0x1800100cb  test    rax, rax
0x1800100ce  jz      loc_1800101F3
0x1800100d4  mov     r10b, [r9]
0x1800100d7  test    r10b, r10b
0x1800100da  jz      loc_1800101F3
0x1800100e0  mov     [r8], r10b
0x1800100e3  add     r9, rbx
0x1800100e6  add     r8, rbx
0x1800100e9  sub     rax, rbx
0x1800100ec  sub     rdx, rbx
0x1800100ef  jnz     short loc_1800100CB
0x1800100f1  jmp     loc_1800101F3
0x1800100f6  lea     r9, aTimesBolditali; "Times-BoldItalic"
0x1800100fd  test    rax, rax
0x180010100  jz      loc_1800101F3
0x180010106  mov     r10b, [r9]
0x180010109  test    r10b, r10b
0x18001010c  jz      loc_1800101F3
0x180010112  mov     [r8], r10b
0x180010115  add     r9, rbx
0x180010118  add     r8, rbx
0x18001011b  sub     rax, rbx
0x18001011e  sub     rdx, rbx
0x180010121  jnz     short loc_1800100FD
0x180010123  jmp     loc_1800101F3
0x180010128  test    dl, 20h
0x18001012b  jz      loc_18001021C
0x180010131  xor     ecx, ecx
0x180010133  mov     eax, 7FFFFFFEh
0x180010138  test    r8w, r8w
0x18001013c  lea     r8, [rbp+var_50]
0x180010140  lea     edx, [rcx+3Ch]
0x180010143  jnz     short loc_1800101A1
0x180010145  test    r9w, r9w
0x180010149  jnz     short loc_18001017A
0x18001014b  lea     r9, aHelvetica; "Helvetica"
0x180010152  test    rax, rax
0x180010155  jz      loc_1800101F3
0x18001015b  mov     r10b, [r9]
0x18001015e  test    r10b, r10b
0x180010161  jz      loc_1800101F3
0x180010167  mov     [r8], r10b
0x18001016a  add     r9, rbx
0x18001016d  add     r8, rbx
0x180010170  sub     rax, rbx
0x180010173  sub     rdx, rbx
0x180010176  jnz     short loc_180010152
0x180010178  jmp     short loc_1800101F3
0x18001017a  lea     r9, aHelveticaObliq; "Helvetica-Oblique"
0x180010181  test    rax, rax
0x180010184  jz      short loc_1800101F3
0x180010186  mov     r10b, [r9]
0x180010189  test    r10b, r10b
0x18001018c  jz      short loc_1800101F3
0x18001018e  mov     [r8], r10b
0x180010191  add     r9, rbx
0x180010194  add     r8, rbx
0x180010197  sub     rax, rbx
0x18001019a  sub     rdx, rbx
0x18001019d  jnz     short loc_180010181
0x18001019f  jmp     short loc_1800101F3
0x1800101a1  test    r9w, r9w
0x1800101a5  jnz     short loc_1800101CE
0x1800101a7  lea     r9, aHelveticaBold; "Helvetica-Bold"
0x1800101ae  test    rax, rax
0x1800101b1  jz      short loc_1800101F3
0x1800101b3  mov     r10b, [r9]
0x1800101b6  test    r10b, r10b
0x1800101b9  jz      short loc_1800101F3
0x1800101bb  mov     [r8], r10b
0x1800101be  add     r9, rbx
0x1800101c1  add     r8, rbx
0x1800101c4  sub     rax, rbx
0x1800101c7  sub     rdx, rbx
0x1800101ca  jnz     short loc_1800101AE
0x1800101cc  jmp     short loc_1800101F3
0x1800101ce  lea     r9, aHelveticaBoldo; "Helvetica-BoldOblique"
0x1800101d5  test    rax, rax
0x1800101d8  jz      short loc_1800101F3
0x1800101da  mov     r10b, [r9]
0x1800101dd  test    r10b, r10b
0x1800101e0  jz      short loc_1800101F3
0x1800101e2  mov     [r8], r10b
0x1800101e5  add     r9, rbx
0x1800101e8  add     r8, rbx
0x1800101eb  sub     rax, rbx
0x1800101ee  sub     rdx, rbx
0x1800101f1  jnz     short loc_1800101D5
0x1800101f3  test    rdx, rdx
0x1800101f6  lea     rax, [r8-1]
0x1800101fa  lea     rdx, [rbp+var_50]
0x1800101fe  cmovnz  rax, r8
0x180010202  mov     [rax], cl
0x180010204  mov     r9d, [r11+0E88h]
0x18001020b  mov     rcx, [r11+0E80h]
0x180010212  sub     r9d, ebx
0x180010215  call    BSearchNameIndex
0x18001021a  jmp     short loc_18001021F
0x18001021c  or      eax, 0FFFFFFFFh
0x18001021f  mov     rcx, [rbp+var_10]
0x180010223  xor     rcx, rsp; StackCookie
0x180010226  call    __security_check_cookie
0x18001022b  mov     rbx, [rsp+70h+arg_8]
0x180010233  add     rsp, 70h
0x180010237  pop     rbp
0x180010238  retn
```
