# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001420`
- end: `0x18000172b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z`
- size: `779`
- prototype: `__int64 __fastcall(int, int, int, __int64, __int64, __int64, __int64, const wchar_t **, __int64, const wchar_t **, __int64, __int64 **, __int64, const wchar_t **, __int64, const wchar_t **, __int64 **, __int64, const wchar_t **, __int64 **, __int64, __int64, const wchar_t **)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x180014ec0`
- `0x180015120`
- `0x180015380`
- `0x1800155e0`
- `0x180015840`
- `0x180015aa0`
- `0x180015d00`
- `0x180015f60`
- `0x1800161c0`
- `0x180016420`
- `0x180016680`
- `0x1800168e0`

## callees

- `0x180001420`
- `0x180001b7c`
- `0x1800027c0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        int a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const wchar_t **a8,
        __int64 a9,
        const wchar_t **a10,
        __int64 a11,
        __int64 **a12,
        __int64 a13,
        const wchar_t **a14,
        __int64 a15,
        const wchar_t **a16,
        __int64 **a17,
        __int64 a18,
        const wchar_t **a19,
        __int64 **a20,
        __int64 a21,
        __int64 a22,
        const wchar_t **a23)
{
  __int64 v25; // rdx
  int v27; // r8d
  const wchar_t *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  int v31; // r9d
  __int64 *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  const wchar_t *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  __int64 *v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  const wchar_t *v41; // rcx
  __int64 v42; // rax
  int v43; // eax
  const wchar_t *v44; // rcx
  __int64 v45; // rax
  int v46; // eax
  __int64 *v47; // rcx
  __int64 v48; // rax
  const wchar_t *v49; // rcx
  __int64 v50; // rax
  int v51; // eax
  const wchar_t *v52; // rcx
  struct _EVENT_DATA_DESCRIPTOR v54; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v55; // [rsp+50h] [rbp-B0h]
  __int64 v56; // [rsp+58h] [rbp-A8h]
  __int64 v57; // [rsp+60h] [rbp-A0h]
  __int64 v58; // [rsp+68h] [rbp-98h]
  __int64 v59; // [rsp+70h] [rbp-90h]
  __int64 v60; // [rsp+78h] [rbp-88h]
  const wchar_t *v61; // [rsp+80h] [rbp-80h]
  int v62; // [rsp+88h] [rbp-78h]
  int v63; // [rsp+8Ch] [rbp-74h]
  __int64 v64; // [rsp+90h] [rbp-70h]
  __int64 v65; // [rsp+98h] [rbp-68h]
  const wchar_t *v66; // [rsp+A0h] [rbp-60h]
  int v67; // [rsp+A8h] [rbp-58h]
  int v68; // [rsp+ACh] [rbp-54h]
  __int64 v69; // [rsp+B0h] [rbp-50h]
  __int64 v70; // [rsp+B8h] [rbp-48h]
  __int64 *v71; // [rsp+C0h] [rbp-40h]
  int v72; // [rsp+C8h] [rbp-38h]
  int v73; // [rsp+CCh] [rbp-34h]
  __int64 v74; // [rsp+D0h] [rbp-30h]
  __int64 v75; // [rsp+D8h] [rbp-28h]
  const wchar_t *v76; // [rsp+E0h] [rbp-20h]
  int v77; // [rsp+E8h] [rbp-18h]
  int v78; // [rsp+ECh] [rbp-14h]
  __int64 v79; // [rsp+F0h] [rbp-10h]
  __int64 v80; // [rsp+F8h] [rbp-8h]
  const wchar_t *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 *v84; // [rsp+110h] [rbp+10h]
  int v85; // [rsp+118h] [rbp+18h]
  int v86; // [rsp+11Ch] [rbp+1Ch]
  __int64 v87; // [rsp+120h] [rbp+20h]
  __int64 v88; // [rsp+128h] [rbp+28h]
  const wchar_t *v89; // [rsp+130h] [rbp+30h]
  int v90; // [rsp+138h] [rbp+38h]
  int v91; // [rsp+13Ch] [rbp+3Ch]
  __int64 *v92; // [rsp+140h] [rbp+40h]
  int v93; // [rsp+148h] [rbp+48h]
  int v94; // [rsp+14Ch] [rbp+4Ch]
  __int64 v95; // [rsp+150h] [rbp+50h]
  __int64 v96; // [rsp+158h] [rbp+58h]
  __int64 v97; // [rsp+160h] [rbp+60h]
  __int64 v98; // [rsp+168h] [rbp+68h]
  const wchar_t *v99; // [rsp+170h] [rbp+70h]
  int v100; // [rsp+178h] [rbp+78h]
  int v101; // [rsp+17Ch] [rbp+7Ch]

  v25 = -1;
  v27 = 1;
  v28 = *a23;
  if ( *a23 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_BYTE *)v28 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &word_18003647A;
    v30 = 1;
  }
  v100 = v30;
  v31 = 2;
  v97 = a22;
  v95 = a21;
  v99 = v28;
  v101 = 0;
  v98 = 4;
  v32 = *a20;
  v96 = 4;
  if ( v32 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *((_WORD *)v32 + v33) );
    v34 = 2 * v33 + 2;
  }
  else
  {
    v32 = &qword_180037068;
    v34 = 2;
  }
  v93 = v34;
  v92 = v32;
  v94 = 0;
  v35 = *a19;
  if ( *a19 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_BYTE *)v35 + v36) );
    v37 = v36 + 1;
  }
  else
  {
    v35 = &word_18003647A;
    v37 = 1;
  }
  v90 = v37;
  v87 = a18;
  v89 = v35;
  v91 = 0;
  v88 = 4;
  v38 = *a17;
  if ( *a17 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *((_WORD *)v38 + v39) );
    v40 = 2 * v39 + 2;
  }
  else
  {
    v38 = &qword_180037068;
    v40 = 2;
  }
  v85 = v40;
  v84 = v38;
  v86 = 0;
  v41 = *a16;
  if ( *a16 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *((_BYTE *)v41 + v42) );
    v43 = v42 + 1;
  }
  else
  {
    v41 = &word_18003647A;
    v43 = 1;
  }
  v82 = v43;
  v79 = a15;
  v81 = v41;
  v83 = 0;
  v80 = 4;
  v44 = *a14;
  if ( *a14 )
  {
    v45 = -1;
    do
      ++v45;
    while ( *((_BYTE *)v44 + v45) );
    v46 = v45 + 1;
  }
  else
  {
    v44 = &word_18003647A;
    v46 = 1;
  }
  v77 = v46;
  v74 = a13;
  v76 = v44;
  v78 = 0;
  v75 = 4;
  v47 = *a12;
  if ( *a12 )
  {
    v48 = -1;
    do
      ++v48;
    while ( *((_WORD *)v47 + v48) );
    v31 = 2 * v48 + 2;
  }
  else
  {
    v47 = &qword_180037068;
  }
  v69 = a11;
  v71 = v47;
  v72 = v31;
  v73 = 0;
  v49 = *a10;
  v70 = 4;
  if ( v49 )
  {
    v50 = -1;
    do
      ++v50;
    while ( *((_BYTE *)v49 + v50) );
    v51 = v50 + 1;
  }
  else
  {
    v49 = &word_18003647A;
    v51 = 1;
  }
  v67 = v51;
  v64 = a9;
  v66 = v49;
  v68 = 0;
  v65 = 4;
  v52 = *a8;
  if ( *a8 )
  {
    do
      ++v25;
    while ( *((_BYTE *)v52 + v25) );
    v27 = v25 + 1;
  }
  else
  {
    v52 = &word_18003647A;
  }
  v59 = a7;
  v57 = a6;
  v55 = a5;
  v61 = v52;
  v62 = v27;
  v63 = 0;
  v60 = 4;
  v58 = 8;
  v56 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x15u, &v54);
}

```

## disassembly

```asm
0x180001420  push    rbp
0x180001422  push    rbx
0x180001423  push    rsi
0x180001424  push    rdi
0x180001425  push    r14
0x180001427  lea     rbp, [rsp-90h]
0x18000142f  sub     rsp, 190h
0x180001436  mov     rax, cs:__security_cookie
0x18000143d  xor     rax, rsp
0x180001440  mov     [rbp+0B0h+var_30], rax
0x180001447  mov     rax, [rbp+0B0h+arg_B0]
0x18000144e  lea     rsi, word_18003647A
0x180001455  mov     r11, rdx
0x180001458  mov     r10, rcx
0x18000145b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000145f  xor     edi, edi
0x180001461  mov     rbx, r8
0x180001464  mov     r8d, 1
0x18000146a  mov     rcx, [rax]
0x18000146d  test    rcx, rcx
0x180001470  jz      short loc_180001482
0x180001472  mov     rax, rdx
0x180001475  inc     rax
0x180001478  cmp     [rcx+rax], dil
0x18000147c  jnz     short loc_180001475
0x18000147e  inc     eax
0x180001480  jmp     short loc_180001488
0x180001482  mov     rcx, rsi
0x180001485  mov     eax, r8d
0x180001488  mov     [rbp+0B0h+var_38], eax
0x18000148b  mov     r9d, 2
0x180001491  mov     rax, [rbp+0B0h+arg_A8]
0x180001498  mov     [rbp+0B0h+var_50], rax
0x18000149c  mov     rax, [rbp+0B0h+arg_A0]
0x1800014a3  mov     [rbp+0B0h+var_60], rax
0x1800014a7  mov     rax, [rbp+0B0h+arg_98]
0x1800014ae  mov     [rbp+0B0h+var_40], rcx
0x1800014b2  mov     [rbp+0B0h+var_34], edi
0x1800014b5  mov     [rbp+0B0h+var_48], 4
0x1800014bd  mov     rcx, [rax]
0x1800014c0  mov     [rbp+0B0h+var_58], 4
0x1800014c8  test    rcx, rcx
0x1800014cb  jz      short loc_1800014E2
0x1800014cd  mov     rax, rdx
0x1800014d0  inc     rax
0x1800014d3  cmp     [rcx+rax*2], di
0x1800014d7  jnz     short loc_1800014D0
0x1800014d9  lea     eax, ds:2[rax*2]
0x1800014e0  jmp     short loc_1800014EC
0x1800014e2  lea     rcx, qword_180037068
0x1800014e9  mov     eax, r9d
0x1800014ec  mov     [rbp+0B0h+var_68], eax
0x1800014ef  mov     rax, [rbp+0B0h+arg_90]
0x1800014f6  mov     [rbp+0B0h+var_70], rcx
0x1800014fa  mov     [rbp+0B0h+var_64], edi
0x1800014fd  mov     rcx, [rax]
0x180001500  test    rcx, rcx
0x180001503  jz      short loc_180001515
0x180001505  mov     rax, rdx
0x180001508  inc     rax
0x18000150b  cmp     [rcx+rax], dil
0x18000150f  jnz     short loc_180001508
0x180001511  inc     eax
0x180001513  jmp     short loc_18000151B
0x180001515  mov     rcx, rsi
0x180001518  mov     eax, r8d
0x18000151b  mov     [rbp+0B0h+var_78], eax
0x18000151e  mov     rax, [rbp+0B0h+arg_88]
0x180001525  mov     [rbp+0B0h+var_90], rax
0x180001529  mov     rax, [rbp+0B0h+arg_80]
0x180001530  mov     [rbp+0B0h+var_80], rcx
0x180001534  mov     [rbp+0B0h+var_74], edi
0x180001537  mov     [rbp+0B0h+var_88], 4
0x18000153f  mov     rcx, [rax]
0x180001542  test    rcx, rcx
0x180001545  jz      short loc_18000155C
0x180001547  mov     rax, rdx
0x18000154a  inc     rax
0x18000154d  cmp     [rcx+rax*2], di
0x180001551  jnz     short loc_18000154A
0x180001553  lea     eax, ds:2[rax*2]
0x18000155a  jmp     short loc_180001566
0x18000155c  lea     rcx, qword_180037068
0x180001563  mov     eax, r9d
0x180001566  mov     [rbp+0B0h+var_98], eax
0x180001569  mov     rax, [rbp+0B0h+arg_78]
0x180001570  mov     [rbp+0B0h+var_A0], rcx
0x180001574  mov     [rbp+0B0h+var_94], edi
0x180001577  mov     rcx, [rax]
0x18000157a  test    rcx, rcx
0x18000157d  jz      short loc_18000158F
0x18000157f  mov     rax, rdx
0x180001582  inc     rax
0x180001585  cmp     [rcx+rax], dil
0x180001589  jnz     short loc_180001582
0x18000158b  inc     eax
0x18000158d  jmp     short loc_180001595
0x18000158f  mov     rcx, rsi
0x180001592  mov     eax, r8d
0x180001595  mov     [rbp+0B0h+var_A8], eax
0x180001598  mov     rax, [rbp+0B0h+arg_70]
0x18000159f  mov     [rbp+0B0h+var_C0], rax
0x1800015a3  mov     rax, [rbp+0B0h+arg_68]
0x1800015aa  mov     [rbp+0B0h+var_B0], rcx
0x1800015ae  mov     [rbp+0B0h+var_A4], edi
0x1800015b1  mov     [rbp+0B0h+var_B8], 4
0x1800015b9  mov     rcx, [rax]
0x1800015bc  test    rcx, rcx
0x1800015bf  jz      short loc_1800015D1
0x1800015c1  mov     rax, rdx
0x1800015c4  inc     rax
0x1800015c7  cmp     [rcx+rax], dil
0x1800015cb  jnz     short loc_1800015C4
0x1800015cd  inc     eax
0x1800015cf  jmp     short loc_1800015D7
0x1800015d1  mov     rcx, rsi
0x1800015d4  mov     eax, r8d
0x1800015d7  mov     [rbp+0B0h+var_C8], eax
0x1800015da  mov     rax, [rbp+0B0h+arg_60]
0x1800015e1  mov     [rbp+0B0h+var_E0], rax
0x1800015e5  mov     rax, [rbp+0B0h+arg_58]
0x1800015ec  mov     [rbp+0B0h+var_D0], rcx
0x1800015f0  mov     [rbp+0B0h+var_C4], edi
0x1800015f3  mov     [rbp+0B0h+var_D8], 4
0x1800015fb  mov     rcx, [rax]
0x1800015fe  test    rcx, rcx
0x180001601  jz      short loc_180001619
0x180001603  mov     rax, rdx
0x180001606  inc     rax
0x180001609  cmp     [rcx+rax*2], di
0x18000160d  jnz     short loc_180001606
0x18000160f  lea     r9d, ds:2[rax*2]
0x180001617  jmp     short loc_180001620
0x180001619  lea     rcx, qword_180037068
0x180001620  mov     rax, [rbp+0B0h+arg_50]
0x180001627  mov     [rbp+0B0h+var_100], rax
0x18000162b  mov     rax, [rbp+0B0h+arg_48]
0x180001632  mov     [rbp+0B0h+var_F0], rcx
0x180001636  mov     [rbp+0B0h+var_E8], r9d
0x18000163a  mov     [rbp+0B0h+var_E4], edi
0x18000163d  mov     rcx, [rax]
0x180001640  mov     [rbp+0B0h+var_F8], 4
0x180001648  test    rcx, rcx
0x18000164b  jz      short loc_18000165D
0x18000164d  mov     rax, rdx
0x180001650  inc     rax
0x180001653  cmp     [rcx+rax], dil
0x180001657  jnz     short loc_180001650
0x180001659  inc     eax
0x18000165b  jmp     short loc_180001663
0x18000165d  mov     rcx, rsi
0x180001660  mov     eax, r8d
0x180001663  mov     [rbp+0B0h+var_108], eax
0x180001666  mov     rax, [rbp+0B0h+arg_40]
0x18000166d  mov     [rbp+0B0h+var_120], rax
0x180001671  mov     rax, [rbp+0B0h+arg_38]
0x180001678  mov     [rbp+0B0h+var_110], rcx
0x18000167c  mov     [rbp+0B0h+var_104], edi
0x18000167f  mov     [rbp+0B0h+var_118], 4
0x180001687  mov     rcx, [rax]
0x18000168a  test    rcx, rcx
0x18000168d  jz      short loc_18000169E
0x18000168f  inc     rdx
0x180001692  cmp     [rcx+rdx], dil
0x180001696  jnz     short loc_18000168F
0x180001698  lea     r8d, [rdx+1]
0x18000169c  jmp     short loc_1800016A1
0x18000169e  mov     rcx, rsi
0x1800016a1  mov     rax, [rbp+0B0h+arg_30]
0x1800016a8  xor     r9d, r9d; int
0x1800016ab  mov     [rsp+1B0h+var_140], rax
0x1800016b0  mov     rdx, r11; int
0x1800016b3  mov     rax, [rbp+0B0h+arg_28]
0x1800016ba  mov     [rsp+1B0h+var_150], rax
0x1800016bf  mov     rax, [rbp+0B0h+arg_20]
0x1800016c6  mov     [rsp+1B0h+var_160], rax
0x1800016cb  lea     rax, [rsp+1B0h+var_180]
0x1800016d0  mov     [rbp+0B0h+var_130], rcx
0x1800016d4  mov     rcx, r10; int
0x1800016d7  mov     [rbp+0B0h+var_128], r8d
0x1800016db  mov     r8, rbx; int
0x1800016de  mov     [rsp+1B0h+var_188], rax; PEVENT_DATA_DESCRIPTOR
0x1800016e3  mov     [rsp+1B0h+var_190], 15h; ULONG
0x1800016eb  mov     [rbp+0B0h+var_124], edi
0x1800016ee  mov     [rsp+1B0h+var_138], 4
0x1800016f7  mov     [rsp+1B0h+var_148], 8
0x180001700  mov     [rsp+1B0h+var_158], 8
0x180001709  call    _tlgWriteTransfer_EventWriteTransfer
0x18000170e  mov     rcx, [rbp+0B0h+var_30]
0x180001715  xor     rcx, rsp; StackCookie
0x180001718  call    __security_check_cookie
0x18000171d  add     rsp, 190h
0x180001724  pop     r14
0x180001726  pop     rdi
0x180001727  pop     rsi
0x180001728  pop     rbx
0x180001729  pop     rbp
0x18000172a  retn
```
