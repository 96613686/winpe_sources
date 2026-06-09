# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1400013f8`
- end: `0x1400016ca`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$01@@U1@U?$_tlgWrapSz@D@@U2@U3@U3@U3@U2@U3@U3@U3@U3@U1@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$01@@3AEBU?$_tlgWrapSz@D@@455545555353@Z`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140009bf0`

## callees

- `0x14000113c`
- `0x1400013f8`
- `0x1400023d0`

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
  __int64 v23; // rcx
  int v25; // edx
  const wchar_t *v26; // r8
  __int64 v27; // rax
  int v28; // eax
  const wchar_t *v29; // r8
  __int64 v30; // rax
  int v31; // eax
  const wchar_t *v32; // r8
  __int64 v33; // rax
  int v34; // eax
  const wchar_t *v35; // r8
  __int64 v36; // rax
  int v37; // eax
  const wchar_t *v38; // r8
  __int64 v39; // rax
  int v40; // eax
  const wchar_t *v41; // r8
  __int64 v42; // rax
  int v43; // eax
  const wchar_t *v44; // r8
  __int64 v45; // rax
  int v46; // eax
  const wchar_t *v47; // r8
  __int64 v48; // rax
  int v49; // eax
  const wchar_t *v50; // r8
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
  const wchar_t *v63; // [rsp+A0h] [rbp-60h]
  int v64; // [rsp+A8h] [rbp-58h]
  int v65; // [rsp+ACh] [rbp-54h]
  __int64 v66; // [rsp+B0h] [rbp-50h]
  __int64 v67; // [rsp+B8h] [rbp-48h]
  const wchar_t *v68; // [rsp+C0h] [rbp-40h]
  int v69; // [rsp+C8h] [rbp-38h]
  int v70; // [rsp+CCh] [rbp-34h]
  const wchar_t *v71; // [rsp+D0h] [rbp-30h]
  int v72; // [rsp+D8h] [rbp-28h]
  int v73; // [rsp+DCh] [rbp-24h]
  const wchar_t *v74; // [rsp+E0h] [rbp-20h]
  int v75; // [rsp+E8h] [rbp-18h]
  int v76; // [rsp+ECh] [rbp-14h]
  __int64 v77; // [rsp+F0h] [rbp-10h]
  __int64 v78; // [rsp+F8h] [rbp-8h]
  const wchar_t *v79; // [rsp+100h] [rbp+0h]
  int v80; // [rsp+108h] [rbp+8h]
  int v81; // [rsp+10Ch] [rbp+Ch]
  const wchar_t *v82; // [rsp+110h] [rbp+10h]
  int v83; // [rsp+118h] [rbp+18h]
  int v84; // [rsp+11Ch] [rbp+1Ch]
  const wchar_t *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  const wchar_t *v88; // [rsp+130h] [rbp+30h]
  int v89; // [rsp+138h] [rbp+38h]
  int v90; // [rsp+13Ch] [rbp+3Ch]
  __int64 v91; // [rsp+140h] [rbp+40h]
  __int64 v92; // [rsp+148h] [rbp+48h]
  const wchar_t *v93; // [rsp+150h] [rbp+50h]
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
    v26 = &word_140013F31;
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
    v29 = &word_140013F31;
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
    v32 = &word_140013F31;
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
    v35 = &word_140013F31;
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
    v38 = &word_140013F31;
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
    v41 = &word_140013F31;
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
    v44 = &word_140013F31;
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
    v47 = &word_140013F31;
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
    v50 = &word_140013F31;
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
0x1400013f8  mov     [rsp-8+arg_10], rbx
0x1400013fd  mov     [rsp-8+arg_18], rsi
0x140001402  push    rbp
0x140001403  lea     rbp, [rsp-80h]
0x140001408  sub     rsp, 180h
0x14000140f  mov     rax, cs:__security_cookie
0x140001416  xor     rax, rsp
0x140001419  mov     [rbp+80h+var_10], rax
0x14000141d  mov     rax, [rbp+80h+arg_A8]
0x140001424  lea     rbx, word_140013F31
0x14000142b  xor     r9d, r9d
0x14000142e  mov     [rbp+80h+var_20], rax
0x140001432  mov     rax, [rbp+80h+arg_A0]
0x140001439  mov     r10, rcx
0x14000143c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001440  mov     [rbp+80h+var_18], 4
0x140001448  mov     r11, rdx
0x14000144b  lea     edx, [r9+1]
0x14000144f  mov     r8, [rax]
0x140001452  test    r8, r8
0x140001455  jz      short loc_140001467
0x140001457  mov     rax, rcx
0x14000145a  inc     rax
0x14000145d  cmp     [r8+rax], r9b
0x140001461  jnz     short loc_14000145A
0x140001463  inc     eax
0x140001465  jmp     short loc_14000146C
0x140001467  mov     r8, rbx
0x14000146a  mov     eax, edx
0x14000146c  mov     [rbp+80h+var_28], eax
0x14000146f  mov     rax, [rbp+80h+arg_98]
0x140001476  mov     [rbp+80h+var_40], rax
0x14000147a  mov     rax, [rbp+80h+arg_90]
0x140001481  mov     [rbp+80h+var_30], r8
0x140001485  mov     [rbp+80h+var_24], r9d
0x140001489  mov     [rbp+80h+var_38], 4
0x140001491  mov     r8, [rax]
0x140001494  test    r8, r8
0x140001497  jz      short loc_1400014A9
0x140001499  mov     rax, rcx
0x14000149c  inc     rax
0x14000149f  cmp     [r8+rax], r9b
0x1400014a3  jnz     short loc_14000149C
0x1400014a5  inc     eax
0x1400014a7  jmp     short loc_1400014AE
0x1400014a9  mov     r8, rbx
0x1400014ac  mov     eax, edx
0x1400014ae  mov     [rbp+80h+var_48], eax
0x1400014b1  mov     rax, [rbp+80h+arg_88]
0x1400014b8  mov     [rbp+80h+var_50], r8
0x1400014bc  mov     [rbp+80h+var_44], r9d
0x1400014c0  mov     r8, [rax]
0x1400014c3  test    r8, r8
0x1400014c6  jz      short loc_1400014D8
0x1400014c8  mov     rax, rcx
0x1400014cb  inc     rax
0x1400014ce  cmp     [r8+rax], r9b
0x1400014d2  jnz     short loc_1400014CB
0x1400014d4  inc     eax
0x1400014d6  jmp     short loc_1400014DD
0x1400014d8  mov     r8, rbx
0x1400014db  mov     eax, edx
0x1400014dd  mov     [rbp+80h+var_58], eax
0x1400014e0  mov     rax, [rbp+80h+arg_80]
0x1400014e7  mov     [rbp+80h+var_60], r8
0x1400014eb  mov     [rbp+80h+var_54], r9d
0x1400014ef  mov     r8, [rax]
0x1400014f2  test    r8, r8
0x1400014f5  jz      short loc_140001507
0x1400014f7  mov     rax, rcx
0x1400014fa  inc     rax
0x1400014fd  cmp     [r8+rax], r9b
0x140001501  jnz     short loc_1400014FA
0x140001503  inc     eax
0x140001505  jmp     short loc_14000150C
0x140001507  mov     r8, rbx
0x14000150a  mov     eax, edx
0x14000150c  mov     [rbp+80h+var_68], eax
0x14000150f  mov     rax, [rbp+80h+arg_78]
0x140001516  mov     [rbp+80h+var_70], r8
0x14000151a  mov     [rbp+80h+var_64], r9d
0x14000151e  mov     r8, [rax]
0x140001521  test    r8, r8
0x140001524  jz      short loc_140001536
0x140001526  mov     rax, rcx
0x140001529  inc     rax
0x14000152c  cmp     [r8+rax], r9b
0x140001530  jnz     short loc_140001529
0x140001532  inc     eax
0x140001534  jmp     short loc_14000153B
0x140001536  mov     r8, rbx
0x140001539  mov     eax, edx
0x14000153b  mov     [rbp+80h+var_78], eax
0x14000153e  mov     rax, [rbp+80h+arg_70]
0x140001545  mov     [rbp+80h+var_90], rax
0x140001549  mov     rax, [rbp+80h+arg_68]
0x140001550  mov     [rbp+80h+var_80], r8
0x140001554  mov     [rbp+80h+var_74], r9d
0x140001558  mov     [rbp+80h+var_88], 2
0x140001560  mov     r8, [rax]
0x140001563  test    r8, r8
0x140001566  jz      short loc_140001578
0x140001568  mov     rax, rcx
0x14000156b  inc     rax
0x14000156e  cmp     [r8+rax], r9b
0x140001572  jnz     short loc_14000156B
0x140001574  inc     eax
0x140001576  jmp     short loc_14000157D
0x140001578  mov     r8, rbx
0x14000157b  mov     eax, edx
0x14000157d  mov     [rbp+80h+var_98], eax
0x140001580  mov     rax, [rbp+80h+arg_60]
0x140001587  mov     [rbp+80h+var_A0], r8
0x14000158b  mov     [rbp+80h+var_94], r9d
0x14000158f  mov     r8, [rax]
0x140001592  test    r8, r8
0x140001595  jz      short loc_1400015A7
0x140001597  mov     rax, rcx
0x14000159a  inc     rax
0x14000159d  cmp     [r8+rax], r9b
0x1400015a1  jnz     short loc_14000159A
0x1400015a3  inc     eax
0x1400015a5  jmp     short loc_1400015AC
0x1400015a7  mov     r8, rbx
0x1400015aa  mov     eax, edx
0x1400015ac  mov     [rbp+80h+var_A8], eax
0x1400015af  mov     rax, [rbp+80h+arg_58]
0x1400015b6  mov     [rbp+80h+var_B0], r8
0x1400015ba  mov     [rbp+80h+var_A4], r9d
0x1400015be  mov     r8, [rax]
0x1400015c1  test    r8, r8
0x1400015c4  jz      short loc_1400015D6
0x1400015c6  mov     rax, rcx
0x1400015c9  inc     rax
0x1400015cc  cmp     [r8+rax], r9b
0x1400015d0  jnz     short loc_1400015C9
0x1400015d2  inc     eax
0x1400015d4  jmp     short loc_1400015DB
0x1400015d6  mov     r8, rbx
0x1400015d9  mov     eax, edx
0x1400015db  mov     [rbp+80h+var_B8], eax
0x1400015de  mov     rax, [rbp+80h+arg_50]
0x1400015e5  mov     [rbp+80h+var_D0], rax
0x1400015e9  mov     rax, [rbp+80h+arg_48]
0x1400015f0  mov     [rbp+80h+var_C0], r8
0x1400015f4  mov     [rbp+80h+var_B4], r9d
0x1400015f8  mov     [rbp+80h+var_C8], 2
0x140001600  mov     r8, [rax]
0x140001603  test    r8, r8
0x140001606  jz      short loc_140001616
0x140001608  inc     rcx
0x14000160b  cmp     [r8+rcx], r9b
0x14000160f  jnz     short loc_140001608
0x140001611  lea     edx, [rcx+1]
0x140001614  jmp     short loc_140001619
0x140001616  mov     r8, rbx
0x140001619  mov     rax, [rbp+80h+arg_40]
0x140001620  mov     rcx, r10
0x140001623  mov     [rbp+80h+var_F0], rax
0x140001627  mov     rax, [rbp+80h+arg_38]
0x14000162e  mov     [rbp+80h+var_100], rax
0x140001632  mov     rax, [rbp+80h+arg_30]
0x140001639  mov     [rsp+180h+var_110], rax
0x14000163e  mov     rax, [rbp+80h+arg_28]
0x140001645  mov     [rsp+180h+var_120], rax
0x14000164a  mov     rax, [rbp+80h+arg_20]
0x140001651  mov     [rsp+180h+var_130], rax
0x140001656  lea     rax, [rsp+180h+var_150]
0x14000165b  mov     [rbp+80h+var_E0], r8
0x14000165f  xor     r8d, r8d
0x140001662  mov     [rbp+80h+var_D8], edx
0x140001665  mov     rdx, r11
0x140001668  mov     [rsp+180h+var_158], rax
0x14000166d  mov     [rsp+180h+var_160], 14h
0x140001675  mov     [rbp+80h+var_D4], r9d
0x140001679  mov     [rbp+80h+var_E8], 4
0x140001681  mov     [rbp+80h+var_F8], 2
0x140001689  mov     [rsp+180h+var_108], 4
0x140001692  mov     [rsp+180h+var_118], 4
0x14000169b  mov     [rsp+180h+var_128], 4
0x1400016a4  call    _tlgWriteTransfer_EventWriteTransfer
0x1400016a9  mov     rcx, [rbp+80h+var_10]
0x1400016ad  xor     rcx, rsp; StackCookie
0x1400016b0  call    __security_check_cookie
0x1400016b5  lea     r11, [rsp+180h+var_s0]
0x1400016bd  mov     rbx, [r11+20h]
0x1400016c1  mov     rsi, [r11+28h]
0x1400016c5  mov     rsp, r11
0x1400016c8  pop     rbp
0x1400016c9  retn
```
