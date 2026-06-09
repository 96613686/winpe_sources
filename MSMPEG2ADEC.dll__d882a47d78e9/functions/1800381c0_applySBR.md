# applySBR

- ea: `0x1800381c0`
- end: `0x180038548`
- name: `applySBR`
- size: `904`
- prototype: `__int64 __fastcall(__int64, int *, __int64, __int64, _DWORD *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180034030`

## callees

- `0x1800017b0`
- `0x180002122`
- `0x1800021a8`
- `0x180037e20`
- `0x1800381c0`
- `0x180038550`
- `0x180088690`
- `0x1800886fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180038410`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180038424`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180038410`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180038424`
- `mfperfhelper!__imp_ippsZero_8u` at `0x180038394`
- `mfperfhelper!__imp_ippsZero_8u` at `0x180038394`
- `mfperfhelper!__imp_ippsCopy_8u` at `0x18003837e`
- `mfperfhelper!__imp_ippsCopy_8u` at `0x18003837e`

## pseudocode

```c
__int64 __fastcall applySBR(__int64 a1, int *a2, __int64 a3, __int64 a4, _DWORD *a5, int a6)
{
  _DWORD *v6; // r11
  int v7; // ebp
  int v8; // ebx
  bool v9; // cc
  int v10; // esi
  _BYTE *v14; // rdi
  _BYTE *v15; // rdx
  int v16; // r10d
  __int64 v17; // r8
  int v18; // edx
  int v19; // eax
  unsigned int v20; // edi
  int v21; // r13d
  unsigned int v22; // ebx
  __int64 v23; // r8
  int i; // r15d
  int v25; // ebx
  const void *v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r9
  int v29; // ebx
  int v30; // ebx
  int v32; // [rsp+50h] [rbp-1178h]
  __int64 v33; // [rsp+54h] [rbp-1174h] BYREF
  __int64 v34; // [rsp+60h] [rbp-1168h]
  _DWORD *v35; // [rsp+68h] [rbp-1160h]
  _BYTE Src[4336]; // [rsp+70h] [rbp-1158h] BYREF
  _OWORD v37[2]; // [rsp+1160h] [rbp-68h] BYREF

  v6 = a5;
  v7 = 0;
  v8 = 0;
  v9 = *a2 <= 8;
  v10 = 1;
  v34 = a4;
  v35 = a5;
  v33 = 0x100000000LL;
  v32 = 0;
  memset(v37, 0, sizeof(v37));
  if ( !v9 )
  {
    v10 = 0;
    *a2 = 8;
    HIDWORD(v33) = 0;
  }
  if ( *(_DWORD *)(a1 + 880864) )
  {
    v14 = *(_BYTE **)(a1 + 346096);
    v15 = v14;
    if ( v10 )
    {
      memcpy_0(Src, v14, 0x10E8u);
      memcpy_0(v14, a2, 0x10E8u);
      v15 = Src;
    }
    memcpy_0(a2, v15, 0x10E8u);
    v6 = v35;
    *(_DWORD *)(a1 + 346104) = v10;
  }
  v16 = *a2;
  v17 = 0;
  if ( *a2 > 0 )
  {
    do
    {
      v18 = a2[135 * (unsigned int)v17 + 2];
      if ( v18 )
      {
        if ( v18 != 1 )
          goto LABEL_14;
        v19 = 2;
      }
      else
      {
        v19 = 1;
      }
      *((_DWORD *)v37 + v17) = v19;
      v8 += v19;
      v17 = (unsigned int)(v17 + 1);
    }
    while ( (int)v17 < v16 );
    if ( v8 > 7 )
    {
LABEL_14:
      v20 = 14;
      goto LABEL_39;
    }
  }
  v21 = 0;
  if ( a6 == 6 && *v6 == 6 && v16 == 3 && LODWORD(v37[0]) == 1 && *(_QWORD *)((char *)v37 + 4) == 0x200000002LL )
  {
    v21 = 1;
    ++v8;
  }
  if ( v8 > 0 )
  {
    v22 = v8 << 12;
    if ( v22 > 0x7000 )
    {
      v20 = 14;
      goto LABEL_39;
    }
    ippsCopy_8u(a4, a1, v22);
  }
  v20 = 0;
  ippsZero_8u(a4, 57344);
  for ( i = 0; i < *a2; ++i )
  {
    LODWORD(v33) = *((_DWORD *)v37 + i);
    v25 = v33;
    memset_0((void *)(a1 + 28672), 0, 0x4000u);
    v29 = v25 << 12;
    if ( !v29 )
      goto LABEL_34;
    if ( a1 == -28672 || (v26 = (const void *)(a1 + 4LL * (v7 << 10))) == 0 )
    {
      *(_DWORD *)_o__errno(v27, v26, v29, v28) = 22;
    }
    else
    {
      if ( (unsigned __int64)v29 <= 0x4000 )
      {
        memcpy_0((void *)(a1 + 28672), v26, v29);
        goto LABEL_34;
      }
      *(_DWORD *)_o__errno(v27, v26, v29, v28) = 34;
    }
    invalid_parameter_noinfo();
LABEL_34:
    v20 = applySBROnOneAE(a1, (int)a2, v7, i, (void *)(a1 + 28672), (__int64)&v33, SHIDWORD(v33), 0, 0, 0);
    if ( v20 )
    {
      v20 = 14;
      goto LABEL_38;
    }
    v30 = v33;
    memcpy_0((void *)(v34 + 4LL * (v7 << 11)), (const void *)(a1 + 28672), (int)((_DWORD)v33 << 13));
    v32 += v30;
    v7 += v30;
  }
  if ( v21 )
    LFEInterpolation(a1 + 20480, v34 + 40960, v23, a1 + 880804);
LABEL_38:
  v7 = v32;
LABEL_39:
  if ( *v35 == 1 && v7 == 2 )
    *v35 = 2;
  return v20;
}

```

## disassembly

```asm
0x1800381c0  push    rbp
0x1800381c2  mov     eax, 11C0h
0x1800381c7  call    _alloca_probe
0x1800381cc  sub     rsp, rax
0x1800381cf  mov     rax, cs:__security_cookie
0x1800381d6  xor     rax, rsp
0x1800381d9  mov     [rsp+11C8h+var_48], rax
0x1800381e1  mov     r11, [rsp+11C8h+arg_20]
0x1800381e9  xor     ebp, ebp
0x1800381eb  mov     [rsp+11C8h+arg_10], rbx
0x1800381f3  xorps   xmm0, xmm0
0x1800381f6  mov     [rsp+11C8h+var_10], rsi
0x1800381fe  xor     ebx, ebx
0x180038200  cmp     dword ptr [rdx], 8
0x180038203  mov     esi, 1
0x180038208  mov     [rsp+11C8h+var_20], r12
0x180038210  mov     r12, rcx
0x180038213  mov     [rsp+11C8h+var_30], r14
0x18003821b  mov     r14, rdx
0x18003821e  mov     [rsp+11C8h+var_38], r15
0x180038226  mov     r15, r9
0x180038229  mov     [rsp+11C8h+var_1168], r9
0x18003822e  mov     [rsp+11C8h+var_1160], r11
0x180038233  mov     dword ptr [rsp+11C8h+var_1174+4], esi
0x180038237  mov     dword ptr [rsp+11C8h+var_1174], ebx
0x18003823b  mov     [rsp+11C8h+var_1178], ebp
0x18003823f  movups  [rsp+11C8h+var_68], xmm0
0x180038247  movups  [rsp+11C8h+var_58], xmm0
0x18003824f  jle     short loc_18003825D
0x180038251  xor     esi, esi
0x180038253  mov     dword ptr [rdx], 8
0x180038259  mov     dword ptr [rsp+11C8h+var_1174+4], esi
0x18003825d  mov     [rsp+11C8h+var_18], rdi
0x180038265  cmp     [rcx+0D70E0h], ebx
0x18003826b  jz      short loc_1800382BC
0x18003826d  mov     rdi, [rcx+547F0h]
0x180038274  mov     r8d, 10E8h; Size
0x18003827a  mov     rdx, rdi; Src
0x18003827d  test    esi, esi
0x18003827f  jz      short loc_1800382A7
0x180038281  lea     rcx, [rsp+11C8h+Src]; void *
0x180038286  call    memcpy_0
0x18003828b  mov     r8d, 10E8h; Size
0x180038291  mov     rdx, r14; Src
0x180038294  mov     rcx, rdi; void *
0x180038297  call    memcpy_0
0x18003829c  mov     r8d, 10E8h; Size
0x1800382a2  lea     rdx, [rsp+11C8h+Src]; Src
0x1800382a7  mov     rcx, r14; void *
0x1800382aa  call    memcpy_0
0x1800382af  mov     r11, [rsp+11C8h+var_1160]
0x1800382b4  mov     [r12+547F8h], esi
0x1800382bc  mov     r10d, [r14]
0x1800382bf  xor     r8d, r8d
0x1800382c2  test    r10d, r10d
0x1800382c5  jle     short loc_180038315
0x1800382c7  nop     word ptr [rax+rax+00000000h]
0x1800382d0  mov     r9d, r8d
0x1800382d3  imul    rcx, r9, 21Ch
0x1800382da  mov     edx, [rcx+r14+8]
0x1800382df  test    edx, edx
0x1800382e1  jz      short loc_1800382EF
0x1800382e3  cmp     edx, 1
0x1800382e6  jnz     short loc_18003830B
0x1800382e8  mov     eax, 2
0x1800382ed  jmp     short loc_1800382F4
0x1800382ef  mov     eax, 1
0x1800382f4  mov     dword ptr [rsp+r8*4+11C8h+var_68], eax
0x1800382fc  add     ebx, eax
0x1800382fe  inc     r8d
0x180038301  cmp     r8d, r10d
0x180038304  jl      short loc_1800382D0
0x180038306  cmp     ebx, 7
0x180038309  jle     short loc_180038315
0x18003830b  mov     edi, 0Eh
0x180038310  jmp     loc_1800384E4
0x180038315  mov     [rsp+11C8h+var_28], r13
0x18003831d  xor     r13d, r13d
0x180038320  cmp     [rsp+11C8h+arg_28], 6
0x180038328  jnz     short loc_18003835C
0x18003832a  cmp     dword ptr [r11], 6
0x18003832e  jnz     short loc_18003835C
0x180038330  cmp     r10d, 3
0x180038334  jnz     short loc_18003835C
0x180038336  cmp     dword ptr [rsp+11C8h+var_68], 1
0x18003833e  jnz     short loc_18003835C
0x180038340  cmp     dword ptr [rsp+11C8h+var_68+4], 2
0x180038348  jnz     short loc_18003835C
0x18003834a  cmp     dword ptr [rsp+11C8h+var_68+8], 2
0x180038352  jnz     short loc_18003835C
0x180038354  mov     r13d, 1
0x18003835a  inc     ebx
0x18003835c  test    ebx, ebx
0x18003835e  jle     short loc_18003838A
0x180038360  shl     ebx, 0Ch
0x180038363  cmp     ebx, 7000h
0x180038369  jbe     short loc_180038375
0x18003836b  mov     edi, 0Eh
0x180038370  jmp     loc_1800384DC
0x180038375  mov     r8d, ebx
0x180038378  mov     rdx, r12
0x18003837b  mov     rcx, r15
0x18003837e  call    cs:__imp_ippsCopy_8u
0x180038385  nop     dword ptr [rax+rax+00h]
0x18003838a  mov     edx, 0E000h
0x18003838f  mov     rcx, r15
0x180038392  xor     edi, edi
0x180038394  call    cs:__imp_ippsZero_8u
0x18003839b  nop     dword ptr [rax+rax+00h]
0x1800383a0  xor     r15d, r15d
0x1800383a3  cmp     [r14], edi
0x1800383a6  jle     loc_1800384B2
0x1800383ac  lea     rsi, [r12+7000h]
0x1800383b4  nop     dword ptr [rax+00h]
0x1800383b8  nop     dword ptr [rax+rax+00000000h]
0x1800383c0  movsxd  rax, r15d
0x1800383c3  xor     edx, edx; Val
0x1800383c5  mov     r8d, 4000h; Size
0x1800383cb  mov     rcx, rsi; void *
0x1800383ce  mov     ebx, dword ptr [rsp+rax*4+11C8h+var_68]
0x1800383d5  mov     dword ptr [rsp+11C8h+var_1174], ebx
0x1800383d9  call    memset_0
0x1800383de  shl     ebx, 0Ch
0x1800383e1  movsxd  r8, ebx; Size
0x1800383e4  test    ebx, ebx
0x1800383e6  jz      short loc_18003843B
0x1800383e8  test    rsi, rsi
0x1800383eb  jz      short loc_180038424
0x1800383ed  mov     eax, ebp
0x1800383ef  shl     eax, 0Ah
0x1800383f2  cdqe
0x1800383f4  lea     rdx, [r12+rax*4]; Src
0x1800383f8  test    rdx, rdx
0x1800383fb  jz      short loc_180038424
0x1800383fd  cmp     r8, 4000h
0x180038404  ja      short loc_180038410
0x180038406  mov     rcx, rsi; void *
0x180038409  call    memcpy_0
0x18003840e  jmp     short loc_18003843B
0x180038410  call    cs:__imp__o__errno
0x180038417  nop     dword ptr [rax+rax+00h]
0x18003841c  mov     dword ptr [rax], 22h ; '"'
0x180038422  jmp     short loc_180038436
0x180038424  call    cs:__imp__o__errno
0x18003842b  nop     dword ptr [rax+rax+00h]
0x180038430  mov     dword ptr [rax], 16h
0x180038436  call    _invalid_parameter_noinfo
0x18003843b  xor     eax, eax
0x18003843d  mov     r9d, r15d; int
0x180038440  mov     [rsp+11C8h+var_1180], eax; int
0x180038444  mov     r8d, ebp; int
0x180038447  mov     [rsp+11C8h+var_1188], eax; int
0x18003844b  mov     rdx, r14; int
0x18003844e  mov     dword ptr [rsp+11C8h+var_1190], eax; char
0x180038452  mov     rcx, r12; int
0x180038455  mov     eax, dword ptr [rsp+11C8h+var_1174+4]
0x180038459  mov     [rsp+11C8h+var_1198], eax; int
0x18003845d  lea     rax, [rsp+11C8h+var_1174]
0x180038462  mov     [rsp+11C8h+var_11A0], rax; __int64
0x180038467  mov     [rsp+11C8h+var_11A8], rsi; void *
0x18003846c  call    applySBROnOneAE
0x180038471  mov     edi, eax
0x180038473  test    eax, eax
0x180038475  jnz     loc_180038541
0x18003847b  mov     rax, [rsp+11C8h+var_1168]
0x180038480  mov     rdx, rsi; Src
0x180038483  mov     ebx, dword ptr [rsp+11C8h+var_1174]
0x180038487  mov     ecx, ebx
0x180038489  shl     ecx, 0Dh
0x18003848c  movsxd  r8, ecx; Size
0x18003848f  mov     ecx, ebp
0x180038491  shl     ecx, 0Bh
0x180038494  movsxd  rcx, ecx
0x180038497  lea     rcx, [rax+rcx*4]; void *
0x18003849b  call    memcpy_0
0x1800384a0  add     [rsp+11C8h+var_1178], ebx
0x1800384a4  add     ebp, ebx
0x1800384a6  inc     r15d
0x1800384a9  cmp     r15d, [r14]
0x1800384ac  jl      loc_1800383C0
0x1800384b2  test    r13d, r13d
0x1800384b5  jz      short loc_1800384D8
0x1800384b7  mov     rdx, [rsp+11C8h+var_1168]
0x1800384bc  lea     r9, [r12+0D70A4h]
0x1800384c4  add     rdx, 0A000h
0x1800384cb  lea     rcx, [r12+5000h]
0x1800384d3  call    LFEInterpolation
0x1800384d8  mov     ebp, [rsp+11C8h+var_1178]
0x1800384dc  mov     r13, [rsp+11C8h+var_28]
0x1800384e4  mov     rax, [rsp+11C8h+var_1160]
0x1800384e9  mov     r15, [rsp+11C8h+var_38]
0x1800384f1  mov     r14, [rsp+11C8h+var_30]
0x1800384f9  mov     r12, [rsp+11C8h+var_20]
0x180038501  cmp     dword ptr [rax], 1
0x180038504  mov     rsi, [rsp+11C8h+var_10]
0x18003850c  mov     rbx, [rsp+11C8h+arg_10]
0x180038514  jnz     short loc_18003851D
0x180038516  cmp     ebp, 2
0x180038519  jnz     short loc_18003851D
0x18003851b  mov     [rax], ebp
0x18003851d  mov     eax, edi
0x18003851f  mov     rdi, [rsp+11C8h+var_18]
0x180038527  mov     rcx, [rsp+11C8h+var_48]
0x18003852f  xor     rcx, rsp; StackCookie
0x180038532  call    __security_check_cookie
0x180038537  add     rsp, 11C0h
0x18003853e  pop     rbp
0x18003853f  retn
0x180038541  mov     edi, 0Eh
0x180038546  jmp     short loc_1800384D8
```
