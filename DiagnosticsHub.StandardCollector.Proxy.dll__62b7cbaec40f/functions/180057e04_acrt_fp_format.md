# __acrt_fp_format

- ea: `0x180057e04`
- end: `0x1800580e9`
- name: `__acrt_fp_format`
- size: `741`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, char *Str@<rdx>, int@<r8d>, __int64, int, size_t, __int64, int, __crt_cached_ptd_host *)`
- caller_count: `12`
- callee_count: `8`
- tags: ``

## callers

- `0x18004e170`
- `0x18004e3cc`
- `0x18004e648`
- `0x18004e8a4`
- `0x18004eb00`
- `0x18004ed7c`
- `0x18004efd8`
- `0x18004f254`
- `0x18004f4f0`
- `0x18004f76c`
- `0x18004f9e8`
- `0x18004fc84`

## callees

- `0x180007b48`
- `0x180007c50`
- `0x18000b570`
- `0x180057214`
- `0x1800575a8`
- `0x180057890`
- `0x180057ab8`
- `0x180057e04`

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
    while ( (&off_18006EEE0[2 * (v13 ^ 1u)])[v16][v18] );
    if ( strcpy_s(v11, v10, (&(&off_18006EEE0[2 * (v13 ^ 1)])[v16])[v10 <= v18]) )
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
0x180057e04  mov     [rsp+arg_0], rbx
0x180057e09  mov     [rsp+arg_8], rsi
0x180057e0e  push    rdi
0x180057e0f  sub     rsp, 50h
0x180057e13  mov     r11, r8
0x180057e16  mov     r10, rdx
0x180057e19  mov     rdi, rcx
0x180057e1c  test    rdx, rdx
0x180057e1f  jnz     short loc_180057E54
0x180057e21  mov     rcx, [rsp+58h+arg_48]
0x180057e29  lea     ebx, [rdx+16h]
0x180057e2c  mov     [rsp+58h+Size], rcx; __crt_cached_ptd_host *
0x180057e31  mov     byte ptr [rcx+30h], 1
0x180057e35  mov     [rcx+2Ch], ebx
0x180057e38  and     [rsp+58h+var_38], 0
0x180057e3e  xor     r9d, r9d; LineNo
0x180057e41  xor     r8d, r8d; FileName
0x180057e44  xor     edx, edx; FunctionName
0x180057e46  xor     ecx, ecx; Expression
0x180057e48  call    _invalid_parameter_internal
0x180057e4d  mov     eax, ebx
0x180057e4f  jmp     loc_1800580C3
0x180057e54  test    r11, r11
0x180057e57  jnz     short loc_180057E74
0x180057e59  mov     rax, [rsp+58h+arg_48]
0x180057e61  mov     ebx, 16h
0x180057e66  mov     [rsp+58h+Size], rax
0x180057e6b  mov     byte ptr [rax+30h], 1
0x180057e6f  mov     [rax+2Ch], ebx
0x180057e72  jmp     short loc_180057E38
0x180057e74  test    r9, r9
0x180057e77  jz      short loc_180057E59
0x180057e79  mov     r8, [rsp+58h+arg_20]
0x180057e81  test    r8, r8
0x180057e84  jz      short loc_180057E59
0x180057e86  mov     ecx, [rsp+58h+arg_28]
0x180057e8d  cmp     ecx, 41h ; 'A'
0x180057e90  jz      short loc_180057E9F
0x180057e92  lea     eax, [rcx-45h]
0x180057e95  cmp     eax, 2
0x180057e98  jbe     short loc_180057E9F
0x180057e9a  xor     sil, sil
0x180057e9d  jmp     short loc_180057EA2
0x180057e9f  mov     sil, 1
0x180057ea2  mov     rbx, [rsp+58h+arg_38]
0x180057eaa  test    bl, 8
0x180057ead  jnz     loc_180057F99
0x180057eb3  mov     rdx, [rdi]
0x180057eb6  mov     rax, rdx
0x180057eb9  shr     rax, 34h
0x180057ebd  and     eax, 7FFh
0x180057ec2  cmp     rax, 7FFh
0x180057ec8  jnz     loc_180057F99
0x180057ece  mov     rcx, 0FFFFFFFFFFFFFh
0x180057ed8  mov     rax, rdx
0x180057edb  mov     r8d, 0Ch
0x180057ee1  and     rax, rcx
0x180057ee4  jnz     short loc_180057EEA
0x180057ee6  xor     ecx, ecx
0x180057ee8  jmp     short loc_180057F17
0x180057eea  mov     rcx, 8000000000000h
0x180057ef4  test    rdx, rdx
0x180057ef7  jns     short loc_180057F03
0x180057ef9  cmp     rax, rcx
0x180057efc  jnz     short loc_180057F03
0x180057efe  mov     rcx, r8
0x180057f01  jmp     short loc_180057F17
0x180057f03  mov     rax, rdx
0x180057f06  and     rax, rcx
0x180057f09  neg     rax
0x180057f0c  sbb     rcx, rcx
0x180057f0f  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180057f13  add     rcx, 8
0x180057f17  shr     rdx, 3Fh
0x180057f1b  lea     rax, [rdx+4]
0x180057f1f  cmp     r11, rax
0x180057f22  jnb     short loc_180057F2A
0x180057f24  mov     byte ptr [r10], 0
0x180057f28  jmp     short loc_180057F91
0x180057f2a  or      r8, 0FFFFFFFFFFFFFFFFh
0x180057f2e  test    dl, dl
0x180057f30  jz      short loc_180057F45
0x180057f32  mov     byte ptr [r10], 2Dh ; '-'
0x180057f36  inc     r10
0x180057f39  mov     byte ptr [r10], 0
0x180057f3d  cmp     r11, r8
0x180057f40  jz      short loc_180057F45
0x180057f42  dec     r11
0x180057f45  movzx   edx, sil
0x180057f49  lea     rbx, off_18006EEE0; "INF"
0x180057f50  xor     edx, 1
0x180057f53  add     edx, edx
0x180057f55  mov     eax, edx
0x180057f57  add     rax, rcx
0x180057f5a  mov     r9, [rbx+rax*8]
0x180057f5e  inc     r8
0x180057f61  cmp     byte ptr [r9+r8], 0
0x180057f66  jnz     short loc_180057F5E
0x180057f68  xor     eax, eax
0x180057f6a  cmp     r11, r8
0x180057f6d  setbe   al
0x180057f70  lea     r8d, [rdx+rax]
0x180057f74  mov     rdx, r11; SizeInBytes
0x180057f77  add     r8, rcx
0x180057f7a  mov     rcx, r10; Destination
0x180057f7d  mov     r8, [rbx+r8*8]; Source
0x180057f81  call    strcpy_s
0x180057f86  test    eax, eax
0x180057f88  jnz     loc_1800580D3
0x180057f8e  xor     r8d, r8d
0x180057f91  mov     eax, r8d
0x180057f94  jmp     loc_1800580C3
0x180057f99  mov     rdx, rbx
0x180057f9c  and     bl, 20h
0x180057f9f  shr     rdx, 4
0x180057fa3  and     edx, 1
0x180057fa6  or      edx, 2
0x180057fa9  neg     bl
0x180057fab  sbb     ebx, ebx
0x180057fad  and     ebx, [rsp+58h+arg_40]
0x180057fb4  sub     ecx, 41h ; 'A'
0x180057fb7  jz      loc_18005808B
0x180057fbd  sub     ecx, 4
0x180057fc0  jz      loc_180058051
0x180057fc6  sub     ecx, 1
0x180057fc9  jz      short loc_180058020
0x180057fcb  sub     ecx, 1
0x180057fce  jz      short loc_180057FE3
0x180057fd0  sub     ecx, 1Ah
0x180057fd3  jz      loc_18005808B
0x180057fd9  sub     ecx, 4
0x180057fdc  jz      short loc_180058051
0x180057fde  cmp     ecx, 1
0x180057fe1  jz      short loc_180058020
0x180057fe3  mov     rax, [rsp+58h+arg_48]
0x180057feb  mov     rcx, rdi
0x180057fee  mov     [rsp+58h+var_10], rax
0x180057ff3  mov     eax, dword ptr [rsp+58h+arg_30]
0x180057ffa  mov     [rsp+58h+var_18], ebx
0x180057ffe  mov     [rsp+58h+var_20], edx
0x180058002  mov     rdx, r10
0x180058005  mov     [rsp+58h+var_28], sil
0x18005800a  mov     dword ptr [rsp+58h+Size], eax
0x18005800e  mov     [rsp+58h+var_38], r8
0x180058013  mov     r8, r11
0x180058016  call    fp_format_g
0x18005801b  jmp     loc_1800580C3
0x180058020  mov     rax, [rsp+58h+arg_48]
0x180058028  mov     rdx, r10
0x18005802b  mov     qword ptr [rsp+58h+var_20], rax
0x180058030  mov     rcx, rdi
0x180058033  mov     eax, dword ptr [rsp+58h+arg_30]
0x18005803a  mov     dword ptr [rsp+58h+var_28], ebx
0x18005803e  mov     dword ptr [rsp+58h+Size], eax
0x180058042  mov     [rsp+58h+var_38], r8
0x180058047  mov     r8, r11
0x18005804a  call    fp_format_f
0x18005804f  jmp     short loc_1800580C3
0x180058051  mov     rax, [rsp+58h+arg_48]
0x180058059  mov     rcx, rdi; int
0x18005805c  mov     [rsp+58h+var_10], rax; __crt_cached_ptd_host *
0x180058061  mov     eax, dword ptr [rsp+58h+arg_30]
0x180058068  mov     [rsp+58h+var_18], ebx; int
0x18005806c  mov     [rsp+58h+var_20], edx; int
0x180058070  mov     rdx, r10; int
0x180058073  mov     [rsp+58h+var_28], sil; char
0x180058078  mov     dword ptr [rsp+58h+Size], eax; int
0x18005807c  mov     [rsp+58h+var_38], r8; __int64
0x180058081  mov     r8, r11; int
0x180058084  call    fp_format_e
0x180058089  jmp     short loc_1800580C3
0x18005808b  mov     rax, [rsp+58h+arg_48]
0x180058093  mov     rcx, rdi; int
0x180058096  mov     [rsp+58h+var_10], rax; __crt_cached_ptd_host *
0x18005809b  mov     eax, dword ptr [rsp+58h+arg_30]
0x1800580a2  mov     [rsp+58h+var_18], ebx; int
0x1800580a6  mov     [rsp+58h+var_20], edx; int
0x1800580aa  mov     rdx, r10; Str
0x1800580ad  mov     [rsp+58h+var_28], sil; char
0x1800580b2  mov     dword ptr [rsp+58h+Size], eax; Size
0x1800580b6  mov     [rsp+58h+var_38], r8; __int64
0x1800580bb  mov     r8, r11
0x1800580be  call    fp_format_a
0x1800580c3  mov     rbx, [rsp+58h+arg_0]
0x1800580c8  mov     rsi, [rsp+58h+arg_8]
0x1800580cd  add     rsp, 50h
0x1800580d1  pop     rdi
0x1800580d2  retn
0x1800580d3  and     [rsp+58h+var_38], 0
0x1800580d9  xor     r9d, r9d; LineNo
0x1800580dc  xor     r8d, r8d; FileName
0x1800580df  xor     edx, edx; FunctionName
0x1800580e1  xor     ecx, ecx; Expression
0x1800580e3  call    _invoke_watson
```
