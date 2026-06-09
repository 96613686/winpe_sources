# VirtualPrinterFillDevInfo

- ea: `0x180029514`
- end: `0x1800296e4`
- name: `VirtualPrinterFillDevInfo`
- size: `464`
- prototype: `__int64 __fastcall(__int64, _OWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180004240`

## callees

- `0x180002836`
- `0x180002938`
- `0x180027c74`
- `0x180027c98`
- `0x180027cd8`
- `0x180029514`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002960e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800296af`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002960e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800296af`
- `GDI32!EngCreatePalette` at `0x1800295ba`
- `GDI32!EngCreatePalette` at `0x1800295ba`

## string_xrefs

- `0x1800295d7`: `EngCreatePalette() failed!`

## pseudocode

```c
__int64 __fastcall VirtualPrinterFillDevInfo(__int64 a1, _OWORD *a2, unsigned int a3)
{
  _OWORD *v3; // rbx
  unsigned int v5; // ebx
  HPALETTE Palette; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  _OWORD *v10; // rax
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int64 v20; // rax
  void *v21; // rdx
  __int64 v22; // r8
  const char *flBlue; // [rsp+28h] [rbp-170h]
  _DWORD v24[71]; // [rsp+30h] [rbp-168h] BYREF
  __int64 v25; // [rsp+14Ch] [rbp-4Ch]
  HPALETTE v26; // [rsp+158h] [rbp-40h]
  int v27; // [rsp+160h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  v3 = a2;
  if ( a3 < 0x138 )
  {
    v5 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDF,
      (__int64)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
      (const char *)0x80070057LL);
    return v5;
  }
  memset_0(a2, 0, a3);
  memset_0(v24, 0, 0x138u);
  v24[0] = 1979752479;
  v27 = 1;
  v24[70] = 0;
  v25 = 5;
  Palette = EngCreatePalette(4u, 0, 0, 0, 0, 0);
  *(_QWORD *)(a1 + 120) = Palette;
  if ( !Palette )
  {
    v5 = -2147467259;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xF8,
      (__int64)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
      (const char *)0x80004005LL,
      (__int64)"EngCreatePalette() failed!",
      flBlue);
    return v5;
  }
  v26 = Palette;
  if ( v3 )
  {
    v9 = 2;
    v10 = v24;
    do
    {
      v11 = v10[1];
      *v3 = *v10;
      v12 = v10[2];
      v3[1] = v11;
      v13 = v10[3];
      v3[2] = v12;
      v14 = v10[4];
      v3[3] = v13;
      v15 = v10[5];
      v3[4] = v14;
      v16 = v10[6];
      v3[5] = v15;
      v17 = v10[7];
      v10 += 8;
      v3[6] = v16;
      v3[7] = v17;
      v3 += 8;
      --v9;
    }
    while ( v9 );
    v18 = v10[1];
    *v3 = *v10;
    v19 = v10[2];
    v20 = *((_QWORD *)v10 + 6);
    v3[1] = v18;
    v3[2] = v19;
    *((_QWORD *)v3 + 6) = v20;
    return 0;
  }
  else
  {
    *(_DWORD *)_o__errno(v8) = 22;
    invalid_parameter_noinfo();
    return wil::details::in1diag3::Return_Win32(retaddr, v21, v22, (const char *)0x16);
  }
}

```

## disassembly

```asm
0x180029514  push    rbx
0x180029516  push    rbp
0x180029517  push    rsi
0x180029518  push    rdi
0x180029519  sub     rsp, 178h
0x180029520  mov     ebp, 138h
0x180029525  mov     rbx, rdx
0x180029528  mov     rsi, rcx
0x18002952b  cmp     r8d, ebp
0x18002952e  jnb     short loc_180029556
0x180029530  mov     rcx, [rsp+198h]; this
0x180029538  lea     r8, aPrintscanPrint; "printscan\\print\\drivers\\usermode\\ps"...
0x18002953f  mov     ebx, 80070057h
0x180029544  lea     edx, [rbp-59h]; void *
0x180029547  mov     r9d, ebx; char *
0x18002954a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002954f  mov     eax, ebx
0x180029551  jmp     loc_1800296D7
0x180029556  mov     edi, r8d
0x180029559  xor     edx, edx; Val
0x18002955b  mov     r8d, r8d; Size
0x18002955e  mov     rcx, rbx; void *
0x180029561  call    memset_0
0x180029566  mov     r8, rbp; Size
0x180029569  lea     rcx, [rsp+198h+var_168]; void *
0x18002956e  xor     edx, edx; Val
0x180029570  call    memset_0
0x180029575  xor     edx, edx; cColors
0x180029577  mov     dword ptr [rsp+198h+flBlue], 0; char *
0x18002957f  xor     r9d, r9d; flRed
0x180029582  mov     [rsp+198h+var_168], 7600A01Fh
0x18002958a  xor     r8d, r8d; pulColors
0x18002958d  mov     [rsp+198h+var_38], 1
0x180029598  mov     [rsp+198h+var_50], 0
0x1800295a3  lea     ecx, [rdx+4]; iMode
0x1800295a6  mov     [rsp+198h+var_4C], 5
0x1800295b2  mov     [rsp+198h+flGreen], 0; unsigned int
0x1800295ba  call    cs:__imp_EngCreatePalette
0x1800295c1  nop     dword ptr [rax+rax+00h]
0x1800295c6  mov     [rsi+78h], rax
0x1800295ca  test    rax, rax
0x1800295cd  jnz     short loc_180029601
0x1800295cf  mov     rcx, [rsp+198h]; this
0x1800295d7  lea     rax, aEngcreatepalet; "EngCreatePalette() failed!"
0x1800295de  mov     ebx, 80004005h
0x1800295e3  mov     qword ptr [rsp+198h+flGreen], rax; int
0x1800295e8  mov     r9d, ebx; char *
0x1800295eb  lea     r8, aPrintscanPrint; "printscan\\print\\drivers\\usermode\\ps"...
0x1800295f2  mov     edx, 0F8h; void *
0x1800295f7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800295fc  jmp     loc_18002954F
0x180029601  mov     [rsp+198h+var_40], rax
0x180029609  test    rbx, rbx
0x18002960c  jnz     short loc_180029624
0x18002960e  call    cs:__imp__o__errno
0x180029615  nop     dword ptr [rax+rax+00h]
0x18002961a  mov     ebx, 16h
0x18002961f  jmp     loc_1800296C0
0x180029624  cmp     rdi, rbp
0x180029627  jb      short loc_1800296A2
0x180029629  mov     ecx, 2
0x18002962e  lea     rax, [rsp+198h+var_168]
0x180029633  lea     edx, [rcx+7Eh]
0x180029636  movups  xmm0, xmmword ptr [rax]
0x180029639  movups  xmm1, xmmword ptr [rax+10h]
0x18002963d  movups  xmmword ptr [rbx], xmm0
0x180029640  movups  xmm0, xmmword ptr [rax+20h]
0x180029644  movups  xmmword ptr [rbx+10h], xmm1
0x180029648  movups  xmm1, xmmword ptr [rax+30h]
0x18002964c  movups  xmmword ptr [rbx+20h], xmm0
0x180029650  movups  xmm0, xmmword ptr [rax+40h]
0x180029654  movups  xmmword ptr [rbx+30h], xmm1
0x180029658  movups  xmm1, xmmword ptr [rax+50h]
0x18002965c  movups  xmmword ptr [rbx+40h], xmm0
0x180029660  movups  xmm0, xmmword ptr [rax+60h]
0x180029664  movups  xmmword ptr [rbx+50h], xmm1
0x180029668  movups  xmm1, xmmword ptr [rax+70h]
0x18002966c  add     rax, rdx
0x18002966f  movups  xmmword ptr [rbx+60h], xmm0
0x180029673  movups  xmmword ptr [rbx+70h], xmm1
0x180029677  add     rbx, rdx
0x18002967a  sub     rcx, 1
0x18002967e  jnz     short loc_180029636
0x180029680  movups  xmm0, xmmword ptr [rax]
0x180029683  movups  xmm1, xmmword ptr [rax+10h]
0x180029687  movups  xmmword ptr [rbx], xmm0
0x18002968a  movups  xmm0, xmmword ptr [rax+20h]
0x18002968e  mov     rax, [rax+30h]
0x180029692  movups  xmmword ptr [rbx+10h], xmm1
0x180029696  movups  xmmword ptr [rbx+20h], xmm0
0x18002969a  mov     [rbx+30h], rax
0x18002969e  xor     eax, eax
0x1800296a0  jmp     short loc_1800296D7
0x1800296a2  mov     r8, rdi; Size
0x1800296a5  xor     edx, edx; Val
0x1800296a7  mov     rcx, rbx; void *
0x1800296aa  call    memset_0
0x1800296af  call    cs:__imp__o__errno
0x1800296b6  nop     dword ptr [rax+rax+00h]
0x1800296bb  mov     ebx, 22h ; '"'
0x1800296c0  mov     [rax], ebx
0x1800296c2  call    _invalid_parameter_noinfo
0x1800296c7  mov     rcx, [rsp+198h]; this
0x1800296cf  mov     r9d, ebx; char *
0x1800296d2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800296d7  add     rsp, 178h
0x1800296de  pop     rdi
0x1800296df  pop     rsi
0x1800296e0  pop     rbp
0x1800296e1  pop     rbx
0x1800296e2  retn
```
