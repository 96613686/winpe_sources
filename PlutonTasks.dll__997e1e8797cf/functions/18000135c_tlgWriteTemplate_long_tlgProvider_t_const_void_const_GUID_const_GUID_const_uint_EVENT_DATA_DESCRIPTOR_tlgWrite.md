# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x18000135c`
- end: `0x18000164c`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800071e8`

## callees

- `0x18000135c`
- `0x1800017d8`
- `0x180001e00`

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
        int **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        int **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        int **a19,
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
  int *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  int *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  int *v46; // rcx
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
  int *v68; // [rsp+B0h] [rbp-50h]
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
  int *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+12Ch] [rbp+2Ch]
  int *v89; // [rsp+130h] [rbp+30h]
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
    v27 = &byte_18000B8A0;
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
    v31 = &dword_18000B8A4;
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
    v34 = &byte_18000B8A0;
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
    v37 = &dword_18000B8A4;
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
    v40 = &byte_18000B8A0;
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
    v43 = &byte_18000B8A0;
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
    v46 = &dword_18000B8A4;
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
    v48 = &byte_18000B8A0;
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
    v51 = &byte_18000B8A0;
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
0x18000135c  push    rbp
0x18000135e  push    rbx
0x18000135f  push    rsi
0x180001360  push    rdi
0x180001361  push    r15
0x180001363  lea     rbp, [rsp-80h]
0x180001368  sub     rsp, 180h
0x18000136f  mov     rax, cs:__security_cookie
0x180001376  xor     rax, rsp
0x180001379  mov     [rbp+0A0h+var_30], rax
0x18000137d  mov     rax, [rbp+0A0h+arg_A8]
0x180001384  lea     rsi, byte_18000B8A0
0x18000138b  mov     r11, rdx
0x18000138e  mov     r10, rcx
0x180001391  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001395  xor     edi, edi
0x180001397  mov     rbx, r8
0x18000139a  mov     r8d, 1
0x1800013a0  mov     rcx, [rax]
0x1800013a3  test    rcx, rcx
0x1800013a6  jz      short loc_1800013B8
0x1800013a8  mov     rax, rdx
0x1800013ab  inc     rax
0x1800013ae  cmp     [rcx+rax], dil
0x1800013b2  jnz     short loc_1800013AB
0x1800013b4  inc     eax
0x1800013b6  jmp     short loc_1800013BE
0x1800013b8  mov     rcx, rsi
0x1800013bb  mov     eax, r8d
0x1800013be  mov     [rbp+0A0h+var_38], eax
0x1800013c1  mov     r9d, 2
0x1800013c7  mov     rax, [rbp+0A0h+arg_A0]
0x1800013ce  mov     [rbp+0A0h+var_50], rax
0x1800013d2  mov     rax, [rbp+0A0h+arg_98]
0x1800013d9  mov     [rbp+0A0h+var_60], rax
0x1800013dd  mov     rax, [rbp+0A0h+arg_90]
0x1800013e4  mov     [rbp+0A0h+var_40], rcx
0x1800013e8  mov     [rbp+0A0h+var_34], edi
0x1800013eb  mov     [rbp+0A0h+var_48], 4
0x1800013f3  mov     rcx, [rax]
0x1800013f6  mov     [rbp+0A0h+var_58], 4
0x1800013fe  test    rcx, rcx
0x180001401  jz      short loc_180001418
0x180001403  mov     rax, rdx
0x180001406  inc     rax
0x180001409  cmp     [rcx+rax*2], di
0x18000140d  jnz     short loc_180001406
0x18000140f  lea     eax, ds:2[rax*2]
0x180001416  jmp     short loc_180001422
0x180001418  lea     rcx, dword_18000B8A4
0x18000141f  mov     eax, r9d
0x180001422  mov     [rbp+0A0h+var_68], eax
0x180001425  mov     rax, [rbp+0A0h+arg_88]
0x18000142c  mov     [rbp+0A0h+var_70], rcx
0x180001430  mov     [rbp+0A0h+var_64], edi
0x180001433  mov     rcx, [rax]
0x180001436  test    rcx, rcx
0x180001439  jz      short loc_18000144B
0x18000143b  mov     rax, rdx
0x18000143e  inc     rax
0x180001441  cmp     [rcx+rax], dil
0x180001445  jnz     short loc_18000143E
0x180001447  inc     eax
0x180001449  jmp     short loc_180001451
0x18000144b  mov     rcx, rsi
0x18000144e  mov     eax, r8d
0x180001451  mov     [rbp+0A0h+var_78], eax
0x180001454  mov     rax, [rbp+0A0h+arg_80]
0x18000145b  mov     [rbp+0A0h+var_90], rax
0x18000145f  mov     rax, [rbp+0A0h+arg_78]
0x180001466  mov     [rbp+0A0h+var_80], rcx
0x18000146a  mov     [rbp+0A0h+var_74], edi
0x18000146d  mov     [rbp+0A0h+var_88], 4
0x180001475  mov     rcx, [rax]
0x180001478  test    rcx, rcx
0x18000147b  jz      short loc_180001492
0x18000147d  mov     rax, rdx
0x180001480  inc     rax
0x180001483  cmp     [rcx+rax*2], di
0x180001487  jnz     short loc_180001480
0x180001489  lea     eax, ds:2[rax*2]
0x180001490  jmp     short loc_18000149C
0x180001492  lea     rcx, dword_18000B8A4
0x180001499  mov     eax, r9d
0x18000149c  mov     [rbp+0A0h+var_98], eax
0x18000149f  mov     rax, [rbp+0A0h+arg_70]
0x1800014a6  mov     [rbp+0A0h+var_A0], rcx
0x1800014aa  mov     [rbp+0A0h+var_94], edi
0x1800014ad  mov     rcx, [rax]
0x1800014b0  test    rcx, rcx
0x1800014b3  jz      short loc_1800014C5
0x1800014b5  mov     rax, rdx
0x1800014b8  inc     rax
0x1800014bb  cmp     [rcx+rax], dil
0x1800014bf  jnz     short loc_1800014B8
0x1800014c1  inc     eax
0x1800014c3  jmp     short loc_1800014CB
0x1800014c5  mov     rcx, rsi
0x1800014c8  mov     eax, r8d
0x1800014cb  mov     [rbp+0A0h+var_A8], eax
0x1800014ce  mov     rax, [rbp+0A0h+arg_68]
0x1800014d5  mov     [rbp+0A0h+var_C0], rax
0x1800014d9  mov     rax, [rbp+0A0h+arg_60]
0x1800014e0  mov     [rbp+0A0h+var_B0], rcx
0x1800014e4  mov     [rbp+0A0h+var_A4], edi
0x1800014e7  mov     [rbp+0A0h+var_B8], 4
0x1800014ef  mov     rcx, [rax]
0x1800014f2  test    rcx, rcx
0x1800014f5  jz      short loc_180001507
0x1800014f7  mov     rax, rdx
0x1800014fa  inc     rax
0x1800014fd  cmp     [rcx+rax], dil
0x180001501  jnz     short loc_1800014FA
0x180001503  inc     eax
0x180001505  jmp     short loc_18000150D
0x180001507  mov     rcx, rsi
0x18000150a  mov     eax, r8d
0x18000150d  mov     [rbp+0A0h+var_C8], eax
0x180001510  mov     rax, [rbp+0A0h+arg_58]
0x180001517  mov     [rbp+0A0h+var_E0], rax
0x18000151b  mov     rax, [rbp+0A0h+arg_50]
0x180001522  mov     [rbp+0A0h+var_D0], rcx
0x180001526  mov     [rbp+0A0h+var_C4], edi
0x180001529  mov     [rbp+0A0h+var_D8], 4
0x180001531  mov     rcx, [rax]
0x180001534  test    rcx, rcx
0x180001537  jz      short loc_18000154F
0x180001539  mov     rax, rdx
0x18000153c  inc     rax
0x18000153f  cmp     [rcx+rax*2], di
0x180001543  jnz     short loc_18000153C
0x180001545  lea     r9d, ds:2[rax*2]
0x18000154d  jmp     short loc_180001556
0x18000154f  lea     rcx, dword_18000B8A4
0x180001556  mov     rax, [rbp+0A0h+arg_48]
0x18000155d  mov     [rbp+0A0h+var_100], rax
0x180001561  mov     rax, [rbp+0A0h+arg_40]
0x180001568  mov     [rbp+0A0h+var_F0], rcx
0x18000156c  mov     [rbp+0A0h+var_E8], r9d
0x180001570  mov     [rbp+0A0h+var_E4], edi
0x180001573  mov     rcx, [rax]
0x180001576  mov     [rbp+0A0h+var_F8], 4
0x18000157e  test    rcx, rcx
0x180001581  jz      short loc_180001593
0x180001583  mov     rax, rdx
0x180001586  inc     rax
0x180001589  cmp     [rcx+rax], dil
0x18000158d  jnz     short loc_180001586
0x18000158f  inc     eax
0x180001591  jmp     short loc_180001599
0x180001593  mov     rcx, rsi
0x180001596  mov     eax, r8d
0x180001599  mov     [rbp+0A0h+var_108], eax
0x18000159c  mov     rax, [rbp+0A0h+arg_38]
0x1800015a3  mov     [rbp+0A0h+var_120], rax
0x1800015a7  mov     rax, [rbp+0A0h+arg_30]
0x1800015ae  mov     [rbp+0A0h+var_110], rcx
0x1800015b2  mov     [rbp+0A0h+var_104], edi
0x1800015b5  mov     [rbp+0A0h+var_118], 4
0x1800015bd  mov     rcx, [rax]
0x1800015c0  test    rcx, rcx
0x1800015c3  jz      short loc_1800015D4
0x1800015c5  inc     rdx
0x1800015c8  cmp     [rcx+rdx], dil
0x1800015cc  jnz     short loc_1800015C5
0x1800015ce  lea     r8d, [rdx+1]
0x1800015d2  jmp     short loc_1800015D7
0x1800015d4  mov     rcx, rsi
0x1800015d7  mov     rax, [rbp+0A0h+arg_28]
0x1800015de  xor     r9d, r9d
0x1800015e1  mov     [rsp+1A0h+var_140], rax
0x1800015e6  mov     rdx, r11
0x1800015e9  mov     rax, [rbp+0A0h+arg_20]
0x1800015f0  mov     [rsp+1A0h+var_150], rax
0x1800015f5  lea     rax, [rsp+1A0h+var_170]
0x1800015fa  mov     [rsp+1A0h+var_130], rcx
0x1800015ff  mov     rcx, r10
0x180001602  mov     [rsp+1A0h+var_128], r8d
0x180001607  mov     r8, rbx
0x18000160a  mov     [rsp+1A0h+var_178], rax
0x18000160f  mov     [rsp+1A0h+var_180], 14h
0x180001617  mov     [rsp+1A0h+var_124], edi
0x18000161b  mov     [rsp+1A0h+var_138], 4
0x180001624  mov     [rsp+1A0h+var_148], 8
0x18000162d  call    _tlgWriteTransfer_EventWriteTransfer
0x180001632  mov     rcx, [rbp+0A0h+var_30]
0x180001636  xor     rcx, rsp; StackCookie
0x180001639  call    __security_check_cookie
0x18000163e  add     rsp, 180h
0x180001645  pop     r15
0x180001647  pop     rdi
0x180001648  pop     rsi
0x180001649  pop     rbx
0x18000164a  pop     rbp
0x18000164b  retn
```
