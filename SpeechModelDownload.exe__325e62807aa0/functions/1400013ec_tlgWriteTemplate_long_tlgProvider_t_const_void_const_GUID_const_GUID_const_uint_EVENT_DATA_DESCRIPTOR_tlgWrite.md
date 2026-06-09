# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1400013ec`
- end: `0x1400016dc`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const size_t **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const size_t **, __int64, const unsigned __int16 **, const size_t **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140007c3c`
- `0x140018330`

## callees

- `0x1400013ec`
- `0x14000176c`
- `0x140002600`

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
        const size_t **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        const size_t **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        const size_t **a19,
        __int64 a20,
        __int64 a21,
        const unsigned __int16 **a22)
{
  __int64 v24; // rdx
  int v26; // r8d
  const unsigned __int16 *v27; // rcx
  __int64 v28; // rax
  int v29; // eax
  int v30; // r9d
  const size_t *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const size_t *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  const size_t *v46; // rcx
  __int64 v47; // rax
  const unsigned __int16 *v48; // rcx
  __int64 v49; // rax
  int v50; // eax
  const unsigned __int16 *v51; // rcx
  _BYTE v53[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v54; // [rsp+50h] [rbp-B0h]
  __int64 v55; // [rsp+58h] [rbp-A8h]
  __int64 v56; // [rsp+60h] [rbp-A0h]
  __int64 v57; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v58; // [rsp+70h] [rbp-90h]
  int v59; // [rsp+78h] [rbp-88h]
  int v60; // [rsp+7Ch] [rbp-84h]
  __int64 v61; // [rsp+80h] [rbp-80h]
  __int64 v62; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v63; // [rsp+90h] [rbp-70h]
  int v64; // [rsp+98h] [rbp-68h]
  int v65; // [rsp+9Ch] [rbp-64h]
  __int64 v66; // [rsp+A0h] [rbp-60h]
  __int64 v67; // [rsp+A8h] [rbp-58h]
  const size_t *v68; // [rsp+B0h] [rbp-50h]
  int v69; // [rsp+B8h] [rbp-48h]
  int v70; // [rsp+BCh] [rbp-44h]
  __int64 v71; // [rsp+C0h] [rbp-40h]
  __int64 v72; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v73; // [rsp+D0h] [rbp-30h]
  int v74; // [rsp+D8h] [rbp-28h]
  int v75; // [rsp+DCh] [rbp-24h]
  __int64 v76; // [rsp+E0h] [rbp-20h]
  __int64 v77; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v78; // [rsp+F0h] [rbp-10h]
  int v79; // [rsp+F8h] [rbp-8h]
  int v80; // [rsp+FCh] [rbp-4h]
  const size_t *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+12Ch] [rbp+2Ch]
  const size_t *v89; // [rsp+130h] [rbp+30h]
  int v90; // [rsp+138h] [rbp+38h]
  int v91; // [rsp+13Ch] [rbp+3Ch]
  __int64 v92; // [rsp+140h] [rbp+40h]
  __int64 v93; // [rsp+148h] [rbp+48h]
  __int64 v94; // [rsp+150h] [rbp+50h]
  __int64 v95; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v96; // [rsp+160h] [rbp+60h]
  int v97; // [rsp+168h] [rbp+68h]
  int v98; // [rsp+16Ch] [rbp+6Ch]

  v24 = -1;
  v26 = 1;
  v27 = *a22;
  if ( *a22 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *((_BYTE *)v27 + v28) );
    v29 = v28 + 1;
  }
  else
  {
    v27 = &word_14001EFBE;
    v29 = 1;
  }
  v97 = v29;
  v30 = 2;
  v94 = a21;
  v92 = a20;
  v96 = v27;
  v98 = 0;
  v95 = 4;
  v31 = *a19;
  v93 = 4;
  if ( v31 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *((_WORD *)v31 + v32) );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &byte_14001EFBC;
    v33 = 2;
  }
  v90 = v33;
  v89 = v31;
  v91 = 0;
  v34 = *a18;
  if ( *a18 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &word_14001EFBE;
    v36 = 1;
  }
  v87 = v36;
  v84 = a17;
  v86 = v34;
  v88 = 0;
  v85 = 4;
  v37 = *a16;
  if ( *a16 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_WORD *)v37 + v38) );
    v39 = 2 * v38 + 2;
  }
  else
  {
    v37 = &byte_14001EFBC;
    v39 = 2;
  }
  v82 = v39;
  v81 = v37;
  v83 = 0;
  v40 = *a15;
  if ( *a15 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_BYTE *)v40 + v41) );
    v42 = v41 + 1;
  }
  else
  {
    v40 = &word_14001EFBE;
    v42 = 1;
  }
  v79 = v42;
  v76 = a14;
  v78 = v40;
  v80 = 0;
  v77 = 4;
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
    v43 = &word_14001EFBE;
    v45 = 1;
  }
  v74 = v45;
  v71 = a12;
  v73 = v43;
  v75 = 0;
  v72 = 4;
  v46 = *a11;
  if ( *a11 )
  {
    v47 = -1;
    do
      ++v47;
    while ( *((_WORD *)v46 + v47) );
    v30 = 2 * v47 + 2;
  }
  else
  {
    v46 = &byte_14001EFBC;
  }
  v66 = a10;
  v68 = v46;
  v69 = v30;
  v70 = 0;
  v48 = *a9;
  v67 = 4;
  if ( v48 )
  {
    v49 = -1;
    do
      ++v49;
    while ( *((_BYTE *)v48 + v49) );
    v50 = v49 + 1;
  }
  else
  {
    v48 = &word_14001EFBE;
    v50 = 1;
  }
  v64 = v50;
  v61 = a8;
  v63 = v48;
  v65 = 0;
  v62 = 4;
  v51 = *a7;
  if ( *a7 )
  {
    do
      ++v24;
    while ( *((_BYTE *)v51 + v24) );
    v26 = v24 + 1;
  }
  else
  {
    v51 = &word_14001EFBE;
  }
  v56 = a6;
  v54 = a5;
  v58 = v51;
  v59 = v26;
  v60 = 0;
  v57 = 4;
  v55 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 20, v53);
}

```

## disassembly

```asm
0x1400013ec  push    rbp
0x1400013ee  push    rbx
0x1400013ef  push    rsi
0x1400013f0  push    rdi
0x1400013f1  push    r15
0x1400013f3  lea     rbp, [rsp-80h]
0x1400013f8  sub     rsp, 180h
0x1400013ff  mov     rax, cs:__security_cookie
0x140001406  xor     rax, rsp
0x140001409  mov     [rbp+0A0h+var_30], rax
0x14000140d  mov     rax, [rbp+0A0h+arg_A8]
0x140001414  lea     rsi, word_14001EFBE
0x14000141b  mov     r11, rdx
0x14000141e  mov     r10, rcx
0x140001421  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140001425  xor     edi, edi
0x140001427  mov     rbx, r8
0x14000142a  mov     r8d, 1
0x140001430  mov     rcx, [rax]
0x140001433  test    rcx, rcx
0x140001436  jz      short loc_140001448
0x140001438  mov     rax, rdx
0x14000143b  inc     rax
0x14000143e  cmp     [rcx+rax], dil
0x140001442  jnz     short loc_14000143B
0x140001444  inc     eax
0x140001446  jmp     short loc_14000144E
0x140001448  mov     rcx, rsi
0x14000144b  mov     eax, r8d
0x14000144e  mov     [rbp+0A0h+var_38], eax
0x140001451  mov     r9d, 2
0x140001457  mov     rax, [rbp+0A0h+arg_A0]
0x14000145e  mov     [rbp+0A0h+var_50], rax
0x140001462  mov     rax, [rbp+0A0h+arg_98]
0x140001469  mov     [rbp+0A0h+var_60], rax
0x14000146d  mov     rax, [rbp+0A0h+arg_90]
0x140001474  mov     [rbp+0A0h+var_40], rcx
0x140001478  mov     [rbp+0A0h+var_34], edi
0x14000147b  mov     [rbp+0A0h+var_48], 4
0x140001483  mov     rcx, [rax]
0x140001486  mov     [rbp+0A0h+var_58], 4
0x14000148e  test    rcx, rcx
0x140001491  jz      short loc_1400014A8
0x140001493  mov     rax, rdx
0x140001496  inc     rax
0x140001499  cmp     [rcx+rax*2], di
0x14000149d  jnz     short loc_140001496
0x14000149f  lea     eax, ds:2[rax*2]
0x1400014a6  jmp     short loc_1400014B2
0x1400014a8  lea     rcx, byte_14001EFBC
0x1400014af  mov     eax, r9d
0x1400014b2  mov     [rbp+0A0h+var_68], eax
0x1400014b5  mov     rax, [rbp+0A0h+arg_88]
0x1400014bc  mov     [rbp+0A0h+var_70], rcx
0x1400014c0  mov     [rbp+0A0h+var_64], edi
0x1400014c3  mov     rcx, [rax]
0x1400014c6  test    rcx, rcx
0x1400014c9  jz      short loc_1400014DB
0x1400014cb  mov     rax, rdx
0x1400014ce  inc     rax
0x1400014d1  cmp     [rcx+rax], dil
0x1400014d5  jnz     short loc_1400014CE
0x1400014d7  inc     eax
0x1400014d9  jmp     short loc_1400014E1
0x1400014db  mov     rcx, rsi
0x1400014de  mov     eax, r8d
0x1400014e1  mov     [rbp+0A0h+var_78], eax
0x1400014e4  mov     rax, [rbp+0A0h+arg_80]
0x1400014eb  mov     [rbp+0A0h+var_90], rax
0x1400014ef  mov     rax, [rbp+0A0h+arg_78]
0x1400014f6  mov     [rbp+0A0h+var_80], rcx
0x1400014fa  mov     [rbp+0A0h+var_74], edi
0x1400014fd  mov     [rbp+0A0h+var_88], 4
0x140001505  mov     rcx, [rax]
0x140001508  test    rcx, rcx
0x14000150b  jz      short loc_140001522
0x14000150d  mov     rax, rdx
0x140001510  inc     rax
0x140001513  cmp     [rcx+rax*2], di
0x140001517  jnz     short loc_140001510
0x140001519  lea     eax, ds:2[rax*2]
0x140001520  jmp     short loc_14000152C
0x140001522  lea     rcx, byte_14001EFBC
0x140001529  mov     eax, r9d
0x14000152c  mov     [rbp+0A0h+var_98], eax
0x14000152f  mov     rax, [rbp+0A0h+arg_70]
0x140001536  mov     [rbp+0A0h+var_A0], rcx
0x14000153a  mov     [rbp+0A0h+var_94], edi
0x14000153d  mov     rcx, [rax]
0x140001540  test    rcx, rcx
0x140001543  jz      short loc_140001555
0x140001545  mov     rax, rdx
0x140001548  inc     rax
0x14000154b  cmp     [rcx+rax], dil
0x14000154f  jnz     short loc_140001548
0x140001551  inc     eax
0x140001553  jmp     short loc_14000155B
0x140001555  mov     rcx, rsi
0x140001558  mov     eax, r8d
0x14000155b  mov     [rbp+0A0h+var_A8], eax
0x14000155e  mov     rax, [rbp+0A0h+arg_68]
0x140001565  mov     [rbp+0A0h+var_C0], rax
0x140001569  mov     rax, [rbp+0A0h+arg_60]
0x140001570  mov     [rbp+0A0h+var_B0], rcx
0x140001574  mov     [rbp+0A0h+var_A4], edi
0x140001577  mov     [rbp+0A0h+var_B8], 4
0x14000157f  mov     rcx, [rax]
0x140001582  test    rcx, rcx
0x140001585  jz      short loc_140001597
0x140001587  mov     rax, rdx
0x14000158a  inc     rax
0x14000158d  cmp     [rcx+rax], dil
0x140001591  jnz     short loc_14000158A
0x140001593  inc     eax
0x140001595  jmp     short loc_14000159D
0x140001597  mov     rcx, rsi
0x14000159a  mov     eax, r8d
0x14000159d  mov     [rbp+0A0h+var_C8], eax
0x1400015a0  mov     rax, [rbp+0A0h+arg_58]
0x1400015a7  mov     [rbp+0A0h+var_E0], rax
0x1400015ab  mov     rax, [rbp+0A0h+arg_50]
0x1400015b2  mov     [rbp+0A0h+var_D0], rcx
0x1400015b6  mov     [rbp+0A0h+var_C4], edi
0x1400015b9  mov     [rbp+0A0h+var_D8], 4
0x1400015c1  mov     rcx, [rax]
0x1400015c4  test    rcx, rcx
0x1400015c7  jz      short loc_1400015DF
0x1400015c9  mov     rax, rdx
0x1400015cc  inc     rax
0x1400015cf  cmp     [rcx+rax*2], di
0x1400015d3  jnz     short loc_1400015CC
0x1400015d5  lea     r9d, ds:2[rax*2]
0x1400015dd  jmp     short loc_1400015E6
0x1400015df  lea     rcx, byte_14001EFBC
0x1400015e6  mov     rax, [rbp+0A0h+arg_48]
0x1400015ed  mov     [rbp+0A0h+var_100], rax
0x1400015f1  mov     rax, [rbp+0A0h+arg_40]
0x1400015f8  mov     [rbp+0A0h+var_F0], rcx
0x1400015fc  mov     [rbp+0A0h+var_E8], r9d
0x140001600  mov     [rbp+0A0h+var_E4], edi
0x140001603  mov     rcx, [rax]
0x140001606  mov     [rbp+0A0h+var_F8], 4
0x14000160e  test    rcx, rcx
0x140001611  jz      short loc_140001623
0x140001613  mov     rax, rdx
0x140001616  inc     rax
0x140001619  cmp     [rcx+rax], dil
0x14000161d  jnz     short loc_140001616
0x14000161f  inc     eax
0x140001621  jmp     short loc_140001629
0x140001623  mov     rcx, rsi
0x140001626  mov     eax, r8d
0x140001629  mov     [rbp+0A0h+var_108], eax
0x14000162c  mov     rax, [rbp+0A0h+arg_38]
0x140001633  mov     [rbp+0A0h+var_120], rax
0x140001637  mov     rax, [rbp+0A0h+arg_30]
0x14000163e  mov     [rbp+0A0h+var_110], rcx
0x140001642  mov     [rbp+0A0h+var_104], edi
0x140001645  mov     [rbp+0A0h+var_118], 4
0x14000164d  mov     rcx, [rax]
0x140001650  test    rcx, rcx
0x140001653  jz      short loc_140001664
0x140001655  inc     rdx
0x140001658  cmp     [rcx+rdx], dil
0x14000165c  jnz     short loc_140001655
0x14000165e  lea     r8d, [rdx+1]
0x140001662  jmp     short loc_140001667
0x140001664  mov     rcx, rsi
0x140001667  mov     rax, [rbp+0A0h+arg_28]
0x14000166e  xor     r9d, r9d
0x140001671  mov     [rsp+1A0h+var_140], rax
0x140001676  mov     rdx, r11
0x140001679  mov     rax, [rbp+0A0h+arg_20]
0x140001680  mov     [rsp+1A0h+var_150], rax
0x140001685  lea     rax, [rsp+1A0h+var_170]
0x14000168a  mov     [rsp+1A0h+var_130], rcx
0x14000168f  mov     rcx, r10
0x140001692  mov     [rsp+1A0h+var_128], r8d
0x140001697  mov     r8, rbx
0x14000169a  mov     [rsp+1A0h+var_178], rax
0x14000169f  mov     [rsp+1A0h+var_180], 14h
0x1400016a7  mov     [rsp+1A0h+var_124], edi
0x1400016ab  mov     [rsp+1A0h+var_138], 4
0x1400016b4  mov     [rsp+1A0h+var_148], 8
0x1400016bd  call    _tlgWriteTransfer_EventWriteTransfer
0x1400016c2  mov     rcx, [rbp+0A0h+var_30]
0x1400016c6  xor     rcx, rsp; StackCookie
0x1400016c9  call    __security_check_cookie
0x1400016ce  add     rsp, 180h
0x1400016d5  pop     r15
0x1400016d7  pop     rdi
0x1400016d8  pop     rsi
0x1400016d9  pop     rbx
0x1400016da  pop     rbp
0x1400016db  retn
```
