# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x140001560`
- end: `0x140001850`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400083b0`
- `0x140008ab4`

## callees

- `0x140001560`
- `0x14000198c`
- `0x140002a30`

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
        const unsigned __int16 **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        const unsigned __int16 **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        const unsigned __int16 **a19,
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
  const unsigned __int16 *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  const unsigned __int16 *v46; // rcx
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
  const unsigned __int16 *v68; // [rsp+B0h] [rbp-50h]
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
  const unsigned __int16 *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+12Ch] [rbp+2Ch]
  const unsigned __int16 *v89; // [rsp+130h] [rbp+30h]
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
    v27 = &qword_1400150C8;
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
    while ( v31[v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &dword_1400158BC;
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
    v34 = &qword_1400150C8;
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
    while ( v37[v38] );
    v39 = 2 * v38 + 2;
  }
  else
  {
    v37 = &dword_1400158BC;
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
    v40 = &qword_1400150C8;
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
    v43 = &qword_1400150C8;
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
    while ( v46[v47] );
    v30 = 2 * v47 + 2;
  }
  else
  {
    v46 = &dword_1400158BC;
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
    v48 = &qword_1400150C8;
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
    v51 = &qword_1400150C8;
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
0x140001560  push    rbp
0x140001562  push    rbx
0x140001563  push    rsi
0x140001564  push    rdi
0x140001565  push    r15
0x140001567  lea     rbp, [rsp-80h]
0x14000156c  sub     rsp, 180h
0x140001573  mov     rax, cs:__security_cookie
0x14000157a  xor     rax, rsp
0x14000157d  mov     [rbp+0A0h+var_30], rax
0x140001581  mov     rax, [rbp+0A0h+arg_A8]
0x140001588  lea     rsi, qword_1400150C8
0x14000158f  mov     r11, rdx
0x140001592  mov     r10, rcx
0x140001595  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140001599  xor     edi, edi
0x14000159b  mov     rbx, r8
0x14000159e  mov     r8d, 1
0x1400015a4  mov     rcx, [rax]
0x1400015a7  test    rcx, rcx
0x1400015aa  jz      short loc_1400015BC
0x1400015ac  mov     rax, rdx
0x1400015af  inc     rax
0x1400015b2  cmp     [rcx+rax], dil
0x1400015b6  jnz     short loc_1400015AF
0x1400015b8  inc     eax
0x1400015ba  jmp     short loc_1400015C2
0x1400015bc  mov     rcx, rsi
0x1400015bf  mov     eax, r8d
0x1400015c2  mov     [rbp+0A0h+var_38], eax
0x1400015c5  mov     r9d, 2
0x1400015cb  mov     rax, [rbp+0A0h+arg_A0]
0x1400015d2  mov     [rbp+0A0h+var_50], rax
0x1400015d6  mov     rax, [rbp+0A0h+arg_98]
0x1400015dd  mov     [rbp+0A0h+var_60], rax
0x1400015e1  mov     rax, [rbp+0A0h+arg_90]
0x1400015e8  mov     [rbp+0A0h+var_40], rcx
0x1400015ec  mov     [rbp+0A0h+var_34], edi
0x1400015ef  mov     [rbp+0A0h+var_48], 4
0x1400015f7  mov     rcx, [rax]
0x1400015fa  mov     [rbp+0A0h+var_58], 4
0x140001602  test    rcx, rcx
0x140001605  jz      short loc_14000161C
0x140001607  mov     rax, rdx
0x14000160a  inc     rax
0x14000160d  cmp     [rcx+rax*2], di
0x140001611  jnz     short loc_14000160A
0x140001613  lea     eax, ds:2[rax*2]
0x14000161a  jmp     short loc_140001626
0x14000161c  lea     rcx, dword_1400158BC
0x140001623  mov     eax, r9d
0x140001626  mov     [rbp+0A0h+var_68], eax
0x140001629  mov     rax, [rbp+0A0h+arg_88]
0x140001630  mov     [rbp+0A0h+var_70], rcx
0x140001634  mov     [rbp+0A0h+var_64], edi
0x140001637  mov     rcx, [rax]
0x14000163a  test    rcx, rcx
0x14000163d  jz      short loc_14000164F
0x14000163f  mov     rax, rdx
0x140001642  inc     rax
0x140001645  cmp     [rcx+rax], dil
0x140001649  jnz     short loc_140001642
0x14000164b  inc     eax
0x14000164d  jmp     short loc_140001655
0x14000164f  mov     rcx, rsi
0x140001652  mov     eax, r8d
0x140001655  mov     [rbp+0A0h+var_78], eax
0x140001658  mov     rax, [rbp+0A0h+arg_80]
0x14000165f  mov     [rbp+0A0h+var_90], rax
0x140001663  mov     rax, [rbp+0A0h+arg_78]
0x14000166a  mov     [rbp+0A0h+var_80], rcx
0x14000166e  mov     [rbp+0A0h+var_74], edi
0x140001671  mov     [rbp+0A0h+var_88], 4
0x140001679  mov     rcx, [rax]
0x14000167c  test    rcx, rcx
0x14000167f  jz      short loc_140001696
0x140001681  mov     rax, rdx
0x140001684  inc     rax
0x140001687  cmp     [rcx+rax*2], di
0x14000168b  jnz     short loc_140001684
0x14000168d  lea     eax, ds:2[rax*2]
0x140001694  jmp     short loc_1400016A0
0x140001696  lea     rcx, dword_1400158BC
0x14000169d  mov     eax, r9d
0x1400016a0  mov     [rbp+0A0h+var_98], eax
0x1400016a3  mov     rax, [rbp+0A0h+arg_70]
0x1400016aa  mov     [rbp+0A0h+var_A0], rcx
0x1400016ae  mov     [rbp+0A0h+var_94], edi
0x1400016b1  mov     rcx, [rax]
0x1400016b4  test    rcx, rcx
0x1400016b7  jz      short loc_1400016C9
0x1400016b9  mov     rax, rdx
0x1400016bc  inc     rax
0x1400016bf  cmp     [rcx+rax], dil
0x1400016c3  jnz     short loc_1400016BC
0x1400016c5  inc     eax
0x1400016c7  jmp     short loc_1400016CF
0x1400016c9  mov     rcx, rsi
0x1400016cc  mov     eax, r8d
0x1400016cf  mov     [rbp+0A0h+var_A8], eax
0x1400016d2  mov     rax, [rbp+0A0h+arg_68]
0x1400016d9  mov     [rbp+0A0h+var_C0], rax
0x1400016dd  mov     rax, [rbp+0A0h+arg_60]
0x1400016e4  mov     [rbp+0A0h+var_B0], rcx
0x1400016e8  mov     [rbp+0A0h+var_A4], edi
0x1400016eb  mov     [rbp+0A0h+var_B8], 4
0x1400016f3  mov     rcx, [rax]
0x1400016f6  test    rcx, rcx
0x1400016f9  jz      short loc_14000170B
0x1400016fb  mov     rax, rdx
0x1400016fe  inc     rax
0x140001701  cmp     [rcx+rax], dil
0x140001705  jnz     short loc_1400016FE
0x140001707  inc     eax
0x140001709  jmp     short loc_140001711
0x14000170b  mov     rcx, rsi
0x14000170e  mov     eax, r8d
0x140001711  mov     [rbp+0A0h+var_C8], eax
0x140001714  mov     rax, [rbp+0A0h+arg_58]
0x14000171b  mov     [rbp+0A0h+var_E0], rax
0x14000171f  mov     rax, [rbp+0A0h+arg_50]
0x140001726  mov     [rbp+0A0h+var_D0], rcx
0x14000172a  mov     [rbp+0A0h+var_C4], edi
0x14000172d  mov     [rbp+0A0h+var_D8], 4
0x140001735  mov     rcx, [rax]
0x140001738  test    rcx, rcx
0x14000173b  jz      short loc_140001753
0x14000173d  mov     rax, rdx
0x140001740  inc     rax
0x140001743  cmp     [rcx+rax*2], di
0x140001747  jnz     short loc_140001740
0x140001749  lea     r9d, ds:2[rax*2]
0x140001751  jmp     short loc_14000175A
0x140001753  lea     rcx, dword_1400158BC
0x14000175a  mov     rax, [rbp+0A0h+arg_48]
0x140001761  mov     [rbp+0A0h+var_100], rax
0x140001765  mov     rax, [rbp+0A0h+arg_40]
0x14000176c  mov     [rbp+0A0h+var_F0], rcx
0x140001770  mov     [rbp+0A0h+var_E8], r9d
0x140001774  mov     [rbp+0A0h+var_E4], edi
0x140001777  mov     rcx, [rax]
0x14000177a  mov     [rbp+0A0h+var_F8], 4
0x140001782  test    rcx, rcx
0x140001785  jz      short loc_140001797
0x140001787  mov     rax, rdx
0x14000178a  inc     rax
0x14000178d  cmp     [rcx+rax], dil
0x140001791  jnz     short loc_14000178A
0x140001793  inc     eax
0x140001795  jmp     short loc_14000179D
0x140001797  mov     rcx, rsi
0x14000179a  mov     eax, r8d
0x14000179d  mov     [rbp+0A0h+var_108], eax
0x1400017a0  mov     rax, [rbp+0A0h+arg_38]
0x1400017a7  mov     [rbp+0A0h+var_120], rax
0x1400017ab  mov     rax, [rbp+0A0h+arg_30]
0x1400017b2  mov     [rbp+0A0h+var_110], rcx
0x1400017b6  mov     [rbp+0A0h+var_104], edi
0x1400017b9  mov     [rbp+0A0h+var_118], 4
0x1400017c1  mov     rcx, [rax]
0x1400017c4  test    rcx, rcx
0x1400017c7  jz      short loc_1400017D8
0x1400017c9  inc     rdx
0x1400017cc  cmp     [rcx+rdx], dil
0x1400017d0  jnz     short loc_1400017C9
0x1400017d2  lea     r8d, [rdx+1]
0x1400017d6  jmp     short loc_1400017DB
0x1400017d8  mov     rcx, rsi
0x1400017db  mov     rax, [rbp+0A0h+arg_28]
0x1400017e2  xor     r9d, r9d
0x1400017e5  mov     [rsp+1A0h+var_140], rax
0x1400017ea  mov     rdx, r11
0x1400017ed  mov     rax, [rbp+0A0h+arg_20]
0x1400017f4  mov     [rsp+1A0h+var_150], rax
0x1400017f9  lea     rax, [rsp+1A0h+var_170]
0x1400017fe  mov     [rsp+1A0h+var_130], rcx
0x140001803  mov     rcx, r10
0x140001806  mov     [rsp+1A0h+var_128], r8d
0x14000180b  mov     r8, rbx
0x14000180e  mov     [rsp+1A0h+var_178], rax
0x140001813  mov     [rsp+1A0h+var_180], 14h
0x14000181b  mov     [rsp+1A0h+var_124], edi
0x14000181f  mov     [rsp+1A0h+var_138], 4
0x140001828  mov     [rsp+1A0h+var_148], 8
0x140001831  call    _tlgWriteTransfer_EventWriteTransfer
0x140001836  mov     rcx, [rbp+0A0h+var_30]
0x14000183a  xor     rcx, rsp; StackCookie
0x14000183d  call    __security_check_cookie
0x140001842  add     rsp, 180h
0x140001849  pop     r15
0x14000184b  pop     rdi
0x14000184c  pop     rsi
0x14000184d  pop     rbx
0x14000184e  pop     rbp
0x14000184f  retn
```
