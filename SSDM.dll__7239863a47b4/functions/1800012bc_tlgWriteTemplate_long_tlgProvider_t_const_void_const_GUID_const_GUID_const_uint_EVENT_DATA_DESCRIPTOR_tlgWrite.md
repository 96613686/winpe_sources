# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1800012bc`
- end: `0x1800015ac`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z`
- size: `752`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const wchar_t **, __int64, const wchar_t **, __int64, char **, __int64, const wchar_t **, __int64, const wchar_t **, char **, __int64, const wchar_t **, char **, __int64, __int64, const wchar_t **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180006cf4`
- `0x18000a970`

## callees

- `0x1800012bc`
- `0x18000163c`
- `0x18000e990`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const wchar_t **a7,
        __int64 a8,
        const wchar_t **a9,
        __int64 a10,
        char **a11,
        __int64 a12,
        const wchar_t **a13,
        __int64 a14,
        const wchar_t **a15,
        char **a16,
        __int64 a17,
        const wchar_t **a18,
        char **a19,
        __int64 a20,
        __int64 a21,
        const wchar_t **a22)
{
  __int64 v24; // rdx
  int v26; // r8d
  const wchar_t *v27; // rcx
  __int64 v28; // rax
  int v29; // eax
  int v30; // r9d
  char *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const wchar_t *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  char *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const wchar_t *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const wchar_t *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  char *v46; // rcx
  __int64 v47; // rax
  const wchar_t *v48; // rcx
  __int64 v49; // rax
  int v50; // eax
  const wchar_t *v51; // rcx
  _BYTE v53[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v54; // [rsp+50h] [rbp-B0h]
  __int64 v55; // [rsp+58h] [rbp-A8h]
  __int64 v56; // [rsp+60h] [rbp-A0h]
  __int64 v57; // [rsp+68h] [rbp-98h]
  const wchar_t *v58; // [rsp+70h] [rbp-90h]
  int v59; // [rsp+78h] [rbp-88h]
  int v60; // [rsp+7Ch] [rbp-84h]
  __int64 v61; // [rsp+80h] [rbp-80h]
  __int64 v62; // [rsp+88h] [rbp-78h]
  const wchar_t *v63; // [rsp+90h] [rbp-70h]
  int v64; // [rsp+98h] [rbp-68h]
  int v65; // [rsp+9Ch] [rbp-64h]
  __int64 v66; // [rsp+A0h] [rbp-60h]
  __int64 v67; // [rsp+A8h] [rbp-58h]
  char *v68; // [rsp+B0h] [rbp-50h]
  int v69; // [rsp+B8h] [rbp-48h]
  int v70; // [rsp+BCh] [rbp-44h]
  __int64 v71; // [rsp+C0h] [rbp-40h]
  __int64 v72; // [rsp+C8h] [rbp-38h]
  const wchar_t *v73; // [rsp+D0h] [rbp-30h]
  int v74; // [rsp+D8h] [rbp-28h]
  int v75; // [rsp+DCh] [rbp-24h]
  __int64 v76; // [rsp+E0h] [rbp-20h]
  __int64 v77; // [rsp+E8h] [rbp-18h]
  const wchar_t *v78; // [rsp+F0h] [rbp-10h]
  int v79; // [rsp+F8h] [rbp-8h]
  int v80; // [rsp+FCh] [rbp-4h]
  char *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  const wchar_t *v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+12Ch] [rbp+2Ch]
  char *v89; // [rsp+130h] [rbp+30h]
  int v90; // [rsp+138h] [rbp+38h]
  int v91; // [rsp+13Ch] [rbp+3Ch]
  __int64 v92; // [rsp+140h] [rbp+40h]
  __int64 v93; // [rsp+148h] [rbp+48h]
  __int64 v94; // [rsp+150h] [rbp+50h]
  __int64 v95; // [rsp+158h] [rbp+58h]
  const wchar_t *v96; // [rsp+160h] [rbp+60h]
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
    v27 = &word_1800138F6;
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
    while ( *(_WORD *)&v31[2 * v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = byte_1800138F4;
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
    v34 = &word_1800138F6;
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
    while ( *(_WORD *)&v37[2 * v38] );
    v39 = 2 * v38 + 2;
  }
  else
  {
    v37 = byte_1800138F4;
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
    v40 = &word_1800138F6;
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
    v43 = &word_1800138F6;
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
    while ( *(_WORD *)&v46[2 * v47] );
    v30 = 2 * v47 + 2;
  }
  else
  {
    v46 = byte_1800138F4;
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
    v48 = &word_1800138F6;
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
    v51 = &word_1800138F6;
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
0x1800012bc  push    rbp
0x1800012be  push    rbx
0x1800012bf  push    rsi
0x1800012c0  push    rdi
0x1800012c1  push    r15
0x1800012c3  lea     rbp, [rsp-80h]
0x1800012c8  sub     rsp, 180h
0x1800012cf  mov     rax, cs:__security_cookie
0x1800012d6  xor     rax, rsp
0x1800012d9  mov     [rbp+0A0h+var_30], rax
0x1800012dd  mov     rax, [rbp+0A0h+arg_A8]
0x1800012e4  lea     rsi, word_1800138F6
0x1800012eb  mov     r11, rdx
0x1800012ee  mov     r10, rcx
0x1800012f1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800012f5  xor     edi, edi
0x1800012f7  mov     rbx, r8
0x1800012fa  mov     r8d, 1
0x180001300  mov     rcx, [rax]
0x180001303  test    rcx, rcx
0x180001306  jz      short loc_180001318
0x180001308  mov     rax, rdx
0x18000130b  inc     rax
0x18000130e  cmp     [rcx+rax], dil
0x180001312  jnz     short loc_18000130B
0x180001314  inc     eax
0x180001316  jmp     short loc_18000131E
0x180001318  mov     rcx, rsi
0x18000131b  mov     eax, r8d
0x18000131e  mov     [rbp+0A0h+var_38], eax
0x180001321  mov     r9d, 2
0x180001327  mov     rax, [rbp+0A0h+arg_A0]
0x18000132e  mov     [rbp+0A0h+var_50], rax
0x180001332  mov     rax, [rbp+0A0h+arg_98]
0x180001339  mov     [rbp+0A0h+var_60], rax
0x18000133d  mov     rax, [rbp+0A0h+arg_90]
0x180001344  mov     [rbp+0A0h+var_40], rcx
0x180001348  mov     [rbp+0A0h+var_34], edi
0x18000134b  mov     [rbp+0A0h+var_48], 4
0x180001353  mov     rcx, [rax]
0x180001356  mov     [rbp+0A0h+var_58], 4
0x18000135e  test    rcx, rcx
0x180001361  jz      short loc_180001378
0x180001363  mov     rax, rdx
0x180001366  inc     rax
0x180001369  cmp     [rcx+rax*2], di
0x18000136d  jnz     short loc_180001366
0x18000136f  lea     eax, ds:2[rax*2]
0x180001376  jmp     short loc_180001382
0x180001378  lea     rcx, byte_1800138F4
0x18000137f  mov     eax, r9d
0x180001382  mov     [rbp+0A0h+var_68], eax
0x180001385  mov     rax, [rbp+0A0h+arg_88]
0x18000138c  mov     [rbp+0A0h+var_70], rcx
0x180001390  mov     [rbp+0A0h+var_64], edi
0x180001393  mov     rcx, [rax]
0x180001396  test    rcx, rcx
0x180001399  jz      short loc_1800013AB
0x18000139b  mov     rax, rdx
0x18000139e  inc     rax
0x1800013a1  cmp     [rcx+rax], dil
0x1800013a5  jnz     short loc_18000139E
0x1800013a7  inc     eax
0x1800013a9  jmp     short loc_1800013B1
0x1800013ab  mov     rcx, rsi
0x1800013ae  mov     eax, r8d
0x1800013b1  mov     [rbp+0A0h+var_78], eax
0x1800013b4  mov     rax, [rbp+0A0h+arg_80]
0x1800013bb  mov     [rbp+0A0h+var_90], rax
0x1800013bf  mov     rax, [rbp+0A0h+arg_78]
0x1800013c6  mov     [rbp+0A0h+var_80], rcx
0x1800013ca  mov     [rbp+0A0h+var_74], edi
0x1800013cd  mov     [rbp+0A0h+var_88], 4
0x1800013d5  mov     rcx, [rax]
0x1800013d8  test    rcx, rcx
0x1800013db  jz      short loc_1800013F2
0x1800013dd  mov     rax, rdx
0x1800013e0  inc     rax
0x1800013e3  cmp     [rcx+rax*2], di
0x1800013e7  jnz     short loc_1800013E0
0x1800013e9  lea     eax, ds:2[rax*2]
0x1800013f0  jmp     short loc_1800013FC
0x1800013f2  lea     rcx, byte_1800138F4
0x1800013f9  mov     eax, r9d
0x1800013fc  mov     [rbp+0A0h+var_98], eax
0x1800013ff  mov     rax, [rbp+0A0h+arg_70]
0x180001406  mov     [rbp+0A0h+var_A0], rcx
0x18000140a  mov     [rbp+0A0h+var_94], edi
0x18000140d  mov     rcx, [rax]
0x180001410  test    rcx, rcx
0x180001413  jz      short loc_180001425
0x180001415  mov     rax, rdx
0x180001418  inc     rax
0x18000141b  cmp     [rcx+rax], dil
0x18000141f  jnz     short loc_180001418
0x180001421  inc     eax
0x180001423  jmp     short loc_18000142B
0x180001425  mov     rcx, rsi
0x180001428  mov     eax, r8d
0x18000142b  mov     [rbp+0A0h+var_A8], eax
0x18000142e  mov     rax, [rbp+0A0h+arg_68]
0x180001435  mov     [rbp+0A0h+var_C0], rax
0x180001439  mov     rax, [rbp+0A0h+arg_60]
0x180001440  mov     [rbp+0A0h+var_B0], rcx
0x180001444  mov     [rbp+0A0h+var_A4], edi
0x180001447  mov     [rbp+0A0h+var_B8], 4
0x18000144f  mov     rcx, [rax]
0x180001452  test    rcx, rcx
0x180001455  jz      short loc_180001467
0x180001457  mov     rax, rdx
0x18000145a  inc     rax
0x18000145d  cmp     [rcx+rax], dil
0x180001461  jnz     short loc_18000145A
0x180001463  inc     eax
0x180001465  jmp     short loc_18000146D
0x180001467  mov     rcx, rsi
0x18000146a  mov     eax, r8d
0x18000146d  mov     [rbp+0A0h+var_C8], eax
0x180001470  mov     rax, [rbp+0A0h+arg_58]
0x180001477  mov     [rbp+0A0h+var_E0], rax
0x18000147b  mov     rax, [rbp+0A0h+arg_50]
0x180001482  mov     [rbp+0A0h+var_D0], rcx
0x180001486  mov     [rbp+0A0h+var_C4], edi
0x180001489  mov     [rbp+0A0h+var_D8], 4
0x180001491  mov     rcx, [rax]
0x180001494  test    rcx, rcx
0x180001497  jz      short loc_1800014AF
0x180001499  mov     rax, rdx
0x18000149c  inc     rax
0x18000149f  cmp     [rcx+rax*2], di
0x1800014a3  jnz     short loc_18000149C
0x1800014a5  lea     r9d, ds:2[rax*2]
0x1800014ad  jmp     short loc_1800014B6
0x1800014af  lea     rcx, byte_1800138F4
0x1800014b6  mov     rax, [rbp+0A0h+arg_48]
0x1800014bd  mov     [rbp+0A0h+var_100], rax
0x1800014c1  mov     rax, [rbp+0A0h+arg_40]
0x1800014c8  mov     [rbp+0A0h+var_F0], rcx
0x1800014cc  mov     [rbp+0A0h+var_E8], r9d
0x1800014d0  mov     [rbp+0A0h+var_E4], edi
0x1800014d3  mov     rcx, [rax]
0x1800014d6  mov     [rbp+0A0h+var_F8], 4
0x1800014de  test    rcx, rcx
0x1800014e1  jz      short loc_1800014F3
0x1800014e3  mov     rax, rdx
0x1800014e6  inc     rax
0x1800014e9  cmp     [rcx+rax], dil
0x1800014ed  jnz     short loc_1800014E6
0x1800014ef  inc     eax
0x1800014f1  jmp     short loc_1800014F9
0x1800014f3  mov     rcx, rsi
0x1800014f6  mov     eax, r8d
0x1800014f9  mov     [rbp+0A0h+var_108], eax
0x1800014fc  mov     rax, [rbp+0A0h+arg_38]
0x180001503  mov     [rbp+0A0h+var_120], rax
0x180001507  mov     rax, [rbp+0A0h+arg_30]
0x18000150e  mov     [rbp+0A0h+var_110], rcx
0x180001512  mov     [rbp+0A0h+var_104], edi
0x180001515  mov     [rbp+0A0h+var_118], 4
0x18000151d  mov     rcx, [rax]
0x180001520  test    rcx, rcx
0x180001523  jz      short loc_180001534
0x180001525  inc     rdx
0x180001528  cmp     [rcx+rdx], dil
0x18000152c  jnz     short loc_180001525
0x18000152e  lea     r8d, [rdx+1]
0x180001532  jmp     short loc_180001537
0x180001534  mov     rcx, rsi
0x180001537  mov     rax, [rbp+0A0h+arg_28]
0x18000153e  xor     r9d, r9d
0x180001541  mov     [rsp+1A0h+var_140], rax
0x180001546  mov     rdx, r11
0x180001549  mov     rax, [rbp+0A0h+arg_20]
0x180001550  mov     [rsp+1A0h+var_150], rax
0x180001555  lea     rax, [rsp+1A0h+var_170]
0x18000155a  mov     [rsp+1A0h+var_130], rcx
0x18000155f  mov     rcx, r10
0x180001562  mov     [rsp+1A0h+var_128], r8d
0x180001567  mov     r8, rbx
0x18000156a  mov     [rsp+1A0h+var_178], rax
0x18000156f  mov     [rsp+1A0h+var_180], 14h
0x180001577  mov     [rsp+1A0h+var_124], edi
0x18000157b  mov     [rsp+1A0h+var_138], 4
0x180001584  mov     [rsp+1A0h+var_148], 8
0x18000158d  call    _tlgWriteTransfer_EventWriteTransfer
0x180001592  mov     rcx, [rbp+0A0h+var_30]
0x180001596  xor     rcx, rsp; StackCookie
0x180001599  call    __security_check_cookie
0x18000159e  add     rsp, 180h
0x1800015a5  pop     r15
0x1800015a7  pop     rdi
0x1800015a8  pop     rsi
0x1800015a9  pop     rbx
0x1800015aa  pop     rbp
0x1800015ab  retn
```
