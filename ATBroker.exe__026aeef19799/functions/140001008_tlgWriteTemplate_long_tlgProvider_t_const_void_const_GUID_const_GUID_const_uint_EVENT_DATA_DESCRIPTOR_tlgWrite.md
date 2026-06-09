# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001008`
- end: `0x1400012da`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$01@@U1@U?$_tlgWrapSz@D@@U2@U3@U3@U3@U2@U3@U3@U3@U3@U1@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$01@@3AEBU?$_tlgWrapSz@D@@455545555353@Z`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140004ee0`

## callees

- `0x140001008`
- `0x140001a8c`
- `0x140015b00`

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
        const unsigned __int16 **a10,
        __int64 a11,
        const unsigned __int16 **a12,
        const unsigned __int16 **a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        const unsigned __int16 **a17,
        const unsigned __int16 **a18,
        const unsigned __int16 **a19,
        __int64 a20,
        const unsigned __int16 **a21,
        __int64 a22)
{
  __int64 v23; // rcx
  int v25; // edx
  const unsigned __int16 *v26; // r8
  __int64 v27; // rax
  int v28; // eax
  const unsigned __int16 *v29; // r8
  __int64 v30; // rax
  int v31; // eax
  const unsigned __int16 *v32; // r8
  __int64 v33; // rax
  int v34; // eax
  const unsigned __int16 *v35; // r8
  __int64 v36; // rax
  int v37; // eax
  const unsigned __int16 *v38; // r8
  __int64 v39; // rax
  int v40; // eax
  const unsigned __int16 *v41; // r8
  __int64 v42; // rax
  int v43; // eax
  const unsigned __int16 *v44; // r8
  __int64 v45; // rax
  int v46; // eax
  const unsigned __int16 *v47; // r8
  __int64 v48; // rax
  int v49; // eax
  const unsigned __int16 *v50; // r8
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B0h]
  __int64 v54; // [rsp+58h] [rbp-A8h]
  __int64 v55; // [rsp+60h] [rbp-A0h]
  __int64 v56; // [rsp+68h] [rbp-98h]
  __int64 v57; // [rsp+70h] [rbp-90h]
  __int64 v58; // [rsp+78h] [rbp-88h]
  __int64 v59; // [rsp+80h] [rbp-80h]
  __int64 v60; // [rsp+88h] [rbp-78h]
  __int64 v61; // [rsp+90h] [rbp-70h]
  __int64 v62; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v63; // [rsp+A0h] [rbp-60h]
  int v64; // [rsp+A8h] [rbp-58h]
  int v65; // [rsp+ACh] [rbp-54h]
  __int64 v66; // [rsp+B0h] [rbp-50h]
  __int64 v67; // [rsp+B8h] [rbp-48h]
  const unsigned __int16 *v68; // [rsp+C0h] [rbp-40h]
  int v69; // [rsp+C8h] [rbp-38h]
  int v70; // [rsp+CCh] [rbp-34h]
  const unsigned __int16 *v71; // [rsp+D0h] [rbp-30h]
  int v72; // [rsp+D8h] [rbp-28h]
  int v73; // [rsp+DCh] [rbp-24h]
  const unsigned __int16 *v74; // [rsp+E0h] [rbp-20h]
  int v75; // [rsp+E8h] [rbp-18h]
  int v76; // [rsp+ECh] [rbp-14h]
  __int64 v77; // [rsp+F0h] [rbp-10h]
  __int64 v78; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v79; // [rsp+100h] [rbp+0h]
  int v80; // [rsp+108h] [rbp+8h]
  int v81; // [rsp+10Ch] [rbp+Ch]
  const unsigned __int16 *v82; // [rsp+110h] [rbp+10h]
  int v83; // [rsp+118h] [rbp+18h]
  int v84; // [rsp+11Ch] [rbp+1Ch]
  const unsigned __int16 *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  const unsigned __int16 *v88; // [rsp+130h] [rbp+30h]
  int v89; // [rsp+138h] [rbp+38h]
  int v90; // [rsp+13Ch] [rbp+3Ch]
  __int64 v91; // [rsp+140h] [rbp+40h]
  __int64 v92; // [rsp+148h] [rbp+48h]
  const unsigned __int16 *v93; // [rsp+150h] [rbp+50h]
  int v94; // [rsp+158h] [rbp+58h]
  int v95; // [rsp+15Ch] [rbp+5Ch]
  __int64 v96; // [rsp+160h] [rbp+60h]
  __int64 v97; // [rsp+168h] [rbp+68h]

  v96 = a22;
  v23 = -1;
  v97 = 4;
  v25 = 1;
  v26 = *a21;
  if ( *a21 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *((_BYTE *)v26 + v27) );
    v28 = v27 + 1;
  }
  else
  {
    v26 = &word_140018C4A;
    v28 = 1;
  }
  v94 = v28;
  v91 = a20;
  v93 = v26;
  v95 = 0;
  v92 = 4;
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
    v29 = &word_140018C4A;
    v31 = 1;
  }
  v89 = v31;
  v88 = v29;
  v90 = 0;
  v32 = *a18;
  if ( *a18 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *((_BYTE *)v32 + v33) );
    v34 = v33 + 1;
  }
  else
  {
    v32 = &word_140018C4A;
    v34 = 1;
  }
  v86 = v34;
  v85 = v32;
  v87 = 0;
  v35 = *a17;
  if ( *a17 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_BYTE *)v35 + v36) );
    v37 = v36 + 1;
  }
  else
  {
    v35 = &word_140018C4A;
    v37 = 1;
  }
  v83 = v37;
  v82 = v35;
  v84 = 0;
  v38 = *a16;
  if ( *a16 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *((_BYTE *)v38 + v39) );
    v40 = v39 + 1;
  }
  else
  {
    v38 = &word_140018C4A;
    v40 = 1;
  }
  v80 = v40;
  v77 = a15;
  v79 = v38;
  v81 = 0;
  v78 = 2;
  v41 = *a14;
  if ( *a14 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *((_BYTE *)v41 + v42) );
    v43 = v42 + 1;
  }
  else
  {
    v41 = &word_140018C4A;
    v43 = 1;
  }
  v75 = v43;
  v74 = v41;
  v76 = 0;
  v44 = *a13;
  if ( *a13 )
  {
    v45 = -1;
    do
      ++v45;
    while ( *((_BYTE *)v44 + v45) );
    v46 = v45 + 1;
  }
  else
  {
    v44 = &word_140018C4A;
    v46 = 1;
  }
  v72 = v46;
  v71 = v44;
  v73 = 0;
  v47 = *a12;
  if ( *a12 )
  {
    v48 = -1;
    do
      ++v48;
    while ( *((_BYTE *)v47 + v48) );
    v49 = v48 + 1;
  }
  else
  {
    v47 = &word_140018C4A;
    v49 = 1;
  }
  v69 = v49;
  v66 = a11;
  v68 = v47;
  v70 = 0;
  v67 = 2;
  v50 = *a10;
  if ( *a10 )
  {
    do
      ++v23;
    while ( *((_BYTE *)v50 + v23) );
    v25 = v23 + 1;
  }
  else
  {
    v50 = &word_140018C4A;
  }
  v61 = a9;
  v59 = a8;
  v57 = a7;
  v55 = a6;
  v53 = a5;
  v63 = v50;
  v64 = v25;
  v65 = 0;
  v62 = 4;
  v60 = 2;
  v58 = 4;
  v56 = 4;
  v54 = 4;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0x14u, &v52);
}

```

## disassembly

```asm
0x140001008  mov     [rsp-8+arg_10], rbx
0x14000100d  mov     [rsp-8+arg_18], rsi
0x140001012  push    rbp
0x140001013  lea     rbp, [rsp-80h]
0x140001018  sub     rsp, 180h
0x14000101f  mov     rax, cs:__security_cookie
0x140001026  xor     rax, rsp
0x140001029  mov     [rbp+80h+var_10], rax
0x14000102d  mov     rax, [rbp+80h+arg_A8]
0x140001034  lea     rbx, word_140018C4A
0x14000103b  xor     r9d, r9d
0x14000103e  mov     [rbp+80h+var_20], rax
0x140001042  mov     rax, [rbp+80h+arg_A0]
0x140001049  mov     r10, rcx
0x14000104c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001050  mov     [rbp+80h+var_18], 4
0x140001058  mov     r11, rdx
0x14000105b  lea     edx, [r9+1]
0x14000105f  mov     r8, [rax]
0x140001062  test    r8, r8
0x140001065  jz      short loc_140001077
0x140001067  mov     rax, rcx
0x14000106a  inc     rax
0x14000106d  cmp     [r8+rax], r9b
0x140001071  jnz     short loc_14000106A
0x140001073  inc     eax
0x140001075  jmp     short loc_14000107C
0x140001077  mov     r8, rbx
0x14000107a  mov     eax, edx
0x14000107c  mov     [rbp+80h+var_28], eax
0x14000107f  mov     rax, [rbp+80h+arg_98]
0x140001086  mov     [rbp+80h+var_40], rax
0x14000108a  mov     rax, [rbp+80h+arg_90]
0x140001091  mov     [rbp+80h+var_30], r8
0x140001095  mov     [rbp+80h+var_24], r9d
0x140001099  mov     [rbp+80h+var_38], 4
0x1400010a1  mov     r8, [rax]
0x1400010a4  test    r8, r8
0x1400010a7  jz      short loc_1400010B9
0x1400010a9  mov     rax, rcx
0x1400010ac  inc     rax
0x1400010af  cmp     [r8+rax], r9b
0x1400010b3  jnz     short loc_1400010AC
0x1400010b5  inc     eax
0x1400010b7  jmp     short loc_1400010BE
0x1400010b9  mov     r8, rbx
0x1400010bc  mov     eax, edx
0x1400010be  mov     [rbp+80h+var_48], eax
0x1400010c1  mov     rax, [rbp+80h+arg_88]
0x1400010c8  mov     [rbp+80h+var_50], r8
0x1400010cc  mov     [rbp+80h+var_44], r9d
0x1400010d0  mov     r8, [rax]
0x1400010d3  test    r8, r8
0x1400010d6  jz      short loc_1400010E8
0x1400010d8  mov     rax, rcx
0x1400010db  inc     rax
0x1400010de  cmp     [r8+rax], r9b
0x1400010e2  jnz     short loc_1400010DB
0x1400010e4  inc     eax
0x1400010e6  jmp     short loc_1400010ED
0x1400010e8  mov     r8, rbx
0x1400010eb  mov     eax, edx
0x1400010ed  mov     [rbp+80h+var_58], eax
0x1400010f0  mov     rax, [rbp+80h+arg_80]
0x1400010f7  mov     [rbp+80h+var_60], r8
0x1400010fb  mov     [rbp+80h+var_54], r9d
0x1400010ff  mov     r8, [rax]
0x140001102  test    r8, r8
0x140001105  jz      short loc_140001117
0x140001107  mov     rax, rcx
0x14000110a  inc     rax
0x14000110d  cmp     [r8+rax], r9b
0x140001111  jnz     short loc_14000110A
0x140001113  inc     eax
0x140001115  jmp     short loc_14000111C
0x140001117  mov     r8, rbx
0x14000111a  mov     eax, edx
0x14000111c  mov     [rbp+80h+var_68], eax
0x14000111f  mov     rax, [rbp+80h+arg_78]
0x140001126  mov     [rbp+80h+var_70], r8
0x14000112a  mov     [rbp+80h+var_64], r9d
0x14000112e  mov     r8, [rax]
0x140001131  test    r8, r8
0x140001134  jz      short loc_140001146
0x140001136  mov     rax, rcx
0x140001139  inc     rax
0x14000113c  cmp     [r8+rax], r9b
0x140001140  jnz     short loc_140001139
0x140001142  inc     eax
0x140001144  jmp     short loc_14000114B
0x140001146  mov     r8, rbx
0x140001149  mov     eax, edx
0x14000114b  mov     [rbp+80h+var_78], eax
0x14000114e  mov     rax, [rbp+80h+arg_70]
0x140001155  mov     [rbp+80h+var_90], rax
0x140001159  mov     rax, [rbp+80h+arg_68]
0x140001160  mov     [rbp+80h+var_80], r8
0x140001164  mov     [rbp+80h+var_74], r9d
0x140001168  mov     [rbp+80h+var_88], 2
0x140001170  mov     r8, [rax]
0x140001173  test    r8, r8
0x140001176  jz      short loc_140001188
0x140001178  mov     rax, rcx
0x14000117b  inc     rax
0x14000117e  cmp     [r8+rax], r9b
0x140001182  jnz     short loc_14000117B
0x140001184  inc     eax
0x140001186  jmp     short loc_14000118D
0x140001188  mov     r8, rbx
0x14000118b  mov     eax, edx
0x14000118d  mov     [rbp+80h+var_98], eax
0x140001190  mov     rax, [rbp+80h+arg_60]
0x140001197  mov     [rbp+80h+var_A0], r8
0x14000119b  mov     [rbp+80h+var_94], r9d
0x14000119f  mov     r8, [rax]
0x1400011a2  test    r8, r8
0x1400011a5  jz      short loc_1400011B7
0x1400011a7  mov     rax, rcx
0x1400011aa  inc     rax
0x1400011ad  cmp     [r8+rax], r9b
0x1400011b1  jnz     short loc_1400011AA
0x1400011b3  inc     eax
0x1400011b5  jmp     short loc_1400011BC
0x1400011b7  mov     r8, rbx
0x1400011ba  mov     eax, edx
0x1400011bc  mov     [rbp+80h+var_A8], eax
0x1400011bf  mov     rax, [rbp+80h+arg_58]
0x1400011c6  mov     [rbp+80h+var_B0], r8
0x1400011ca  mov     [rbp+80h+var_A4], r9d
0x1400011ce  mov     r8, [rax]
0x1400011d1  test    r8, r8
0x1400011d4  jz      short loc_1400011E6
0x1400011d6  mov     rax, rcx
0x1400011d9  inc     rax
0x1400011dc  cmp     [r8+rax], r9b
0x1400011e0  jnz     short loc_1400011D9
0x1400011e2  inc     eax
0x1400011e4  jmp     short loc_1400011EB
0x1400011e6  mov     r8, rbx
0x1400011e9  mov     eax, edx
0x1400011eb  mov     [rbp+80h+var_B8], eax
0x1400011ee  mov     rax, [rbp+80h+arg_50]
0x1400011f5  mov     [rbp+80h+var_D0], rax
0x1400011f9  mov     rax, [rbp+80h+arg_48]
0x140001200  mov     [rbp+80h+var_C0], r8
0x140001204  mov     [rbp+80h+var_B4], r9d
0x140001208  mov     [rbp+80h+var_C8], 2
0x140001210  mov     r8, [rax]
0x140001213  test    r8, r8
0x140001216  jz      short loc_140001226
0x140001218  inc     rcx
0x14000121b  cmp     [r8+rcx], r9b
0x14000121f  jnz     short loc_140001218
0x140001221  lea     edx, [rcx+1]
0x140001224  jmp     short loc_140001229
0x140001226  mov     r8, rbx
0x140001229  mov     rax, [rbp+80h+arg_40]
0x140001230  mov     rcx, r10
0x140001233  mov     [rbp+80h+var_F0], rax
0x140001237  mov     rax, [rbp+80h+arg_38]
0x14000123e  mov     [rbp+80h+var_100], rax
0x140001242  mov     rax, [rbp+80h+arg_30]
0x140001249  mov     [rsp+180h+var_110], rax
0x14000124e  mov     rax, [rbp+80h+arg_28]
0x140001255  mov     [rsp+180h+var_120], rax
0x14000125a  mov     rax, [rbp+80h+arg_20]
0x140001261  mov     [rsp+180h+var_130], rax
0x140001266  lea     rax, [rsp+180h+var_150]
0x14000126b  mov     [rbp+80h+var_E0], r8
0x14000126f  xor     r8d, r8d
0x140001272  mov     [rbp+80h+var_D8], edx
0x140001275  mov     rdx, r11
0x140001278  mov     [rsp+180h+var_158], rax
0x14000127d  mov     [rsp+180h+var_160], 14h
0x140001285  mov     [rbp+80h+var_D4], r9d
0x140001289  mov     [rbp+80h+var_E8], 4
0x140001291  mov     [rbp+80h+var_F8], 2
0x140001299  mov     [rsp+180h+var_108], 4
0x1400012a2  mov     [rsp+180h+var_118], 4
0x1400012ab  mov     [rsp+180h+var_128], 4
0x1400012b4  call    _tlgWriteTransfer_EventWriteTransfer
0x1400012b9  mov     rcx, [rbp+80h+var_10]
0x1400012bd  xor     rcx, rsp; StackCookie
0x1400012c0  call    __security_check_cookie
0x1400012c5  lea     r11, [rsp+180h+var_s0]
0x1400012cd  mov     rbx, [r11+20h]
0x1400012d1  mov     rsi, [r11+28h]
0x1400012d5  mov     rsp, r11
0x1400012d8  pop     rbp
0x1400012d9  retn
```
