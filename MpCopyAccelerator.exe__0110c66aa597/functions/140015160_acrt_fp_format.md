# __acrt_fp_format

- ea: `0x140015160`
- end: `0x140015445`
- name: `__acrt_fp_format`
- size: `741`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, char *Str@<rdx>, int@<r8d>, __int64, int, size_t, __int64, int, __crt_cached_ptd_host *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x14000fd18`
- `0x14000ff74`

## callees

- `0x14000bea4`
- `0x14000bf7c`
- `0x1400136b0`
- `0x140014650`
- `0x1400149e4`
- `0x140014ccc`
- `0x140014ef4`
- `0x140015160`

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
    while ( (&off_14002AFC0[2 * (v13 ^ 1u)])[v16][v18] );
    if ( strcpy_s(v11, v10, (&(&off_14002AFC0[2 * (v13 ^ 1)])[v16])[v10 <= v18]) )
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
0x140015160  mov     [rsp+arg_0], rbx
0x140015165  mov     [rsp+arg_8], rsi
0x14001516a  push    rdi
0x14001516b  sub     rsp, 50h
0x14001516f  mov     r11, r8
0x140015172  mov     r10, rdx
0x140015175  mov     rdi, rcx
0x140015178  test    rdx, rdx
0x14001517b  jnz     short loc_1400151B0
0x14001517d  mov     rcx, [rsp+58h+arg_48]
0x140015185  lea     ebx, [rdx+16h]
0x140015188  mov     [rsp+58h+Size], rcx; __crt_cached_ptd_host *
0x14001518d  mov     byte ptr [rcx+30h], 1
0x140015191  mov     [rcx+2Ch], ebx
0x140015194  and     [rsp+58h+var_38], 0
0x14001519a  xor     r9d, r9d; LineNo
0x14001519d  xor     r8d, r8d; FileName
0x1400151a0  xor     edx, edx; FunctionName
0x1400151a2  xor     ecx, ecx; Expression
0x1400151a4  call    _invalid_parameter_internal
0x1400151a9  mov     eax, ebx
0x1400151ab  jmp     loc_14001541F
0x1400151b0  test    r11, r11
0x1400151b3  jnz     short loc_1400151D0
0x1400151b5  mov     rax, [rsp+58h+arg_48]
0x1400151bd  mov     ebx, 16h
0x1400151c2  mov     [rsp+58h+Size], rax
0x1400151c7  mov     byte ptr [rax+30h], 1
0x1400151cb  mov     [rax+2Ch], ebx
0x1400151ce  jmp     short loc_140015194
0x1400151d0  test    r9, r9
0x1400151d3  jz      short loc_1400151B5
0x1400151d5  mov     r8, [rsp+58h+arg_20]
0x1400151dd  test    r8, r8
0x1400151e0  jz      short loc_1400151B5
0x1400151e2  mov     ecx, [rsp+58h+arg_28]
0x1400151e9  cmp     ecx, 41h ; 'A'
0x1400151ec  jz      short loc_1400151FB
0x1400151ee  lea     eax, [rcx-45h]
0x1400151f1  cmp     eax, 2
0x1400151f4  jbe     short loc_1400151FB
0x1400151f6  xor     sil, sil
0x1400151f9  jmp     short loc_1400151FE
0x1400151fb  mov     sil, 1
0x1400151fe  mov     rbx, [rsp+58h+arg_38]
0x140015206  test    bl, 8
0x140015209  jnz     loc_1400152F5
0x14001520f  mov     rdx, [rdi]
0x140015212  mov     rax, rdx
0x140015215  shr     rax, 34h
0x140015219  and     eax, 7FFh
0x14001521e  cmp     rax, 7FFh
0x140015224  jnz     loc_1400152F5
0x14001522a  mov     rcx, 0FFFFFFFFFFFFFh
0x140015234  mov     rax, rdx
0x140015237  mov     r8d, 0Ch
0x14001523d  and     rax, rcx
0x140015240  jnz     short loc_140015246
0x140015242  xor     ecx, ecx
0x140015244  jmp     short loc_140015273
0x140015246  mov     rcx, 8000000000000h
0x140015250  test    rdx, rdx
0x140015253  jns     short loc_14001525F
0x140015255  cmp     rax, rcx
0x140015258  jnz     short loc_14001525F
0x14001525a  mov     rcx, r8
0x14001525d  jmp     short loc_140015273
0x14001525f  mov     rax, rdx
0x140015262  and     rax, rcx
0x140015265  neg     rax
0x140015268  sbb     rcx, rcx
0x14001526b  and     rcx, 0FFFFFFFFFFFFFFFCh
0x14001526f  add     rcx, 8
0x140015273  shr     rdx, 3Fh
0x140015277  lea     rax, [rdx+4]
0x14001527b  cmp     r11, rax
0x14001527e  jnb     short loc_140015286
0x140015280  mov     byte ptr [r10], 0
0x140015284  jmp     short loc_1400152ED
0x140015286  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001528a  test    dl, dl
0x14001528c  jz      short loc_1400152A1
0x14001528e  mov     byte ptr [r10], 2Dh ; '-'
0x140015292  inc     r10
0x140015295  mov     byte ptr [r10], 0
0x140015299  cmp     r11, r8
0x14001529c  jz      short loc_1400152A1
0x14001529e  dec     r11
0x1400152a1  movzx   edx, sil
0x1400152a5  lea     rbx, off_14002AFC0
0x1400152ac  xor     edx, 1
0x1400152af  add     edx, edx
0x1400152b1  mov     eax, edx
0x1400152b3  add     rax, rcx
0x1400152b6  mov     r9, [rbx+rax*8]
0x1400152ba  inc     r8
0x1400152bd  cmp     byte ptr [r9+r8], 0
0x1400152c2  jnz     short loc_1400152BA
0x1400152c4  xor     eax, eax
0x1400152c6  cmp     r11, r8
0x1400152c9  setbe   al
0x1400152cc  lea     r8d, [rdx+rax]
0x1400152d0  mov     rdx, r11; SizeInBytes
0x1400152d3  add     r8, rcx
0x1400152d6  mov     rcx, r10; Destination
0x1400152d9  mov     r8, [rbx+r8*8]; Source
0x1400152dd  call    strcpy_s
0x1400152e2  test    eax, eax
0x1400152e4  jnz     loc_14001542F
0x1400152ea  xor     r8d, r8d
0x1400152ed  mov     eax, r8d
0x1400152f0  jmp     loc_14001541F
0x1400152f5  mov     rdx, rbx
0x1400152f8  and     bl, 20h
0x1400152fb  shr     rdx, 4
0x1400152ff  and     edx, 1
0x140015302  or      edx, 2
0x140015305  neg     bl
0x140015307  sbb     ebx, ebx
0x140015309  and     ebx, [rsp+58h+arg_40]
0x140015310  sub     ecx, 41h ; 'A'
0x140015313  jz      loc_1400153E7
0x140015319  sub     ecx, 4
0x14001531c  jz      loc_1400153AD
0x140015322  sub     ecx, 1
0x140015325  jz      short loc_14001537C
0x140015327  sub     ecx, 1
0x14001532a  jz      short loc_14001533F
0x14001532c  sub     ecx, 1Ah
0x14001532f  jz      loc_1400153E7
0x140015335  sub     ecx, 4
0x140015338  jz      short loc_1400153AD
0x14001533a  cmp     ecx, 1
0x14001533d  jz      short loc_14001537C
0x14001533f  mov     rax, [rsp+58h+arg_48]
0x140015347  mov     rcx, rdi
0x14001534a  mov     [rsp+58h+var_10], rax
0x14001534f  mov     eax, dword ptr [rsp+58h+arg_30]
0x140015356  mov     [rsp+58h+var_18], ebx
0x14001535a  mov     [rsp+58h+var_20], edx
0x14001535e  mov     rdx, r10
0x140015361  mov     [rsp+58h+var_28], sil
0x140015366  mov     dword ptr [rsp+58h+Size], eax
0x14001536a  mov     [rsp+58h+var_38], r8
0x14001536f  mov     r8, r11
0x140015372  call    fp_format_g
0x140015377  jmp     loc_14001541F
0x14001537c  mov     rax, [rsp+58h+arg_48]
0x140015384  mov     rdx, r10
0x140015387  mov     qword ptr [rsp+58h+var_20], rax
0x14001538c  mov     rcx, rdi
0x14001538f  mov     eax, dword ptr [rsp+58h+arg_30]
0x140015396  mov     dword ptr [rsp+58h+var_28], ebx
0x14001539a  mov     dword ptr [rsp+58h+Size], eax
0x14001539e  mov     [rsp+58h+var_38], r8
0x1400153a3  mov     r8, r11
0x1400153a6  call    fp_format_f
0x1400153ab  jmp     short loc_14001541F
0x1400153ad  mov     rax, [rsp+58h+arg_48]
0x1400153b5  mov     rcx, rdi; int
0x1400153b8  mov     [rsp+58h+var_10], rax; __crt_cached_ptd_host *
0x1400153bd  mov     eax, dword ptr [rsp+58h+arg_30]
0x1400153c4  mov     [rsp+58h+var_18], ebx; int
0x1400153c8  mov     [rsp+58h+var_20], edx; int
0x1400153cc  mov     rdx, r10; int
0x1400153cf  mov     [rsp+58h+var_28], sil; char
0x1400153d4  mov     dword ptr [rsp+58h+Size], eax; int
0x1400153d8  mov     [rsp+58h+var_38], r8; __int64
0x1400153dd  mov     r8, r11; int
0x1400153e0  call    fp_format_e
0x1400153e5  jmp     short loc_14001541F
0x1400153e7  mov     rax, [rsp+58h+arg_48]
0x1400153ef  mov     rcx, rdi; int
0x1400153f2  mov     [rsp+58h+var_10], rax; __crt_cached_ptd_host *
0x1400153f7  mov     eax, dword ptr [rsp+58h+arg_30]
0x1400153fe  mov     [rsp+58h+var_18], ebx; int
0x140015402  mov     [rsp+58h+var_20], edx; int
0x140015406  mov     rdx, r10; Str
0x140015409  mov     [rsp+58h+var_28], sil; char
0x14001540e  mov     dword ptr [rsp+58h+Size], eax; Size
0x140015412  mov     [rsp+58h+var_38], r8; __int64
0x140015417  mov     r8, r11
0x14001541a  call    fp_format_a
0x14001541f  mov     rbx, [rsp+58h+arg_0]
0x140015424  mov     rsi, [rsp+58h+arg_8]
0x140015429  add     rsp, 50h
0x14001542d  pop     rdi
0x14001542e  retn
0x14001542f  and     [rsp+58h+var_38], 0
0x140015435  xor     r9d, r9d; LineNo
0x140015438  xor     r8d, r8d; FileName
0x14001543b  xor     edx, edx; FunctionName
0x14001543d  xor     ecx, ecx; Expression
0x14001543f  call    _invoke_watson
```
