# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1400013f0`
- end: `0x1400016fb`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `779`
- prototype: `__int64 __fastcall(int, int, int, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const WCHAR **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const WCHAR **, __int64, const unsigned __int16 **, const WCHAR **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140019bd0`
- `0x140019ea0`
- `0x14001a170`

## callees

- `0x1400013f0`
- `0x140001a8c`
- `0x140002310`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        int a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const unsigned __int16 **a8,
        __int64 a9,
        const unsigned __int16 **a10,
        __int64 a11,
        const WCHAR **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        const WCHAR **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        const WCHAR **a20,
        __int64 a21,
        __int64 a22,
        const unsigned __int16 **a23)
{
  __int64 v25; // rdx
  int v27; // r8d
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  int v31; // r9d
  const WCHAR *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  const unsigned __int16 *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  const WCHAR *v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  const unsigned __int16 *v41; // rcx
  __int64 v42; // rax
  int v43; // eax
  const unsigned __int16 *v44; // rcx
  __int64 v45; // rax
  int v46; // eax
  const WCHAR *v47; // rcx
  __int64 v48; // rax
  const unsigned __int16 *v49; // rcx
  __int64 v50; // rax
  int v51; // eax
  const unsigned __int16 *v52; // rcx
  struct _EVENT_DATA_DESCRIPTOR v54; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v55; // [rsp+50h] [rbp-B0h]
  __int64 v56; // [rsp+58h] [rbp-A8h]
  __int64 v57; // [rsp+60h] [rbp-A0h]
  __int64 v58; // [rsp+68h] [rbp-98h]
  __int64 v59; // [rsp+70h] [rbp-90h]
  __int64 v60; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v61; // [rsp+80h] [rbp-80h]
  int v62; // [rsp+88h] [rbp-78h]
  int v63; // [rsp+8Ch] [rbp-74h]
  __int64 v64; // [rsp+90h] [rbp-70h]
  __int64 v65; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v66; // [rsp+A0h] [rbp-60h]
  int v67; // [rsp+A8h] [rbp-58h]
  int v68; // [rsp+ACh] [rbp-54h]
  __int64 v69; // [rsp+B0h] [rbp-50h]
  __int64 v70; // [rsp+B8h] [rbp-48h]
  const WCHAR *v71; // [rsp+C0h] [rbp-40h]
  int v72; // [rsp+C8h] [rbp-38h]
  int v73; // [rsp+CCh] [rbp-34h]
  __int64 v74; // [rsp+D0h] [rbp-30h]
  __int64 v75; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v76; // [rsp+E0h] [rbp-20h]
  int v77; // [rsp+E8h] [rbp-18h]
  int v78; // [rsp+ECh] [rbp-14h]
  __int64 v79; // [rsp+F0h] [rbp-10h]
  __int64 v80; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  const WCHAR *v84; // [rsp+110h] [rbp+10h]
  int v85; // [rsp+118h] [rbp+18h]
  int v86; // [rsp+11Ch] [rbp+1Ch]
  __int64 v87; // [rsp+120h] [rbp+20h]
  __int64 v88; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v89; // [rsp+130h] [rbp+30h]
  int v90; // [rsp+138h] [rbp+38h]
  int v91; // [rsp+13Ch] [rbp+3Ch]
  const WCHAR *v92; // [rsp+140h] [rbp+40h]
  int v93; // [rsp+148h] [rbp+48h]
  int v94; // [rsp+14Ch] [rbp+4Ch]
  __int64 v95; // [rsp+150h] [rbp+50h]
  __int64 v96; // [rsp+158h] [rbp+58h]
  __int64 v97; // [rsp+160h] [rbp+60h]
  __int64 v98; // [rsp+168h] [rbp+68h]
  const unsigned __int16 *v99; // [rsp+170h] [rbp+70h]
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
    v28 = &byte_1400273CD;
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
    while ( v32[v33] );
    v34 = 2 * v33 + 2;
  }
  else
  {
    v32 = &szPassword;
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
    v35 = &byte_1400273CD;
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
    while ( v38[v39] );
    v40 = 2 * v39 + 2;
  }
  else
  {
    v38 = &szPassword;
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
    v41 = &byte_1400273CD;
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
    v44 = &byte_1400273CD;
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
    while ( v47[v48] );
    v31 = 2 * v48 + 2;
  }
  else
  {
    v47 = &szPassword;
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
    v49 = &byte_1400273CD;
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
    v52 = &byte_1400273CD;
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
0x1400013f0  push    rbp
0x1400013f2  push    rbx
0x1400013f3  push    rsi
0x1400013f4  push    rdi
0x1400013f5  push    r14
0x1400013f7  lea     rbp, [rsp-90h]
0x1400013ff  sub     rsp, 190h
0x140001406  mov     rax, cs:__security_cookie
0x14000140d  xor     rax, rsp
0x140001410  mov     [rbp+0B0h+var_30], rax
0x140001417  mov     rax, [rbp+0B0h+arg_B0]
0x14000141e  lea     rsi, byte_1400273CD
0x140001425  mov     r11, rdx
0x140001428  mov     r10, rcx
0x14000142b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000142f  xor     edi, edi
0x140001431  mov     rbx, r8
0x140001434  mov     r8d, 1
0x14000143a  mov     rcx, [rax]
0x14000143d  test    rcx, rcx
0x140001440  jz      short loc_140001452
0x140001442  mov     rax, rdx
0x140001445  inc     rax
0x140001448  cmp     [rcx+rax], dil
0x14000144c  jnz     short loc_140001445
0x14000144e  inc     eax
0x140001450  jmp     short loc_140001458
0x140001452  mov     rcx, rsi
0x140001455  mov     eax, r8d
0x140001458  mov     [rbp+0B0h+var_38], eax
0x14000145b  mov     r9d, 2
0x140001461  mov     rax, [rbp+0B0h+arg_A8]
0x140001468  mov     [rbp+0B0h+var_50], rax
0x14000146c  mov     rax, [rbp+0B0h+arg_A0]
0x140001473  mov     [rbp+0B0h+var_60], rax
0x140001477  mov     rax, [rbp+0B0h+arg_98]
0x14000147e  mov     [rbp+0B0h+var_40], rcx
0x140001482  mov     [rbp+0B0h+var_34], edi
0x140001485  mov     [rbp+0B0h+var_48], 4
0x14000148d  mov     rcx, [rax]
0x140001490  mov     [rbp+0B0h+var_58], 4
0x140001498  test    rcx, rcx
0x14000149b  jz      short loc_1400014B2
0x14000149d  mov     rax, rdx
0x1400014a0  inc     rax
0x1400014a3  cmp     [rcx+rax*2], di
0x1400014a7  jnz     short loc_1400014A0
0x1400014a9  lea     eax, ds:2[rax*2]
0x1400014b0  jmp     short loc_1400014BC
0x1400014b2  lea     rcx, szPassword
0x1400014b9  mov     eax, r9d
0x1400014bc  mov     [rbp+0B0h+var_68], eax
0x1400014bf  mov     rax, [rbp+0B0h+arg_90]
0x1400014c6  mov     [rbp+0B0h+var_70], rcx
0x1400014ca  mov     [rbp+0B0h+var_64], edi
0x1400014cd  mov     rcx, [rax]
0x1400014d0  test    rcx, rcx
0x1400014d3  jz      short loc_1400014E5
0x1400014d5  mov     rax, rdx
0x1400014d8  inc     rax
0x1400014db  cmp     [rcx+rax], dil
0x1400014df  jnz     short loc_1400014D8
0x1400014e1  inc     eax
0x1400014e3  jmp     short loc_1400014EB
0x1400014e5  mov     rcx, rsi
0x1400014e8  mov     eax, r8d
0x1400014eb  mov     [rbp+0B0h+var_78], eax
0x1400014ee  mov     rax, [rbp+0B0h+arg_88]
0x1400014f5  mov     [rbp+0B0h+var_90], rax
0x1400014f9  mov     rax, [rbp+0B0h+arg_80]
0x140001500  mov     [rbp+0B0h+var_80], rcx
0x140001504  mov     [rbp+0B0h+var_74], edi
0x140001507  mov     [rbp+0B0h+var_88], 4
0x14000150f  mov     rcx, [rax]
0x140001512  test    rcx, rcx
0x140001515  jz      short loc_14000152C
0x140001517  mov     rax, rdx
0x14000151a  inc     rax
0x14000151d  cmp     [rcx+rax*2], di
0x140001521  jnz     short loc_14000151A
0x140001523  lea     eax, ds:2[rax*2]
0x14000152a  jmp     short loc_140001536
0x14000152c  lea     rcx, szPassword
0x140001533  mov     eax, r9d
0x140001536  mov     [rbp+0B0h+var_98], eax
0x140001539  mov     rax, [rbp+0B0h+arg_78]
0x140001540  mov     [rbp+0B0h+var_A0], rcx
0x140001544  mov     [rbp+0B0h+var_94], edi
0x140001547  mov     rcx, [rax]
0x14000154a  test    rcx, rcx
0x14000154d  jz      short loc_14000155F
0x14000154f  mov     rax, rdx
0x140001552  inc     rax
0x140001555  cmp     [rcx+rax], dil
0x140001559  jnz     short loc_140001552
0x14000155b  inc     eax
0x14000155d  jmp     short loc_140001565
0x14000155f  mov     rcx, rsi
0x140001562  mov     eax, r8d
0x140001565  mov     [rbp+0B0h+var_A8], eax
0x140001568  mov     rax, [rbp+0B0h+arg_70]
0x14000156f  mov     [rbp+0B0h+var_C0], rax
0x140001573  mov     rax, [rbp+0B0h+arg_68]
0x14000157a  mov     [rbp+0B0h+var_B0], rcx
0x14000157e  mov     [rbp+0B0h+var_A4], edi
0x140001581  mov     [rbp+0B0h+var_B8], 4
0x140001589  mov     rcx, [rax]
0x14000158c  test    rcx, rcx
0x14000158f  jz      short loc_1400015A1
0x140001591  mov     rax, rdx
0x140001594  inc     rax
0x140001597  cmp     [rcx+rax], dil
0x14000159b  jnz     short loc_140001594
0x14000159d  inc     eax
0x14000159f  jmp     short loc_1400015A7
0x1400015a1  mov     rcx, rsi
0x1400015a4  mov     eax, r8d
0x1400015a7  mov     [rbp+0B0h+var_C8], eax
0x1400015aa  mov     rax, [rbp+0B0h+arg_60]
0x1400015b1  mov     [rbp+0B0h+var_E0], rax
0x1400015b5  mov     rax, [rbp+0B0h+arg_58]
0x1400015bc  mov     [rbp+0B0h+var_D0], rcx
0x1400015c0  mov     [rbp+0B0h+var_C4], edi
0x1400015c3  mov     [rbp+0B0h+var_D8], 4
0x1400015cb  mov     rcx, [rax]
0x1400015ce  test    rcx, rcx
0x1400015d1  jz      short loc_1400015E9
0x1400015d3  mov     rax, rdx
0x1400015d6  inc     rax
0x1400015d9  cmp     [rcx+rax*2], di
0x1400015dd  jnz     short loc_1400015D6
0x1400015df  lea     r9d, ds:2[rax*2]
0x1400015e7  jmp     short loc_1400015F0
0x1400015e9  lea     rcx, szPassword
0x1400015f0  mov     rax, [rbp+0B0h+arg_50]
0x1400015f7  mov     [rbp+0B0h+var_100], rax
0x1400015fb  mov     rax, [rbp+0B0h+arg_48]
0x140001602  mov     [rbp+0B0h+var_F0], rcx
0x140001606  mov     [rbp+0B0h+var_E8], r9d
0x14000160a  mov     [rbp+0B0h+var_E4], edi
0x14000160d  mov     rcx, [rax]
0x140001610  mov     [rbp+0B0h+var_F8], 4
0x140001618  test    rcx, rcx
0x14000161b  jz      short loc_14000162D
0x14000161d  mov     rax, rdx
0x140001620  inc     rax
0x140001623  cmp     [rcx+rax], dil
0x140001627  jnz     short loc_140001620
0x140001629  inc     eax
0x14000162b  jmp     short loc_140001633
0x14000162d  mov     rcx, rsi
0x140001630  mov     eax, r8d
0x140001633  mov     [rbp+0B0h+var_108], eax
0x140001636  mov     rax, [rbp+0B0h+arg_40]
0x14000163d  mov     [rbp+0B0h+var_120], rax
0x140001641  mov     rax, [rbp+0B0h+arg_38]
0x140001648  mov     [rbp+0B0h+var_110], rcx
0x14000164c  mov     [rbp+0B0h+var_104], edi
0x14000164f  mov     [rbp+0B0h+var_118], 4
0x140001657  mov     rcx, [rax]
0x14000165a  test    rcx, rcx
0x14000165d  jz      short loc_14000166E
0x14000165f  inc     rdx
0x140001662  cmp     [rcx+rdx], dil
0x140001666  jnz     short loc_14000165F
0x140001668  lea     r8d, [rdx+1]
0x14000166c  jmp     short loc_140001671
0x14000166e  mov     rcx, rsi
0x140001671  mov     rax, [rbp+0B0h+arg_30]
0x140001678  xor     r9d, r9d; int
0x14000167b  mov     [rsp+1B0h+var_140], rax
0x140001680  mov     rdx, r11; int
0x140001683  mov     rax, [rbp+0B0h+arg_28]
0x14000168a  mov     [rsp+1B0h+var_150], rax
0x14000168f  mov     rax, [rbp+0B0h+arg_20]
0x140001696  mov     [rsp+1B0h+var_160], rax
0x14000169b  lea     rax, [rsp+1B0h+var_180]
0x1400016a0  mov     [rbp+0B0h+var_130], rcx
0x1400016a4  mov     rcx, r10; int
0x1400016a7  mov     [rbp+0B0h+var_128], r8d
0x1400016ab  mov     r8, rbx; int
0x1400016ae  mov     [rsp+1B0h+var_188], rax; PEVENT_DATA_DESCRIPTOR
0x1400016b3  mov     [rsp+1B0h+var_190], 15h; ULONG
0x1400016bb  mov     [rbp+0B0h+var_124], edi
0x1400016be  mov     [rsp+1B0h+var_138], 4
0x1400016c7  mov     [rsp+1B0h+var_148], 8
0x1400016d0  mov     [rsp+1B0h+var_158], 8
0x1400016d9  call    _tlgWriteTransfer_EventWriteTransfer
0x1400016de  mov     rcx, [rbp+0B0h+var_30]
0x1400016e5  xor     rcx, rsp; StackCookie
0x1400016e8  call    __security_check_cookie
0x1400016ed  add     rsp, 190h
0x1400016f4  pop     r14
0x1400016f6  pop     rdi
0x1400016f7  pop     rsi
0x1400016f8  pop     rbx
0x1400016f9  pop     rbp
0x1400016fa  retn
```
