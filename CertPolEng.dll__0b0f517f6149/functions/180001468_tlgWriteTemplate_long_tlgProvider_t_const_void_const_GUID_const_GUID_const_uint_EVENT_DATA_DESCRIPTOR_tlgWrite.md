# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001468`
- end: `0x180001757`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `751`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, __int64 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64 **, __int64, const unsigned __int16 **, __int64 **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001799c`

## callees

- `0x180001468`
- `0x180007e00`
- `0x18001a380`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9,
        __int64 a10,
        __int64 **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        __int64 **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        __int64 **a19,
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
  __int64 *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  __int64 *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  __int64 *v45; // rcx
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
  __int64 *v67; // [rsp+B0h] [rbp-50h]
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
  __int64 *v80; // [rsp+100h] [rbp+0h]
  int v81; // [rsp+108h] [rbp+8h]
  int v82; // [rsp+10Ch] [rbp+Ch]
  __int64 v83; // [rsp+110h] [rbp+10h]
  __int64 v84; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  __int64 *v88; // [rsp+130h] [rbp+30h]
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
    v26 = &dword_18001E424;
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
    v30 = &qword_180020CC0;
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
    v33 = &dword_18001E424;
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
    v36 = &qword_180020CC0;
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
    v39 = &dword_18001E424;
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
    v42 = &dword_18001E424;
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
    v45 = &qword_180020CC0;
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
    v47 = &dword_18001E424;
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
    v50 = &dword_18001E424;
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
0x180001468  mov     [rsp-8+arg_10], rbx
0x18000146d  push    rbp
0x18000146e  push    rdi
0x18000146f  push    r14
0x180001471  lea     rbp, [rsp-80h]
0x180001476  sub     rsp, 180h
0x18000147d  mov     rax, cs:__security_cookie
0x180001484  xor     rax, rsp
0x180001487  mov     [rbp+90h+var_20], rax
0x18000148b  mov     rax, [rbp+90h+arg_A8]
0x180001492  lea     rdi, dword_18001E424
0x180001499  mov     r11, rdx
0x18000149c  mov     r10, rcx
0x18000149f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800014a3  xor     ebx, ebx
0x1800014a5  mov     r8d, 1
0x1800014ab  mov     rcx, [rax]
0x1800014ae  test    rcx, rcx
0x1800014b1  jz      short loc_1800014C2
0x1800014b3  mov     rax, rdx
0x1800014b6  inc     rax
0x1800014b9  cmp     [rcx+rax], bl
0x1800014bc  jnz     short loc_1800014B6
0x1800014be  inc     eax
0x1800014c0  jmp     short loc_1800014C8
0x1800014c2  mov     rcx, rdi
0x1800014c5  mov     eax, r8d
0x1800014c8  mov     [rbp+90h+var_28], eax
0x1800014cb  mov     r9d, 2
0x1800014d1  mov     rax, [rbp+90h+arg_A0]
0x1800014d8  mov     [rbp+90h+var_40], rax
0x1800014dc  mov     rax, [rbp+90h+arg_98]
0x1800014e3  mov     [rbp+90h+var_50], rax
0x1800014e7  mov     rax, [rbp+90h+arg_90]
0x1800014ee  mov     [rbp+90h+var_30], rcx
0x1800014f2  mov     [rbp+90h+var_24], ebx
0x1800014f5  mov     [rbp+90h+var_38], 4
0x1800014fd  mov     rcx, [rax]
0x180001500  mov     [rbp+90h+var_48], 4
0x180001508  test    rcx, rcx
0x18000150b  jz      short loc_180001522
0x18000150d  mov     rax, rdx
0x180001510  inc     rax
0x180001513  cmp     [rcx+rax*2], bx
0x180001517  jnz     short loc_180001510
0x180001519  lea     eax, ds:2[rax*2]
0x180001520  jmp     short loc_18000152C
0x180001522  lea     rcx, qword_180020CC0
0x180001529  mov     eax, r9d
0x18000152c  mov     [rbp+90h+var_58], eax
0x18000152f  mov     rax, [rbp+90h+arg_88]
0x180001536  mov     [rbp+90h+var_60], rcx
0x18000153a  mov     [rbp+90h+var_54], ebx
0x18000153d  mov     rcx, [rax]
0x180001540  test    rcx, rcx
0x180001543  jz      short loc_180001554
0x180001545  mov     rax, rdx
0x180001548  inc     rax
0x18000154b  cmp     [rcx+rax], bl
0x18000154e  jnz     short loc_180001548
0x180001550  inc     eax
0x180001552  jmp     short loc_18000155A
0x180001554  mov     rcx, rdi
0x180001557  mov     eax, r8d
0x18000155a  mov     [rbp+90h+var_68], eax
0x18000155d  mov     rax, [rbp+90h+arg_80]
0x180001564  mov     [rbp+90h+var_80], rax
0x180001568  mov     rax, [rbp+90h+arg_78]
0x18000156f  mov     [rbp+90h+var_70], rcx
0x180001573  mov     [rbp+90h+var_64], ebx
0x180001576  mov     [rbp+90h+var_78], 4
0x18000157e  mov     rcx, [rax]
0x180001581  test    rcx, rcx
0x180001584  jz      short loc_18000159B
0x180001586  mov     rax, rdx
0x180001589  inc     rax
0x18000158c  cmp     [rcx+rax*2], bx
0x180001590  jnz     short loc_180001589
0x180001592  lea     eax, ds:2[rax*2]
0x180001599  jmp     short loc_1800015A5
0x18000159b  lea     rcx, qword_180020CC0
0x1800015a2  mov     eax, r9d
0x1800015a5  mov     [rbp+90h+var_88], eax
0x1800015a8  mov     rax, [rbp+90h+arg_70]
0x1800015af  mov     [rbp+90h+var_90], rcx
0x1800015b3  mov     [rbp+90h+var_84], ebx
0x1800015b6  mov     rcx, [rax]
0x1800015b9  test    rcx, rcx
0x1800015bc  jz      short loc_1800015CD
0x1800015be  mov     rax, rdx
0x1800015c1  inc     rax
0x1800015c4  cmp     [rcx+rax], bl
0x1800015c7  jnz     short loc_1800015C1
0x1800015c9  inc     eax
0x1800015cb  jmp     short loc_1800015D3
0x1800015cd  mov     rcx, rdi
0x1800015d0  mov     eax, r8d
0x1800015d3  mov     [rbp+90h+var_98], eax
0x1800015d6  mov     rax, [rbp+90h+arg_68]
0x1800015dd  mov     [rbp+90h+var_B0], rax
0x1800015e1  mov     rax, [rbp+90h+arg_60]
0x1800015e8  mov     [rbp+90h+var_A0], rcx
0x1800015ec  mov     [rbp+90h+var_94], ebx
0x1800015ef  mov     [rbp+90h+var_A8], 4
0x1800015f7  mov     rcx, [rax]
0x1800015fa  test    rcx, rcx
0x1800015fd  jz      short loc_18000160E
0x1800015ff  mov     rax, rdx
0x180001602  inc     rax
0x180001605  cmp     [rcx+rax], bl
0x180001608  jnz     short loc_180001602
0x18000160a  inc     eax
0x18000160c  jmp     short loc_180001614
0x18000160e  mov     rcx, rdi
0x180001611  mov     eax, r8d
0x180001614  mov     [rbp+90h+var_B8], eax
0x180001617  mov     rax, [rbp+90h+arg_58]
0x18000161e  mov     [rbp+90h+var_D0], rax
0x180001622  mov     rax, [rbp+90h+arg_50]
0x180001629  mov     [rbp+90h+var_C0], rcx
0x18000162d  mov     [rbp+90h+var_B4], ebx
0x180001630  mov     [rbp+90h+var_C8], 4
0x180001638  mov     rcx, [rax]
0x18000163b  test    rcx, rcx
0x18000163e  jz      short loc_180001656
0x180001640  mov     rax, rdx
0x180001643  inc     rax
0x180001646  cmp     [rcx+rax*2], bx
0x18000164a  jnz     short loc_180001643
0x18000164c  lea     r9d, ds:2[rax*2]
0x180001654  jmp     short loc_18000165D
0x180001656  lea     rcx, qword_180020CC0
0x18000165d  mov     rax, [rbp+90h+arg_48]
0x180001664  mov     [rbp+90h+var_F0], rax
0x180001668  mov     rax, [rbp+90h+arg_40]
0x18000166f  mov     [rbp+90h+var_E0], rcx
0x180001673  mov     [rbp+90h+var_D8], r9d
0x180001677  mov     [rbp+90h+var_D4], ebx
0x18000167a  mov     rcx, [rax]
0x18000167d  mov     [rbp+90h+var_E8], 4
0x180001685  test    rcx, rcx
0x180001688  jz      short loc_180001699
0x18000168a  mov     rax, rdx
0x18000168d  inc     rax
0x180001690  cmp     [rcx+rax], bl
0x180001693  jnz     short loc_18000168D
0x180001695  inc     eax
0x180001697  jmp     short loc_18000169F
0x180001699  mov     rcx, rdi
0x18000169c  mov     eax, r8d
0x18000169f  mov     [rbp+90h+var_F8], eax
0x1800016a2  mov     rax, [rbp+90h+arg_38]
0x1800016a9  mov     [rbp+90h+var_110], rax
0x1800016ad  mov     rax, [rbp+90h+arg_30]
0x1800016b4  mov     [rbp+90h+var_100], rcx
0x1800016b8  mov     [rbp+90h+var_F4], ebx
0x1800016bb  mov     [rbp+90h+var_108], 4
0x1800016c3  mov     rcx, [rax]
0x1800016c6  test    rcx, rcx
0x1800016c9  jz      short loc_1800016D9
0x1800016cb  inc     rdx
0x1800016ce  cmp     [rcx+rdx], bl
0x1800016d1  jnz     short loc_1800016CB
0x1800016d3  lea     r8d, [rdx+1]
0x1800016d7  jmp     short loc_1800016DC
0x1800016d9  mov     rcx, rdi
0x1800016dc  mov     rax, [rbp+90h+arg_28]
0x1800016e3  xor     r9d, r9d
0x1800016e6  mov     [rsp+190h+var_130], rax
0x1800016eb  mov     rdx, r11
0x1800016ee  mov     rax, [rbp+90h+arg_20]
0x1800016f5  mov     [rsp+190h+var_140], rax
0x1800016fa  lea     rax, [rsp+190h+var_160]
0x1800016ff  mov     [rsp+190h+var_120], rcx
0x180001704  mov     rcx, r10
0x180001707  mov     [rsp+190h+var_118], r8d
0x18000170c  xor     r8d, r8d
0x18000170f  mov     [rsp+190h+var_168], rax
0x180001714  mov     [rsp+190h+var_170], 14h
0x18000171c  mov     [rsp+190h+var_114], ebx
0x180001720  mov     [rsp+190h+var_128], 4
0x180001729  mov     [rsp+190h+var_138], 8
0x180001732  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180001737  mov     rcx, [rbp+90h+var_20]
0x18000173b  xor     rcx, rsp; StackCookie
0x18000173e  call    __security_check_cookie
0x180001743  mov     rbx, [rsp+190h+arg_10]
0x18000174b  add     rsp, 180h
0x180001752  pop     r14
0x180001754  pop     rdi
0x180001755  pop     rbp
0x180001756  retn
```
