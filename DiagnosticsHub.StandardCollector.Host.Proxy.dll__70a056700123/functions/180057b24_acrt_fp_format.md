# __acrt_fp_format

- ea: `0x180057b24`
- end: `0x180057e09`
- name: `__acrt_fp_format`
- size: `741`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, char *Str@<rdx>, int@<r8d>, __int64, int, size_t, __int64, int, __crt_cached_ptd_host *)`
- caller_count: `12`
- callee_count: `8`
- tags: ``

## callers

- `0x18004de90`
- `0x18004e0ec`
- `0x18004e368`
- `0x18004e5c4`
- `0x18004e820`
- `0x18004ea9c`
- `0x18004ecf8`
- `0x18004ef74`
- `0x18004f210`
- `0x18004f48c`
- `0x18004f708`
- `0x18004f9a4`

## callees

- `0x1800073e8`
- `0x1800074f0`
- `0x18000ae10`
- `0x180056f34`
- `0x1800572c8`
- `0x1800575b0`
- `0x1800577d8`
- `0x180057b24`

## pseudocode

```c
__int64 __fastcall _acrt_fp_format(
        __int64 *a1,
        char *Str,
        rsize_t a3,
        __int64 a4,
        __int64 a5,
        int a6,
        size_t a7,
        unsigned __int64 a8,
        int a9,
        __crt_cached_ptd_host *a10)
{
  rsize_t v10; // r11
  char *v11; // r10
  unsigned __int8 v13; // si
  __int64 v14; // rdx
  unsigned int v15; // r8d
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // r8
  int v19; // edx
  int v20; // ebx
  size_t Size; // [rsp+28h] [rbp-30h]

  v10 = a3;
  v11 = Str;
  if ( !Str || !a3 || !a4 || !a5 )
  {
    *((_BYTE *)a10 + 48) = 1;
    *((_DWORD *)a10 + 11) = 22;
    invalid_parameter_internal(0, 0, 0, 0, 0, a10);
    return 22;
  }
  v13 = a6 == 65 || (unsigned int)(a6 - 69) <= 2;
  if ( (a8 & 8) != 0 || (v14 = *a1, (((unsigned __int64)*a1 >> 52) & 0x7FF) != 0x7FF) )
  {
    v19 = (a8 >> 4) & 1 | 2;
    v20 = (a8 & 0x20) != 0 ? a9 : 0;
    if ( a6 != 65 )
    {
      switch ( a6 )
      {
        case 'E':
          return fp_format_e((int)a1, (int)v11, a3, a4, a5, a7, v13, v19, v20, a10);
        case 'F':
          return fp_format_f(a1, v11, a3);
        case 'G':
          return fp_format_g(a1, v11, a3);
      }
      if ( a6 != 97 )
      {
        if ( a6 != 101 )
        {
          if ( a6 != 102 )
            return fp_format_g(a1, v11, a3);
          return fp_format_f(a1, v11, a3);
        }
        return fp_format_e((int)a1, (int)v11, a3, a4, a5, a7, v13, v19, v20, a10);
      }
    }
    LODWORD(Size) = a7;
    return fp_format_a((int)a1, v11, a5, Size, v13, v19, v20, a10);
  }
  v15 = 12;
  if ( (v14 & 0xFFFFFFFFFFFFFLL) != 0 )
  {
    if ( v14 < 0 && (v14 & 0xFFFFFFFFFFFFFLL) == 0x8000000000000LL )
      v16 = 12;
    else
      v16 = (-(__int64)((v14 & 0x8000000000000LL) != 0) & 0xFFFFFFFFFFFFFFFCuLL) + 8;
  }
  else
  {
    v16 = 0;
  }
  v17 = (unsigned __int64)v14 >> 63;
  if ( v10 >= v17 + 4 )
  {
    v18 = -1;
    if ( (_BYTE)v17 )
    {
      *v11++ = 45;
      *v11 = 0;
      if ( v10 != -1 )
        --v10;
    }
    do
      ++v18;
    while ( (&off_18006B810[2 * (v13 ^ 1u)])[v16][v18] );
    if ( strcpy_s(v11, v10, (&(&off_18006B810[2 * (v13 ^ 1)])[v16])[v10 <= v18]) )
      invoke_watson(0, 0, 0, 0, 0);
    return 0;
  }
  else
  {
    *v11 = 0;
  }
  return v15;
}

```

## disassembly

```asm
0x180057b24  mov     [rsp+arg_0], rbx
0x180057b29  mov     [rsp+arg_8], rsi
0x180057b2e  push    rdi
0x180057b2f  sub     rsp, 50h
0x180057b33  mov     r11, r8
0x180057b36  mov     r10, rdx
0x180057b39  mov     rdi, rcx
0x180057b3c  test    rdx, rdx
0x180057b3f  jnz     short loc_180057B74
0x180057b41  mov     rcx, [rsp+58h+arg_48]
0x180057b49  lea     ebx, [rdx+16h]
0x180057b4c  mov     [rsp+58h+Size], rcx; __crt_cached_ptd_host *
0x180057b51  mov     byte ptr [rcx+30h], 1
0x180057b55  mov     [rcx+2Ch], ebx
0x180057b58  and     [rsp+58h+var_38], 0
0x180057b5e  xor     r9d, r9d; LineNo
0x180057b61  xor     r8d, r8d; FileName
0x180057b64  xor     edx, edx; FunctionName
0x180057b66  xor     ecx, ecx; Expression
0x180057b68  call    _invalid_parameter_internal
0x180057b6d  mov     eax, ebx
0x180057b6f  jmp     loc_180057DE3
0x180057b74  test    r11, r11
0x180057b77  jnz     short loc_180057B94
0x180057b79  mov     rax, [rsp+58h+arg_48]
0x180057b81  mov     ebx, 16h
0x180057b86  mov     [rsp+58h+Size], rax
0x180057b8b  mov     byte ptr [rax+30h], 1
0x180057b8f  mov     [rax+2Ch], ebx
0x180057b92  jmp     short loc_180057B58
0x180057b94  test    r9, r9
0x180057b97  jz      short loc_180057B79
0x180057b99  mov     r8, [rsp+58h+arg_20]
0x180057ba1  test    r8, r8
0x180057ba4  jz      short loc_180057B79
0x180057ba6  mov     ecx, [rsp+58h+arg_28]
0x180057bad  cmp     ecx, 41h ; 'A'
0x180057bb0  jz      short loc_180057BBF
0x180057bb2  lea     eax, [rcx-45h]
0x180057bb5  cmp     eax, 2
0x180057bb8  jbe     short loc_180057BBF
0x180057bba  xor     sil, sil
0x180057bbd  jmp     short loc_180057BC2
0x180057bbf  mov     sil, 1
0x180057bc2  mov     rbx, [rsp+58h+arg_38]
0x180057bca  test    bl, 8
0x180057bcd  jnz     loc_180057CB9
0x180057bd3  mov     rdx, [rdi]
0x180057bd6  mov     rax, rdx
0x180057bd9  shr     rax, 34h
0x180057bdd  and     eax, 7FFh
0x180057be2  cmp     rax, 7FFh
0x180057be8  jnz     loc_180057CB9
0x180057bee  mov     rcx, 0FFFFFFFFFFFFFh
0x180057bf8  mov     rax, rdx
0x180057bfb  mov     r8d, 0Ch
0x180057c01  and     rax, rcx
0x180057c04  jnz     short loc_180057C0A
0x180057c06  xor     ecx, ecx
0x180057c08  jmp     short loc_180057C37
0x180057c0a  mov     rcx, 8000000000000h
0x180057c14  test    rdx, rdx
0x180057c17  jns     short loc_180057C23
0x180057c19  cmp     rax, rcx
0x180057c1c  jnz     short loc_180057C23
0x180057c1e  mov     rcx, r8
0x180057c21  jmp     short loc_180057C37
0x180057c23  mov     rax, rdx
0x180057c26  and     rax, rcx
0x180057c29  neg     rax
0x180057c2c  sbb     rcx, rcx
0x180057c2f  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180057c33  add     rcx, 8
0x180057c37  shr     rdx, 3Fh
0x180057c3b  lea     rax, [rdx+4]
0x180057c3f  cmp     r11, rax
0x180057c42  jnb     short loc_180057C4A
0x180057c44  mov     byte ptr [r10], 0
0x180057c48  jmp     short loc_180057CB1
0x180057c4a  or      r8, 0FFFFFFFFFFFFFFFFh
0x180057c4e  test    dl, dl
0x180057c50  jz      short loc_180057C65
0x180057c52  mov     byte ptr [r10], 2Dh ; '-'
0x180057c56  inc     r10
0x180057c59  mov     byte ptr [r10], 0
0x180057c5d  cmp     r11, r8
0x180057c60  jz      short loc_180057C65
0x180057c62  dec     r11
0x180057c65  movzx   edx, sil
0x180057c69  lea     rbx, off_18006B810; "INF"
0x180057c70  xor     edx, 1
0x180057c73  add     edx, edx
0x180057c75  mov     eax, edx
0x180057c77  add     rax, rcx
0x180057c7a  mov     r9, [rbx+rax*8]
0x180057c7e  inc     r8
0x180057c81  cmp     byte ptr [r9+r8], 0
0x180057c86  jnz     short loc_180057C7E
0x180057c88  xor     eax, eax
0x180057c8a  cmp     r11, r8
0x180057c8d  setbe   al
0x180057c90  lea     r8d, [rdx+rax]
0x180057c94  mov     rdx, r11; SizeInBytes
0x180057c97  add     r8, rcx
0x180057c9a  mov     rcx, r10; Destination
0x180057c9d  mov     r8, [rbx+r8*8]; Source
0x180057ca1  call    strcpy_s
0x180057ca6  test    eax, eax
0x180057ca8  jnz     loc_180057DF3
0x180057cae  xor     r8d, r8d
0x180057cb1  mov     eax, r8d
0x180057cb4  jmp     loc_180057DE3
0x180057cb9  mov     rdx, rbx
0x180057cbc  and     bl, 20h
0x180057cbf  shr     rdx, 4
0x180057cc3  and     edx, 1
0x180057cc6  or      edx, 2
0x180057cc9  neg     bl
0x180057ccb  sbb     ebx, ebx
0x180057ccd  and     ebx, [rsp+58h+arg_40]
0x180057cd4  sub     ecx, 41h ; 'A'
0x180057cd7  jz      loc_180057DAB
0x180057cdd  sub     ecx, 4
0x180057ce0  jz      loc_180057D71
0x180057ce6  sub     ecx, 1
0x180057ce9  jz      short loc_180057D40
0x180057ceb  sub     ecx, 1
0x180057cee  jz      short loc_180057D03
0x180057cf0  sub     ecx, 1Ah
0x180057cf3  jz      loc_180057DAB
0x180057cf9  sub     ecx, 4
0x180057cfc  jz      short loc_180057D71
0x180057cfe  cmp     ecx, 1
0x180057d01  jz      short loc_180057D40
0x180057d03  mov     rax, [rsp+58h+arg_48]
0x180057d0b  mov     rcx, rdi
0x180057d0e  mov     [rsp+58h+var_10], rax
0x180057d13  mov     eax, dword ptr [rsp+58h+arg_30]
0x180057d1a  mov     [rsp+58h+var_18], ebx
0x180057d1e  mov     [rsp+58h+var_20], edx
0x180057d22  mov     rdx, r10
0x180057d25  mov     [rsp+58h+var_28], sil
0x180057d2a  mov     dword ptr [rsp+58h+Size], eax
0x180057d2e  mov     [rsp+58h+var_38], r8
0x180057d33  mov     r8, r11
0x180057d36  call    fp_format_g
0x180057d3b  jmp     loc_180057DE3
0x180057d40  mov     rax, [rsp+58h+arg_48]
0x180057d48  mov     rdx, r10
0x180057d4b  mov     qword ptr [rsp+58h+var_20], rax
0x180057d50  mov     rcx, rdi
0x180057d53  mov     eax, dword ptr [rsp+58h+arg_30]
0x180057d5a  mov     dword ptr [rsp+58h+var_28], ebx
0x180057d5e  mov     dword ptr [rsp+58h+Size], eax
0x180057d62  mov     [rsp+58h+var_38], r8
0x180057d67  mov     r8, r11
0x180057d6a  call    fp_format_f
0x180057d6f  jmp     short loc_180057DE3
0x180057d71  mov     rax, [rsp+58h+arg_48]
0x180057d79  mov     rcx, rdi; int
0x180057d7c  mov     [rsp+58h+var_10], rax; __crt_cached_ptd_host *
0x180057d81  mov     eax, dword ptr [rsp+58h+arg_30]
0x180057d88  mov     [rsp+58h+var_18], ebx; int
0x180057d8c  mov     [rsp+58h+var_20], edx; int
0x180057d90  mov     rdx, r10; int
0x180057d93  mov     [rsp+58h+var_28], sil; char
0x180057d98  mov     dword ptr [rsp+58h+Size], eax; int
0x180057d9c  mov     [rsp+58h+var_38], r8; __int64
0x180057da1  mov     r8, r11; int
0x180057da4  call    fp_format_e
0x180057da9  jmp     short loc_180057DE3
0x180057dab  mov     rax, [rsp+58h+arg_48]
0x180057db3  mov     rcx, rdi; int
0x180057db6  mov     [rsp+58h+var_10], rax; __crt_cached_ptd_host *
0x180057dbb  mov     eax, dword ptr [rsp+58h+arg_30]
0x180057dc2  mov     [rsp+58h+var_18], ebx; int
0x180057dc6  mov     [rsp+58h+var_20], edx; int
0x180057dca  mov     rdx, r10; Str
0x180057dcd  mov     [rsp+58h+var_28], sil; char
0x180057dd2  mov     dword ptr [rsp+58h+Size], eax; Size
0x180057dd6  mov     [rsp+58h+var_38], r8; __int64
0x180057ddb  mov     r8, r11
0x180057dde  call    fp_format_a
0x180057de3  mov     rbx, [rsp+58h+arg_0]
0x180057de8  mov     rsi, [rsp+58h+arg_8]
0x180057ded  add     rsp, 50h
0x180057df1  pop     rdi
0x180057df2  retn
0x180057df3  and     [rsp+58h+var_38], 0
0x180057df9  xor     r9d, r9d; LineNo
0x180057dfc  xor     r8d, r8d; FileName
0x180057dff  xor     edx, edx; FunctionName
0x180057e01  xor     ecx, ecx; Expression
0x180057e03  call    _invoke_watson
```
