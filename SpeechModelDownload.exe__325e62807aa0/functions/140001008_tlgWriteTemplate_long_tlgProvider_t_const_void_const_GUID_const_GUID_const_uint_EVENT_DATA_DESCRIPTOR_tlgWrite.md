# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001008`
- end: `0x1400012b5`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `685`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const size_t **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const size_t **, __int64, const unsigned __int16 **, const size_t **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140007ad4`
- `0x140019680`

## callees

- `0x140001008`
- `0x14000176c`
- `0x140002600`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
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
        const size_t **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        const size_t **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        const size_t **a20)
{
  __int64 v22; // rdx
  int v24; // r9d
  const size_t *v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  int v28; // r8d
  const unsigned __int16 *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  const size_t *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  const unsigned __int16 *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  const unsigned __int16 *v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  const size_t *v41; // rcx
  __int64 v42; // rax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  const unsigned __int16 *v46; // rcx
  _BYTE v48[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v49; // [rsp+50h] [rbp-B0h]
  __int64 v50; // [rsp+58h] [rbp-A8h]
  __int64 v51; // [rsp+60h] [rbp-A0h]
  __int64 v52; // [rsp+68h] [rbp-98h]
  __int64 v53; // [rsp+70h] [rbp-90h]
  __int64 v54; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v55; // [rsp+80h] [rbp-80h]
  int v56; // [rsp+88h] [rbp-78h]
  int v57; // [rsp+8Ch] [rbp-74h]
  __int64 v58; // [rsp+90h] [rbp-70h]
  __int64 v59; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v60; // [rsp+A0h] [rbp-60h]
  int v61; // [rsp+A8h] [rbp-58h]
  int v62; // [rsp+ACh] [rbp-54h]
  __int64 v63; // [rsp+B0h] [rbp-50h]
  __int64 v64; // [rsp+B8h] [rbp-48h]
  const size_t *v65; // [rsp+C0h] [rbp-40h]
  int v66; // [rsp+C8h] [rbp-38h]
  int v67; // [rsp+CCh] [rbp-34h]
  __int64 v68; // [rsp+D0h] [rbp-30h]
  __int64 v69; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v70; // [rsp+E0h] [rbp-20h]
  int v71; // [rsp+E8h] [rbp-18h]
  int v72; // [rsp+ECh] [rbp-14h]
  __int64 v73; // [rsp+F0h] [rbp-10h]
  __int64 v74; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  const size_t *v78; // [rsp+110h] [rbp+10h]
  int v79; // [rsp+118h] [rbp+18h]
  int v80; // [rsp+11Ch] [rbp+1Ch]
  __int64 v81; // [rsp+120h] [rbp+20h]
  __int64 v82; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v83; // [rsp+130h] [rbp+30h]
  int v84; // [rsp+138h] [rbp+38h]
  int v85; // [rsp+13Ch] [rbp+3Ch]
  const size_t *v86; // [rsp+140h] [rbp+40h]
  int v87; // [rsp+148h] [rbp+48h]
  int v88; // [rsp+14Ch] [rbp+4Ch]

  v22 = -1;
  v24 = 2;
  v25 = *a20;
  if ( *a20 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *((_WORD *)v25 + v26) );
    v27 = 2 * v26 + 2;
  }
  else
  {
    v25 = &byte_14001EFBC;
    v27 = 2;
  }
  v87 = v27;
  v28 = 1;
  v86 = v25;
  v88 = 0;
  v29 = *a19;
  if ( *a19 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *((_BYTE *)v29 + v30) );
    v31 = v30 + 1;
  }
  else
  {
    v29 = &word_14001EFBE;
    v31 = 1;
  }
  v84 = v31;
  v81 = a18;
  v83 = v29;
  v85 = 0;
  v82 = 4;
  v32 = *a17;
  if ( *a17 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *((_WORD *)v32 + v33) );
    v34 = 2 * v33 + 2;
  }
  else
  {
    v32 = &byte_14001EFBC;
    v34 = 2;
  }
  v79 = v34;
  v78 = v32;
  v80 = 0;
  v35 = *a16;
  if ( *a16 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_BYTE *)v35 + v36) );
    v37 = v36 + 1;
  }
  else
  {
    v35 = &word_14001EFBE;
    v37 = 1;
  }
  v76 = v37;
  v73 = a15;
  v75 = v35;
  v77 = 0;
  v74 = 4;
  v38 = *a14;
  if ( *a14 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *((_BYTE *)v38 + v39) );
    v40 = v39 + 1;
  }
  else
  {
    v38 = &word_14001EFBE;
    v40 = 1;
  }
  v71 = v40;
  v68 = a13;
  v70 = v38;
  v72 = 0;
  v69 = 4;
  v41 = *a12;
  if ( *a12 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *((_WORD *)v41 + v42) );
    v24 = 2 * v42 + 2;
  }
  else
  {
    v41 = &byte_14001EFBC;
  }
  v63 = a11;
  v65 = v41;
  v66 = v24;
  v67 = 0;
  v43 = *a10;
  v64 = 4;
  if ( v43 )
  {
    v44 = -1;
    do
      ++v44;
    while ( *((_BYTE *)v43 + v44) );
    v45 = v44 + 1;
  }
  else
  {
    v43 = &word_14001EFBE;
    v45 = 1;
  }
  v61 = v45;
  v58 = a9;
  v60 = v43;
  v62 = 0;
  v59 = 4;
  v46 = *a8;
  if ( *a8 )
  {
    do
      ++v22;
    while ( *((_BYTE *)v46 + v22) );
    v28 = v22 + 1;
  }
  else
  {
    v46 = &word_14001EFBE;
  }
  v53 = a7;
  v51 = a6;
  v49 = a5;
  v55 = v46;
  v56 = v28;
  v57 = 0;
  v54 = 4;
  v52 = 8;
  v50 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 18, v48);
}

```

## disassembly

```asm
0x140001008  push    rbp
0x14000100a  push    rbx
0x14000100b  push    rsi
0x14000100c  push    rdi
0x14000100d  push    r14
0x14000100f  lea     rbp, [rsp-60h]
0x140001014  sub     rsp, 160h
0x14000101b  mov     rax, cs:__security_cookie
0x140001022  xor     rax, rsp
0x140001025  mov     [rbp+80h+var_30], rax
0x140001029  mov     rax, [rbp+80h+arg_98]
0x140001030  mov     r11, rdx
0x140001033  mov     r10, rcx
0x140001036  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000103a  xor     edi, edi
0x14000103c  mov     rbx, r8
0x14000103f  mov     r9d, 2
0x140001045  mov     rcx, [rax]
0x140001048  test    rcx, rcx
0x14000104b  jz      short loc_140001062
0x14000104d  mov     rax, rdx
0x140001050  inc     rax
0x140001053  cmp     [rcx+rax*2], di
0x140001057  jnz     short loc_140001050
0x140001059  lea     eax, ds:2[rax*2]
0x140001060  jmp     short loc_14000106C
0x140001062  lea     rcx, byte_14001EFBC
0x140001069  mov     eax, r9d
0x14000106c  mov     [rbp+80h+var_38], eax
0x14000106f  lea     rsi, word_14001EFBE
0x140001076  mov     rax, [rbp+80h+arg_90]
0x14000107d  mov     r8d, 1
0x140001083  mov     [rbp+80h+var_40], rcx
0x140001087  mov     [rbp+80h+var_34], edi
0x14000108a  mov     rcx, [rax]
0x14000108d  test    rcx, rcx
0x140001090  jz      short loc_1400010A2
0x140001092  mov     rax, rdx
0x140001095  inc     rax
0x140001098  cmp     [rcx+rax], dil
0x14000109c  jnz     short loc_140001095
0x14000109e  inc     eax
0x1400010a0  jmp     short loc_1400010A8
0x1400010a2  mov     rcx, rsi
0x1400010a5  mov     eax, r8d
0x1400010a8  mov     [rbp+80h+var_48], eax
0x1400010ab  mov     rax, [rbp+80h+arg_88]
0x1400010b2  mov     [rbp+80h+var_60], rax
0x1400010b6  mov     rax, [rbp+80h+arg_80]
0x1400010bd  mov     [rbp+80h+var_50], rcx
0x1400010c1  mov     [rbp+80h+var_44], edi
0x1400010c4  mov     [rbp+80h+var_58], 4
0x1400010cc  mov     rcx, [rax]
0x1400010cf  test    rcx, rcx
0x1400010d2  jz      short loc_1400010E9
0x1400010d4  mov     rax, rdx
0x1400010d7  inc     rax
0x1400010da  cmp     [rcx+rax*2], di
0x1400010de  jnz     short loc_1400010D7
0x1400010e0  lea     eax, ds:2[rax*2]
0x1400010e7  jmp     short loc_1400010F3
0x1400010e9  lea     rcx, byte_14001EFBC
0x1400010f0  mov     eax, r9d
0x1400010f3  mov     [rbp+80h+var_68], eax
0x1400010f6  mov     rax, [rbp+80h+arg_78]
0x1400010fd  mov     [rbp+80h+var_70], rcx
0x140001101  mov     [rbp+80h+var_64], edi
0x140001104  mov     rcx, [rax]
0x140001107  test    rcx, rcx
0x14000110a  jz      short loc_14000111C
0x14000110c  mov     rax, rdx
0x14000110f  inc     rax
0x140001112  cmp     [rcx+rax], dil
0x140001116  jnz     short loc_14000110F
0x140001118  inc     eax
0x14000111a  jmp     short loc_140001122
0x14000111c  mov     rcx, rsi
0x14000111f  mov     eax, r8d
0x140001122  mov     [rbp+80h+var_78], eax
0x140001125  mov     rax, [rbp+80h+arg_70]
0x14000112c  mov     [rbp+80h+var_90], rax
0x140001130  mov     rax, [rbp+80h+arg_68]
0x140001137  mov     [rbp+80h+var_80], rcx
0x14000113b  mov     [rbp+80h+var_74], edi
0x14000113e  mov     [rbp+80h+var_88], 4
0x140001146  mov     rcx, [rax]
0x140001149  test    rcx, rcx
0x14000114c  jz      short loc_14000115E
0x14000114e  mov     rax, rdx
0x140001151  inc     rax
0x140001154  cmp     [rcx+rax], dil
0x140001158  jnz     short loc_140001151
0x14000115a  inc     eax
0x14000115c  jmp     short loc_140001164
0x14000115e  mov     rcx, rsi
0x140001161  mov     eax, r8d
0x140001164  mov     [rbp+80h+var_98], eax
0x140001167  mov     rax, [rbp+80h+arg_60]
0x14000116e  mov     [rbp+80h+var_B0], rax
0x140001172  mov     rax, [rbp+80h+arg_58]
0x140001179  mov     [rbp+80h+var_A0], rcx
0x14000117d  mov     [rbp+80h+var_94], edi
0x140001180  mov     [rbp+80h+var_A8], 4
0x140001188  mov     rcx, [rax]
0x14000118b  test    rcx, rcx
0x14000118e  jz      short loc_1400011A6
0x140001190  mov     rax, rdx
0x140001193  inc     rax
0x140001196  cmp     [rcx+rax*2], di
0x14000119a  jnz     short loc_140001193
0x14000119c  lea     r9d, ds:2[rax*2]
0x1400011a4  jmp     short loc_1400011AD
0x1400011a6  lea     rcx, byte_14001EFBC
0x1400011ad  mov     rax, [rbp+80h+arg_50]
0x1400011b4  mov     [rbp+80h+var_D0], rax
0x1400011b8  mov     rax, [rbp+80h+arg_48]
0x1400011bf  mov     [rbp+80h+var_C0], rcx
0x1400011c3  mov     [rbp+80h+var_B8], r9d
0x1400011c7  mov     [rbp+80h+var_B4], edi
0x1400011ca  mov     rcx, [rax]
0x1400011cd  mov     [rbp+80h+var_C8], 4
0x1400011d5  test    rcx, rcx
0x1400011d8  jz      short loc_1400011EA
0x1400011da  mov     rax, rdx
0x1400011dd  inc     rax
0x1400011e0  cmp     [rcx+rax], dil
0x1400011e4  jnz     short loc_1400011DD
0x1400011e6  inc     eax
0x1400011e8  jmp     short loc_1400011F0
0x1400011ea  mov     rcx, rsi
0x1400011ed  mov     eax, r8d
0x1400011f0  mov     [rbp+80h+var_D8], eax
0x1400011f3  mov     rax, [rbp+80h+arg_40]
0x1400011fa  mov     [rbp+80h+var_F0], rax
0x1400011fe  mov     rax, [rbp+80h+arg_38]
0x140001205  mov     [rbp+80h+var_E0], rcx
0x140001209  mov     [rbp+80h+var_D4], edi
0x14000120c  mov     [rbp+80h+var_E8], 4
0x140001214  mov     rcx, [rax]
0x140001217  test    rcx, rcx
0x14000121a  jz      short loc_14000122B
0x14000121c  inc     rdx
0x14000121f  cmp     [rcx+rdx], dil
0x140001223  jnz     short loc_14000121C
0x140001225  lea     r8d, [rdx+1]
0x140001229  jmp     short loc_14000122E
0x14000122b  mov     rcx, rsi
0x14000122e  mov     rax, [rbp+80h+arg_30]
0x140001235  xor     r9d, r9d
0x140001238  mov     [rsp+180h+var_110], rax
0x14000123d  mov     rdx, r11
0x140001240  mov     rax, [rbp+80h+arg_28]
0x140001247  mov     [rsp+180h+var_120], rax
0x14000124c  mov     rax, [rbp+80h+arg_20]
0x140001253  mov     [rsp+180h+var_130], rax
0x140001258  lea     rax, [rsp+180h+var_150]
0x14000125d  mov     [rbp+80h+var_100], rcx
0x140001261  mov     rcx, r10
0x140001264  mov     [rbp+80h+var_F8], r8d
0x140001268  mov     r8, rbx
0x14000126b  mov     [rsp+180h+var_158], rax
0x140001270  mov     [rsp+180h+var_160], 12h
0x140001278  mov     [rbp+80h+var_F4], edi
0x14000127b  mov     [rsp+180h+var_108], 4
0x140001284  mov     [rsp+180h+var_118], 8
0x14000128d  mov     [rsp+180h+var_128], 8
0x140001296  call    _tlgWriteTransfer_EventWriteTransfer
0x14000129b  mov     rcx, [rbp+80h+var_30]
0x14000129f  xor     rcx, rsp; StackCookie
0x1400012a2  call    __security_check_cookie
0x1400012a7  add     rsp, 160h
0x1400012ae  pop     r14
0x1400012b0  pop     rdi
0x1400012b1  pop     rsi
0x1400012b2  pop     rbx
0x1400012b3  pop     rbp
0x1400012b4  retn
```
