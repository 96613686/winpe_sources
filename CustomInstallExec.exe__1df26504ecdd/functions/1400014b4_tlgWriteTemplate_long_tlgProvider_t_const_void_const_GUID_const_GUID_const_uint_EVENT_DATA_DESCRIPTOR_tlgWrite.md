# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1400014b4`
- end: `0x1400017e2`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperByRef@$0BA@@@U4@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456AEBU?$_tlgWrapperByRef@$0BA@@@634@Z`
- size: `814`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **, __int64 *, const unsigned __int16 **, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ad14`

## callees

- `0x1400014b4`
- `0x1400025b8`
- `0x1400033b0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
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
        __int64 a23,
        __int64 a24)
{
  __int64 v26; // rdx
  int v27; // r9d
  const unsigned __int16 *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  const unsigned __int16 *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  int v35; // r8d
  const unsigned __int16 *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rcx
  __int64 v46; // rax
  int v47; // eax
  const unsigned __int16 *v48; // rcx
  __int64 v49; // rax
  const unsigned __int16 *v50; // rcx
  __int64 v51; // rax
  int v52; // eax
  const unsigned __int16 *v53; // rcx
  _BYTE v55[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v56; // [rsp+50h] [rbp-B0h]
  __int64 v57; // [rsp+58h] [rbp-A8h]
  __int64 v58; // [rsp+60h] [rbp-A0h]
  __int64 v59; // [rsp+68h] [rbp-98h]
  __int64 v60; // [rsp+70h] [rbp-90h]
  __int64 v61; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v62; // [rsp+80h] [rbp-80h]
  int v63; // [rsp+88h] [rbp-78h]
  int v64; // [rsp+8Ch] [rbp-74h]
  __int64 v65; // [rsp+90h] [rbp-70h]
  __int64 v66; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v67; // [rsp+A0h] [rbp-60h]
  int v68; // [rsp+A8h] [rbp-58h]
  int v69; // [rsp+ACh] [rbp-54h]
  __int64 v70; // [rsp+B0h] [rbp-50h]
  __int64 v71; // [rsp+B8h] [rbp-48h]
  const unsigned __int16 *v72; // [rsp+C0h] [rbp-40h]
  int v73; // [rsp+C8h] [rbp-38h]
  int v74; // [rsp+CCh] [rbp-34h]
  __int64 v75; // [rsp+D0h] [rbp-30h]
  __int64 v76; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v77; // [rsp+E0h] [rbp-20h]
  int v78; // [rsp+E8h] [rbp-18h]
  int v79; // [rsp+ECh] [rbp-14h]
  __int64 v80; // [rsp+F0h] [rbp-10h]
  __int64 v81; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v82; // [rsp+100h] [rbp+0h]
  int v83; // [rsp+108h] [rbp+8h]
  int v84; // [rsp+10Ch] [rbp+Ch]
  const unsigned __int16 *v85; // [rsp+110h] [rbp+10h]
  int v86; // [rsp+118h] [rbp+18h]
  int v87; // [rsp+11Ch] [rbp+1Ch]
  __int64 v88; // [rsp+120h] [rbp+20h]
  __int64 v89; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v90; // [rsp+130h] [rbp+30h]
  int v91; // [rsp+138h] [rbp+38h]
  int v92; // [rsp+13Ch] [rbp+3Ch]
  const unsigned __int16 *v93; // [rsp+140h] [rbp+40h]
  int v94; // [rsp+148h] [rbp+48h]
  int v95; // [rsp+14Ch] [rbp+4Ch]
  __int64 v96; // [rsp+150h] [rbp+50h]
  __int64 v97; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v98; // [rsp+160h] [rbp+60h]
  int v99; // [rsp+168h] [rbp+68h]
  int v100; // [rsp+16Ch] [rbp+6Ch]
  __int64 v101; // [rsp+170h] [rbp+70h]
  __int64 v102; // [rsp+178h] [rbp+78h]
  __int64 v103; // [rsp+180h] [rbp+80h]
  __int64 v104; // [rsp+188h] [rbp+88h]

  v103 = a24;
  v101 = a23;
  v26 = -1;
  v27 = 2;
  v104 = 4;
  v102 = 8;
  v29 = *a22;
  if ( *a22 )
  {
    v30 = -1;
    do
      ++v30;
    while ( v29[v30] );
    v31 = 2 * v30 + 2;
  }
  else
  {
    v29 = &qword_140010DA8;
    v31 = 2;
  }
  v99 = v31;
  v98 = v29;
  v100 = 0;
  v97 = 16;
  v96 = *a21;
  v32 = *a20;
  if ( *a20 )
  {
    v33 = -1;
    do
      ++v33;
    while ( v32[v33] );
    v34 = 2 * v33 + 2;
  }
  else
  {
    v32 = &qword_140010DA8;
    v34 = 2;
  }
  v94 = v34;
  v35 = 1;
  v93 = v32;
  v95 = 0;
  v36 = *a19;
  if ( *a19 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_BYTE *)v36 + v37) );
    v38 = v37 + 1;
  }
  else
  {
    v36 = &dword_140010DA4;
    v38 = 1;
  }
  v91 = v38;
  v88 = a18;
  v90 = v36;
  v92 = 0;
  v89 = 4;
  v39 = *a17;
  if ( *a17 )
  {
    v40 = -1;
    do
      ++v40;
    while ( v39[v40] );
    v41 = 2 * v40 + 2;
  }
  else
  {
    v39 = &qword_140010DA8;
    v41 = 2;
  }
  v86 = v41;
  v85 = v39;
  v87 = 0;
  v42 = *a16;
  if ( *a16 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &dword_140010DA4;
    v44 = 1;
  }
  v83 = v44;
  v80 = a15;
  v82 = v42;
  v84 = 0;
  v81 = 4;
  v45 = *a14;
  if ( *a14 )
  {
    v46 = -1;
    do
      ++v46;
    while ( *((_BYTE *)v45 + v46) );
    v47 = v46 + 1;
  }
  else
  {
    v45 = &dword_140010DA4;
    v47 = 1;
  }
  v78 = v47;
  v75 = a13;
  v77 = v45;
  v79 = 0;
  v76 = 4;
  v48 = *a12;
  if ( *a12 )
  {
    v49 = -1;
    do
      ++v49;
    while ( v48[v49] );
    v27 = 2 * v49 + 2;
  }
  else
  {
    v48 = &qword_140010DA8;
  }
  v70 = a11;
  v72 = v48;
  v73 = v27;
  v74 = 0;
  v50 = *a10;
  v71 = 4;
  if ( v50 )
  {
    v51 = -1;
    do
      ++v51;
    while ( *((_BYTE *)v50 + v51) );
    v52 = v51 + 1;
  }
  else
  {
    v50 = &dword_140010DA4;
    v52 = 1;
  }
  v68 = v52;
  v65 = a9;
  v67 = v50;
  v69 = 0;
  v66 = 4;
  v53 = *a8;
  if ( *a8 )
  {
    do
      ++v26;
    while ( *((_BYTE *)v53 + v26) );
    v35 = v26 + 1;
  }
  else
  {
    v53 = &dword_140010DA4;
  }
  v60 = a7;
  v58 = a6;
  v56 = a5;
  v62 = v53;
  v63 = v35;
  v64 = 0;
  v61 = 4;
  v59 = 8;
  v57 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 22, v55);
}

```

## disassembly

```asm
0x1400014b4  push    rbp
0x1400014b6  push    rbx
0x1400014b7  push    rsi
0x1400014b8  push    rdi
0x1400014b9  push    r15
0x1400014bb  lea     rbp, [rsp-0A0h]
0x1400014c3  sub     rsp, 1A0h
0x1400014ca  mov     rax, cs:__security_cookie
0x1400014d1  xor     rax, rsp
0x1400014d4  mov     [rbp+0C0h+var_30], rax
0x1400014db  mov     rax, [rbp+0C0h+arg_B8]
0x1400014e2  xor     edi, edi
0x1400014e4  mov     [rbp+0C0h+var_40], rax
0x1400014eb  mov     r11, rdx
0x1400014ee  mov     rax, [rbp+0C0h+arg_B0]
0x1400014f5  mov     r10, rcx
0x1400014f8  mov     [rbp+0C0h+var_50], rax
0x1400014fc  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140001500  mov     rax, [rbp+0C0h+arg_A8]
0x140001507  lea     r9d, [rdi+2]
0x14000150b  mov     rbx, r8
0x14000150e  mov     [rbp+0C0h+var_38], 4
0x140001519  mov     [rbp+0C0h+var_48], 8
0x140001521  mov     rcx, [rax]
0x140001524  test    rcx, rcx
0x140001527  jz      short loc_14000153E
0x140001529  mov     rax, rdx
0x14000152c  inc     rax
0x14000152f  cmp     [rcx+rax*2], di
0x140001533  jnz     short loc_14000152C
0x140001535  lea     eax, ds:2[rax*2]
0x14000153c  jmp     short loc_140001548
0x14000153e  lea     rcx, qword_140010DA8
0x140001545  mov     eax, r9d
0x140001548  mov     [rbp+0C0h+var_58], eax
0x14000154b  mov     rax, [rbp+0C0h+arg_A0]
0x140001552  mov     [rbp+0C0h+var_60], rcx
0x140001556  mov     [rbp+0C0h+var_54], edi
0x140001559  mov     [rbp+0C0h+var_68], 10h
0x140001561  mov     rcx, [rax]
0x140001564  mov     rax, [rbp+0C0h+arg_98]
0x14000156b  mov     [rbp+0C0h+var_70], rcx
0x14000156f  mov     rcx, [rax]
0x140001572  test    rcx, rcx
0x140001575  jz      short loc_14000158C
0x140001577  mov     rax, rdx
0x14000157a  inc     rax
0x14000157d  cmp     [rcx+rax*2], di
0x140001581  jnz     short loc_14000157A
0x140001583  lea     eax, ds:2[rax*2]
0x14000158a  jmp     short loc_140001596
0x14000158c  lea     rcx, qword_140010DA8
0x140001593  mov     eax, r9d
0x140001596  mov     [rbp+0C0h+var_78], eax
0x140001599  lea     rsi, dword_140010DA4
0x1400015a0  mov     rax, [rbp+0C0h+arg_90]
0x1400015a7  mov     r8d, 1
0x1400015ad  mov     [rbp+0C0h+var_80], rcx
0x1400015b1  mov     [rbp+0C0h+var_74], edi
0x1400015b4  mov     rcx, [rax]
0x1400015b7  test    rcx, rcx
0x1400015ba  jz      short loc_1400015CC
0x1400015bc  mov     rax, rdx
0x1400015bf  inc     rax
0x1400015c2  cmp     [rcx+rax], dil
0x1400015c6  jnz     short loc_1400015BF
0x1400015c8  inc     eax
0x1400015ca  jmp     short loc_1400015D2
0x1400015cc  mov     rcx, rsi
0x1400015cf  mov     eax, r8d
0x1400015d2  mov     [rbp+0C0h+var_88], eax
0x1400015d5  mov     rax, [rbp+0C0h+arg_88]
0x1400015dc  mov     [rbp+0C0h+var_A0], rax
0x1400015e0  mov     rax, [rbp+0C0h+arg_80]
0x1400015e7  mov     [rbp+0C0h+var_90], rcx
0x1400015eb  mov     [rbp+0C0h+var_84], edi
0x1400015ee  mov     [rbp+0C0h+var_98], 4
0x1400015f6  mov     rcx, [rax]
0x1400015f9  test    rcx, rcx
0x1400015fc  jz      short loc_140001613
0x1400015fe  mov     rax, rdx
0x140001601  inc     rax
0x140001604  cmp     [rcx+rax*2], di
0x140001608  jnz     short loc_140001601
0x14000160a  lea     eax, ds:2[rax*2]
0x140001611  jmp     short loc_14000161D
0x140001613  lea     rcx, qword_140010DA8
0x14000161a  mov     eax, r9d
0x14000161d  mov     [rbp+0C0h+var_A8], eax
0x140001620  mov     rax, [rbp+0C0h+arg_78]
0x140001627  mov     [rbp+0C0h+var_B0], rcx
0x14000162b  mov     [rbp+0C0h+var_A4], edi
0x14000162e  mov     rcx, [rax]
0x140001631  test    rcx, rcx
0x140001634  jz      short loc_140001646
0x140001636  mov     rax, rdx
0x140001639  inc     rax
0x14000163c  cmp     [rcx+rax], dil
0x140001640  jnz     short loc_140001639
0x140001642  inc     eax
0x140001644  jmp     short loc_14000164C
0x140001646  mov     rcx, rsi
0x140001649  mov     eax, r8d
0x14000164c  mov     [rbp+0C0h+var_B8], eax
0x14000164f  mov     rax, [rbp+0C0h+arg_70]
0x140001656  mov     [rbp+0C0h+var_D0], rax
0x14000165a  mov     rax, [rbp+0C0h+arg_68]
0x140001661  mov     [rbp+0C0h+var_C0], rcx
0x140001665  mov     [rbp+0C0h+var_B4], edi
0x140001668  mov     [rbp+0C0h+var_C8], 4
0x140001670  mov     rcx, [rax]
0x140001673  test    rcx, rcx
0x140001676  jz      short loc_140001688
0x140001678  mov     rax, rdx
0x14000167b  inc     rax
0x14000167e  cmp     [rcx+rax], dil
0x140001682  jnz     short loc_14000167B
0x140001684  inc     eax
0x140001686  jmp     short loc_14000168E
0x140001688  mov     rcx, rsi
0x14000168b  mov     eax, r8d
0x14000168e  mov     [rbp+0C0h+var_D8], eax
0x140001691  mov     rax, [rbp+0C0h+arg_60]
0x140001698  mov     [rbp+0C0h+var_F0], rax
0x14000169c  mov     rax, [rbp+0C0h+arg_58]
0x1400016a3  mov     [rbp+0C0h+var_E0], rcx
0x1400016a7  mov     [rbp+0C0h+var_D4], edi
0x1400016aa  mov     [rbp+0C0h+var_E8], 4
0x1400016b2  mov     rcx, [rax]
0x1400016b5  test    rcx, rcx
0x1400016b8  jz      short loc_1400016D0
0x1400016ba  mov     rax, rdx
0x1400016bd  inc     rax
0x1400016c0  cmp     [rcx+rax*2], di
0x1400016c4  jnz     short loc_1400016BD
0x1400016c6  lea     r9d, ds:2[rax*2]
0x1400016ce  jmp     short loc_1400016D7
0x1400016d0  lea     rcx, qword_140010DA8
0x1400016d7  mov     rax, [rbp+0C0h+arg_50]
0x1400016de  mov     [rbp+0C0h+var_110], rax
0x1400016e2  mov     rax, [rbp+0C0h+arg_48]
0x1400016e9  mov     [rbp+0C0h+var_100], rcx
0x1400016ed  mov     [rbp+0C0h+var_F8], r9d
0x1400016f1  mov     [rbp+0C0h+var_F4], edi
0x1400016f4  mov     rcx, [rax]
0x1400016f7  mov     [rbp+0C0h+var_108], 4
0x1400016ff  test    rcx, rcx
0x140001702  jz      short loc_140001714
0x140001704  mov     rax, rdx
0x140001707  inc     rax
0x14000170a  cmp     [rcx+rax], dil
0x14000170e  jnz     short loc_140001707
0x140001710  inc     eax
0x140001712  jmp     short loc_14000171A
0x140001714  mov     rcx, rsi
0x140001717  mov     eax, r8d
0x14000171a  mov     [rbp+0C0h+var_118], eax
0x14000171d  mov     rax, [rbp+0C0h+arg_40]
0x140001724  mov     [rbp+0C0h+var_130], rax
0x140001728  mov     rax, [rbp+0C0h+arg_38]
0x14000172f  mov     [rbp+0C0h+var_120], rcx
0x140001733  mov     [rbp+0C0h+var_114], edi
0x140001736  mov     [rbp+0C0h+var_128], 4
0x14000173e  mov     rcx, [rax]
0x140001741  test    rcx, rcx
0x140001744  jz      short loc_140001755
0x140001746  inc     rdx
0x140001749  cmp     [rcx+rdx], dil
0x14000174d  jnz     short loc_140001746
0x14000174f  lea     r8d, [rdx+1]
0x140001753  jmp     short loc_140001758
0x140001755  mov     rcx, rsi
0x140001758  mov     rax, [rbp+0C0h+arg_30]
0x14000175f  xor     r9d, r9d
0x140001762  mov     [rsp+1C0h+var_150], rax
0x140001767  mov     rdx, r11
0x14000176a  mov     rax, [rbp+0C0h+arg_28]
0x140001771  mov     [rsp+1C0h+var_160], rax
0x140001776  mov     rax, [rbp+0C0h+arg_20]
0x14000177d  mov     [rsp+1C0h+var_170], rax
0x140001782  lea     rax, [rsp+1C0h+var_190]
0x140001787  mov     [rbp+0C0h+var_140], rcx
0x14000178b  mov     rcx, r10
0x14000178e  mov     [rbp+0C0h+var_138], r8d
0x140001792  mov     r8, rbx
0x140001795  mov     [rsp+1C0h+var_198], rax
0x14000179a  mov     [rsp+1C0h+var_1A0], 16h
0x1400017a2  mov     [rbp+0C0h+var_134], edi
0x1400017a5  mov     [rsp+1C0h+var_148], 4
0x1400017ae  mov     [rsp+1C0h+var_158], 8
0x1400017b7  mov     [rsp+1C0h+var_168], 8
0x1400017c0  call    _tlgWriteTransfer_EventWriteTransfer
0x1400017c5  mov     rcx, [rbp+0C0h+var_30]
0x1400017cc  xor     rcx, rsp; StackCookie
0x1400017cf  call    __security_check_cookie
0x1400017d4  add     rsp, 1A0h
0x1400017db  pop     r15
0x1400017dd  pop     rdi
0x1400017de  pop     rsi
0x1400017df  pop     rbx
0x1400017e0  pop     rbp
0x1400017e1  retn
```
