# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x140001010`
- end: `0x140001326`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `790`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const WCHAR **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const WCHAR **, __int64, const unsigned __int16 **, const WCHAR **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140016c90`
- `0x140016ed0`
- `0x140017110`

## callees

- `0x140001010`
- `0x140001f48`
- `0x140002930`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const unsigned __int16 **a8,
        __int64 a9,
        const unsigned __int16 **a10,
        __int64 a11,
        const WCHAR **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        const WCHAR **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        const WCHAR **a20,
        __int64 a21,
        __int64 a22,
        const unsigned __int16 **a23)
{
  __int64 v23; // r9
  const unsigned __int16 *v24; // rax
  __int64 v25; // r10
  int v26; // r10d
  int v27; // r11d
  int v28; // ebx
  const WCHAR *v29; // r10
  __int64 v30; // rax
  bool v31; // zf
  int v32; // eax
  const unsigned __int16 *v33; // r10
  __int64 v34; // rax
  int v35; // eax
  const WCHAR *v36; // r10
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // r10
  __int64 v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // r10
  __int64 v43; // rax
  int v44; // eax
  const WCHAR *v45; // r10
  __int64 v46; // rax
  const unsigned __int16 *v47; // r10
  __int64 v48; // rax
  int v49; // eax
  const unsigned __int16 *v50; // r10
  _BYTE v52[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B0h]
  __int64 v54; // [rsp+58h] [rbp-A8h]
  __int64 v55; // [rsp+60h] [rbp-A0h]
  __int64 v56; // [rsp+68h] [rbp-98h]
  __int64 v57; // [rsp+70h] [rbp-90h]
  __int64 v58; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v59; // [rsp+80h] [rbp-80h]
  int v60; // [rsp+88h] [rbp-78h]
  int v61; // [rsp+8Ch] [rbp-74h]
  __int64 v62; // [rsp+90h] [rbp-70h]
  __int64 v63; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v64; // [rsp+A0h] [rbp-60h]
  int v65; // [rsp+A8h] [rbp-58h]
  int v66; // [rsp+ACh] [rbp-54h]
  __int64 v67; // [rsp+B0h] [rbp-50h]
  __int64 v68; // [rsp+B8h] [rbp-48h]
  const WCHAR *v69; // [rsp+C0h] [rbp-40h]
  int v70; // [rsp+C8h] [rbp-38h]
  int v71; // [rsp+CCh] [rbp-34h]
  __int64 v72; // [rsp+D0h] [rbp-30h]
  __int64 v73; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v74; // [rsp+E0h] [rbp-20h]
  int v75; // [rsp+E8h] [rbp-18h]
  int v76; // [rsp+ECh] [rbp-14h]
  __int64 v77; // [rsp+F0h] [rbp-10h]
  __int64 v78; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v79; // [rsp+100h] [rbp+0h]
  int v80; // [rsp+108h] [rbp+8h]
  int v81; // [rsp+10Ch] [rbp+Ch]
  const WCHAR *v82; // [rsp+110h] [rbp+10h]
  int v83; // [rsp+118h] [rbp+18h]
  int v84; // [rsp+11Ch] [rbp+1Ch]
  __int64 v85; // [rsp+120h] [rbp+20h]
  __int64 v86; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v87; // [rsp+130h] [rbp+30h]
  int v88; // [rsp+138h] [rbp+38h]
  int v89; // [rsp+13Ch] [rbp+3Ch]
  const WCHAR *v90; // [rsp+140h] [rbp+40h]
  int v91; // [rsp+148h] [rbp+48h]
  int v92; // [rsp+14Ch] [rbp+4Ch]
  __int64 v93; // [rsp+150h] [rbp+50h]
  __int64 v94; // [rsp+158h] [rbp+58h]
  __int64 v95; // [rsp+160h] [rbp+60h]
  __int64 v96; // [rsp+168h] [rbp+68h]
  const unsigned __int16 *v97; // [rsp+170h] [rbp+70h]
  int v98; // [rsp+178h] [rbp+78h]
  int v99; // [rsp+17Ch] [rbp+7Ch]

  v23 = -1;
  v24 = *a23;
  if ( *a23 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *((_BYTE *)v24 + v25) );
    v26 = v25 + 1;
    v27 = 1;
  }
  else
  {
    v27 = 1;
    v24 = &byte_14001ACA1;
    v26 = 1;
  }
  v97 = v24;
  v28 = 2;
  v95 = a22;
  v93 = a21;
  v98 = v26;
  v99 = 0;
  v96 = 4;
  v29 = *a20;
  v94 = 4;
  if ( v29 )
  {
    v30 = -1;
    do
      v31 = v29[++v30] == 0;
    while ( !v31 );
    v32 = 2 * v30 + 2;
  }
  else
  {
    v29 = &sourceString;
    v32 = 2;
  }
  v91 = v32;
  v90 = v29;
  v92 = 0;
  v33 = *a19;
  if ( *a19 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_BYTE *)v33 + v34) );
    v35 = v34 + 1;
  }
  else
  {
    v33 = &byte_14001ACA1;
    v35 = 1;
  }
  v88 = v35;
  v85 = a18;
  v87 = v33;
  v89 = 0;
  v86 = 4;
  v36 = *a17;
  if ( *a17 )
  {
    v37 = -1;
    do
      v31 = v36[++v37] == 0;
    while ( !v31 );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v36 = &sourceString;
    v38 = 2;
  }
  v83 = v38;
  v82 = v36;
  v84 = 0;
  v39 = *a16;
  if ( *a16 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_BYTE *)v39 + v40) );
    v41 = v40 + 1;
  }
  else
  {
    v39 = &byte_14001ACA1;
    v41 = 1;
  }
  v80 = v41;
  v77 = a15;
  v79 = v39;
  v81 = 0;
  v78 = 4;
  v42 = *a14;
  if ( *a14 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &byte_14001ACA1;
    v44 = 1;
  }
  v75 = v44;
  v72 = a13;
  v74 = v42;
  v76 = 0;
  v73 = 4;
  v45 = *a12;
  if ( *a12 )
  {
    v46 = -1;
    do
      v31 = v45[++v46] == 0;
    while ( !v31 );
    v28 = 2 * v46 + 2;
  }
  else
  {
    v45 = &sourceString;
  }
  v67 = a11;
  v69 = v45;
  v70 = v28;
  v71 = 0;
  v47 = *a10;
  v68 = 4;
  if ( v47 )
  {
    v48 = -1;
    do
      ++v48;
    while ( *((_BYTE *)v47 + v48) );
    v49 = v48 + 1;
  }
  else
  {
    v47 = &byte_14001ACA1;
    v49 = 1;
  }
  v65 = v49;
  v62 = a9;
  v64 = v47;
  v66 = 0;
  v63 = 4;
  v50 = *a8;
  if ( *a8 )
  {
    do
      v31 = *((_BYTE *)v50 + ++v23) == 0;
    while ( !v31 );
    v27 = v23 + 1;
  }
  else
  {
    v50 = &byte_14001ACA1;
  }
  v57 = a7;
  v55 = a6;
  v53 = a5;
  v59 = v50;
  v60 = v27;
  v61 = 0;
  v58 = 4;
  v56 = 8;
  v54 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 21, v52);
}

```

## disassembly

```asm
0x140001010  push    rbp
0x140001012  push    rbx
0x140001013  push    rdi
0x140001014  lea     rbp, [rsp-90h]
0x14000101c  sub     rsp, 190h
0x140001023  mov     rax, cs:__security_cookie
0x14000102a  xor     rax, rsp
0x14000102d  mov     [rbp+0A0h+var_20], rax
0x140001034  mov     rax, [rbp+0A0h+arg_B0]
0x14000103b  mov     r9, 0FFFFFFFFFFFFFFFFh
0x140001042  mov     rax, [rax]
0x140001045  test    rax, rax
0x140001048  jz      short loc_140001062
0x14000104a  mov     r10, r9
0x14000104d  inc     r10
0x140001050  cmp     byte ptr [rax+r10], 0
0x140001055  jnz     short loc_14000104D
0x140001057  inc     r10d
0x14000105a  mov     r11d, 1
0x140001060  jmp     short loc_140001072
0x140001062  mov     r11d, 1
0x140001068  lea     rax, byte_14001ACA1
0x14000106f  mov     r10d, r11d
0x140001072  mov     [rbp+0A0h+var_30], rax
0x140001076  xor     edi, edi
0x140001078  mov     rax, [rbp+0A0h+arg_A8]
0x14000107f  mov     ebx, 2
0x140001084  mov     [rbp+0A0h+var_40], rax
0x140001088  mov     rax, [rbp+0A0h+arg_A0]
0x14000108f  mov     [rbp+0A0h+var_50], rax
0x140001093  mov     rax, [rbp+0A0h+arg_98]
0x14000109a  mov     [rbp+0A0h+var_28], r10d
0x14000109e  mov     [rbp+0A0h+var_24], edi
0x1400010a1  mov     [rbp+0A0h+var_38], 4
0x1400010a9  mov     r10, [rax]
0x1400010ac  mov     [rbp+0A0h+var_48], 4
0x1400010b4  test    r10, r10
0x1400010b7  jz      short loc_1400010D1
0x1400010b9  mov     rax, r9
0x1400010bc  cmp     [r10+rax*2+2], di
0x1400010c2  lea     rax, [rax+1]
0x1400010c6  jnz     short loc_1400010BC
0x1400010c8  lea     eax, ds:2[rax*2]
0x1400010cf  jmp     short loc_1400010DA
0x1400010d1  lea     r10, sourceString
0x1400010d8  mov     eax, ebx
0x1400010da  mov     [rbp+0A0h+var_58], eax
0x1400010dd  mov     rax, [rbp+0A0h+arg_90]
0x1400010e4  mov     [rbp+0A0h+var_60], r10
0x1400010e8  mov     [rbp+0A0h+var_54], edi
0x1400010eb  mov     r10, [rax]
0x1400010ee  test    r10, r10
0x1400010f1  jz      short loc_140001103
0x1400010f3  mov     rax, r9
0x1400010f6  inc     rax
0x1400010f9  cmp     [r10+rax], dil
0x1400010fd  jnz     short loc_1400010F6
0x1400010ff  inc     eax
0x140001101  jmp     short loc_14000110D
0x140001103  lea     r10, byte_14001ACA1
0x14000110a  mov     eax, r11d
0x14000110d  mov     [rbp+0A0h+var_68], eax
0x140001110  mov     rax, [rbp+0A0h+arg_88]
0x140001117  mov     [rbp+0A0h+var_80], rax
0x14000111b  mov     rax, [rbp+0A0h+arg_80]
0x140001122  mov     [rbp+0A0h+var_70], r10
0x140001126  mov     [rbp+0A0h+var_64], edi
0x140001129  mov     [rbp+0A0h+var_78], 4
0x140001131  mov     r10, [rax]
0x140001134  test    r10, r10
0x140001137  jz      short loc_140001151
0x140001139  mov     rax, r9
0x14000113c  cmp     [r10+rax*2+2], di
0x140001142  lea     rax, [rax+1]
0x140001146  jnz     short loc_14000113C
0x140001148  lea     eax, ds:2[rax*2]
0x14000114f  jmp     short loc_14000115A
0x140001151  lea     r10, sourceString
0x140001158  mov     eax, ebx
0x14000115a  mov     [rbp+0A0h+var_88], eax
0x14000115d  mov     rax, [rbp+0A0h+arg_78]
0x140001164  mov     [rbp+0A0h+var_90], r10
0x140001168  mov     [rbp+0A0h+var_84], edi
0x14000116b  mov     r10, [rax]
0x14000116e  test    r10, r10
0x140001171  jz      short loc_140001183
0x140001173  mov     rax, r9
0x140001176  inc     rax
0x140001179  cmp     [r10+rax], dil
0x14000117d  jnz     short loc_140001176
0x14000117f  inc     eax
0x140001181  jmp     short loc_14000118D
0x140001183  lea     r10, byte_14001ACA1
0x14000118a  mov     eax, r11d
0x14000118d  mov     [rbp+0A0h+var_98], eax
0x140001190  mov     rax, [rbp+0A0h+arg_70]
0x140001197  mov     [rbp+0A0h+var_B0], rax
0x14000119b  mov     rax, [rbp+0A0h+arg_68]
0x1400011a2  mov     [rbp+0A0h+var_A0], r10
0x1400011a6  mov     [rbp+0A0h+var_94], edi
0x1400011a9  mov     [rbp+0A0h+var_A8], 4
0x1400011b1  mov     r10, [rax]
0x1400011b4  test    r10, r10
0x1400011b7  jz      short loc_1400011C9
0x1400011b9  mov     rax, r9
0x1400011bc  inc     rax
0x1400011bf  cmp     [r10+rax], dil
0x1400011c3  jnz     short loc_1400011BC
0x1400011c5  inc     eax
0x1400011c7  jmp     short loc_1400011D3
0x1400011c9  lea     r10, byte_14001ACA1
0x1400011d0  mov     eax, r11d
0x1400011d3  mov     [rbp+0A0h+var_B8], eax
0x1400011d6  mov     rax, [rbp+0A0h+arg_60]
0x1400011dd  mov     [rbp+0A0h+var_D0], rax
0x1400011e1  mov     rax, [rbp+0A0h+arg_58]
0x1400011e8  mov     [rbp+0A0h+var_C0], r10
0x1400011ec  mov     [rbp+0A0h+var_B4], edi
0x1400011ef  mov     [rbp+0A0h+var_C8], 4
0x1400011f7  mov     r10, [rax]
0x1400011fa  test    r10, r10
0x1400011fd  jz      short loc_140001217
0x1400011ff  mov     rax, r9
0x140001202  cmp     [r10+rax*2+2], di
0x140001208  lea     rax, [rax+1]
0x14000120c  jnz     short loc_140001202
0x14000120e  lea     ebx, ds:2[rax*2]
0x140001215  jmp     short loc_14000121E
0x140001217  lea     r10, sourceString
0x14000121e  mov     rax, [rbp+0A0h+arg_50]
0x140001225  mov     [rbp+0A0h+var_F0], rax
0x140001229  mov     rax, [rbp+0A0h+arg_48]
0x140001230  mov     [rbp+0A0h+var_E0], r10
0x140001234  mov     [rbp+0A0h+var_D8], ebx
0x140001237  mov     [rbp+0A0h+var_D4], edi
0x14000123a  mov     r10, [rax]
0x14000123d  mov     [rbp+0A0h+var_E8], 4
0x140001245  test    r10, r10
0x140001248  jz      short loc_14000125A
0x14000124a  mov     rax, r9
0x14000124d  inc     rax
0x140001250  cmp     [r10+rax], dil
0x140001254  jnz     short loc_14000124D
0x140001256  inc     eax
0x140001258  jmp     short loc_140001264
0x14000125a  lea     r10, byte_14001ACA1
0x140001261  mov     eax, r11d
0x140001264  mov     [rbp+0A0h+var_F8], eax
0x140001267  mov     rax, [rbp+0A0h+arg_40]
0x14000126e  mov     [rbp+0A0h+var_110], rax
0x140001272  mov     rax, [rbp+0A0h+arg_38]
0x140001279  mov     [rbp+0A0h+var_100], r10
0x14000127d  mov     [rbp+0A0h+var_F4], edi
0x140001280  mov     [rbp+0A0h+var_108], 4
0x140001288  mov     r10, [rax]
0x14000128b  test    r10, r10
0x14000128e  jz      short loc_1400012A1
0x140001290  cmp     [r10+r9+1], dil
0x140001295  lea     r9, [r9+1]
0x140001299  jnz     short loc_140001290
0x14000129b  lea     r11d, [r9+1]
0x14000129f  jmp     short loc_1400012A8
0x1400012a1  lea     r10, byte_14001ACA1
0x1400012a8  mov     rax, [rbp+0A0h+arg_30]
0x1400012af  xor     r9d, r9d
0x1400012b2  mov     [rsp+1A0h+var_130], rax
0x1400012b7  mov     rax, [rbp+0A0h+arg_28]
0x1400012be  mov     [rsp+1A0h+var_140], rax
0x1400012c3  mov     rax, [rbp+0A0h+arg_20]
0x1400012ca  mov     [rsp+1A0h+var_150], rax
0x1400012cf  lea     rax, [rsp+1A0h+var_170]
0x1400012d4  mov     [rsp+1A0h+var_178], rax
0x1400012d9  mov     [rsp+1A0h+var_180], 15h
0x1400012e1  mov     [rbp+0A0h+var_120], r10
0x1400012e5  mov     [rbp+0A0h+var_118], r11d
0x1400012e9  mov     [rbp+0A0h+var_114], edi
0x1400012ec  mov     [rsp+1A0h+var_128], 4
0x1400012f5  mov     [rsp+1A0h+var_138], 8
0x1400012fe  mov     [rsp+1A0h+var_148], 8
0x140001307  call    _tlgWriteTransfer_EventWriteTransfer
0x14000130c  mov     rcx, [rbp+0A0h+var_20]
0x140001313  xor     rcx, rsp; StackCookie
0x140001316  call    __security_check_cookie
0x14000131b  add     rsp, 190h
0x140001322  pop     rdi
0x140001323  pop     rbx
0x140001324  pop     rbp
0x140001325  retn
```
