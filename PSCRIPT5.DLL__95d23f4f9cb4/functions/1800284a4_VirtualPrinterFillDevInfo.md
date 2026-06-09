# VirtualPrinterFillDevInfo

- ea: `0x1800284a4`
- end: `0x180028661`
- name: `VirtualPrinterFillDevInfo`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800041a0`

## callees

- `0x1800027d6`
- `0x1800028d8`
- `0x180026e80`
- `0x180026ea4`
- `0x180026ee0`
- `0x1800284a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180028598`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180028633`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180028598`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180028633`
- `GDI32!EngCreatePalette` at `0x18002854a`
- `GDI32!EngCreatePalette` at `0x18002854a`

## string_xrefs

- `0x180028561`: `EngCreatePalette() failed!`

## pseudocode

```c
int __fastcall VirtualPrinterFillDevInfo(__int64 a1, _OWORD *a2, unsigned int a3)
{
  _OWORD *v3; // rbx
  int v5; // ebx
  HPALETTE Palette; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rcx
  _OWORD *v12; // rax
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int64 v22; // rax
  void *v23; // rdx
  unsigned int v24; // r8d
  int flGreen; // [rsp+20h] [rbp-178h]
  unsigned int flGreena; // [rsp+20h] [rbp-178h]
  const char *flBlue; // [rsp+28h] [rbp-170h]
  _DWORD v28[71]; // [rsp+30h] [rbp-168h] BYREF
  __int64 v29; // [rsp+14Ch] [rbp-4Ch]
  HPALETTE v30; // [rsp+158h] [rbp-40h]
  int v31; // [rsp+160h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  v3 = a2;
  if ( a3 < 0x138 )
  {
    v5 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDF,
      (unsigned int)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
      (const char *)0x80070057LL,
      flGreen);
    return v5;
  }
  memset_0(a2, 0, a3);
  memset_0(v28, 0, 0x138u);
  v28[0] = 1979752479;
  v31 = 1;
  v28[70] = 0;
  v29 = 5;
  Palette = EngCreatePalette(4u, 0, 0, 0, 0, 0);
  *(_QWORD *)(a1 + 120) = Palette;
  if ( !Palette )
  {
    v5 = -2147467259;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xF8,
      (unsigned int)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
      (const char *)0x80004005LL,
      (int)"EngCreatePalette() failed!",
      flBlue);
    return v5;
  }
  v30 = Palette;
  if ( v3 )
  {
    v11 = 2;
    v12 = v28;
    do
    {
      v13 = v12[1];
      *v3 = *v12;
      v14 = v12[2];
      v3[1] = v13;
      v15 = v12[3];
      v3[2] = v14;
      v16 = v12[4];
      v3[3] = v15;
      v17 = v12[5];
      v3[4] = v16;
      v18 = v12[6];
      v3[5] = v17;
      v19 = v12[7];
      v12 += 8;
      v3[6] = v18;
      v3[7] = v19;
      v3 += 8;
      --v11;
    }
    while ( v11 );
    v20 = v12[1];
    *v3 = *v12;
    v21 = v12[2];
    v22 = *((_QWORD *)v12 + 6);
    v3[1] = v20;
    v3[2] = v21;
    *((_QWORD *)v3 + 6) = v22;
    return 0;
  }
  else
  {
    *(_DWORD *)_o__errno(v9, v8, v10) = 22;
    invalid_parameter_noinfo();
    return wil::details::in1diag3::Return_Win32(retaddr, v23, v24, (const char *)0x16, flGreena);
  }
}

```

## disassembly

```asm
0x1800284a4  push    rbx
0x1800284a6  push    rbp
0x1800284a7  push    rsi
0x1800284a8  push    rdi
0x1800284a9  sub     rsp, 178h
0x1800284b0  mov     ebp, 138h
0x1800284b5  mov     rbx, rdx
0x1800284b8  mov     rsi, rcx
0x1800284bb  cmp     r8d, ebp
0x1800284be  jnb     short loc_1800284E6
0x1800284c0  mov     rcx, [rsp+198h]; this
0x1800284c8  lea     r8, aPrintscanPrint; "printscan\\print\\drivers\\usermode\\ps"...
0x1800284cf  mov     ebx, 80070057h
0x1800284d4  lea     edx, [rbp-59h]; void *
0x1800284d7  mov     r9d, ebx; char *
0x1800284da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800284df  mov     eax, ebx
0x1800284e1  jmp     loc_180028655
0x1800284e6  mov     edi, r8d
0x1800284e9  xor     edx, edx; Val
0x1800284eb  mov     r8d, r8d; Size
0x1800284ee  mov     rcx, rbx; void *
0x1800284f1  call    memset_0
0x1800284f6  mov     r8, rbp; Size
0x1800284f9  lea     rcx, [rsp+198h+var_168]; void *
0x1800284fe  xor     edx, edx; Val
0x180028500  call    memset_0
0x180028505  xor     edx, edx; cColors
0x180028507  mov     dword ptr [rsp+198h+flBlue], 0; char *
0x18002850f  xor     r9d, r9d; flRed
0x180028512  mov     [rsp+198h+var_168], 7600A01Fh
0x18002851a  xor     r8d, r8d; pulColors
0x18002851d  mov     [rsp+198h+var_38], 1
0x180028528  mov     [rsp+198h+var_50], 0
0x180028533  lea     ecx, [rdx+4]; iMode
0x180028536  mov     [rsp+198h+var_4C], 5
0x180028542  mov     [rsp+198h+flGreen], 0; unsigned int
0x18002854a  call    cs:__imp_EngCreatePalette
0x180028550  mov     [rsi+78h], rax
0x180028554  test    rax, rax
0x180028557  jnz     short loc_18002858B
0x180028559  mov     rcx, [rsp+198h]; this
0x180028561  lea     rax, aEngcreatepalet; "EngCreatePalette() failed!"
0x180028568  mov     ebx, 80004005h
0x18002856d  mov     qword ptr [rsp+198h+flGreen], rax; int
0x180028572  mov     r9d, ebx; char *
0x180028575  lea     r8, aPrintscanPrint; "printscan\\print\\drivers\\usermode\\ps"...
0x18002857c  mov     edx, 0F8h; void *
0x180028581  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180028586  jmp     loc_1800284DF
0x18002858b  mov     [rsp+198h+var_40], rax
0x180028593  test    rbx, rbx
0x180028596  jnz     short loc_1800285A8
0x180028598  call    cs:__imp__o__errno
0x18002859e  mov     ebx, 16h
0x1800285a3  jmp     loc_18002863E
0x1800285a8  cmp     rdi, rbp
0x1800285ab  jb      short loc_180028626
0x1800285ad  mov     ecx, 2
0x1800285b2  lea     rax, [rsp+198h+var_168]
0x1800285b7  lea     edx, [rcx+7Eh]
0x1800285ba  movups  xmm0, xmmword ptr [rax]
0x1800285bd  movups  xmm1, xmmword ptr [rax+10h]
0x1800285c1  movups  xmmword ptr [rbx], xmm0
0x1800285c4  movups  xmm0, xmmword ptr [rax+20h]
0x1800285c8  movups  xmmword ptr [rbx+10h], xmm1
0x1800285cc  movups  xmm1, xmmword ptr [rax+30h]
0x1800285d0  movups  xmmword ptr [rbx+20h], xmm0
0x1800285d4  movups  xmm0, xmmword ptr [rax+40h]
0x1800285d8  movups  xmmword ptr [rbx+30h], xmm1
0x1800285dc  movups  xmm1, xmmword ptr [rax+50h]
0x1800285e0  movups  xmmword ptr [rbx+40h], xmm0
0x1800285e4  movups  xmm0, xmmword ptr [rax+60h]
0x1800285e8  movups  xmmword ptr [rbx+50h], xmm1
0x1800285ec  movups  xmm1, xmmword ptr [rax+70h]
0x1800285f0  add     rax, rdx
0x1800285f3  movups  xmmword ptr [rbx+60h], xmm0
0x1800285f7  movups  xmmword ptr [rbx+70h], xmm1
0x1800285fb  add     rbx, rdx
0x1800285fe  sub     rcx, 1
0x180028602  jnz     short loc_1800285BA
0x180028604  movups  xmm0, xmmword ptr [rax]
0x180028607  movups  xmm1, xmmword ptr [rax+10h]
0x18002860b  movups  xmmword ptr [rbx], xmm0
0x18002860e  movups  xmm0, xmmword ptr [rax+20h]
0x180028612  mov     rax, [rax+30h]
0x180028616  movups  xmmword ptr [rbx+10h], xmm1
0x18002861a  movups  xmmword ptr [rbx+20h], xmm0
0x18002861e  mov     [rbx+30h], rax
0x180028622  xor     eax, eax
0x180028624  jmp     short loc_180028655
0x180028626  mov     r8, rdi; Size
0x180028629  xor     edx, edx; Val
0x18002862b  mov     rcx, rbx; void *
0x18002862e  call    memset_0
0x180028633  call    cs:__imp__o__errno
0x180028639  mov     ebx, 22h ; '"'
0x18002863e  mov     [rax], ebx
0x180028640  call    _invalid_parameter_noinfo
0x180028645  mov     rcx, [rsp+198h]; this
0x18002864d  mov     r9d, ebx; char *
0x180028650  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180028655  add     rsp, 178h
0x18002865c  pop     rdi
0x18002865d  pop     rsi
0x18002865e  pop     rbp
0x18002865f  pop     rbx
0x180028660  retn
```
