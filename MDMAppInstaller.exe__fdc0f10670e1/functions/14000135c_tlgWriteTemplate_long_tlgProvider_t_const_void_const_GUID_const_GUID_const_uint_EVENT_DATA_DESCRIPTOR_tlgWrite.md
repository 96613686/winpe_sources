# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x14000135c`
- end: `0x14000164b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `751`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const OLECHAR **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const OLECHAR **, __int64, const unsigned __int16 **, const OLECHAR **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140007a3c`

## callees

- `0x14000135c`
- `0x1400017d8`
- `0x14001a8d0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9,
        __int64 a10,
        const OLECHAR **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        const OLECHAR **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        const OLECHAR **a19,
        __int64 a20,
        __int64 a21,
        const unsigned __int16 **a22)
{
  __int64 v24; // rdx
  int v25; // r8d
  const unsigned __int16 *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int v29; // r9d
  const OLECHAR *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  const OLECHAR *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  const OLECHAR *v45; // rcx
  __int64 v46; // rax
  const unsigned __int16 *v47; // rcx
  __int64 v48; // rax
  int v49; // eax
  const unsigned __int16 *v50; // rcx
  _BYTE v52[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B0h]
  __int64 v54; // [rsp+58h] [rbp-A8h]
  __int64 v55; // [rsp+60h] [rbp-A0h]
  __int64 v56; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v57; // [rsp+70h] [rbp-90h]
  int v58; // [rsp+78h] [rbp-88h]
  int v59; // [rsp+7Ch] [rbp-84h]
  __int64 v60; // [rsp+80h] [rbp-80h]
  __int64 v61; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v62; // [rsp+90h] [rbp-70h]
  int v63; // [rsp+98h] [rbp-68h]
  int v64; // [rsp+9Ch] [rbp-64h]
  __int64 v65; // [rsp+A0h] [rbp-60h]
  __int64 v66; // [rsp+A8h] [rbp-58h]
  const OLECHAR *v67; // [rsp+B0h] [rbp-50h]
  int v68; // [rsp+B8h] [rbp-48h]
  int v69; // [rsp+BCh] [rbp-44h]
  __int64 v70; // [rsp+C0h] [rbp-40h]
  __int64 v71; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v72; // [rsp+D0h] [rbp-30h]
  int v73; // [rsp+D8h] [rbp-28h]
  int v74; // [rsp+DCh] [rbp-24h]
  __int64 v75; // [rsp+E0h] [rbp-20h]
  __int64 v76; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v77; // [rsp+F0h] [rbp-10h]
  int v78; // [rsp+F8h] [rbp-8h]
  int v79; // [rsp+FCh] [rbp-4h]
  const OLECHAR *v80; // [rsp+100h] [rbp+0h]
  int v81; // [rsp+108h] [rbp+8h]
  int v82; // [rsp+10Ch] [rbp+Ch]
  __int64 v83; // [rsp+110h] [rbp+10h]
  __int64 v84; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  const OLECHAR *v88; // [rsp+130h] [rbp+30h]
  int v89; // [rsp+138h] [rbp+38h]
  int v90; // [rsp+13Ch] [rbp+3Ch]
  __int64 v91; // [rsp+140h] [rbp+40h]
  __int64 v92; // [rsp+148h] [rbp+48h]
  __int64 v93; // [rsp+150h] [rbp+50h]
  __int64 v94; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v95; // [rsp+160h] [rbp+60h]
  int v96; // [rsp+168h] [rbp+68h]
  int v97; // [rsp+16Ch] [rbp+6Ch]

  v24 = -1;
  v25 = 1;
  v26 = *a22;
  if ( *a22 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *((_BYTE *)v26 + v27) );
    v28 = v27 + 1;
  }
  else
  {
    v26 = &byte_14001E239;
    v28 = 1;
  }
  v96 = v28;
  v29 = 2;
  v93 = a21;
  v91 = a20;
  v95 = v26;
  v97 = 0;
  v94 = 4;
  v30 = *a19;
  v92 = 4;
  if ( v30 )
  {
    v31 = -1;
    do
      ++v31;
    while ( v30[v31] );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &word_14001E5B4;
    v32 = 2;
  }
  v89 = v32;
  v88 = v30;
  v90 = 0;
  v33 = *a18;
  if ( *a18 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_BYTE *)v33 + v34) );
    v35 = v34 + 1;
  }
  else
  {
    v33 = &byte_14001E239;
    v35 = 1;
  }
  v86 = v35;
  v83 = a17;
  v85 = v33;
  v87 = 0;
  v84 = 4;
  v36 = *a16;
  if ( *a16 )
  {
    v37 = -1;
    do
      ++v37;
    while ( v36[v37] );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v36 = &word_14001E5B4;
    v38 = 2;
  }
  v81 = v38;
  v80 = v36;
  v82 = 0;
  v39 = *a15;
  if ( *a15 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_BYTE *)v39 + v40) );
    v41 = v40 + 1;
  }
  else
  {
    v39 = &byte_14001E239;
    v41 = 1;
  }
  v78 = v41;
  v75 = a14;
  v77 = v39;
  v79 = 0;
  v76 = 4;
  v42 = *a13;
  if ( *a13 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &byte_14001E239;
    v44 = 1;
  }
  v73 = v44;
  v70 = a12;
  v72 = v42;
  v74 = 0;
  v71 = 4;
  v45 = *a11;
  if ( *a11 )
  {
    v46 = -1;
    do
      ++v46;
    while ( v45[v46] );
    v29 = 2 * v46 + 2;
  }
  else
  {
    v45 = &word_14001E5B4;
  }
  v65 = a10;
  v67 = v45;
  v68 = v29;
  v69 = 0;
  v47 = *a9;
  v66 = 4;
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
    v47 = &byte_14001E239;
    v49 = 1;
  }
  v63 = v49;
  v60 = a8;
  v62 = v47;
  v64 = 0;
  v61 = 4;
  v50 = *a7;
  if ( *a7 )
  {
    do
      ++v24;
    while ( *((_BYTE *)v50 + v24) );
    v25 = v24 + 1;
  }
  else
  {
    v50 = &byte_14001E239;
  }
  v55 = a6;
  v53 = a5;
  v57 = v50;
  v58 = v25;
  v59 = 0;
  v56 = 4;
  v54 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 20, v52);
}

```

## disassembly

```asm
0x14000135c  mov     [rsp-8+arg_10], rbx
0x140001361  push    rbp
0x140001362  push    rdi
0x140001363  push    r14
0x140001365  lea     rbp, [rsp-80h]
0x14000136a  sub     rsp, 180h
0x140001371  mov     rax, cs:__security_cookie
0x140001378  xor     rax, rsp
0x14000137b  mov     [rbp+90h+var_20], rax
0x14000137f  mov     rax, [rbp+90h+arg_A8]
0x140001386  lea     rdi, byte_14001E239
0x14000138d  mov     r11, rdx
0x140001390  mov     r10, rcx
0x140001393  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140001397  xor     ebx, ebx
0x140001399  mov     r8d, 1
0x14000139f  mov     rcx, [rax]
0x1400013a2  test    rcx, rcx
0x1400013a5  jz      short loc_1400013B6
0x1400013a7  mov     rax, rdx
0x1400013aa  inc     rax
0x1400013ad  cmp     [rcx+rax], bl
0x1400013b0  jnz     short loc_1400013AA
0x1400013b2  inc     eax
0x1400013b4  jmp     short loc_1400013BC
0x1400013b6  mov     rcx, rdi
0x1400013b9  mov     eax, r8d
0x1400013bc  mov     [rbp+90h+var_28], eax
0x1400013bf  mov     r9d, 2
0x1400013c5  mov     rax, [rbp+90h+arg_A0]
0x1400013cc  mov     [rbp+90h+var_40], rax
0x1400013d0  mov     rax, [rbp+90h+arg_98]
0x1400013d7  mov     [rbp+90h+var_50], rax
0x1400013db  mov     rax, [rbp+90h+arg_90]
0x1400013e2  mov     [rbp+90h+var_30], rcx
0x1400013e6  mov     [rbp+90h+var_24], ebx
0x1400013e9  mov     [rbp+90h+var_38], 4
0x1400013f1  mov     rcx, [rax]
0x1400013f4  mov     [rbp+90h+var_48], 4
0x1400013fc  test    rcx, rcx
0x1400013ff  jz      short loc_140001416
0x140001401  mov     rax, rdx
0x140001404  inc     rax
0x140001407  cmp     [rcx+rax*2], bx
0x14000140b  jnz     short loc_140001404
0x14000140d  lea     eax, ds:2[rax*2]
0x140001414  jmp     short loc_140001420
0x140001416  lea     rcx, word_14001E5B4
0x14000141d  mov     eax, r9d
0x140001420  mov     [rbp+90h+var_58], eax
0x140001423  mov     rax, [rbp+90h+arg_88]
0x14000142a  mov     [rbp+90h+var_60], rcx
0x14000142e  mov     [rbp+90h+var_54], ebx
0x140001431  mov     rcx, [rax]
0x140001434  test    rcx, rcx
0x140001437  jz      short loc_140001448
0x140001439  mov     rax, rdx
0x14000143c  inc     rax
0x14000143f  cmp     [rcx+rax], bl
0x140001442  jnz     short loc_14000143C
0x140001444  inc     eax
0x140001446  jmp     short loc_14000144E
0x140001448  mov     rcx, rdi
0x14000144b  mov     eax, r8d
0x14000144e  mov     [rbp+90h+var_68], eax
0x140001451  mov     rax, [rbp+90h+arg_80]
0x140001458  mov     [rbp+90h+var_80], rax
0x14000145c  mov     rax, [rbp+90h+arg_78]
0x140001463  mov     [rbp+90h+var_70], rcx
0x140001467  mov     [rbp+90h+var_64], ebx
0x14000146a  mov     [rbp+90h+var_78], 4
0x140001472  mov     rcx, [rax]
0x140001475  test    rcx, rcx
0x140001478  jz      short loc_14000148F
0x14000147a  mov     rax, rdx
0x14000147d  inc     rax
0x140001480  cmp     [rcx+rax*2], bx
0x140001484  jnz     short loc_14000147D
0x140001486  lea     eax, ds:2[rax*2]
0x14000148d  jmp     short loc_140001499
0x14000148f  lea     rcx, word_14001E5B4
0x140001496  mov     eax, r9d
0x140001499  mov     [rbp+90h+var_88], eax
0x14000149c  mov     rax, [rbp+90h+arg_70]
0x1400014a3  mov     [rbp+90h+var_90], rcx
0x1400014a7  mov     [rbp+90h+var_84], ebx
0x1400014aa  mov     rcx, [rax]
0x1400014ad  test    rcx, rcx
0x1400014b0  jz      short loc_1400014C1
0x1400014b2  mov     rax, rdx
0x1400014b5  inc     rax
0x1400014b8  cmp     [rcx+rax], bl
0x1400014bb  jnz     short loc_1400014B5
0x1400014bd  inc     eax
0x1400014bf  jmp     short loc_1400014C7
0x1400014c1  mov     rcx, rdi
0x1400014c4  mov     eax, r8d
0x1400014c7  mov     [rbp+90h+var_98], eax
0x1400014ca  mov     rax, [rbp+90h+arg_68]
0x1400014d1  mov     [rbp+90h+var_B0], rax
0x1400014d5  mov     rax, [rbp+90h+arg_60]
0x1400014dc  mov     [rbp+90h+var_A0], rcx
0x1400014e0  mov     [rbp+90h+var_94], ebx
0x1400014e3  mov     [rbp+90h+var_A8], 4
0x1400014eb  mov     rcx, [rax]
0x1400014ee  test    rcx, rcx
0x1400014f1  jz      short loc_140001502
0x1400014f3  mov     rax, rdx
0x1400014f6  inc     rax
0x1400014f9  cmp     [rcx+rax], bl
0x1400014fc  jnz     short loc_1400014F6
0x1400014fe  inc     eax
0x140001500  jmp     short loc_140001508
0x140001502  mov     rcx, rdi
0x140001505  mov     eax, r8d
0x140001508  mov     [rbp+90h+var_B8], eax
0x14000150b  mov     rax, [rbp+90h+arg_58]
0x140001512  mov     [rbp+90h+var_D0], rax
0x140001516  mov     rax, [rbp+90h+arg_50]
0x14000151d  mov     [rbp+90h+var_C0], rcx
0x140001521  mov     [rbp+90h+var_B4], ebx
0x140001524  mov     [rbp+90h+var_C8], 4
0x14000152c  mov     rcx, [rax]
0x14000152f  test    rcx, rcx
0x140001532  jz      short loc_14000154A
0x140001534  mov     rax, rdx
0x140001537  inc     rax
0x14000153a  cmp     [rcx+rax*2], bx
0x14000153e  jnz     short loc_140001537
0x140001540  lea     r9d, ds:2[rax*2]
0x140001548  jmp     short loc_140001551
0x14000154a  lea     rcx, word_14001E5B4
0x140001551  mov     rax, [rbp+90h+arg_48]
0x140001558  mov     [rbp+90h+var_F0], rax
0x14000155c  mov     rax, [rbp+90h+arg_40]
0x140001563  mov     [rbp+90h+var_E0], rcx
0x140001567  mov     [rbp+90h+var_D8], r9d
0x14000156b  mov     [rbp+90h+var_D4], ebx
0x14000156e  mov     rcx, [rax]
0x140001571  mov     [rbp+90h+var_E8], 4
0x140001579  test    rcx, rcx
0x14000157c  jz      short loc_14000158D
0x14000157e  mov     rax, rdx
0x140001581  inc     rax
0x140001584  cmp     [rcx+rax], bl
0x140001587  jnz     short loc_140001581
0x140001589  inc     eax
0x14000158b  jmp     short loc_140001593
0x14000158d  mov     rcx, rdi
0x140001590  mov     eax, r8d
0x140001593  mov     [rbp+90h+var_F8], eax
0x140001596  mov     rax, [rbp+90h+arg_38]
0x14000159d  mov     [rbp+90h+var_110], rax
0x1400015a1  mov     rax, [rbp+90h+arg_30]
0x1400015a8  mov     [rbp+90h+var_100], rcx
0x1400015ac  mov     [rbp+90h+var_F4], ebx
0x1400015af  mov     [rbp+90h+var_108], 4
0x1400015b7  mov     rcx, [rax]
0x1400015ba  test    rcx, rcx
0x1400015bd  jz      short loc_1400015CD
0x1400015bf  inc     rdx
0x1400015c2  cmp     [rcx+rdx], bl
0x1400015c5  jnz     short loc_1400015BF
0x1400015c7  lea     r8d, [rdx+1]
0x1400015cb  jmp     short loc_1400015D0
0x1400015cd  mov     rcx, rdi
0x1400015d0  mov     rax, [rbp+90h+arg_28]
0x1400015d7  xor     r9d, r9d
0x1400015da  mov     [rsp+190h+var_130], rax
0x1400015df  mov     rdx, r11
0x1400015e2  mov     rax, [rbp+90h+arg_20]
0x1400015e9  mov     [rsp+190h+var_140], rax
0x1400015ee  lea     rax, [rsp+190h+var_160]
0x1400015f3  mov     [rsp+190h+var_120], rcx
0x1400015f8  mov     rcx, r10
0x1400015fb  mov     [rsp+190h+var_118], r8d
0x140001600  xor     r8d, r8d
0x140001603  mov     [rsp+190h+var_168], rax
0x140001608  mov     [rsp+190h+var_170], 14h
0x140001610  mov     [rsp+190h+var_114], ebx
0x140001614  mov     [rsp+190h+var_128], 4
0x14000161d  mov     [rsp+190h+var_138], 8
0x140001626  call    _tlgWriteTransfer_EventWriteTransfer
0x14000162b  mov     rcx, [rbp+90h+var_20]
0x14000162f  xor     rcx, rsp; StackCookie
0x140001632  call    __security_check_cookie
0x140001637  mov     rbx, [rsp+190h+arg_10]
0x14000163f  add     rsp, 180h
0x140001646  pop     r14
0x140001648  pop     rdi
0x140001649  pop     rbp
0x14000164a  retn
```
