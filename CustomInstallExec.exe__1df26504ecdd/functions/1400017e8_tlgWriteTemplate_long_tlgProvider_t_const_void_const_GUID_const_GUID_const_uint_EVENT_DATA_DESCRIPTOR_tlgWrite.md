# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1400017e8`
- end: `0x140001b55`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperByRef@$0BA@@@U4@U4@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456AEBU?$_tlgWrapperByRef@$0BA@@@6644@Z`
- size: `877`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **, __int64 *, const unsigned __int16 **, const unsigned __int16 **, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000afd4`

## callees

- `0x1400017e8`
- `0x1400025b8`
- `0x1400033b0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
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
        const unsigned __int16 **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        const unsigned __int16 **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        const unsigned __int16 **a20,
        __int64 *a21,
        const unsigned __int16 **a22,
        const unsigned __int16 **a23,
        __int64 a24,
        __int64 a25)
{
  __int64 v27; // rdx
  int v29; // r9d
  const unsigned __int16 *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  const unsigned __int16 *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  int v39; // r8d
  const unsigned __int16 *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  const unsigned __int16 *v46; // rcx
  __int64 v47; // rax
  int v48; // eax
  const unsigned __int16 *v49; // rcx
  __int64 v50; // rax
  int v51; // eax
  const unsigned __int16 *v52; // rcx
  __int64 v53; // rax
  const unsigned __int16 *v54; // rcx
  __int64 v55; // rax
  int v56; // eax
  const unsigned __int16 *v57; // rcx
  _BYTE v59[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v60; // [rsp+50h] [rbp-B0h]
  __int64 v61; // [rsp+58h] [rbp-A8h]
  __int64 v62; // [rsp+60h] [rbp-A0h]
  __int64 v63; // [rsp+68h] [rbp-98h]
  __int64 v64; // [rsp+70h] [rbp-90h]
  __int64 v65; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v66; // [rsp+80h] [rbp-80h]
  int v67; // [rsp+88h] [rbp-78h]
  int v68; // [rsp+8Ch] [rbp-74h]
  __int64 v69; // [rsp+90h] [rbp-70h]
  __int64 v70; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v71; // [rsp+A0h] [rbp-60h]
  int v72; // [rsp+A8h] [rbp-58h]
  int v73; // [rsp+ACh] [rbp-54h]
  __int64 v74; // [rsp+B0h] [rbp-50h]
  __int64 v75; // [rsp+B8h] [rbp-48h]
  const unsigned __int16 *v76; // [rsp+C0h] [rbp-40h]
  int v77; // [rsp+C8h] [rbp-38h]
  int v78; // [rsp+CCh] [rbp-34h]
  __int64 v79; // [rsp+D0h] [rbp-30h]
  __int64 v80; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v81; // [rsp+E0h] [rbp-20h]
  int v82; // [rsp+E8h] [rbp-18h]
  int v83; // [rsp+ECh] [rbp-14h]
  __int64 v84; // [rsp+F0h] [rbp-10h]
  __int64 v85; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v86; // [rsp+100h] [rbp+0h]
  int v87; // [rsp+108h] [rbp+8h]
  int v88; // [rsp+10Ch] [rbp+Ch]
  const unsigned __int16 *v89; // [rsp+110h] [rbp+10h]
  int v90; // [rsp+118h] [rbp+18h]
  int v91; // [rsp+11Ch] [rbp+1Ch]
  __int64 v92; // [rsp+120h] [rbp+20h]
  __int64 v93; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v94; // [rsp+130h] [rbp+30h]
  int v95; // [rsp+138h] [rbp+38h]
  int v96; // [rsp+13Ch] [rbp+3Ch]
  const unsigned __int16 *v97; // [rsp+140h] [rbp+40h]
  int v98; // [rsp+148h] [rbp+48h]
  int v99; // [rsp+14Ch] [rbp+4Ch]
  __int64 v100; // [rsp+150h] [rbp+50h]
  __int64 v101; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v102; // [rsp+160h] [rbp+60h]
  int v103; // [rsp+168h] [rbp+68h]
  int v104; // [rsp+16Ch] [rbp+6Ch]
  const unsigned __int16 *v105; // [rsp+170h] [rbp+70h]
  int v106; // [rsp+178h] [rbp+78h]
  int v107; // [rsp+17Ch] [rbp+7Ch]
  __int64 v108; // [rsp+180h] [rbp+80h]
  __int64 v109; // [rsp+188h] [rbp+88h]
  __int64 v110; // [rsp+190h] [rbp+90h]
  __int64 v111; // [rsp+198h] [rbp+98h]

  v110 = a25;
  v108 = a24;
  v27 = -1;
  v111 = 4;
  v109 = 4;
  v29 = 2;
  v30 = *a23;
  if ( *a23 )
  {
    v31 = -1;
    do
      ++v31;
    while ( v30[v31] );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &qword_140010DA8;
    v32 = 2;
  }
  v106 = v32;
  v105 = v30;
  v107 = 0;
  v33 = *a22;
  if ( *a22 )
  {
    v34 = -1;
    do
      ++v34;
    while ( v33[v34] );
    v35 = 2 * v34 + 2;
  }
  else
  {
    v33 = &qword_140010DA8;
    v35 = 2;
  }
  v103 = v35;
  v102 = v33;
  v104 = 0;
  v101 = 16;
  v100 = *a21;
  v36 = *a20;
  if ( *a20 )
  {
    v37 = -1;
    do
      ++v37;
    while ( v36[v37] );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v36 = &qword_140010DA8;
    v38 = 2;
  }
  v98 = v38;
  v39 = 1;
  v97 = v36;
  v99 = 0;
  v40 = *a19;
  if ( *a19 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_BYTE *)v40 + v41) );
    v42 = v41 + 1;
  }
  else
  {
    v40 = &dword_140010DA4;
    v42 = 1;
  }
  v95 = v42;
  v92 = a18;
  v94 = v40;
  v96 = 0;
  v93 = 4;
  v43 = *a17;
  if ( *a17 )
  {
    v44 = -1;
    do
      ++v44;
    while ( v43[v44] );
    v45 = 2 * v44 + 2;
  }
  else
  {
    v43 = &qword_140010DA8;
    v45 = 2;
  }
  v90 = v45;
  v89 = v43;
  v91 = 0;
  v46 = *a16;
  if ( *a16 )
  {
    v47 = -1;
    do
      ++v47;
    while ( *((_BYTE *)v46 + v47) );
    v48 = v47 + 1;
  }
  else
  {
    v46 = &dword_140010DA4;
    v48 = 1;
  }
  v87 = v48;
  v84 = a15;
  v86 = v46;
  v88 = 0;
  v85 = 4;
  v49 = *a14;
  if ( *a14 )
  {
    v50 = -1;
    do
      ++v50;
    while ( *((_BYTE *)v49 + v50) );
    v51 = v50 + 1;
  }
  else
  {
    v49 = &dword_140010DA4;
    v51 = 1;
  }
  v82 = v51;
  v79 = a13;
  v81 = v49;
  v83 = 0;
  v80 = 4;
  v52 = *a12;
  if ( *a12 )
  {
    v53 = -1;
    do
      ++v53;
    while ( v52[v53] );
    v29 = 2 * v53 + 2;
  }
  else
  {
    v52 = &qword_140010DA8;
  }
  v74 = a11;
  v76 = v52;
  v77 = v29;
  v78 = 0;
  v54 = *a10;
  v75 = 4;
  if ( v54 )
  {
    v55 = -1;
    do
      ++v55;
    while ( *((_BYTE *)v54 + v55) );
    v56 = v55 + 1;
  }
  else
  {
    v54 = &dword_140010DA4;
    v56 = 1;
  }
  v72 = v56;
  v69 = a9;
  v71 = v54;
  v73 = 0;
  v70 = 4;
  v57 = *a8;
  if ( *a8 )
  {
    do
      ++v27;
    while ( *((_BYTE *)v57 + v27) );
    v39 = v27 + 1;
  }
  else
  {
    v57 = &dword_140010DA4;
  }
  v64 = a7;
  v62 = a6;
  v60 = a5;
  v66 = v57;
  v67 = v39;
  v68 = 0;
  v65 = 4;
  v63 = 8;
  v61 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 23, v59);
}

```

## disassembly

```asm
0x1400017e8  mov     [rsp-8+arg_18], rbx
0x1400017ed  push    rbp
0x1400017ee  push    rsi
0x1400017ef  push    rdi
0x1400017f0  push    r14
0x1400017f2  push    r15
0x1400017f4  lea     rbp, [rsp-0B0h]
0x1400017fc  sub     rsp, 1B0h
0x140001803  mov     rax, cs:__security_cookie
0x14000180a  xor     rax, rsp
0x14000180d  mov     [rbp+0D0h+var_30], rax
0x140001814  mov     rax, [rbp+0D0h+arg_C0]
0x14000181b  lea     r14, qword_140010DA8
0x140001822  mov     [rbp+0D0h+var_40], rax
0x140001829  xor     edi, edi
0x14000182b  mov     rax, [rbp+0D0h+arg_B8]
0x140001832  mov     r11, rdx
0x140001835  mov     [rbp+0D0h+var_50], rax
0x14000183c  mov     r10, rcx
0x14000183f  mov     rax, [rbp+0D0h+arg_B0]
0x140001846  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000184a  mov     rbx, r8
0x14000184d  mov     [rbp+0D0h+var_38], 4
0x140001858  mov     [rbp+0D0h+var_48], 4
0x140001863  lea     r9d, [rdi+2]
0x140001867  mov     rcx, [rax]
0x14000186a  test    rcx, rcx
0x14000186d  jz      short loc_140001884
0x14000186f  mov     rax, rdx
0x140001872  inc     rax
0x140001875  cmp     [rcx+rax*2], di
0x140001879  jnz     short loc_140001872
0x14000187b  lea     eax, ds:2[rax*2]
0x140001882  jmp     short loc_14000188A
0x140001884  mov     rcx, r14
0x140001887  mov     eax, r9d
0x14000188a  mov     [rbp+0D0h+var_58], eax
0x14000188d  mov     rax, [rbp+0D0h+arg_A8]
0x140001894  mov     [rbp+0D0h+var_60], rcx
0x140001898  mov     [rbp+0D0h+var_54], edi
0x14000189b  mov     rcx, [rax]
0x14000189e  test    rcx, rcx
0x1400018a1  jz      short loc_1400018B8
0x1400018a3  mov     rax, rdx
0x1400018a6  inc     rax
0x1400018a9  cmp     [rcx+rax*2], di
0x1400018ad  jnz     short loc_1400018A6
0x1400018af  lea     eax, ds:2[rax*2]
0x1400018b6  jmp     short loc_1400018BE
0x1400018b8  mov     rcx, r14
0x1400018bb  mov     eax, r9d
0x1400018be  mov     [rbp+0D0h+var_68], eax
0x1400018c1  mov     rax, [rbp+0D0h+arg_A0]
0x1400018c8  mov     [rbp+0D0h+var_70], rcx
0x1400018cc  mov     [rbp+0D0h+var_64], edi
0x1400018cf  mov     [rbp+0D0h+var_78], 10h
0x1400018d7  mov     rcx, [rax]
0x1400018da  mov     rax, [rbp+0D0h+arg_98]
0x1400018e1  mov     [rbp+0D0h+var_80], rcx
0x1400018e5  mov     rcx, [rax]
0x1400018e8  test    rcx, rcx
0x1400018eb  jz      short loc_140001902
0x1400018ed  mov     rax, rdx
0x1400018f0  inc     rax
0x1400018f3  cmp     [rcx+rax*2], di
0x1400018f7  jnz     short loc_1400018F0
0x1400018f9  lea     eax, ds:2[rax*2]
0x140001900  jmp     short loc_140001908
0x140001902  mov     rcx, r14
0x140001905  mov     eax, r9d
0x140001908  mov     [rbp+0D0h+var_88], eax
0x14000190b  lea     rsi, dword_140010DA4
0x140001912  mov     rax, [rbp+0D0h+arg_90]
0x140001919  mov     r8d, 1
0x14000191f  mov     [rbp+0D0h+var_90], rcx
0x140001923  mov     [rbp+0D0h+var_84], edi
0x140001926  mov     rcx, [rax]
0x140001929  test    rcx, rcx
0x14000192c  jz      short loc_14000193E
0x14000192e  mov     rax, rdx
0x140001931  inc     rax
0x140001934  cmp     [rcx+rax], dil
0x140001938  jnz     short loc_140001931
0x14000193a  inc     eax
0x14000193c  jmp     short loc_140001944
0x14000193e  mov     rcx, rsi
0x140001941  mov     eax, r8d
0x140001944  mov     [rbp+0D0h+var_98], eax
0x140001947  mov     rax, [rbp+0D0h+arg_88]
0x14000194e  mov     [rbp+0D0h+var_B0], rax
0x140001952  mov     rax, [rbp+0D0h+arg_80]
0x140001959  mov     [rbp+0D0h+var_A0], rcx
0x14000195d  mov     [rbp+0D0h+var_94], edi
0x140001960  mov     [rbp+0D0h+var_A8], 4
0x140001968  mov     rcx, [rax]
0x14000196b  test    rcx, rcx
0x14000196e  jz      short loc_140001985
0x140001970  mov     rax, rdx
0x140001973  inc     rax
0x140001976  cmp     [rcx+rax*2], di
0x14000197a  jnz     short loc_140001973
0x14000197c  lea     eax, ds:2[rax*2]
0x140001983  jmp     short loc_14000198B
0x140001985  mov     rcx, r14
0x140001988  mov     eax, r9d
0x14000198b  mov     [rbp+0D0h+var_B8], eax
0x14000198e  mov     rax, [rbp+0D0h+arg_78]
0x140001995  mov     [rbp+0D0h+var_C0], rcx
0x140001999  mov     [rbp+0D0h+var_B4], edi
0x14000199c  mov     rcx, [rax]
0x14000199f  test    rcx, rcx
0x1400019a2  jz      short loc_1400019B4
0x1400019a4  mov     rax, rdx
0x1400019a7  inc     rax
0x1400019aa  cmp     [rcx+rax], dil
0x1400019ae  jnz     short loc_1400019A7
0x1400019b0  inc     eax
0x1400019b2  jmp     short loc_1400019BA
0x1400019b4  mov     rcx, rsi
0x1400019b7  mov     eax, r8d
0x1400019ba  mov     [rbp+0D0h+var_C8], eax
0x1400019bd  mov     rax, [rbp+0D0h+arg_70]
0x1400019c4  mov     [rbp+0D0h+var_E0], rax
0x1400019c8  mov     rax, [rbp+0D0h+arg_68]
0x1400019cf  mov     [rbp+0D0h+var_D0], rcx
0x1400019d3  mov     [rbp+0D0h+var_C4], edi
0x1400019d6  mov     [rbp+0D0h+var_D8], 4
0x1400019de  mov     rcx, [rax]
0x1400019e1  test    rcx, rcx
0x1400019e4  jz      short loc_1400019F6
0x1400019e6  mov     rax, rdx
0x1400019e9  inc     rax
0x1400019ec  cmp     [rcx+rax], dil
0x1400019f0  jnz     short loc_1400019E9
0x1400019f2  inc     eax
0x1400019f4  jmp     short loc_1400019FC
0x1400019f6  mov     rcx, rsi
0x1400019f9  mov     eax, r8d
0x1400019fc  mov     [rbp+0D0h+var_E8], eax
0x1400019ff  mov     rax, [rbp+0D0h+arg_60]
0x140001a06  mov     [rbp+0D0h+var_100], rax
0x140001a0a  mov     rax, [rbp+0D0h+arg_58]
0x140001a11  mov     [rbp+0D0h+var_F0], rcx
0x140001a15  mov     [rbp+0D0h+var_E4], edi
0x140001a18  mov     [rbp+0D0h+var_F8], 4
0x140001a20  mov     rcx, [rax]
0x140001a23  test    rcx, rcx
0x140001a26  jz      short loc_140001A3E
0x140001a28  mov     rax, rdx
0x140001a2b  inc     rax
0x140001a2e  cmp     [rcx+rax*2], di
0x140001a32  jnz     short loc_140001A2B
0x140001a34  lea     r9d, ds:2[rax*2]
0x140001a3c  jmp     short loc_140001A41
0x140001a3e  mov     rcx, r14
0x140001a41  mov     rax, [rbp+0D0h+arg_50]
0x140001a48  mov     [rbp+0D0h+var_120], rax
0x140001a4c  mov     rax, [rbp+0D0h+arg_48]
0x140001a53  mov     [rbp+0D0h+var_110], rcx
0x140001a57  mov     [rbp+0D0h+var_108], r9d
0x140001a5b  mov     [rbp+0D0h+var_104], edi
0x140001a5e  mov     rcx, [rax]
0x140001a61  mov     [rbp+0D0h+var_118], 4
0x140001a69  test    rcx, rcx
0x140001a6c  jz      short loc_140001A7E
0x140001a6e  mov     rax, rdx
0x140001a71  inc     rax
0x140001a74  cmp     [rcx+rax], dil
0x140001a78  jnz     short loc_140001A71
0x140001a7a  inc     eax
0x140001a7c  jmp     short loc_140001A84
0x140001a7e  mov     rcx, rsi
0x140001a81  mov     eax, r8d
0x140001a84  mov     [rbp+0D0h+var_128], eax
0x140001a87  mov     rax, [rbp+0D0h+arg_40]
0x140001a8e  mov     [rbp+0D0h+var_140], rax
0x140001a92  mov     rax, [rbp+0D0h+arg_38]
0x140001a99  mov     [rbp+0D0h+var_130], rcx
0x140001a9d  mov     [rbp+0D0h+var_124], edi
0x140001aa0  mov     [rbp+0D0h+var_138], 4
0x140001aa8  mov     rcx, [rax]
0x140001aab  test    rcx, rcx
0x140001aae  jz      short loc_140001ABF
0x140001ab0  inc     rdx
0x140001ab3  cmp     [rcx+rdx], dil
0x140001ab7  jnz     short loc_140001AB0
0x140001ab9  lea     r8d, [rdx+1]
0x140001abd  jmp     short loc_140001AC2
0x140001abf  mov     rcx, rsi
0x140001ac2  mov     rax, [rbp+0D0h+arg_30]
0x140001ac9  xor     r9d, r9d
0x140001acc  mov     [rsp+1D0h+var_160], rax
0x140001ad1  mov     rdx, r11
0x140001ad4  mov     rax, [rbp+0D0h+arg_28]
0x140001adb  mov     [rsp+1D0h+var_170], rax
0x140001ae0  mov     rax, [rbp+0D0h+arg_20]
0x140001ae7  mov     [rsp+1D0h+var_180], rax
0x140001aec  lea     rax, [rsp+1D0h+var_1A0]
0x140001af1  mov     [rbp+0D0h+var_150], rcx
0x140001af5  mov     rcx, r10
0x140001af8  mov     [rbp+0D0h+var_148], r8d
0x140001afc  mov     r8, rbx
0x140001aff  mov     [rsp+1D0h+var_1A8], rax
0x140001b04  mov     [rsp+1D0h+var_1B0], 17h
0x140001b0c  mov     [rbp+0D0h+var_144], edi
0x140001b0f  mov     [rsp+1D0h+var_158], 4
0x140001b18  mov     [rsp+1D0h+var_168], 8
0x140001b21  mov     [rsp+1D0h+var_178], 8
0x140001b2a  call    _tlgWriteTransfer_EventWriteTransfer
0x140001b2f  mov     rcx, [rbp+0D0h+var_30]
0x140001b36  xor     rcx, rsp; StackCookie
0x140001b39  call    __security_check_cookie
0x140001b3e  mov     rbx, [rsp+1D0h+arg_18]
0x140001b46  add     rsp, 1B0h
0x140001b4d  pop     r15
0x140001b4f  pop     r14
0x140001b51  pop     rdi
0x140001b52  pop     rsi
0x140001b53  pop     rbp
0x140001b54  retn
```
