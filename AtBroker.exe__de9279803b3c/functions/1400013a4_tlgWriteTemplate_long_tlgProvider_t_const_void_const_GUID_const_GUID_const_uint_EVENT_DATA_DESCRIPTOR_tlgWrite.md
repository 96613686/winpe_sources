# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1400013a4`
- end: `0x14000164f`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const BYTE **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const BYTE **, __int64, const unsigned __int16 **, const BYTE **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140008d54`

## callees

- `0x1400013a4`
- `0x140001a8c`
- `0x140015b00`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const unsigned __int16 **a8,
        __int64 a9,
        const unsigned __int16 **a10,
        __int64 a11,
        const BYTE **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        const BYTE **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        const BYTE **a20)
{
  __int64 v22; // rcx
  int v23; // r9d
  const BYTE *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  const BYTE *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  const BYTE *v40; // rdx
  __int64 v41; // rax
  const unsigned __int16 *v42; // rdx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rdx
  _BYTE v47[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  __int64 v52; // [rsp+70h] [rbp-90h]
  __int64 v53; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v54; // [rsp+80h] [rbp-80h]
  int v55; // [rsp+88h] [rbp-78h]
  int v56; // [rsp+8Ch] [rbp-74h]
  __int64 v57; // [rsp+90h] [rbp-70h]
  __int64 v58; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v59; // [rsp+A0h] [rbp-60h]
  int v60; // [rsp+A8h] [rbp-58h]
  int v61; // [rsp+ACh] [rbp-54h]
  __int64 v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+B8h] [rbp-48h]
  const BYTE *v64; // [rsp+C0h] [rbp-40h]
  int v65; // [rsp+C8h] [rbp-38h]
  int v66; // [rsp+CCh] [rbp-34h]
  __int64 v67; // [rsp+D0h] [rbp-30h]
  __int64 v68; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v69; // [rsp+E0h] [rbp-20h]
  int v70; // [rsp+E8h] [rbp-18h]
  int v71; // [rsp+ECh] [rbp-14h]
  __int64 v72; // [rsp+F0h] [rbp-10h]
  __int64 v73; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v74; // [rsp+100h] [rbp+0h]
  int v75; // [rsp+108h] [rbp+8h]
  int v76; // [rsp+10Ch] [rbp+Ch]
  const BYTE *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  const BYTE *v85; // [rsp+140h] [rbp+40h]
  int v86; // [rsp+148h] [rbp+48h]
  int v87; // [rsp+14Ch] [rbp+4Ch]

  v22 = -1;
  v23 = 2;
  v24 = *a20;
  if ( *a20 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *(_WORD *)&v24[2 * v25] );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &Data;
    v26 = 2;
  }
  v86 = v26;
  v27 = 1;
  v85 = v24;
  v87 = 0;
  v28 = *a19;
  if ( *a19 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_BYTE *)v28 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &word_140018C4A;
    v30 = 1;
  }
  v83 = v30;
  v80 = a18;
  v82 = v28;
  v84 = 0;
  v81 = 4;
  v31 = *a17;
  if ( *a17 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *(_WORD *)&v31[2 * v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &Data;
    v33 = 2;
  }
  v78 = v33;
  v77 = v31;
  v79 = 0;
  v34 = *a16;
  if ( *a16 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &word_140018C4A;
    v36 = 1;
  }
  v75 = v36;
  v72 = a15;
  v74 = v34;
  v76 = 0;
  v73 = 4;
  v37 = *a14;
  if ( *a14 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_BYTE *)v37 + v38) );
    v39 = v38 + 1;
  }
  else
  {
    v37 = &word_140018C4A;
    v39 = 1;
  }
  v70 = v39;
  v67 = a13;
  v69 = v37;
  v71 = 0;
  v68 = 4;
  v40 = *a12;
  if ( *a12 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *(_WORD *)&v40[2 * v41] );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = &Data;
  }
  v62 = a11;
  v64 = v40;
  v65 = v23;
  v66 = 0;
  v42 = *a10;
  v63 = 4;
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
    v42 = &word_140018C4A;
    v44 = 1;
  }
  v60 = v44;
  v57 = a9;
  v59 = v42;
  v61 = 0;
  v58 = 4;
  v45 = *a8;
  if ( *a8 )
  {
    do
      ++v22;
    while ( *((_BYTE *)v45 + v22) );
    v27 = v22 + 1;
  }
  else
  {
    v45 = &word_140018C4A;
  }
  v52 = a7;
  v50 = a6;
  v48 = a5;
  v54 = v45;
  v55 = v27;
  v56 = 0;
  v53 = 4;
  v51 = 8;
  v49 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 18, v47);
}

```

## disassembly

```asm
0x1400013a4  mov     [rsp-8+arg_10], rbx
0x1400013a9  push    rbp
0x1400013aa  push    rsi
0x1400013ab  push    rdi
0x1400013ac  lea     rbp, [rsp-60h]
0x1400013b1  sub     rsp, 160h
0x1400013b8  mov     rax, cs:__security_cookie
0x1400013bf  xor     rax, rsp
0x1400013c2  mov     [rbp+70h+var_20], rax
0x1400013c6  mov     rax, [rbp+70h+arg_98]
0x1400013cd  mov     r11, rdx
0x1400013d0  mov     r10, rcx
0x1400013d3  xor     ebx, ebx
0x1400013d5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400013d9  mov     r9d, 2
0x1400013df  mov     rdx, [rax]
0x1400013e2  test    rdx, rdx
0x1400013e5  jz      short loc_1400013FC
0x1400013e7  mov     rax, rcx
0x1400013ea  inc     rax
0x1400013ed  cmp     [rdx+rax*2], bx
0x1400013f1  jnz     short loc_1400013EA
0x1400013f3  lea     eax, ds:2[rax*2]
0x1400013fa  jmp     short loc_140001406
0x1400013fc  lea     rdx, Data
0x140001403  mov     eax, r9d
0x140001406  mov     [rbp+70h+var_28], eax
0x140001409  lea     rdi, word_140018C4A
0x140001410  mov     rax, [rbp+70h+arg_90]
0x140001417  mov     r8d, 1
0x14000141d  mov     [rbp+70h+var_30], rdx
0x140001421  mov     [rbp+70h+var_24], ebx
0x140001424  mov     rdx, [rax]
0x140001427  test    rdx, rdx
0x14000142a  jz      short loc_14000143B
0x14000142c  mov     rax, rcx
0x14000142f  inc     rax
0x140001432  cmp     [rdx+rax], bl
0x140001435  jnz     short loc_14000142F
0x140001437  inc     eax
0x140001439  jmp     short loc_140001441
0x14000143b  mov     rdx, rdi
0x14000143e  mov     eax, r8d
0x140001441  mov     [rbp+70h+var_38], eax
0x140001444  mov     rax, [rbp+70h+arg_88]
0x14000144b  mov     [rbp+70h+var_50], rax
0x14000144f  mov     rax, [rbp+70h+arg_80]
0x140001456  mov     [rbp+70h+var_40], rdx
0x14000145a  mov     [rbp+70h+var_34], ebx
0x14000145d  mov     [rbp+70h+var_48], 4
0x140001465  mov     rdx, [rax]
0x140001468  test    rdx, rdx
0x14000146b  jz      short loc_140001482
0x14000146d  mov     rax, rcx
0x140001470  inc     rax
0x140001473  cmp     [rdx+rax*2], bx
0x140001477  jnz     short loc_140001470
0x140001479  lea     eax, ds:2[rax*2]
0x140001480  jmp     short loc_14000148C
0x140001482  lea     rdx, Data
0x140001489  mov     eax, r9d
0x14000148c  mov     [rbp+70h+var_58], eax
0x14000148f  mov     rax, [rbp+70h+arg_78]
0x140001496  mov     [rbp+70h+var_60], rdx
0x14000149a  mov     [rbp+70h+var_54], ebx
0x14000149d  mov     rdx, [rax]
0x1400014a0  test    rdx, rdx
0x1400014a3  jz      short loc_1400014B4
0x1400014a5  mov     rax, rcx
0x1400014a8  inc     rax
0x1400014ab  cmp     [rdx+rax], bl
0x1400014ae  jnz     short loc_1400014A8
0x1400014b0  inc     eax
0x1400014b2  jmp     short loc_1400014BA
0x1400014b4  mov     rdx, rdi
0x1400014b7  mov     eax, r8d
0x1400014ba  mov     [rbp+70h+var_68], eax
0x1400014bd  mov     rax, [rbp+70h+arg_70]
0x1400014c4  mov     [rbp+70h+var_80], rax
0x1400014c8  mov     rax, [rbp+70h+arg_68]
0x1400014cf  mov     [rbp+70h+var_70], rdx
0x1400014d3  mov     [rbp+70h+var_64], ebx
0x1400014d6  mov     [rbp+70h+var_78], 4
0x1400014de  mov     rdx, [rax]
0x1400014e1  test    rdx, rdx
0x1400014e4  jz      short loc_1400014F5
0x1400014e6  mov     rax, rcx
0x1400014e9  inc     rax
0x1400014ec  cmp     [rdx+rax], bl
0x1400014ef  jnz     short loc_1400014E9
0x1400014f1  inc     eax
0x1400014f3  jmp     short loc_1400014FB
0x1400014f5  mov     rdx, rdi
0x1400014f8  mov     eax, r8d
0x1400014fb  mov     [rbp+70h+var_88], eax
0x1400014fe  mov     rax, [rbp+70h+arg_60]
0x140001505  mov     [rbp+70h+var_A0], rax
0x140001509  mov     rax, [rbp+70h+arg_58]
0x140001510  mov     [rbp+70h+var_90], rdx
0x140001514  mov     [rbp+70h+var_84], ebx
0x140001517  mov     [rbp+70h+var_98], 4
0x14000151f  mov     rdx, [rax]
0x140001522  test    rdx, rdx
0x140001525  jz      short loc_14000153D
0x140001527  mov     rax, rcx
0x14000152a  inc     rax
0x14000152d  cmp     [rdx+rax*2], bx
0x140001531  jnz     short loc_14000152A
0x140001533  lea     r9d, ds:2[rax*2]
0x14000153b  jmp     short loc_140001544
0x14000153d  lea     rdx, Data
0x140001544  mov     rax, [rbp+70h+arg_50]
0x14000154b  mov     [rbp+70h+var_C0], rax
0x14000154f  mov     rax, [rbp+70h+arg_48]
0x140001556  mov     [rbp+70h+var_B0], rdx
0x14000155a  mov     [rbp+70h+var_A8], r9d
0x14000155e  mov     [rbp+70h+var_A4], ebx
0x140001561  mov     rdx, [rax]
0x140001564  mov     [rbp+70h+var_B8], 4
0x14000156c  test    rdx, rdx
0x14000156f  jz      short loc_140001580
0x140001571  mov     rax, rcx
0x140001574  inc     rax
0x140001577  cmp     [rdx+rax], bl
0x14000157a  jnz     short loc_140001574
0x14000157c  inc     eax
0x14000157e  jmp     short loc_140001586
0x140001580  mov     rdx, rdi
0x140001583  mov     eax, r8d
0x140001586  mov     [rbp+70h+var_C8], eax
0x140001589  mov     rax, [rbp+70h+arg_40]
0x140001590  mov     [rbp+70h+var_E0], rax
0x140001594  mov     rax, [rbp+70h+arg_38]
0x14000159b  mov     [rbp+70h+var_D0], rdx
0x14000159f  mov     [rbp+70h+var_C4], ebx
0x1400015a2  mov     [rbp+70h+var_D8], 4
0x1400015aa  mov     rdx, [rax]
0x1400015ad  test    rdx, rdx
0x1400015b0  jz      short loc_1400015C0
0x1400015b2  inc     rcx
0x1400015b5  cmp     [rdx+rcx], bl
0x1400015b8  jnz     short loc_1400015B2
0x1400015ba  lea     r8d, [rcx+1]
0x1400015be  jmp     short loc_1400015C3
0x1400015c0  mov     rdx, rdi
0x1400015c3  mov     rax, [rbp+70h+arg_30]
0x1400015ca  xor     r9d, r9d
0x1400015cd  mov     [rsp+170h+var_100], rax
0x1400015d2  mov     rcx, r10
0x1400015d5  mov     rax, [rbp+70h+arg_28]
0x1400015dc  mov     [rsp+170h+var_110], rax
0x1400015e1  mov     rax, [rbp+70h+arg_20]
0x1400015e8  mov     [rsp+170h+var_120], rax
0x1400015ed  lea     rax, [rsp+170h+var_140]
0x1400015f2  mov     [rbp+70h+var_F0], rdx
0x1400015f6  mov     rdx, r11
0x1400015f9  mov     [rbp+70h+var_E8], r8d
0x1400015fd  xor     r8d, r8d
0x140001600  mov     [rsp+170h+var_148], rax
0x140001605  mov     [rsp+170h+var_150], 12h
0x14000160d  mov     [rbp+70h+var_E4], ebx
0x140001610  mov     [rsp+170h+var_F8], 4
0x140001619  mov     [rsp+170h+var_108], 8
0x140001622  mov     [rsp+170h+var_118], 8
0x14000162b  call    _tlgWriteTransfer_EventWriteTransfer
0x140001630  mov     rcx, [rbp+70h+var_20]
0x140001634  xor     rcx, rsp; StackCookie
0x140001637  call    __security_check_cookie
0x14000163c  mov     rbx, [rsp+170h+arg_10]
0x140001644  add     rsp, 160h
0x14000164b  pop     rdi
0x14000164c  pop     rsi
0x14000164d  pop     rbp
0x14000164e  retn
```
