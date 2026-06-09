# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1400014c4`
- end: `0x1400017b3`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `751`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e1fc`

## callees

- `0x1400014c4`
- `0x140001898`
- `0x140008c80`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
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
  int v25; // r8d
  const unsigned __int16 *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int v29; // r9d
  const size_t *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  const size_t *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  const size_t *v45; // rcx
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
  const size_t *v67; // [rsp+B0h] [rbp-50h]
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
  const size_t *v80; // [rsp+100h] [rbp+0h]
  int v81; // [rsp+108h] [rbp+8h]
  int v82; // [rsp+10Ch] [rbp+Ch]
  __int64 v83; // [rsp+110h] [rbp+10h]
  __int64 v84; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  const size_t *v88; // [rsp+130h] [rbp+30h]
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
    v26 = &dword_1400135E4;
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
    while ( *((_WORD *)v30 + v31) );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &Format;
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
    v33 = &dword_1400135E4;
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
    while ( *((_WORD *)v36 + v37) );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v36 = &Format;
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
    v39 = &dword_1400135E4;
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
    v42 = &dword_1400135E4;
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
    while ( *((_WORD *)v45 + v46) );
    v29 = 2 * v46 + 2;
  }
  else
  {
    v45 = &Format;
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
    v47 = &dword_1400135E4;
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
    v50 = &dword_1400135E4;
  }
  v55 = a6;
  v53 = a5;
  v57 = v50;
  v58 = v25;
  v59 = 0;
  v56 = 4;
  v54 = 8;
  return tlgWriteTransfer_EtwEventWriteTransfer(a1, a2, 0, 0, 20, (__int64)v52);
}

```

## disassembly

```asm
0x1400014c4  mov     [rsp-8+arg_10], rbx
0x1400014c9  push    rbp
0x1400014ca  push    rdi
0x1400014cb  push    r14
0x1400014cd  lea     rbp, [rsp-80h]
0x1400014d2  sub     rsp, 180h
0x1400014d9  mov     rax, cs:__security_cookie
0x1400014e0  xor     rax, rsp
0x1400014e3  mov     [rbp+90h+var_20], rax
0x1400014e7  mov     rax, [rbp+90h+arg_A8]
0x1400014ee  lea     rdi, dword_1400135E4
0x1400014f5  mov     r11, rdx
0x1400014f8  mov     r10, rcx
0x1400014fb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400014ff  xor     ebx, ebx
0x140001501  mov     r8d, 1
0x140001507  mov     rcx, [rax]
0x14000150a  test    rcx, rcx
0x14000150d  jz      short loc_14000151E
0x14000150f  mov     rax, rdx
0x140001512  inc     rax
0x140001515  cmp     [rcx+rax], bl
0x140001518  jnz     short loc_140001512
0x14000151a  inc     eax
0x14000151c  jmp     short loc_140001524
0x14000151e  mov     rcx, rdi
0x140001521  mov     eax, r8d
0x140001524  mov     [rbp+90h+var_28], eax
0x140001527  mov     r9d, 2
0x14000152d  mov     rax, [rbp+90h+arg_A0]
0x140001534  mov     [rbp+90h+var_40], rax
0x140001538  mov     rax, [rbp+90h+arg_98]
0x14000153f  mov     [rbp+90h+var_50], rax
0x140001543  mov     rax, [rbp+90h+arg_90]
0x14000154a  mov     [rbp+90h+var_30], rcx
0x14000154e  mov     [rbp+90h+var_24], ebx
0x140001551  mov     [rbp+90h+var_38], 4
0x140001559  mov     rcx, [rax]
0x14000155c  mov     [rbp+90h+var_48], 4
0x140001564  test    rcx, rcx
0x140001567  jz      short loc_14000157E
0x140001569  mov     rax, rdx
0x14000156c  inc     rax
0x14000156f  cmp     [rcx+rax*2], bx
0x140001573  jnz     short loc_14000156C
0x140001575  lea     eax, ds:2[rax*2]
0x14000157c  jmp     short loc_140001588
0x14000157e  lea     rcx, Format
0x140001585  mov     eax, r9d
0x140001588  mov     [rbp+90h+var_58], eax
0x14000158b  mov     rax, [rbp+90h+arg_88]
0x140001592  mov     [rbp+90h+var_60], rcx
0x140001596  mov     [rbp+90h+var_54], ebx
0x140001599  mov     rcx, [rax]
0x14000159c  test    rcx, rcx
0x14000159f  jz      short loc_1400015B0
0x1400015a1  mov     rax, rdx
0x1400015a4  inc     rax
0x1400015a7  cmp     [rcx+rax], bl
0x1400015aa  jnz     short loc_1400015A4
0x1400015ac  inc     eax
0x1400015ae  jmp     short loc_1400015B6
0x1400015b0  mov     rcx, rdi
0x1400015b3  mov     eax, r8d
0x1400015b6  mov     [rbp+90h+var_68], eax
0x1400015b9  mov     rax, [rbp+90h+arg_80]
0x1400015c0  mov     [rbp+90h+var_80], rax
0x1400015c4  mov     rax, [rbp+90h+arg_78]
0x1400015cb  mov     [rbp+90h+var_70], rcx
0x1400015cf  mov     [rbp+90h+var_64], ebx
0x1400015d2  mov     [rbp+90h+var_78], 4
0x1400015da  mov     rcx, [rax]
0x1400015dd  test    rcx, rcx
0x1400015e0  jz      short loc_1400015F7
0x1400015e2  mov     rax, rdx
0x1400015e5  inc     rax
0x1400015e8  cmp     [rcx+rax*2], bx
0x1400015ec  jnz     short loc_1400015E5
0x1400015ee  lea     eax, ds:2[rax*2]
0x1400015f5  jmp     short loc_140001601
0x1400015f7  lea     rcx, Format
0x1400015fe  mov     eax, r9d
0x140001601  mov     [rbp+90h+var_88], eax
0x140001604  mov     rax, [rbp+90h+arg_70]
0x14000160b  mov     [rbp+90h+var_90], rcx
0x14000160f  mov     [rbp+90h+var_84], ebx
0x140001612  mov     rcx, [rax]
0x140001615  test    rcx, rcx
0x140001618  jz      short loc_140001629
0x14000161a  mov     rax, rdx
0x14000161d  inc     rax
0x140001620  cmp     [rcx+rax], bl
0x140001623  jnz     short loc_14000161D
0x140001625  inc     eax
0x140001627  jmp     short loc_14000162F
0x140001629  mov     rcx, rdi
0x14000162c  mov     eax, r8d
0x14000162f  mov     [rbp+90h+var_98], eax
0x140001632  mov     rax, [rbp+90h+arg_68]
0x140001639  mov     [rbp+90h+var_B0], rax
0x14000163d  mov     rax, [rbp+90h+arg_60]
0x140001644  mov     [rbp+90h+var_A0], rcx
0x140001648  mov     [rbp+90h+var_94], ebx
0x14000164b  mov     [rbp+90h+var_A8], 4
0x140001653  mov     rcx, [rax]
0x140001656  test    rcx, rcx
0x140001659  jz      short loc_14000166A
0x14000165b  mov     rax, rdx
0x14000165e  inc     rax
0x140001661  cmp     [rcx+rax], bl
0x140001664  jnz     short loc_14000165E
0x140001666  inc     eax
0x140001668  jmp     short loc_140001670
0x14000166a  mov     rcx, rdi
0x14000166d  mov     eax, r8d
0x140001670  mov     [rbp+90h+var_B8], eax
0x140001673  mov     rax, [rbp+90h+arg_58]
0x14000167a  mov     [rbp+90h+var_D0], rax
0x14000167e  mov     rax, [rbp+90h+arg_50]
0x140001685  mov     [rbp+90h+var_C0], rcx
0x140001689  mov     [rbp+90h+var_B4], ebx
0x14000168c  mov     [rbp+90h+var_C8], 4
0x140001694  mov     rcx, [rax]
0x140001697  test    rcx, rcx
0x14000169a  jz      short loc_1400016B2
0x14000169c  mov     rax, rdx
0x14000169f  inc     rax
0x1400016a2  cmp     [rcx+rax*2], bx
0x1400016a6  jnz     short loc_14000169F
0x1400016a8  lea     r9d, ds:2[rax*2]
0x1400016b0  jmp     short loc_1400016B9
0x1400016b2  lea     rcx, Format
0x1400016b9  mov     rax, [rbp+90h+arg_48]
0x1400016c0  mov     [rbp+90h+var_F0], rax
0x1400016c4  mov     rax, [rbp+90h+arg_40]
0x1400016cb  mov     [rbp+90h+var_E0], rcx
0x1400016cf  mov     [rbp+90h+var_D8], r9d
0x1400016d3  mov     [rbp+90h+var_D4], ebx
0x1400016d6  mov     rcx, [rax]
0x1400016d9  mov     [rbp+90h+var_E8], 4
0x1400016e1  test    rcx, rcx
0x1400016e4  jz      short loc_1400016F5
0x1400016e6  mov     rax, rdx
0x1400016e9  inc     rax
0x1400016ec  cmp     [rcx+rax], bl
0x1400016ef  jnz     short loc_1400016E9
0x1400016f1  inc     eax
0x1400016f3  jmp     short loc_1400016FB
0x1400016f5  mov     rcx, rdi
0x1400016f8  mov     eax, r8d
0x1400016fb  mov     [rbp+90h+var_F8], eax
0x1400016fe  mov     rax, [rbp+90h+arg_38]
0x140001705  mov     [rbp+90h+var_110], rax
0x140001709  mov     rax, [rbp+90h+arg_30]
0x140001710  mov     [rbp+90h+var_100], rcx
0x140001714  mov     [rbp+90h+var_F4], ebx
0x140001717  mov     [rbp+90h+var_108], 4
0x14000171f  mov     rcx, [rax]
0x140001722  test    rcx, rcx
0x140001725  jz      short loc_140001735
0x140001727  inc     rdx
0x14000172a  cmp     [rcx+rdx], bl
0x14000172d  jnz     short loc_140001727
0x14000172f  lea     r8d, [rdx+1]
0x140001733  jmp     short loc_140001738
0x140001735  mov     rcx, rdi
0x140001738  mov     rax, [rbp+90h+arg_28]
0x14000173f  xor     r9d, r9d
0x140001742  mov     [rsp+190h+var_130], rax
0x140001747  mov     rdx, r11
0x14000174a  mov     rax, [rbp+90h+arg_20]
0x140001751  mov     [rsp+190h+var_140], rax
0x140001756  lea     rax, [rsp+190h+var_160]
0x14000175b  mov     [rsp+190h+var_120], rcx
0x140001760  mov     rcx, r10
0x140001763  mov     [rsp+190h+var_118], r8d
0x140001768  xor     r8d, r8d
0x14000176b  mov     [rsp+190h+var_168], rax
0x140001770  mov     [rsp+190h+var_170], 14h
0x140001778  mov     [rsp+190h+var_114], ebx
0x14000177c  mov     [rsp+190h+var_128], 4
0x140001785  mov     [rsp+190h+var_138], 8
0x14000178e  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x140001793  mov     rcx, [rbp+90h+var_20]
0x140001797  xor     rcx, rsp; StackCookie
0x14000179a  call    __security_check_cookie
0x14000179f  mov     rbx, [rsp+190h+arg_10]
0x1400017a7  add     rsp, 180h
0x1400017ae  pop     r14
0x1400017b0  pop     rdi
0x1400017b1  pop     rbp
0x1400017b2  retn
```
