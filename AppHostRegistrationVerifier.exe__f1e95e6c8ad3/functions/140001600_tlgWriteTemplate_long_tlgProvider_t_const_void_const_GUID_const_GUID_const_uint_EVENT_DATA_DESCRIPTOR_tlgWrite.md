# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x140001600`
- end: `0x1400018f0`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d610`
- `0x14000ddbc`

## callees

- `0x140001600`
- `0x140001b78`
- `0x140002210`

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
        int **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        int **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        int **a19,
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
  int *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  int *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  int *v46; // rcx
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
  int *v68; // [rsp+B0h] [rbp-50h]
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
  int *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+12Ch] [rbp+2Ch]
  int *v89; // [rsp+130h] [rbp+30h]
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
    v27 = &byte_1400140E0;
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
    v31 = &dword_1400140E4;
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
    v34 = &byte_1400140E0;
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
    v37 = &dword_1400140E4;
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
    v40 = &byte_1400140E0;
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
    v43 = &byte_1400140E0;
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
    v46 = &dword_1400140E4;
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
    v48 = &byte_1400140E0;
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
    v51 = &byte_1400140E0;
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
0x140001600  push    rbp
0x140001602  push    rbx
0x140001603  push    rsi
0x140001604  push    rdi
0x140001605  push    r15
0x140001607  lea     rbp, [rsp-80h]
0x14000160c  sub     rsp, 180h
0x140001613  mov     rax, cs:__security_cookie
0x14000161a  xor     rax, rsp
0x14000161d  mov     [rbp+0A0h+var_30], rax
0x140001621  mov     rax, [rbp+0A0h+arg_A8]
0x140001628  lea     rsi, byte_1400140E0
0x14000162f  mov     r11, rdx
0x140001632  mov     r10, rcx
0x140001635  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140001639  xor     edi, edi
0x14000163b  mov     rbx, r8
0x14000163e  mov     r8d, 1
0x140001644  mov     rcx, [rax]
0x140001647  test    rcx, rcx
0x14000164a  jz      short loc_14000165C
0x14000164c  mov     rax, rdx
0x14000164f  inc     rax
0x140001652  cmp     [rcx+rax], dil
0x140001656  jnz     short loc_14000164F
0x140001658  inc     eax
0x14000165a  jmp     short loc_140001662
0x14000165c  mov     rcx, rsi
0x14000165f  mov     eax, r8d
0x140001662  mov     [rbp+0A0h+var_38], eax
0x140001665  mov     r9d, 2
0x14000166b  mov     rax, [rbp+0A0h+arg_A0]
0x140001672  mov     [rbp+0A0h+var_50], rax
0x140001676  mov     rax, [rbp+0A0h+arg_98]
0x14000167d  mov     [rbp+0A0h+var_60], rax
0x140001681  mov     rax, [rbp+0A0h+arg_90]
0x140001688  mov     [rbp+0A0h+var_40], rcx
0x14000168c  mov     [rbp+0A0h+var_34], edi
0x14000168f  mov     [rbp+0A0h+var_48], 4
0x140001697  mov     rcx, [rax]
0x14000169a  mov     [rbp+0A0h+var_58], 4
0x1400016a2  test    rcx, rcx
0x1400016a5  jz      short loc_1400016BC
0x1400016a7  mov     rax, rdx
0x1400016aa  inc     rax
0x1400016ad  cmp     [rcx+rax*2], di
0x1400016b1  jnz     short loc_1400016AA
0x1400016b3  lea     eax, ds:2[rax*2]
0x1400016ba  jmp     short loc_1400016C6
0x1400016bc  lea     rcx, dword_1400140E4
0x1400016c3  mov     eax, r9d
0x1400016c6  mov     [rbp+0A0h+var_68], eax
0x1400016c9  mov     rax, [rbp+0A0h+arg_88]
0x1400016d0  mov     [rbp+0A0h+var_70], rcx
0x1400016d4  mov     [rbp+0A0h+var_64], edi
0x1400016d7  mov     rcx, [rax]
0x1400016da  test    rcx, rcx
0x1400016dd  jz      short loc_1400016EF
0x1400016df  mov     rax, rdx
0x1400016e2  inc     rax
0x1400016e5  cmp     [rcx+rax], dil
0x1400016e9  jnz     short loc_1400016E2
0x1400016eb  inc     eax
0x1400016ed  jmp     short loc_1400016F5
0x1400016ef  mov     rcx, rsi
0x1400016f2  mov     eax, r8d
0x1400016f5  mov     [rbp+0A0h+var_78], eax
0x1400016f8  mov     rax, [rbp+0A0h+arg_80]
0x1400016ff  mov     [rbp+0A0h+var_90], rax
0x140001703  mov     rax, [rbp+0A0h+arg_78]
0x14000170a  mov     [rbp+0A0h+var_80], rcx
0x14000170e  mov     [rbp+0A0h+var_74], edi
0x140001711  mov     [rbp+0A0h+var_88], 4
0x140001719  mov     rcx, [rax]
0x14000171c  test    rcx, rcx
0x14000171f  jz      short loc_140001736
0x140001721  mov     rax, rdx
0x140001724  inc     rax
0x140001727  cmp     [rcx+rax*2], di
0x14000172b  jnz     short loc_140001724
0x14000172d  lea     eax, ds:2[rax*2]
0x140001734  jmp     short loc_140001740
0x140001736  lea     rcx, dword_1400140E4
0x14000173d  mov     eax, r9d
0x140001740  mov     [rbp+0A0h+var_98], eax
0x140001743  mov     rax, [rbp+0A0h+arg_70]
0x14000174a  mov     [rbp+0A0h+var_A0], rcx
0x14000174e  mov     [rbp+0A0h+var_94], edi
0x140001751  mov     rcx, [rax]
0x140001754  test    rcx, rcx
0x140001757  jz      short loc_140001769
0x140001759  mov     rax, rdx
0x14000175c  inc     rax
0x14000175f  cmp     [rcx+rax], dil
0x140001763  jnz     short loc_14000175C
0x140001765  inc     eax
0x140001767  jmp     short loc_14000176F
0x140001769  mov     rcx, rsi
0x14000176c  mov     eax, r8d
0x14000176f  mov     [rbp+0A0h+var_A8], eax
0x140001772  mov     rax, [rbp+0A0h+arg_68]
0x140001779  mov     [rbp+0A0h+var_C0], rax
0x14000177d  mov     rax, [rbp+0A0h+arg_60]
0x140001784  mov     [rbp+0A0h+var_B0], rcx
0x140001788  mov     [rbp+0A0h+var_A4], edi
0x14000178b  mov     [rbp+0A0h+var_B8], 4
0x140001793  mov     rcx, [rax]
0x140001796  test    rcx, rcx
0x140001799  jz      short loc_1400017AB
0x14000179b  mov     rax, rdx
0x14000179e  inc     rax
0x1400017a1  cmp     [rcx+rax], dil
0x1400017a5  jnz     short loc_14000179E
0x1400017a7  inc     eax
0x1400017a9  jmp     short loc_1400017B1
0x1400017ab  mov     rcx, rsi
0x1400017ae  mov     eax, r8d
0x1400017b1  mov     [rbp+0A0h+var_C8], eax
0x1400017b4  mov     rax, [rbp+0A0h+arg_58]
0x1400017bb  mov     [rbp+0A0h+var_E0], rax
0x1400017bf  mov     rax, [rbp+0A0h+arg_50]
0x1400017c6  mov     [rbp+0A0h+var_D0], rcx
0x1400017ca  mov     [rbp+0A0h+var_C4], edi
0x1400017cd  mov     [rbp+0A0h+var_D8], 4
0x1400017d5  mov     rcx, [rax]
0x1400017d8  test    rcx, rcx
0x1400017db  jz      short loc_1400017F3
0x1400017dd  mov     rax, rdx
0x1400017e0  inc     rax
0x1400017e3  cmp     [rcx+rax*2], di
0x1400017e7  jnz     short loc_1400017E0
0x1400017e9  lea     r9d, ds:2[rax*2]
0x1400017f1  jmp     short loc_1400017FA
0x1400017f3  lea     rcx, dword_1400140E4
0x1400017fa  mov     rax, [rbp+0A0h+arg_48]
0x140001801  mov     [rbp+0A0h+var_100], rax
0x140001805  mov     rax, [rbp+0A0h+arg_40]
0x14000180c  mov     [rbp+0A0h+var_F0], rcx
0x140001810  mov     [rbp+0A0h+var_E8], r9d
0x140001814  mov     [rbp+0A0h+var_E4], edi
0x140001817  mov     rcx, [rax]
0x14000181a  mov     [rbp+0A0h+var_F8], 4
0x140001822  test    rcx, rcx
0x140001825  jz      short loc_140001837
0x140001827  mov     rax, rdx
0x14000182a  inc     rax
0x14000182d  cmp     [rcx+rax], dil
0x140001831  jnz     short loc_14000182A
0x140001833  inc     eax
0x140001835  jmp     short loc_14000183D
0x140001837  mov     rcx, rsi
0x14000183a  mov     eax, r8d
0x14000183d  mov     [rbp+0A0h+var_108], eax
0x140001840  mov     rax, [rbp+0A0h+arg_38]
0x140001847  mov     [rbp+0A0h+var_120], rax
0x14000184b  mov     rax, [rbp+0A0h+arg_30]
0x140001852  mov     [rbp+0A0h+var_110], rcx
0x140001856  mov     [rbp+0A0h+var_104], edi
0x140001859  mov     [rbp+0A0h+var_118], 4
0x140001861  mov     rcx, [rax]
0x140001864  test    rcx, rcx
0x140001867  jz      short loc_140001878
0x140001869  inc     rdx
0x14000186c  cmp     [rcx+rdx], dil
0x140001870  jnz     short loc_140001869
0x140001872  lea     r8d, [rdx+1]
0x140001876  jmp     short loc_14000187B
0x140001878  mov     rcx, rsi
0x14000187b  mov     rax, [rbp+0A0h+arg_28]
0x140001882  xor     r9d, r9d
0x140001885  mov     [rsp+1A0h+var_140], rax
0x14000188a  mov     rdx, r11
0x14000188d  mov     rax, [rbp+0A0h+arg_20]
0x140001894  mov     [rsp+1A0h+var_150], rax
0x140001899  lea     rax, [rsp+1A0h+var_170]
0x14000189e  mov     [rsp+1A0h+var_130], rcx
0x1400018a3  mov     rcx, r10
0x1400018a6  mov     [rsp+1A0h+var_128], r8d
0x1400018ab  mov     r8, rbx
0x1400018ae  mov     [rsp+1A0h+var_178], rax
0x1400018b3  mov     [rsp+1A0h+var_180], 14h
0x1400018bb  mov     [rsp+1A0h+var_124], edi
0x1400018bf  mov     [rsp+1A0h+var_138], 4
0x1400018c8  mov     [rsp+1A0h+var_148], 8
0x1400018d1  call    _tlgWriteTransfer_EventWriteTransfer
0x1400018d6  mov     rcx, [rbp+0A0h+var_30]
0x1400018da  xor     rcx, rsp; StackCookie
0x1400018dd  call    __security_check_cookie
0x1400018e2  add     rsp, 180h
0x1400018e9  pop     r15
0x1400018eb  pop     rdi
0x1400018ec  pop     rsi
0x1400018ed  pop     rbx
0x1400018ee  pop     rbp
0x1400018ef  retn
```
