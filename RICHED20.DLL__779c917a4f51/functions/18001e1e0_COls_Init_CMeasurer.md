# COls::Init(CMeasurer *)

- ea: `0x18001e1e0`
- end: `0x18001e55c`
- name: `?Init@COls@@QEAAJPEAVCMeasurer@@@Z`
- size: `892`
- prototype: `__int64 __fastcall(COls *__hidden this, struct CMeasurer *)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ea70`
- `0x18000feb0`
- `0x1800114e8`
- `0x1800167f0`
- `0x18001e030`
- `0x18001e564`
- `0x18001fafc`

## callees

- `0x18001e1e0`
- `0x180035ee0`
- `0x18009110a`
- `0x180091140`

## import_xrefs

- `msls31!__imp_LsCreateContext` at `0x18001e42f`
- `msls31!__imp_LsCreateContext` at `0x18001e42f`
- `msls31!__imp_LsSetBreaking` at `0x18001e529`
- `msls31!__imp_LsSetBreaking` at `0x18001e529`
- `msls31!__imp_LsGetReverseLsimethods` at `0x18001e2bc`
- `msls31!__imp_LsGetReverseLsimethods` at `0x18001e2bc`

## pseudocode

```c
__int64 __fastcall COls::Init(COls *this, struct CMeasurer *a2)
{
  COls *v2; // rbx
  __m128i si128; // xmm0
  __int64 v4; // rdx
  char *v5; // rcx
  __int128 *v6; // rax
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int64 v21; // rbx
  char *v22; // rdi
  int i; // esi
  int v24; // r15d
  bool v25; // zf
  char v26; // r15
  _OWORD v28[11]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 (__fastcall *v29)(CDisplay *__hidden); // [rsp+E0h] [rbp-20h]
  _BYTE v30[184]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v31[4]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v32; // [rsp+1A4h] [rbp+A4h]
  _OWORD *v33; // [rsp+1A8h] [rbp+A8h]
  int v34; // [rsp+1B0h] [rbp+B0h]
  __int16 v35; // [rsp+1B4h] [rbp+B4h]
  __int64 v36; // [rsp+1B6h] [rbp+B6h]
  _BYTE v37[18]; // [rsp+1BEh] [rbp+BEh]
  __m128i v38; // [rsp+1D0h] [rbp+D0h]
  _BYTE v39[44]; // [rsp+1E0h] [rbp+E0h] BYREF
  COls *v40; // [rsp+210h] [rbp+110h]
  char v41; // [rsp+218h] [rbp+118h] BYREF
  int v42; // [rsp+408h] [rbp+308h]
  _BYTE v43[256]; // [rsp+410h] [rbp+310h] BYREF

  v2 = g_pols;
  *(_QWORD *)g_pols = a2;
  if ( g_plsc )
    return 0;
  memset_0(v31, 0, 0x270u);
  v28[0] = vlsimethodsOle;
  v29 = CDisplay::GetYScroll;
  v28[2] = *(_OWORD *)&off_180093050;
  v28[1] = *(_OWORD *)&off_180093040;
  v28[4] = *(_OWORD *)byte_180093070;
  v28[3] = xmmword_180093060;
  v28[6] = *(_OWORD *)&off_180093090;
  v28[5] = *(_OWORD *)&off_180093080;
  v28[8] = *(_OWORD *)byte_1800930B0;
  v28[7] = *(_OWORD *)&off_1800930A0;
  v28[10] = *(_OWORD *)byte_1800930D0;
  v28[9] = *(_OWORD *)off_1800930C0;
  if ( (unsigned int)LsGetReverseLsimethods(v30) )
    return 2147500037LL;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v33 = v28;
  v35 = si128.m128i_i16[2];
  v32 = 2;
  *(__m128i *)&v37[2] = si128;
  *(_WORD *)&v37[6] = 11;
  v4 = 3;
  v42 = 1;
  *(__m128i *)&v39[16] = si128;
  v34 = 66;
  *(__m128i *)v39 = si128;
  strcpy(&v39[12], " ");
  v5 = &v41;
  v38 = si128;
  v38.m128i_i16[0] = 173;
  *(__m128i *)&v39[28] = si128;
  *(_WORD *)&v39[40] = 159;
  v6 = (__int128 *)&lscbk;
  v36 = 0x9002D00200000LL;
  *(_DWORD *)v37 = 655373;
  *(_DWORD *)&v39[14] = 2097184;
  v40 = v2;
  do
  {
    v5 += 128;
    v7 = *v6;
    v8 = v6[1];
    v6 += 8;
    *((_OWORD *)v5 - 8) = v7;
    v9 = *(v6 - 6);
    *((_OWORD *)v5 - 7) = v8;
    v10 = *(v6 - 5);
    *((_OWORD *)v5 - 6) = v9;
    v11 = *(v6 - 4);
    *((_OWORD *)v5 - 5) = v10;
    v12 = *(v6 - 3);
    *((_OWORD *)v5 - 4) = v11;
    v13 = *(v6 - 2);
    *((_OWORD *)v5 - 3) = v12;
    v14 = *(v6 - 1);
    *((_OWORD *)v5 - 2) = v13;
    *((_OWORD *)v5 - 1) = v14;
    --v4;
  }
  while ( v4 );
  v15 = v6[1];
  *(_OWORD *)v5 = *v6;
  v16 = v6[2];
  *((_OWORD *)v5 + 1) = v15;
  v17 = v6[3];
  *((_OWORD *)v5 + 2) = v16;
  v18 = v6[4];
  *((_OWORD *)v5 + 3) = v17;
  v19 = v6[5];
  *((_OWORD *)v5 + 4) = v18;
  v20 = v6[6];
  *((_OWORD *)v5 + 5) = v19;
  *((_OWORD *)v5 + 6) = v20;
  if ( (unsigned int)LsCreateContext(v31, &g_plsc) )
    return 2147500037LL;
  v21 = 0;
  v22 = v43;
  do
  {
    for ( i = 0; i < 16; ++i )
    {
      v24 = (*((unsigned __int16 *)qword_180098190 + v21) >> i) & 1;
      v25 = 2 * v24 == 0;
      v26 = 2 * v24;
      if ( v25 && (unsigned int)GetKinsokuClass(v21) != 1 && (unsigned int)GetKinsokuClass(i) != 1 )
        v26 = 1;
      *v22++ = v26;
    }
    v21 = (unsigned int)(v21 + 1);
  }
  while ( (int)v21 < 16 );
  return (unsigned int)LsSetBreaking(g_plsc, 3, &qword_180098FC8, 16, v43) != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x18001e1e0  push    rbp
0x18001e1e2  push    rbx
0x18001e1e3  lea     rbp, [rsp-438h]
0x18001e1eb  sub     rsp, 538h
0x18001e1f2  mov     rax, cs:__security_cookie
0x18001e1f9  xor     rax, rsp
0x18001e1fc  mov     [rbp+440h+var_30], rax
0x18001e203  mov     rbx, cs:?g_pols@@3PEAUCOls@@EA; COls * g_pols
0x18001e20a  mov     [rbx], rdx
0x18001e20d  cmp     cs:?g_plsc@@3PEAUCLineServices@@EA, 0; CLineServices * g_plsc
0x18001e215  jnz     loc_18001E541
0x18001e21b  xor     edx, edx; Val
0x18001e21d  lea     rcx, [rbp+440h+var_3A0]; void *
0x18001e224  mov     r8d, 270h; Size
0x18001e22a  call    memset_0
0x18001e22f  movaps  xmm0, xmmword ptr cs:?vlsimethodsOle@@3ULSIMETHODS@@B; LSIMETHODS const vlsimethodsOle
0x18001e236  lea     rcx, [rbp+440h+var_458]
0x18001e23a  movaps  xmm1, xmmword ptr cs:off_180093040
0x18001e241  mov     rax, cs:off_1800930E0
0x18001e248  movups  [rsp+540h+var_510], xmm0
0x18001e24d  mov     [rbp+440h+var_460], rax
0x18001e251  movaps  xmm0, xmmword ptr cs:off_180093050
0x18001e258  movups  [rsp+540h+var_4F0], xmm0
0x18001e25d  movaps  xmm0, xmmword ptr cs:byte_180093070
0x18001e264  movups  [rsp+540h+var_500], xmm1
0x18001e269  movaps  xmm1, cs:xmmword_180093060
0x18001e270  movups  [rsp+540h+var_4D0], xmm0
0x18001e275  movaps  xmm0, xmmword ptr cs:off_180093090
0x18001e27c  movups  [rsp+540h+var_4E0], xmm1
0x18001e281  movaps  xmm1, xmmword ptr cs:off_180093080
0x18001e288  movups  [rbp+440h+var_4B0], xmm0
0x18001e28c  movaps  xmm0, xmmword ptr cs:byte_1800930B0
0x18001e293  movups  [rbp+440h+var_4C0], xmm1
0x18001e297  movaps  xmm1, xmmword ptr cs:off_1800930A0
0x18001e29e  movups  [rbp+440h+var_490], xmm0
0x18001e2a2  movaps  xmm0, xmmword ptr cs:byte_1800930D0
0x18001e2a9  movups  [rbp+440h+var_4A0], xmm1
0x18001e2ad  movaps  xmm1, xmmword ptr cs:off_1800930C0
0x18001e2b4  movups  [rbp+440h+var_470], xmm0
0x18001e2b8  movups  [rbp+440h+var_480], xmm1
0x18001e2bc  call    cs:__imp_LsGetReverseLsimethods
0x18001e2c2  test    eax, eax
0x18001e2c4  jnz     loc_18001E53A
0x18001e2ca  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18001e2d2  lea     rax, [rsp+540h+var_510]
0x18001e2d7  mov     [rbp+440h+var_398], rax
0x18001e2de  mov     ecx, 20h ; ' '
0x18001e2e3  movups  [rbp+440h+var_390], xmm0
0x18001e2ea  mov     eax, 0Bh
0x18001e2ef  mov     [rbp+440h+var_39C], 2
0x18001e2f9  movups  [rbp+440h+var_380], xmm0
0x18001e300  mov     word ptr [rbp+440h+var_380+4], ax
0x18001e307  mov     edx, 3
0x18001e30c  mov     eax, 0ADh
0x18001e311  mov     [rbp+440h+var_138], 1
0x18001e31b  movups  [rbp+440h+var_350], xmm0
0x18001e322  mov     dword ptr [rbp+440h+var_390], 42h ; 'B'
0x18001e32c  movups  [rbp+440h+var_360], xmm0
0x18001e333  mov     word ptr [rbp+440h+var_360+0Ch], cx
0x18001e33a  lea     rcx, [rbp+440h+var_328]
0x18001e341  movups  [rbp+440h+var_370], xmm0
0x18001e348  mov     word ptr [rbp+440h+var_370], ax
0x18001e34f  mov     eax, 9Fh
0x18001e354  movups  [rbp+440h+var_350+0Ch], xmm0
0x18001e35b  mov     [rbp+440h+var_338], ax
0x18001e362  lea     rax, ?lscbk@@3U0@B; lscbk const lscbk
0x18001e369  mov     dword ptr [rbp+440h+var_390+6], 200000h
0x18001e373  mov     dword ptr [rbp+440h+var_390+0Ah], 9002Dh
0x18001e37d  mov     dword ptr [rbp+440h+var_390+0Eh], 0A000Dh
0x18001e387  mov     dword ptr [rbp+440h+var_360+0Eh], 200020h
0x18001e391  mov     [rbp+440h+var_330], rbx
0x18001e398  lea     rcx, [rcx+80h]
0x18001e39f  movups  xmm0, xmmword ptr [rax]
0x18001e3a2  movups  xmm1, xmmword ptr [rax+10h]
0x18001e3a6  lea     rax, [rax+80h]
0x18001e3ad  movups  xmmword ptr [rcx-80h], xmm0
0x18001e3b1  movups  xmm0, xmmword ptr [rax-60h]
0x18001e3b5  movups  xmmword ptr [rcx-70h], xmm1
0x18001e3b9  movups  xmm1, xmmword ptr [rax-50h]
0x18001e3bd  movups  xmmword ptr [rcx-60h], xmm0
0x18001e3c1  movups  xmm0, xmmword ptr [rax-40h]
0x18001e3c5  movups  xmmword ptr [rcx-50h], xmm1
0x18001e3c9  movups  xmm1, xmmword ptr [rax-30h]
0x18001e3cd  movups  xmmword ptr [rcx-40h], xmm0
0x18001e3d1  movups  xmm0, xmmword ptr [rax-20h]
0x18001e3d5  movups  xmmword ptr [rcx-30h], xmm1
0x18001e3d9  movups  xmm1, xmmword ptr [rax-10h]
0x18001e3dd  movups  xmmword ptr [rcx-20h], xmm0
0x18001e3e1  movups  xmmword ptr [rcx-10h], xmm1
0x18001e3e5  sub     rdx, 1
0x18001e3e9  jnz     short loc_18001E398
0x18001e3eb  movups  xmm0, xmmword ptr [rax]
0x18001e3ee  lea     rdx, ?g_plsc@@3PEAUCLineServices@@EA; CLineServices * g_plsc
0x18001e3f5  movups  xmm1, xmmword ptr [rax+10h]
0x18001e3f9  movups  xmmword ptr [rcx], xmm0
0x18001e3fc  movups  xmm0, xmmword ptr [rax+20h]
0x18001e400  movups  xmmword ptr [rcx+10h], xmm1
0x18001e404  movups  xmm1, xmmword ptr [rax+30h]
0x18001e408  movups  xmmword ptr [rcx+20h], xmm0
0x18001e40c  movups  xmm0, xmmword ptr [rax+40h]
0x18001e410  movups  xmmword ptr [rcx+30h], xmm1
0x18001e414  movups  xmm1, xmmword ptr [rax+50h]
0x18001e418  movups  xmmword ptr [rcx+40h], xmm0
0x18001e41c  movups  xmm0, xmmword ptr [rax+60h]
0x18001e420  movups  xmmword ptr [rcx+50h], xmm1
0x18001e424  movups  xmmword ptr [rcx+60h], xmm0
0x18001e428  lea     rcx, [rbp+440h+var_3A0]
0x18001e42f  call    cs:__imp_LsCreateContext
0x18001e435  test    eax, eax
0x18001e437  jnz     loc_18001E53A
0x18001e43d  mov     [rsp+540h+arg_0], rsi
0x18001e445  xor     ebx, ebx
0x18001e447  mov     [rsp+540h+arg_8], rdi
0x18001e44f  lea     rdi, [rbp+440h+var_130]
0x18001e456  mov     [rsp+540h+arg_10], r12
0x18001e45e  mov     [rsp+540h+var_10], r13
0x18001e466  lea     r13, qword_180098190
0x18001e46d  mov     [rsp+540h+var_18], r14
0x18001e475  mov     [rsp+540h+var_20], r15
0x18001e47d  xor     esi, esi
0x18001e47f  lea     r14, ds:0[rbx*2]
0x18001e487  movzx   r15d, word ptr [r14+r13]
0x18001e48c  movzx   r12d, si
0x18001e490  mov     ecx, r12d
0x18001e493  shr     r15d, cl
0x18001e496  and     r15d, 1
0x18001e49a  add     r15d, r15d
0x18001e49d  jnz     short loc_18001E4C0
0x18001e49f  movzx   ecx, bx; unsigned __int16
0x18001e4a2  call    ?GetKinsokuClass@@YAHG@Z; GetKinsokuClass(ushort)
0x18001e4a7  cmp     eax, 1
0x18001e4aa  jz      short loc_18001E4C0
0x18001e4ac  movzx   ecx, si; unsigned __int16
0x18001e4af  call    ?GetKinsokuClass@@YAHG@Z; GetKinsokuClass(ushort)
0x18001e4b4  cmp     eax, 1
0x18001e4b7  mov     eax, 1
0x18001e4bc  cmovnz  r15d, eax
0x18001e4c0  mov     [rdi], r15b
0x18001e4c3  inc     esi
0x18001e4c5  inc     rdi
0x18001e4c8  cmp     esi, 10h
0x18001e4cb  jl      short loc_18001E487
0x18001e4cd  inc     ebx
0x18001e4cf  cmp     ebx, 10h
0x18001e4d2  jl      short loc_18001E47D
0x18001e4d4  mov     rcx, cs:?g_plsc@@3PEAUCLineServices@@EA; CLineServices * g_plsc
0x18001e4db  lea     rax, [rbp+440h+var_130]
0x18001e4e2  mov     r15, [rsp+540h+var_20]
0x18001e4ea  lea     r8, qword_180098FC8
0x18001e4f1  mov     r14, [rsp+540h+var_18]
0x18001e4f9  mov     r9d, 10h
0x18001e4ff  mov     r13, [rsp+540h+var_10]
0x18001e507  mov     edx, 3
0x18001e50c  mov     r12, [rsp+540h+arg_10]
0x18001e514  mov     rdi, [rsp+540h+arg_8]
0x18001e51c  mov     rsi, [rsp+540h+arg_0]
0x18001e524  mov     [rsp+540h+var_520], rax
0x18001e529  call    cs:__imp_LsSetBreaking
0x18001e52f  neg     eax
0x18001e531  sbb     eax, eax
0x18001e533  and     eax, 80004005h
0x18001e538  jmp     short loc_18001E543
0x18001e53a  mov     eax, 80004005h
0x18001e53f  jmp     short loc_18001E543
0x18001e541  xor     eax, eax
0x18001e543  mov     rcx, [rbp+440h+var_30]
0x18001e54a  xor     rcx, rsp; StackCookie
0x18001e54d  call    __security_check_cookie
0x18001e552  add     rsp, 538h
0x18001e559  pop     rbx
0x18001e55a  pop     rbp
0x18001e55b  retn
```
