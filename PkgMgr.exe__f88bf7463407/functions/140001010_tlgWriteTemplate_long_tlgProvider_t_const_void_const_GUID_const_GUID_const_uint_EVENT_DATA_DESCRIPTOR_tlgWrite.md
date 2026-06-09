# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001010`
- end: `0x1400012fd`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$01@@U1@U?$_tlgWrapSz@D@@U2@U3@U3@U3@U2@U3@U3@U3@U3@U1@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$01@@3AEBU?$_tlgWrapSz@D@@455545555353@Z`
- size: `749`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140023b70`

## callees

- `0x140001010`
- `0x140001c88`
- `0x140002360`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        const wchar_t **a10,
        __int64 a11,
        const wchar_t **a12,
        const wchar_t **a13,
        const wchar_t **a14,
        __int64 a15,
        const wchar_t **a16,
        const wchar_t **a17,
        const wchar_t **a18,
        const wchar_t **a19,
        __int64 a20,
        const wchar_t **a21,
        __int64 a22)
{
  __int64 v22; // r8
  const wchar_t *v23; // rax
  __int64 v24; // r9
  bool v25; // zf
  int v26; // r10d
  int v27; // r9d
  const wchar_t *v28; // r10
  __int64 v29; // rax
  int v30; // eax
  const wchar_t *v31; // r10
  __int64 v32; // rax
  int v33; // eax
  const wchar_t *v34; // r10
  __int64 v35; // rax
  int v36; // eax
  const wchar_t *v37; // r10
  __int64 v38; // rax
  int v39; // eax
  const wchar_t *v40; // r10
  __int64 v41; // rax
  int v42; // eax
  const wchar_t *v43; // r10
  __int64 v44; // rax
  int v45; // eax
  const wchar_t *v46; // r10
  __int64 v47; // rax
  int v48; // eax
  const wchar_t *v49; // r10
  struct _EVENT_DATA_DESCRIPTOR v51; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v52; // [rsp+50h] [rbp-B0h]
  __int64 v53; // [rsp+58h] [rbp-A8h]
  __int64 v54; // [rsp+60h] [rbp-A0h]
  __int64 v55; // [rsp+68h] [rbp-98h]
  __int64 v56; // [rsp+70h] [rbp-90h]
  __int64 v57; // [rsp+78h] [rbp-88h]
  __int64 v58; // [rsp+80h] [rbp-80h]
  __int64 v59; // [rsp+88h] [rbp-78h]
  __int64 v60; // [rsp+90h] [rbp-70h]
  __int64 v61; // [rsp+98h] [rbp-68h]
  const wchar_t *v62; // [rsp+A0h] [rbp-60h]
  int v63; // [rsp+A8h] [rbp-58h]
  int v64; // [rsp+ACh] [rbp-54h]
  __int64 v65; // [rsp+B0h] [rbp-50h]
  __int64 v66; // [rsp+B8h] [rbp-48h]
  const wchar_t *v67; // [rsp+C0h] [rbp-40h]
  int v68; // [rsp+C8h] [rbp-38h]
  int v69; // [rsp+CCh] [rbp-34h]
  const wchar_t *v70; // [rsp+D0h] [rbp-30h]
  int v71; // [rsp+D8h] [rbp-28h]
  int v72; // [rsp+DCh] [rbp-24h]
  const wchar_t *v73; // [rsp+E0h] [rbp-20h]
  int v74; // [rsp+E8h] [rbp-18h]
  int v75; // [rsp+ECh] [rbp-14h]
  __int64 v76; // [rsp+F0h] [rbp-10h]
  __int64 v77; // [rsp+F8h] [rbp-8h]
  const wchar_t *v78; // [rsp+100h] [rbp+0h]
  int v79; // [rsp+108h] [rbp+8h]
  int v80; // [rsp+10Ch] [rbp+Ch]
  const wchar_t *v81; // [rsp+110h] [rbp+10h]
  int v82; // [rsp+118h] [rbp+18h]
  int v83; // [rsp+11Ch] [rbp+1Ch]
  const wchar_t *v84; // [rsp+120h] [rbp+20h]
  int v85; // [rsp+128h] [rbp+28h]
  int v86; // [rsp+12Ch] [rbp+2Ch]
  const wchar_t *v87; // [rsp+130h] [rbp+30h]
  int v88; // [rsp+138h] [rbp+38h]
  int v89; // [rsp+13Ch] [rbp+3Ch]
  __int64 v90; // [rsp+140h] [rbp+40h]
  __int64 v91; // [rsp+148h] [rbp+48h]
  const wchar_t *v92; // [rsp+150h] [rbp+50h]
  int v93; // [rsp+158h] [rbp+58h]
  int v94; // [rsp+15Ch] [rbp+5Ch]
  __int64 v95; // [rsp+160h] [rbp+60h]
  __int64 v96; // [rsp+168h] [rbp+68h]

  v95 = a22;
  v22 = -1;
  v96 = 4;
  v23 = *a21;
  if ( *a21 )
  {
    v24 = -1;
    do
      v25 = *((_BYTE *)v23 + ++v24) == 0;
    while ( !v25 );
    v26 = v24 + 1;
    v27 = 1;
  }
  else
  {
    v27 = 1;
    v23 = &word_14002D1C8;
    v26 = 1;
  }
  v92 = v23;
  v90 = a20;
  v93 = v26;
  v94 = 0;
  v91 = 4;
  v28 = *a19;
  if ( *a19 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_BYTE *)v28 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &word_14002D1C8;
    v30 = 1;
  }
  v88 = v30;
  v87 = v28;
  v89 = 0;
  v31 = *a18;
  if ( *a18 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *((_BYTE *)v31 + v32) );
    v33 = v32 + 1;
  }
  else
  {
    v31 = &word_14002D1C8;
    v33 = 1;
  }
  v85 = v33;
  v84 = v31;
  v86 = 0;
  v34 = *a17;
  if ( *a17 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &word_14002D1C8;
    v36 = 1;
  }
  v82 = v36;
  v81 = v34;
  v83 = 0;
  v37 = *a16;
  if ( *a16 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_BYTE *)v37 + v38) );
    v39 = v38 + 1;
  }
  else
  {
    v37 = &word_14002D1C8;
    v39 = 1;
  }
  v79 = v39;
  v76 = a15;
  v78 = v37;
  v80 = 0;
  v77 = 2;
  v40 = *a14;
  if ( *a14 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_BYTE *)v40 + v41) );
    v42 = v41 + 1;
  }
  else
  {
    v40 = &word_14002D1C8;
    v42 = 1;
  }
  v74 = v42;
  v73 = v40;
  v75 = 0;
  v43 = *a13;
  if ( *a13 )
  {
    v44 = -1;
    do
      ++v44;
    while ( *((_BYTE *)v43 + v44) );
    v45 = v44 + 1;
  }
  else
  {
    v43 = &word_14002D1C8;
    v45 = 1;
  }
  v71 = v45;
  v70 = v43;
  v72 = 0;
  v46 = *a12;
  if ( *a12 )
  {
    v47 = -1;
    do
      ++v47;
    while ( *((_BYTE *)v46 + v47) );
    v48 = v47 + 1;
  }
  else
  {
    v46 = &word_14002D1C8;
    v48 = 1;
  }
  v68 = v48;
  v65 = a11;
  v67 = v46;
  v69 = 0;
  v66 = 2;
  v49 = *a10;
  if ( *a10 )
  {
    do
      v25 = *((_BYTE *)v49 + ++v22) == 0;
    while ( !v25 );
    v27 = v22 + 1;
  }
  else
  {
    v49 = &word_14002D1C8;
  }
  v60 = a9;
  v58 = a8;
  v56 = a7;
  v54 = a6;
  v52 = a5;
  v63 = v27;
  v62 = v49;
  v64 = 0;
  v61 = 4;
  v59 = 2;
  v57 = 4;
  v55 = 4;
  v53 = 4;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0x14u, &v51);
}

```

## disassembly

```asm
0x140001010  push    rbp
0x140001012  lea     rbp, [rsp-80h]
0x140001017  sub     rsp, 180h
0x14000101e  mov     rax, cs:__security_cookie
0x140001025  xor     rax, rsp
0x140001028  mov     [rbp+80h+var_10], rax
0x14000102c  mov     rax, [rbp+80h+arg_A8]
0x140001033  xor     r11d, r11d
0x140001036  mov     [rbp+80h+var_20], rax
0x14000103a  mov     r8, 0FFFFFFFFFFFFFFFFh
0x140001041  mov     rax, [rbp+80h+arg_A0]
0x140001048  mov     [rbp+80h+var_18], 4
0x140001050  mov     rax, [rax]
0x140001053  test    rax, rax
0x140001056  jz      short loc_140001072
0x140001058  mov     r9, r8
0x14000105b  cmp     [rax+r9+1], r11b
0x140001060  lea     r9, [r9+1]
0x140001064  jnz     short loc_14000105B
0x140001066  lea     r10d, [r9+1]
0x14000106a  mov     r9d, 1
0x140001070  jmp     short loc_140001082
0x140001072  mov     r9d, 1
0x140001078  lea     rax, word_14002D1C8
0x14000107f  mov     r10d, r9d
0x140001082  mov     [rbp+80h+var_30], rax
0x140001086  mov     rax, [rbp+80h+arg_98]
0x14000108d  mov     [rbp+80h+var_40], rax
0x140001091  mov     rax, [rbp+80h+arg_90]
0x140001098  mov     [rbp+80h+var_28], r10d
0x14000109c  mov     [rbp+80h+var_24], r11d
0x1400010a0  mov     [rbp+80h+var_38], 4
0x1400010a8  mov     r10, [rax]
0x1400010ab  test    r10, r10
0x1400010ae  jz      short loc_1400010C0
0x1400010b0  mov     rax, r8
0x1400010b3  inc     rax
0x1400010b6  cmp     [r10+rax], r11b
0x1400010ba  jnz     short loc_1400010B3
0x1400010bc  inc     eax
0x1400010be  jmp     short loc_1400010CA
0x1400010c0  lea     r10, word_14002D1C8
0x1400010c7  mov     eax, r9d
0x1400010ca  mov     [rbp+80h+var_48], eax
0x1400010cd  mov     rax, [rbp+80h+arg_88]
0x1400010d4  mov     [rbp+80h+var_50], r10
0x1400010d8  mov     [rbp+80h+var_44], r11d
0x1400010dc  mov     r10, [rax]
0x1400010df  test    r10, r10
0x1400010e2  jz      short loc_1400010F4
0x1400010e4  mov     rax, r8
0x1400010e7  inc     rax
0x1400010ea  cmp     [r10+rax], r11b
0x1400010ee  jnz     short loc_1400010E7
0x1400010f0  inc     eax
0x1400010f2  jmp     short loc_1400010FE
0x1400010f4  lea     r10, word_14002D1C8
0x1400010fb  mov     eax, r9d
0x1400010fe  mov     [rbp+80h+var_58], eax
0x140001101  mov     rax, [rbp+80h+arg_80]
0x140001108  mov     [rbp+80h+var_60], r10
0x14000110c  mov     [rbp+80h+var_54], r11d
0x140001110  mov     r10, [rax]
0x140001113  test    r10, r10
0x140001116  jz      short loc_140001128
0x140001118  mov     rax, r8
0x14000111b  inc     rax
0x14000111e  cmp     [r10+rax], r11b
0x140001122  jnz     short loc_14000111B
0x140001124  inc     eax
0x140001126  jmp     short loc_140001132
0x140001128  lea     r10, word_14002D1C8
0x14000112f  mov     eax, r9d
0x140001132  mov     [rbp+80h+var_68], eax
0x140001135  mov     rax, [rbp+80h+arg_78]
0x14000113c  mov     [rbp+80h+var_70], r10
0x140001140  mov     [rbp+80h+var_64], r11d
0x140001144  mov     r10, [rax]
0x140001147  test    r10, r10
0x14000114a  jz      short loc_14000115C
0x14000114c  mov     rax, r8
0x14000114f  inc     rax
0x140001152  cmp     [r10+rax], r11b
0x140001156  jnz     short loc_14000114F
0x140001158  inc     eax
0x14000115a  jmp     short loc_140001166
0x14000115c  lea     r10, word_14002D1C8
0x140001163  mov     eax, r9d
0x140001166  mov     [rbp+80h+var_78], eax
0x140001169  mov     rax, [rbp+80h+arg_70]
0x140001170  mov     [rbp+80h+var_90], rax
0x140001174  mov     rax, [rbp+80h+arg_68]
0x14000117b  mov     [rbp+80h+var_80], r10
0x14000117f  mov     [rbp+80h+var_74], r11d
0x140001183  mov     [rbp+80h+var_88], 2
0x14000118b  mov     r10, [rax]
0x14000118e  test    r10, r10
0x140001191  jz      short loc_1400011A3
0x140001193  mov     rax, r8
0x140001196  inc     rax
0x140001199  cmp     [r10+rax], r11b
0x14000119d  jnz     short loc_140001196
0x14000119f  inc     eax
0x1400011a1  jmp     short loc_1400011AD
0x1400011a3  lea     r10, word_14002D1C8
0x1400011aa  mov     eax, r9d
0x1400011ad  mov     [rbp+80h+var_98], eax
0x1400011b0  mov     rax, [rbp+80h+arg_60]
0x1400011b7  mov     [rbp+80h+var_A0], r10
0x1400011bb  mov     [rbp+80h+var_94], r11d
0x1400011bf  mov     r10, [rax]
0x1400011c2  test    r10, r10
0x1400011c5  jz      short loc_1400011D7
0x1400011c7  mov     rax, r8
0x1400011ca  inc     rax
0x1400011cd  cmp     [r10+rax], r11b
0x1400011d1  jnz     short loc_1400011CA
0x1400011d3  inc     eax
0x1400011d5  jmp     short loc_1400011E1
0x1400011d7  lea     r10, word_14002D1C8
0x1400011de  mov     eax, r9d
0x1400011e1  mov     [rbp+80h+var_A8], eax
0x1400011e4  mov     rax, [rbp+80h+arg_58]
0x1400011eb  mov     [rbp+80h+var_B0], r10
0x1400011ef  mov     [rbp+80h+var_A4], r11d
0x1400011f3  mov     r10, [rax]
0x1400011f6  test    r10, r10
0x1400011f9  jz      short loc_14000120B
0x1400011fb  mov     rax, r8
0x1400011fe  inc     rax
0x140001201  cmp     [r10+rax], r11b
0x140001205  jnz     short loc_1400011FE
0x140001207  inc     eax
0x140001209  jmp     short loc_140001215
0x14000120b  lea     r10, word_14002D1C8
0x140001212  mov     eax, r9d
0x140001215  mov     [rbp+80h+var_B8], eax
0x140001218  mov     rax, [rbp+80h+arg_50]
0x14000121f  mov     [rbp+80h+var_D0], rax
0x140001223  mov     rax, [rbp+80h+arg_48]
0x14000122a  mov     [rbp+80h+var_C0], r10
0x14000122e  mov     [rbp+80h+var_B4], r11d
0x140001232  mov     [rbp+80h+var_C8], 2
0x14000123a  mov     r10, [rax]
0x14000123d  test    r10, r10
0x140001240  jz      short loc_140001253
0x140001242  cmp     [r10+r8+1], r11b
0x140001247  lea     r8, [r8+1]
0x14000124b  jnz     short loc_140001242
0x14000124d  lea     r9d, [r8+1]
0x140001251  jmp     short loc_14000125A
0x140001253  lea     r10, word_14002D1C8
0x14000125a  mov     rax, [rbp+80h+arg_40]
0x140001261  xor     r8d, r8d; int
0x140001264  mov     [rbp+80h+var_F0], rax
0x140001268  mov     rax, [rbp+80h+arg_38]
0x14000126f  mov     [rbp+80h+var_100], rax
0x140001273  mov     rax, [rbp+80h+arg_30]
0x14000127a  mov     [rsp+180h+var_110], rax
0x14000127f  mov     rax, [rbp+80h+arg_28]
0x140001286  mov     [rsp+180h+var_120], rax
0x14000128b  mov     rax, [rbp+80h+arg_20]
0x140001292  mov     [rsp+180h+var_130], rax
0x140001297  lea     rax, [rsp+180h+var_150]
0x14000129c  mov     [rbp+80h+var_D8], r9d
0x1400012a0  xor     r9d, r9d; int
0x1400012a3  mov     [rsp+180h+var_158], rax; PEVENT_DATA_DESCRIPTOR
0x1400012a8  mov     [rsp+180h+var_160], 14h; ULONG
0x1400012b0  mov     [rbp+80h+var_E0], r10
0x1400012b4  mov     [rbp+80h+var_D4], r11d
0x1400012b8  mov     [rbp+80h+var_E8], 4
0x1400012c0  mov     [rbp+80h+var_F8], 2
0x1400012c8  mov     [rsp+180h+var_108], 4
0x1400012d1  mov     [rsp+180h+var_118], 4
0x1400012da  mov     [rsp+180h+var_128], 4
0x1400012e3  call    _tlgWriteTransfer_EventWriteTransfer
0x1400012e8  mov     rcx, [rbp+80h+var_10]
0x1400012ec  xor     rcx, rsp; StackCookie
0x1400012ef  call    __security_check_cookie
0x1400012f4  add     rsp, 180h
0x1400012fb  pop     rbp
0x1400012fc  retn
```
