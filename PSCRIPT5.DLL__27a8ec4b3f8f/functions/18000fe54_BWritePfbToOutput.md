# BWritePfbToOutput

- ea: `0x18000fe54`
- end: `0x1800101c2`
- name: `BWritePfbToOutput`
- size: `878`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000f2e4`
- `0x18000f9d4`

## callees

- `0x180001f20`
- `0x18000fe54`
- `0x1800170a0`
- `0x180017644`
- `0x18001b388`
- `0x18001b6f0`
- `0x18005f010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800100f5`
- `KERNEL32!SetLastError` at `0x180010148`
- `KERNEL32!SetLastError` at `0x1800100f5`
- `KERNEL32!SetLastError` at `0x180010148`
- `KERNEL32!LocalFree` at `0x180010111`
- `KERNEL32!LocalFree` at `0x180010111`
- `KERNEL32!LocalAlloc` at `0x18000ffe8`
- `KERNEL32!LocalAlloc` at `0x18000ffe8`

## pseudocode

```c
__int64 __fastcall BWritePfbToOutput(__int64 a1, __int64 a2, _DWORD *a3)
{
  int v3; // eax
  int v6; // ebx
  _BYTE *v7; // r14
  unsigned __int64 v8; // rbp
  __int64 v9; // r15
  const char *v10; // rdx
  unsigned int v11; // edi
  unsigned __int64 v12; // rax
  unsigned int v13; // eax
  unsigned __int64 v14; // r12
  char *v15; // rax
  char v16; // r15
  char *v17; // r14
  unsigned int v18; // ebx
  _BYTE *v19; // rax
  _BYTE *v20; // r8
  unsigned int v21; // ecx
  char v22; // al
  unsigned int v23; // edx
  char v24; // al
  unsigned int v25; // ecx
  _BYTE *hMem; // [rsp+30h] [rbp-F8h]
  char v28[160]; // [rsp+40h] [rbp-E8h] BYREF

  v3 = *(_DWORD *)(a2 + 392);
  *a3 = v3;
  if ( !v3 )
    return 0;
  v6 = *(_DWORD *)(a2 + 416);
  v7 = (_BYTE *)(a2 + 48);
  v8 = *(_QWORD *)(a2 + 400);
  v9 = *(unsigned int *)(a2 + 392);
  v10 = "\r\n%%%%IncludeResource: %s %s\r\n";
  v11 = 1;
  if ( !v6 )
    v10 = "\r\n%%%%BeginResource: %s %s\r\n";
  DSCSend(a1, v10, "font", v7);
  RESIncludeOrDefineResource(a1, 1, **(unsigned int **)(a1 + 3536), v7, v6 == 0);
  if ( (*(_DWORD *)(a1 + 3564) & 0x400000) != 0 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v7[v12] );
    if ( v12 < 0x80 )
    {
      v13 = OPSprintf((__int64)v28, 148, "/%s findfont pop\n", v7);
      v11 = OPRawPortWrite(a1, v28, v13);
      if ( !v11 )
        return v11;
      goto LABEL_9;
    }
    return 0;
  }
LABEL_9:
  v14 = v9 + v8;
  while ( v8 < v14 && !*(_DWORD *)(a2 + 416) )
  {
    if ( *(_BYTE *)v8 != 0x80 )
      goto LABEL_51;
    v15 = (char *)(v8 + 1);
    if ( v8 + 1 >= v14 )
      goto LABEL_51;
    v16 = *v15;
    if ( *v15 == 3 )
      break;
    v17 = (char *)(v8 + 6);
    if ( v8 + 6 >= v14
      || (v18 = *(unsigned __int8 *)(v8 + 2)
              | ((*(unsigned __int8 *)(v8 + 3) | (*(unsigned __int16 *)(v8 + 4) << 8)) << 8),
          v18 >= *(_DWORD *)(a2 + 392))
      || (unsigned __int64)&v17[v18] >= v14 )
    {
LABEL_51:
      if ( !*(_DWORD *)(a1 + 3440) )
      {
        *(_DWORD *)(a1 + 3440) = 1;
        SetLastError(0xDu);
      }
      return 0;
    }
    v19 = LocalAlloc(0, 4 * v18);
    v20 = v19;
    if ( !v19 )
      return 0;
    hMem = v19;
    if ( v16 == 1 )
    {
      v21 = 0;
      if ( v18 )
      {
        do
        {
          v22 = *v17++;
          *v20++ = v22;
          if ( v22 == 13 )
            *v20++ = 10;
          ++v21;
        }
        while ( v21 < v18 );
        goto LABEL_35;
      }
    }
    else
    {
      if ( v16 != 2 )
      {
        if ( !*(_DWORD *)(a1 + 3440) )
        {
          *(_DWORD *)(a1 + 3440) = 1;
          SetLastError(0xDu);
        }
        v11 = 0;
        goto LABEL_40;
      }
      if ( *(_WORD *)(a1 + 166) )
      {
        v25 = 1;
        if ( v18 )
        {
          do
          {
            ++v25;
            *v20++ = *v17++;
          }
          while ( v25 <= v18 );
LABEL_35:
          v19 = hMem;
        }
      }
      else
      {
        v23 = 1;
        if ( v18 )
        {
          do
          {
            *v20 = *((_BYTE *)ghexBytes + ((unsigned __int64)(unsigned __int8)*v17 >> 4));
            v24 = *v17++;
            v20[1] = *((_BYTE *)ghexBytes + (v24 & 0xF));
            v20 += 2;
            if ( (v23 & 0x1F) == 0 || v23 == v18 )
            {
              *(_WORD *)v20 = 2573;
              v20 += 2;
            }
            ++v23;
          }
          while ( v23 <= v18 );
          goto LABEL_35;
        }
      }
    }
    v11 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _QWORD))(a1 + 3432))(
            a1,
            v19,
            (unsigned int)((_DWORD)v20 - (_DWORD)v19),
            0);
LABEL_40:
    LocalFree(hMem);
    v8 += v18 + 6;
    if ( !v11 )
      return v11;
  }
  if ( !*(_DWORD *)(a2 + 416) )
  {
    v11 = OPRawPortWrite(a1, "\r\n", 2u, 0);
    DSCSend(a1, "%%%%EndResource\r\n\r\n");
  }
  return v11;
}

```

## disassembly

```asm
0x18000fe54  mov     [rsp+arg_18], rbx
0x18000fe59  push    rbp
0x18000fe5a  push    rsi
0x18000fe5b  push    rdi
0x18000fe5c  push    r12
0x18000fe5e  push    r13
0x18000fe60  push    r14
0x18000fe62  push    r15
0x18000fe64  sub     rsp, 0F0h
0x18000fe6b  mov     rax, cs:__security_cookie
0x18000fe72  xor     rax, rsp
0x18000fe75  mov     [rsp+128h+var_48], rax
0x18000fe7d  mov     eax, [rdx+188h]
0x18000fe83  xor     r12d, r12d
0x18000fe86  mov     [r8], eax
0x18000fe89  mov     r13, rdx
0x18000fe8c  mov     rsi, rcx
0x18000fe8f  test    eax, eax
0x18000fe91  jz      loc_180010191
0x18000fe97  mov     ebx, [rdx+1A0h]
0x18000fe9d  lea     r14, [rdx+30h]
0x18000fea1  mov     rbp, [rdx+190h]
0x18000fea8  lea     rax, DSC_BeginResource; "\r\n%%%%BeginResource: %s %s\r\n"
0x18000feaf  mov     r15d, [rdx+188h]
0x18000feb6  lea     r8, RES_font; "font"
0x18000febd  test    ebx, ebx
0x18000febf  lea     rdx, DSC_IncludeResource; "\r\n%%%%IncludeResource: %s %s\r\n"
0x18000fec6  mov     r9, r14
0x18000fec9  lea     edi, [r12+1]
0x18000fece  cmovz   rdx, rax
0x18000fed2  call    DSCSend
0x18000fed7  mov     rax, [rsi+0DD0h]
0x18000fede  mov     ecx, r12d
0x18000fee1  test    ebx, ebx
0x18000fee3  mov     r9, r14
0x18000fee6  mov     edx, edi
0x18000fee8  setz    cl
0x18000feeb  mov     r8d, [rax]
0x18000feee  mov     [rsp+128h+var_108], ecx
0x18000fef2  mov     rcx, rsi
0x18000fef5  call    RESIncludeOrDefineResource
0x18000fefa  test    dword ptr [rsi+0DECh], 400000h
0x18000ff04  jz      short loc_18000FF57
0x18000ff06  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ff0a  inc     rax
0x18000ff0d  cmp     [r14+rax], r12b
0x18000ff11  jnz     short loc_18000FF0A
0x18000ff13  cmp     rax, 80h
0x18000ff19  jnb     loc_180010191
0x18000ff1f  mov     r9, r14
0x18000ff22  lea     r8, aSFindfontPop; "/%s findfont pop\n"
0x18000ff29  mov     edx, 94h
0x18000ff2e  lea     rcx, [rsp+128h+var_E8]
0x18000ff33  call    OPSprintf
0x18000ff38  mov     r8d, eax
0x18000ff3b  lea     rdx, [rsp+128h+var_E8]
0x18000ff40  mov     rcx, rsi
0x18000ff43  call    OPRawPortWrite
0x18000ff48  xor     r9d, r9d
0x18000ff4b  mov     edi, eax
0x18000ff4d  test    eax, eax
0x18000ff4f  jz      loc_180010194
0x18000ff55  jmp     short loc_18000FF5A
0x18000ff57  xor     r9d, r9d
0x18000ff5a  lea     r12, [r15+rbp]
0x18000ff5e  cmp     rbp, r12
0x18000ff61  jnb     loc_18001015C
0x18000ff67  cmp     [r13+1A0h], r9d
0x18000ff6e  jnz     loc_18001015C
0x18000ff74  cmp     byte ptr [rbp+0], 80h
0x18000ff78  jnz     loc_180010130
0x18000ff7e  lea     rax, [rbp+1]
0x18000ff82  cmp     rax, r12
0x18000ff85  jnb     loc_180010130
0x18000ff8b  mov     r15b, [rax]
0x18000ff8e  cmp     r15b, 3
0x18000ff92  jz      loc_18001015C
0x18000ff98  lea     r14, [rbp+6]
0x18000ff9c  cmp     r14, r12
0x18000ff9f  jnb     loc_180010130
0x18000ffa5  movzx   eax, byte ptr [rbp+4]
0x18000ffa9  movzx   ebx, byte ptr [rbp+5]
0x18000ffad  shl     ebx, 8
0x18000ffb0  or      ebx, eax
0x18000ffb2  movzx   eax, byte ptr [rbp+3]
0x18000ffb6  shl     ebx, 8
0x18000ffb9  or      ebx, eax
0x18000ffbb  movzx   eax, byte ptr [rbp+2]
0x18000ffbf  shl     ebx, 8
0x18000ffc2  or      ebx, eax
0x18000ffc4  cmp     ebx, [r13+188h]
0x18000ffcb  jnb     loc_180010130
0x18000ffd1  mov     eax, ebx
0x18000ffd3  add     rax, r14
0x18000ffd6  cmp     rax, r12
0x18000ffd9  jnb     loc_180010130
0x18000ffdf  lea     edx, ds:0[rbx*4]; uBytes
0x18000ffe6  xor     ecx, ecx; uFlags
0x18000ffe8  call    cs:__imp_LocalAlloc
0x18000ffef  nop     dword ptr [rax+rax+00h]
0x18000fff4  xor     r9d, r9d
0x18000fff7  mov     r8, rax
0x18000fffa  test    rax, rax
0x18000fffd  jz      loc_180010157
0x180010003  lea     r10d, [r9+1]
0x180010007  mov     [rsp+128h+hMem], rax
0x18001000c  cmp     r15b, r10b
0x18001000f  jnz     short loc_18001003C
0x180010011  mov     ecx, r9d
0x180010014  test    ebx, ebx
0x180010016  jz      loc_1800100C0
0x18001001c  mov     al, [r14]
0x18001001f  add     r14, r10
0x180010022  mov     [r8], al
0x180010025  inc     r8
0x180010028  cmp     al, 0Dh
0x18001002a  jnz     short loc_180010033
0x18001002c  mov     byte ptr [r8], 0Ah
0x180010030  inc     r8
0x180010033  add     ecx, r10d
0x180010036  cmp     ecx, ebx
0x180010038  jb      short loc_18001001C
0x18001003a  jmp     short loc_1800100BB
0x18001003c  cmp     r15b, 2
0x180010040  jnz     loc_1800100E0
0x180010046  cmp     [rsi+0A6h], r9w
0x18001004e  jnz     short loc_1800100A0
0x180010050  mov     edx, r10d
0x180010053  cmp     ebx, r10d
0x180010056  jb      short loc_1800100C0
0x180010058  lea     r11, ghexBytes
0x18001005f  movzx   eax, byte ptr [r14]
0x180010063  shr     rax, 4
0x180010067  mov     al, [rax+r11]
0x18001006b  mov     [r8], al
0x18001006e  movzx   eax, byte ptr [r14]
0x180010072  add     r14, r10
0x180010075  and     eax, 0Fh
0x180010078  mov     al, [rax+r11]
0x18001007c  mov     [r8+1], al
0x180010080  add     r8, 2
0x180010084  test    dl, 1Fh
0x180010087  jz      short loc_18001008D
0x180010089  cmp     edx, ebx
0x18001008b  jnz     short loc_180010097
0x18001008d  mov     word ptr [r8], 0A0Dh
0x180010093  add     r8, 2
0x180010097  add     edx, r10d
0x18001009a  cmp     edx, ebx
0x18001009c  jbe     short loc_18001005F
0x18001009e  jmp     short loc_1800100BB
0x1800100a0  mov     ecx, r10d
0x1800100a3  cmp     ebx, r10d
0x1800100a6  jb      short loc_1800100C0
0x1800100a8  mov     al, [r14]
0x1800100ab  add     ecx, r10d
0x1800100ae  mov     [r8], al
0x1800100b1  add     r14, r10
0x1800100b4  add     r8, r10
0x1800100b7  cmp     ecx, ebx
0x1800100b9  jbe     short loc_1800100A8
0x1800100bb  mov     rax, [rsp+128h+hMem]
0x1800100c0  test    edi, edi
0x1800100c2  jz      short loc_180010107
0x1800100c4  sub     r8d, eax
0x1800100c7  mov     rdx, rax
0x1800100ca  mov     rax, [rsi+0D68h]
0x1800100d1  mov     rcx, rsi
0x1800100d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100d9  mov     edi, eax
0x1800100db  xor     r9d, r9d
0x1800100de  jmp     short loc_180010107
0x1800100e0  cmp     [rsi+0D70h], r9d
0x1800100e7  jnz     short loc_180010104
0x1800100e9  mov     ecx, 0Dh; dwErrCode
0x1800100ee  mov     [rsi+0D70h], r10d
0x1800100f5  call    cs:__imp_SetLastError
0x1800100fc  nop     dword ptr [rax+rax+00h]
0x180010101  xor     r9d, r9d
0x180010104  mov     edi, r9d
0x180010107  mov     rcx, [rsp+128h+hMem]; hMem
0x18001010c  test    rcx, rcx
0x18001010f  jz      short loc_180010120
0x180010111  call    cs:__imp_LocalFree
0x180010118  nop     dword ptr [rax+rax+00h]
0x18001011d  xor     r9d, r9d
0x180010120  lea     ecx, [rbx+6]
0x180010123  add     rbp, rcx
0x180010126  test    edi, edi
0x180010128  jnz     loc_18000FF5E
0x18001012e  jmp     short loc_180010194
0x180010130  cmp     [rsi+0D70h], r9d
0x180010137  jnz     short loc_180010157
0x180010139  mov     ecx, 0Dh; dwErrCode
0x18001013e  mov     dword ptr [rsi+0D70h], 1
0x180010148  call    cs:__imp_SetLastError
0x18001014f  nop     dword ptr [rax+rax+00h]
0x180010154  xor     r9d, r9d
0x180010157  mov     edi, r9d
0x18001015a  jmp     short loc_180010194
0x18001015c  test    edi, edi
0x18001015e  jz      short loc_180010194
0x180010160  cmp     [r13+1A0h], r9d
0x180010167  jnz     short loc_180010194
0x180010169  mov     r8d, 2
0x18001016f  lea     rdx, asc_180064FCC; "\r\n"
0x180010176  mov     rcx, rsi
0x180010179  call    OPRawPortWrite
0x18001017e  lea     rdx, DSC_EndResource; "%%%%EndResource\r\n\r\n"
0x180010185  mov     rcx, rsi
0x180010188  mov     edi, eax
0x18001018a  call    DSCSend
0x18001018f  jmp     short loc_180010194
0x180010191  mov     edi, r12d
0x180010194  mov     eax, edi
0x180010196  mov     rcx, [rsp+128h+var_48]
0x18001019e  xor     rcx, rsp; StackCookie
0x1800101a1  call    __security_check_cookie
0x1800101a6  mov     rbx, [rsp+128h+arg_18]
0x1800101ae  add     rsp, 0F0h
0x1800101b5  pop     r15
0x1800101b7  pop     r14
0x1800101b9  pop     r13
0x1800101bb  pop     r12
0x1800101bd  pop     rdi
0x1800101be  pop     rsi
0x1800101bf  pop     rbp
0x1800101c0  retn
```
