# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800013ec`
- end: `0x180001687`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `667`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a820`

## callees

- `0x180001008`
- `0x1800013ec`
- `0x18000f0a0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9,
        __int64 a10,
        const wchar_t **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        const wchar_t **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        const wchar_t **a19)
{
  __int64 v21; // rdx
  int v23; // r9d
  const wchar_t *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  const wchar_t *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const wchar_t *v40; // rcx
  __int64 v41; // rax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rcx
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v52; // [rsp+70h] [rbp-90h]
  int v53; // [rsp+78h] [rbp-88h]
  int v54; // [rsp+7Ch] [rbp-84h]
  __int64 v55; // [rsp+80h] [rbp-80h]
  __int64 v56; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v57; // [rsp+90h] [rbp-70h]
  int v58; // [rsp+98h] [rbp-68h]
  int v59; // [rsp+9Ch] [rbp-64h]
  __int64 v60; // [rsp+A0h] [rbp-60h]
  __int64 v61; // [rsp+A8h] [rbp-58h]
  const wchar_t *v62; // [rsp+B0h] [rbp-50h]
  int v63; // [rsp+B8h] [rbp-48h]
  int v64; // [rsp+BCh] [rbp-44h]
  __int64 v65; // [rsp+C0h] [rbp-40h]
  __int64 v66; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v67; // [rsp+D0h] [rbp-30h]
  int v68; // [rsp+D8h] [rbp-28h]
  int v69; // [rsp+DCh] [rbp-24h]
  __int64 v70; // [rsp+E0h] [rbp-20h]
  __int64 v71; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v72; // [rsp+F0h] [rbp-10h]
  int v73; // [rsp+F8h] [rbp-8h]
  int v74; // [rsp+FCh] [rbp-4h]
  const wchar_t *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  __int64 v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v80; // [rsp+120h] [rbp+20h]
  int v81; // [rsp+128h] [rbp+28h]
  int v82; // [rsp+12Ch] [rbp+2Ch]
  const wchar_t *v83; // [rsp+130h] [rbp+30h]
  int v84; // [rsp+138h] [rbp+38h]
  int v85; // [rsp+13Ch] [rbp+3Ch]

  v21 = -1;
  v23 = 2;
  v24 = *a19;
  if ( *a19 )
  {
    v25 = -1;
    do
      ++v25;
    while ( v24[v25] );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &pszFormat;
    v26 = 2;
  }
  v84 = v26;
  v27 = 1;
  v83 = v24;
  v85 = 0;
  v28 = *a18;
  if ( *a18 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_BYTE *)v28 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &word_18001423A;
    v30 = 1;
  }
  v81 = v30;
  v78 = a17;
  v80 = v28;
  v82 = 0;
  v79 = 4;
  v31 = *a16;
  if ( *a16 )
  {
    v32 = -1;
    do
      ++v32;
    while ( v31[v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &pszFormat;
    v33 = 2;
  }
  v76 = v33;
  v75 = v31;
  v77 = 0;
  v34 = *a15;
  if ( *a15 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &word_18001423A;
    v36 = 1;
  }
  v73 = v36;
  v70 = a14;
  v72 = v34;
  v74 = 0;
  v71 = 4;
  v37 = *a13;
  if ( *a13 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_BYTE *)v37 + v38) );
    v39 = v38 + 1;
  }
  else
  {
    v37 = &word_18001423A;
    v39 = 1;
  }
  v68 = v39;
  v65 = a12;
  v67 = v37;
  v69 = 0;
  v66 = 4;
  v40 = *a11;
  if ( *a11 )
  {
    v41 = -1;
    do
      ++v41;
    while ( v40[v41] );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = &pszFormat;
  }
  v60 = a10;
  v62 = v40;
  v63 = v23;
  v64 = 0;
  v42 = *a9;
  v61 = 4;
  if ( v42 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &word_18001423A;
    v44 = 1;
  }
  v58 = v44;
  v55 = a8;
  v57 = v42;
  v59 = 0;
  v56 = 4;
  v45 = *a7;
  if ( *a7 )
  {
    do
      ++v21;
    while ( *((_BYTE *)v45 + v21) );
    v27 = v21 + 1;
  }
  else
  {
    v45 = &word_18001423A;
  }
  v50 = a6;
  v48 = a5;
  v52 = v45;
  v53 = v27;
  v54 = 0;
  v51 = 4;
  v49 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x11u, &v47);
}

```

## disassembly

```asm
0x1800013ec  push    rbp
0x1800013ee  push    rbx
0x1800013ef  push    rsi
0x1800013f0  push    rdi
0x1800013f1  push    r14
0x1800013f3  lea     rbp, [rsp-50h]
0x1800013f8  sub     rsp, 150h
0x1800013ff  mov     rax, cs:__security_cookie
0x180001406  xor     rax, rsp
0x180001409  mov     [rbp+70h+var_30], rax
0x18000140d  mov     rax, [rbp+70h+arg_90]
0x180001414  mov     r11, rdx
0x180001417  mov     r10, rcx
0x18000141a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000141e  xor     edi, edi
0x180001420  mov     rbx, r8
0x180001423  mov     r9d, 2
0x180001429  mov     rcx, [rax]
0x18000142c  test    rcx, rcx
0x18000142f  jz      short loc_180001446
0x180001431  mov     rax, rdx
0x180001434  inc     rax
0x180001437  cmp     [rcx+rax*2], di
0x18000143b  jnz     short loc_180001434
0x18000143d  lea     eax, ds:2[rax*2]
0x180001444  jmp     short loc_180001450
0x180001446  lea     rcx, pszFormat
0x18000144d  mov     eax, r9d
0x180001450  mov     [rbp+70h+var_38], eax
0x180001453  lea     rsi, word_18001423A
0x18000145a  mov     rax, [rbp+70h+arg_88]
0x180001461  mov     r8d, 1
0x180001467  mov     [rbp+70h+var_40], rcx
0x18000146b  mov     [rbp+70h+var_34], edi
0x18000146e  mov     rcx, [rax]
0x180001471  test    rcx, rcx
0x180001474  jz      short loc_180001486
0x180001476  mov     rax, rdx
0x180001479  inc     rax
0x18000147c  cmp     [rcx+rax], dil
0x180001480  jnz     short loc_180001479
0x180001482  inc     eax
0x180001484  jmp     short loc_18000148C
0x180001486  mov     rcx, rsi
0x180001489  mov     eax, r8d
0x18000148c  mov     [rbp+70h+var_48], eax
0x18000148f  mov     rax, [rbp+70h+arg_80]
0x180001496  mov     [rbp+70h+var_60], rax
0x18000149a  mov     rax, [rbp+70h+arg_78]
0x1800014a1  mov     [rbp+70h+var_50], rcx
0x1800014a5  mov     [rbp+70h+var_44], edi
0x1800014a8  mov     [rbp+70h+var_58], 4
0x1800014b0  mov     rcx, [rax]
0x1800014b3  test    rcx, rcx
0x1800014b6  jz      short loc_1800014CD
0x1800014b8  mov     rax, rdx
0x1800014bb  inc     rax
0x1800014be  cmp     [rcx+rax*2], di
0x1800014c2  jnz     short loc_1800014BB
0x1800014c4  lea     eax, ds:2[rax*2]
0x1800014cb  jmp     short loc_1800014D7
0x1800014cd  lea     rcx, pszFormat
0x1800014d4  mov     eax, r9d
0x1800014d7  mov     [rbp+70h+var_68], eax
0x1800014da  mov     rax, [rbp+70h+arg_70]
0x1800014e1  mov     [rbp+70h+var_70], rcx
0x1800014e5  mov     [rbp+70h+var_64], edi
0x1800014e8  mov     rcx, [rax]
0x1800014eb  test    rcx, rcx
0x1800014ee  jz      short loc_180001500
0x1800014f0  mov     rax, rdx
0x1800014f3  inc     rax
0x1800014f6  cmp     [rcx+rax], dil
0x1800014fa  jnz     short loc_1800014F3
0x1800014fc  inc     eax
0x1800014fe  jmp     short loc_180001506
0x180001500  mov     rcx, rsi
0x180001503  mov     eax, r8d
0x180001506  mov     [rbp+70h+var_78], eax
0x180001509  mov     rax, [rbp+70h+arg_68]
0x180001510  mov     [rbp+70h+var_90], rax
0x180001514  mov     rax, [rbp+70h+arg_60]
0x18000151b  mov     [rbp+70h+var_80], rcx
0x18000151f  mov     [rbp+70h+var_74], edi
0x180001522  mov     [rbp+70h+var_88], 4
0x18000152a  mov     rcx, [rax]
0x18000152d  test    rcx, rcx
0x180001530  jz      short loc_180001542
0x180001532  mov     rax, rdx
0x180001535  inc     rax
0x180001538  cmp     [rcx+rax], dil
0x18000153c  jnz     short loc_180001535
0x18000153e  inc     eax
0x180001540  jmp     short loc_180001548
0x180001542  mov     rcx, rsi
0x180001545  mov     eax, r8d
0x180001548  mov     [rbp+70h+var_98], eax
0x18000154b  mov     rax, [rbp+70h+arg_58]
0x180001552  mov     [rbp+70h+var_B0], rax
0x180001556  mov     rax, [rbp+70h+arg_50]
0x18000155d  mov     [rbp+70h+var_A0], rcx
0x180001561  mov     [rbp+70h+var_94], edi
0x180001564  mov     [rbp+70h+var_A8], 4
0x18000156c  mov     rcx, [rax]
0x18000156f  test    rcx, rcx
0x180001572  jz      short loc_18000158A
0x180001574  mov     rax, rdx
0x180001577  inc     rax
0x18000157a  cmp     [rcx+rax*2], di
0x18000157e  jnz     short loc_180001577
0x180001580  lea     r9d, ds:2[rax*2]
0x180001588  jmp     short loc_180001591
0x18000158a  lea     rcx, pszFormat
0x180001591  mov     rax, [rbp+70h+arg_48]
0x180001598  mov     [rbp+70h+var_D0], rax
0x18000159c  mov     rax, [rbp+70h+arg_40]
0x1800015a3  mov     [rbp+70h+var_C0], rcx
0x1800015a7  mov     [rbp+70h+var_B8], r9d
0x1800015ab  mov     [rbp+70h+var_B4], edi
0x1800015ae  mov     rcx, [rax]
0x1800015b1  mov     [rbp+70h+var_C8], 4
0x1800015b9  test    rcx, rcx
0x1800015bc  jz      short loc_1800015CE
0x1800015be  mov     rax, rdx
0x1800015c1  inc     rax
0x1800015c4  cmp     [rcx+rax], dil
0x1800015c8  jnz     short loc_1800015C1
0x1800015ca  inc     eax
0x1800015cc  jmp     short loc_1800015D4
0x1800015ce  mov     rcx, rsi
0x1800015d1  mov     eax, r8d
0x1800015d4  mov     [rbp+70h+var_D8], eax
0x1800015d7  mov     rax, [rbp+70h+arg_38]
0x1800015de  mov     [rbp+70h+var_F0], rax
0x1800015e2  mov     rax, [rbp+70h+arg_30]
0x1800015e9  mov     [rbp+70h+var_E0], rcx
0x1800015ed  mov     [rbp+70h+var_D4], edi
0x1800015f0  mov     [rbp+70h+var_E8], 4
0x1800015f8  mov     rcx, [rax]
0x1800015fb  test    rcx, rcx
0x1800015fe  jz      short loc_18000160F
0x180001600  inc     rdx
0x180001603  cmp     [rcx+rdx], dil
0x180001607  jnz     short loc_180001600
0x180001609  lea     r8d, [rdx+1]
0x18000160d  jmp     short loc_180001612
0x18000160f  mov     rcx, rsi
0x180001612  mov     rax, [rbp+70h+arg_28]
0x180001619  xor     r9d, r9d
0x18000161c  mov     [rsp+170h+var_110], rax
0x180001621  mov     rdx, r11
0x180001624  mov     rax, [rbp+70h+arg_20]
0x18000162b  mov     [rsp+170h+var_120], rax
0x180001630  lea     rax, [rsp+170h+var_140]
0x180001635  mov     [rsp+170h+var_100], rcx
0x18000163a  mov     rcx, r10
0x18000163d  mov     [rsp+170h+var_F8], r8d
0x180001642  mov     r8, rbx
0x180001645  mov     [rsp+170h+var_148], rax
0x18000164a  mov     [rsp+170h+var_150], 11h
0x180001652  mov     [rsp+170h+var_F4], edi
0x180001656  mov     [rsp+170h+var_108], 4
0x18000165f  mov     [rsp+170h+var_118], 8
0x180001668  call    _tlgWriteTransfer_EventWriteTransfer
0x18000166d  mov     rcx, [rbp+70h+var_30]
0x180001671  xor     rcx, rsp; StackCookie
0x180001674  call    __security_check_cookie
0x180001679  add     rsp, 150h
0x180001680  pop     r14
0x180001682  pop     rdi
0x180001683  pop     rsi
0x180001684  pop     rbx
0x180001685  pop     rbp
0x180001686  retn
```
