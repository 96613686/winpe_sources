# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001560`
- end: `0x180001850`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180008ad0`
- `0x18000a5bc`

## callees

- `0x180001560`
- `0x1800018dc`
- `0x18000c990`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
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
  int v26; // r8d
  const unsigned __int16 *v27; // rcx
  __int64 v28; // rax
  int v29; // eax
  int v30; // r9d
  __int64 *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  __int64 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  __int64 *v46; // rcx
  __int64 v47; // rax
  const unsigned __int16 *v48; // rcx
  __int64 v49; // rax
  int v50; // eax
  const unsigned __int16 *v51; // rcx
  struct _EVENT_DATA_DESCRIPTOR v53; // [rsp+30h] [rbp-D0h] BYREF
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
  __int64 *v68; // [rsp+B0h] [rbp-50h]
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
  __int64 *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+12Ch] [rbp+2Ch]
  __int64 *v89; // [rsp+130h] [rbp+30h]
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
    v27 = &word_18000FECE;
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
    v31 = &qword_180010930;
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
    v34 = &word_18000FECE;
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
    v37 = &qword_180010930;
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
    v40 = &word_18000FECE;
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
    v43 = &word_18000FECE;
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
    v46 = &qword_180010930;
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
    v48 = &word_18000FECE;
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
    v51 = &word_18000FECE;
  }
  v56 = a6;
  v54 = a5;
  v58 = v51;
  v59 = v26;
  v60 = 0;
  v57 = 4;
  v55 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x14u, &v53);
}

```

## disassembly

```asm
0x180001560  push    rbp
0x180001562  push    rbx
0x180001563  push    rsi
0x180001564  push    rdi
0x180001565  push    r15
0x180001567  lea     rbp, [rsp-80h]
0x18000156c  sub     rsp, 180h
0x180001573  mov     rax, cs:__security_cookie
0x18000157a  xor     rax, rsp
0x18000157d  mov     [rbp+0A0h+var_30], rax
0x180001581  mov     rax, [rbp+0A0h+arg_A8]
0x180001588  lea     rsi, word_18000FECE
0x18000158f  mov     r11, rdx
0x180001592  mov     r10, rcx
0x180001595  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001599  xor     edi, edi
0x18000159b  mov     rbx, r8
0x18000159e  mov     r8d, 1
0x1800015a4  mov     rcx, [rax]
0x1800015a7  test    rcx, rcx
0x1800015aa  jz      short loc_1800015BC
0x1800015ac  mov     rax, rdx
0x1800015af  inc     rax
0x1800015b2  cmp     [rcx+rax], dil
0x1800015b6  jnz     short loc_1800015AF
0x1800015b8  inc     eax
0x1800015ba  jmp     short loc_1800015C2
0x1800015bc  mov     rcx, rsi
0x1800015bf  mov     eax, r8d
0x1800015c2  mov     [rbp+0A0h+var_38], eax
0x1800015c5  mov     r9d, 2
0x1800015cb  mov     rax, [rbp+0A0h+arg_A0]
0x1800015d2  mov     [rbp+0A0h+var_50], rax
0x1800015d6  mov     rax, [rbp+0A0h+arg_98]
0x1800015dd  mov     [rbp+0A0h+var_60], rax
0x1800015e1  mov     rax, [rbp+0A0h+arg_90]
0x1800015e8  mov     [rbp+0A0h+var_40], rcx
0x1800015ec  mov     [rbp+0A0h+var_34], edi
0x1800015ef  mov     [rbp+0A0h+var_48], 4
0x1800015f7  mov     rcx, [rax]
0x1800015fa  mov     [rbp+0A0h+var_58], 4
0x180001602  test    rcx, rcx
0x180001605  jz      short loc_18000161C
0x180001607  mov     rax, rdx
0x18000160a  inc     rax
0x18000160d  cmp     [rcx+rax*2], di
0x180001611  jnz     short loc_18000160A
0x180001613  lea     eax, ds:2[rax*2]
0x18000161a  jmp     short loc_180001626
0x18000161c  lea     rcx, qword_180010930
0x180001623  mov     eax, r9d
0x180001626  mov     [rbp+0A0h+var_68], eax
0x180001629  mov     rax, [rbp+0A0h+arg_88]
0x180001630  mov     [rbp+0A0h+var_70], rcx
0x180001634  mov     [rbp+0A0h+var_64], edi
0x180001637  mov     rcx, [rax]
0x18000163a  test    rcx, rcx
0x18000163d  jz      short loc_18000164F
0x18000163f  mov     rax, rdx
0x180001642  inc     rax
0x180001645  cmp     [rcx+rax], dil
0x180001649  jnz     short loc_180001642
0x18000164b  inc     eax
0x18000164d  jmp     short loc_180001655
0x18000164f  mov     rcx, rsi
0x180001652  mov     eax, r8d
0x180001655  mov     [rbp+0A0h+var_78], eax
0x180001658  mov     rax, [rbp+0A0h+arg_80]
0x18000165f  mov     [rbp+0A0h+var_90], rax
0x180001663  mov     rax, [rbp+0A0h+arg_78]
0x18000166a  mov     [rbp+0A0h+var_80], rcx
0x18000166e  mov     [rbp+0A0h+var_74], edi
0x180001671  mov     [rbp+0A0h+var_88], 4
0x180001679  mov     rcx, [rax]
0x18000167c  test    rcx, rcx
0x18000167f  jz      short loc_180001696
0x180001681  mov     rax, rdx
0x180001684  inc     rax
0x180001687  cmp     [rcx+rax*2], di
0x18000168b  jnz     short loc_180001684
0x18000168d  lea     eax, ds:2[rax*2]
0x180001694  jmp     short loc_1800016A0
0x180001696  lea     rcx, qword_180010930
0x18000169d  mov     eax, r9d
0x1800016a0  mov     [rbp+0A0h+var_98], eax
0x1800016a3  mov     rax, [rbp+0A0h+arg_70]
0x1800016aa  mov     [rbp+0A0h+var_A0], rcx
0x1800016ae  mov     [rbp+0A0h+var_94], edi
0x1800016b1  mov     rcx, [rax]
0x1800016b4  test    rcx, rcx
0x1800016b7  jz      short loc_1800016C9
0x1800016b9  mov     rax, rdx
0x1800016bc  inc     rax
0x1800016bf  cmp     [rcx+rax], dil
0x1800016c3  jnz     short loc_1800016BC
0x1800016c5  inc     eax
0x1800016c7  jmp     short loc_1800016CF
0x1800016c9  mov     rcx, rsi
0x1800016cc  mov     eax, r8d
0x1800016cf  mov     [rbp+0A0h+var_A8], eax
0x1800016d2  mov     rax, [rbp+0A0h+arg_68]
0x1800016d9  mov     [rbp+0A0h+var_C0], rax
0x1800016dd  mov     rax, [rbp+0A0h+arg_60]
0x1800016e4  mov     [rbp+0A0h+var_B0], rcx
0x1800016e8  mov     [rbp+0A0h+var_A4], edi
0x1800016eb  mov     [rbp+0A0h+var_B8], 4
0x1800016f3  mov     rcx, [rax]
0x1800016f6  test    rcx, rcx
0x1800016f9  jz      short loc_18000170B
0x1800016fb  mov     rax, rdx
0x1800016fe  inc     rax
0x180001701  cmp     [rcx+rax], dil
0x180001705  jnz     short loc_1800016FE
0x180001707  inc     eax
0x180001709  jmp     short loc_180001711
0x18000170b  mov     rcx, rsi
0x18000170e  mov     eax, r8d
0x180001711  mov     [rbp+0A0h+var_C8], eax
0x180001714  mov     rax, [rbp+0A0h+arg_58]
0x18000171b  mov     [rbp+0A0h+var_E0], rax
0x18000171f  mov     rax, [rbp+0A0h+arg_50]
0x180001726  mov     [rbp+0A0h+var_D0], rcx
0x18000172a  mov     [rbp+0A0h+var_C4], edi
0x18000172d  mov     [rbp+0A0h+var_D8], 4
0x180001735  mov     rcx, [rax]
0x180001738  test    rcx, rcx
0x18000173b  jz      short loc_180001753
0x18000173d  mov     rax, rdx
0x180001740  inc     rax
0x180001743  cmp     [rcx+rax*2], di
0x180001747  jnz     short loc_180001740
0x180001749  lea     r9d, ds:2[rax*2]
0x180001751  jmp     short loc_18000175A
0x180001753  lea     rcx, qword_180010930
0x18000175a  mov     rax, [rbp+0A0h+arg_48]
0x180001761  mov     [rbp+0A0h+var_100], rax
0x180001765  mov     rax, [rbp+0A0h+arg_40]
0x18000176c  mov     [rbp+0A0h+var_F0], rcx
0x180001770  mov     [rbp+0A0h+var_E8], r9d
0x180001774  mov     [rbp+0A0h+var_E4], edi
0x180001777  mov     rcx, [rax]
0x18000177a  mov     [rbp+0A0h+var_F8], 4
0x180001782  test    rcx, rcx
0x180001785  jz      short loc_180001797
0x180001787  mov     rax, rdx
0x18000178a  inc     rax
0x18000178d  cmp     [rcx+rax], dil
0x180001791  jnz     short loc_18000178A
0x180001793  inc     eax
0x180001795  jmp     short loc_18000179D
0x180001797  mov     rcx, rsi
0x18000179a  mov     eax, r8d
0x18000179d  mov     [rbp+0A0h+var_108], eax
0x1800017a0  mov     rax, [rbp+0A0h+arg_38]
0x1800017a7  mov     [rbp+0A0h+var_120], rax
0x1800017ab  mov     rax, [rbp+0A0h+arg_30]
0x1800017b2  mov     [rbp+0A0h+var_110], rcx
0x1800017b6  mov     [rbp+0A0h+var_104], edi
0x1800017b9  mov     [rbp+0A0h+var_118], 4
0x1800017c1  mov     rcx, [rax]
0x1800017c4  test    rcx, rcx
0x1800017c7  jz      short loc_1800017D8
0x1800017c9  inc     rdx
0x1800017cc  cmp     [rcx+rdx], dil
0x1800017d0  jnz     short loc_1800017C9
0x1800017d2  lea     r8d, [rdx+1]
0x1800017d6  jmp     short loc_1800017DB
0x1800017d8  mov     rcx, rsi
0x1800017db  mov     rax, [rbp+0A0h+arg_28]
0x1800017e2  xor     r9d, r9d
0x1800017e5  mov     [rsp+1A0h+var_140], rax
0x1800017ea  mov     rdx, r11
0x1800017ed  mov     rax, [rbp+0A0h+arg_20]
0x1800017f4  mov     [rsp+1A0h+var_150], rax
0x1800017f9  lea     rax, [rsp+1A0h+var_170]
0x1800017fe  mov     [rsp+1A0h+var_130], rcx
0x180001803  mov     rcx, r10
0x180001806  mov     [rsp+1A0h+var_128], r8d
0x18000180b  mov     r8, rbx
0x18000180e  mov     [rsp+1A0h+var_178], rax
0x180001813  mov     [rsp+1A0h+var_180], 14h
0x18000181b  mov     [rsp+1A0h+var_124], edi
0x18000181f  mov     [rsp+1A0h+var_138], 4
0x180001828  mov     [rsp+1A0h+var_148], 8
0x180001831  call    _tlgWriteTransfer_EventWriteTransfer
0x180001836  mov     rcx, [rbp+0A0h+var_30]
0x18000183a  xor     rcx, rsp; StackCookie
0x18000183d  call    __security_check_cookie
0x180001842  add     rsp, 180h
0x180001849  pop     r15
0x18000184b  pop     rdi
0x18000184c  pop     rsi
0x18000184d  pop     rbx
0x18000184e  pop     rbp
0x18000184f  retn
```
