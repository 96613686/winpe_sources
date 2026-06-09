# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1800017e0`
- end: `0x180001acf`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `751`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008e84`

## callees

- `0x1800017e0`
- `0x180001bb4`
- `0x180003c80`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9,
        __int64 a10,
        char **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        char **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        char **a19,
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
  char *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  char *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  char *v45; // rcx
  __int64 v46; // rax
  const unsigned __int16 *v47; // rcx
  __int64 v48; // rax
  int v49; // eax
  const unsigned __int16 *v50; // rcx
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+30h] [rbp-D0h] BYREF
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
  char *v67; // [rsp+B0h] [rbp-50h]
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
  char *v80; // [rsp+100h] [rbp+0h]
  int v81; // [rsp+108h] [rbp+8h]
  int v82; // [rsp+10Ch] [rbp+Ch]
  __int64 v83; // [rsp+110h] [rbp+10h]
  __int64 v84; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  char *v88; // [rsp+130h] [rbp+30h]
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
    v26 = &word_1804F782A;
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
    while ( *(_WORD *)&v30[2 * v31] );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = byte_1804F7828;
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
    v33 = &word_1804F782A;
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
    while ( *(_WORD *)&v36[2 * v37] );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v36 = byte_1804F7828;
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
    v39 = &word_1804F782A;
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
    v42 = &word_1804F782A;
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
    while ( *(_WORD *)&v45[2 * v46] );
    v29 = 2 * v46 + 2;
  }
  else
  {
    v45 = byte_1804F7828;
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
    v47 = &word_1804F782A;
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
    v50 = &word_1804F782A;
  }
  v55 = a6;
  v53 = a5;
  v57 = v50;
  v58 = v25;
  v59 = 0;
  v56 = 4;
  v54 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0x14u, &v52);
}

```

## disassembly

```asm
0x1800017e0  mov     [rsp-8+arg_10], rbx
0x1800017e5  push    rbp
0x1800017e6  push    rdi
0x1800017e7  push    r14
0x1800017e9  lea     rbp, [rsp-80h]
0x1800017ee  sub     rsp, 180h
0x1800017f5  mov     rax, cs:__security_cookie
0x1800017fc  xor     rax, rsp
0x1800017ff  mov     [rbp+90h+var_20], rax
0x180001803  mov     rax, [rbp+90h+arg_A8]
0x18000180a  lea     rdi, word_1804F782A
0x180001811  mov     r11, rdx
0x180001814  mov     r10, rcx
0x180001817  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000181b  xor     ebx, ebx
0x18000181d  mov     r8d, 1
0x180001823  mov     rcx, [rax]
0x180001826  test    rcx, rcx
0x180001829  jz      short loc_18000183A
0x18000182b  mov     rax, rdx
0x18000182e  inc     rax
0x180001831  cmp     [rcx+rax], bl
0x180001834  jnz     short loc_18000182E
0x180001836  inc     eax
0x180001838  jmp     short loc_180001840
0x18000183a  mov     rcx, rdi
0x18000183d  mov     eax, r8d
0x180001840  mov     [rbp+90h+var_28], eax
0x180001843  mov     r9d, 2
0x180001849  mov     rax, [rbp+90h+arg_A0]
0x180001850  mov     [rbp+90h+var_40], rax
0x180001854  mov     rax, [rbp+90h+arg_98]
0x18000185b  mov     [rbp+90h+var_50], rax
0x18000185f  mov     rax, [rbp+90h+arg_90]
0x180001866  mov     [rbp+90h+var_30], rcx
0x18000186a  mov     [rbp+90h+var_24], ebx
0x18000186d  mov     [rbp+90h+var_38], 4
0x180001875  mov     rcx, [rax]
0x180001878  mov     [rbp+90h+var_48], 4
0x180001880  test    rcx, rcx
0x180001883  jz      short loc_18000189A
0x180001885  mov     rax, rdx
0x180001888  inc     rax
0x18000188b  cmp     [rcx+rax*2], bx
0x18000188f  jnz     short loc_180001888
0x180001891  lea     eax, ds:2[rax*2]
0x180001898  jmp     short loc_1800018A4
0x18000189a  lea     rcx, byte_1804F7828
0x1800018a1  mov     eax, r9d
0x1800018a4  mov     [rbp+90h+var_58], eax
0x1800018a7  mov     rax, [rbp+90h+arg_88]
0x1800018ae  mov     [rbp+90h+var_60], rcx
0x1800018b2  mov     [rbp+90h+var_54], ebx
0x1800018b5  mov     rcx, [rax]
0x1800018b8  test    rcx, rcx
0x1800018bb  jz      short loc_1800018CC
0x1800018bd  mov     rax, rdx
0x1800018c0  inc     rax
0x1800018c3  cmp     [rcx+rax], bl
0x1800018c6  jnz     short loc_1800018C0
0x1800018c8  inc     eax
0x1800018ca  jmp     short loc_1800018D2
0x1800018cc  mov     rcx, rdi
0x1800018cf  mov     eax, r8d
0x1800018d2  mov     [rbp+90h+var_68], eax
0x1800018d5  mov     rax, [rbp+90h+arg_80]
0x1800018dc  mov     [rbp+90h+var_80], rax
0x1800018e0  mov     rax, [rbp+90h+arg_78]
0x1800018e7  mov     [rbp+90h+var_70], rcx
0x1800018eb  mov     [rbp+90h+var_64], ebx
0x1800018ee  mov     [rbp+90h+var_78], 4
0x1800018f6  mov     rcx, [rax]
0x1800018f9  test    rcx, rcx
0x1800018fc  jz      short loc_180001913
0x1800018fe  mov     rax, rdx
0x180001901  inc     rax
0x180001904  cmp     [rcx+rax*2], bx
0x180001908  jnz     short loc_180001901
0x18000190a  lea     eax, ds:2[rax*2]
0x180001911  jmp     short loc_18000191D
0x180001913  lea     rcx, byte_1804F7828
0x18000191a  mov     eax, r9d
0x18000191d  mov     [rbp+90h+var_88], eax
0x180001920  mov     rax, [rbp+90h+arg_70]
0x180001927  mov     [rbp+90h+var_90], rcx
0x18000192b  mov     [rbp+90h+var_84], ebx
0x18000192e  mov     rcx, [rax]
0x180001931  test    rcx, rcx
0x180001934  jz      short loc_180001945
0x180001936  mov     rax, rdx
0x180001939  inc     rax
0x18000193c  cmp     [rcx+rax], bl
0x18000193f  jnz     short loc_180001939
0x180001941  inc     eax
0x180001943  jmp     short loc_18000194B
0x180001945  mov     rcx, rdi
0x180001948  mov     eax, r8d
0x18000194b  mov     [rbp+90h+var_98], eax
0x18000194e  mov     rax, [rbp+90h+arg_68]
0x180001955  mov     [rbp+90h+var_B0], rax
0x180001959  mov     rax, [rbp+90h+arg_60]
0x180001960  mov     [rbp+90h+var_A0], rcx
0x180001964  mov     [rbp+90h+var_94], ebx
0x180001967  mov     [rbp+90h+var_A8], 4
0x18000196f  mov     rcx, [rax]
0x180001972  test    rcx, rcx
0x180001975  jz      short loc_180001986
0x180001977  mov     rax, rdx
0x18000197a  inc     rax
0x18000197d  cmp     [rcx+rax], bl
0x180001980  jnz     short loc_18000197A
0x180001982  inc     eax
0x180001984  jmp     short loc_18000198C
0x180001986  mov     rcx, rdi
0x180001989  mov     eax, r8d
0x18000198c  mov     [rbp+90h+var_B8], eax
0x18000198f  mov     rax, [rbp+90h+arg_58]
0x180001996  mov     [rbp+90h+var_D0], rax
0x18000199a  mov     rax, [rbp+90h+arg_50]
0x1800019a1  mov     [rbp+90h+var_C0], rcx
0x1800019a5  mov     [rbp+90h+var_B4], ebx
0x1800019a8  mov     [rbp+90h+var_C8], 4
0x1800019b0  mov     rcx, [rax]
0x1800019b3  test    rcx, rcx
0x1800019b6  jz      short loc_1800019CE
0x1800019b8  mov     rax, rdx
0x1800019bb  inc     rax
0x1800019be  cmp     [rcx+rax*2], bx
0x1800019c2  jnz     short loc_1800019BB
0x1800019c4  lea     r9d, ds:2[rax*2]
0x1800019cc  jmp     short loc_1800019D5
0x1800019ce  lea     rcx, byte_1804F7828
0x1800019d5  mov     rax, [rbp+90h+arg_48]
0x1800019dc  mov     [rbp+90h+var_F0], rax
0x1800019e0  mov     rax, [rbp+90h+arg_40]
0x1800019e7  mov     [rbp+90h+var_E0], rcx
0x1800019eb  mov     [rbp+90h+var_D8], r9d
0x1800019ef  mov     [rbp+90h+var_D4], ebx
0x1800019f2  mov     rcx, [rax]
0x1800019f5  mov     [rbp+90h+var_E8], 4
0x1800019fd  test    rcx, rcx
0x180001a00  jz      short loc_180001A11
0x180001a02  mov     rax, rdx
0x180001a05  inc     rax
0x180001a08  cmp     [rcx+rax], bl
0x180001a0b  jnz     short loc_180001A05
0x180001a0d  inc     eax
0x180001a0f  jmp     short loc_180001A17
0x180001a11  mov     rcx, rdi
0x180001a14  mov     eax, r8d
0x180001a17  mov     [rbp+90h+var_F8], eax
0x180001a1a  mov     rax, [rbp+90h+arg_38]
0x180001a21  mov     [rbp+90h+var_110], rax
0x180001a25  mov     rax, [rbp+90h+arg_30]
0x180001a2c  mov     [rbp+90h+var_100], rcx
0x180001a30  mov     [rbp+90h+var_F4], ebx
0x180001a33  mov     [rbp+90h+var_108], 4
0x180001a3b  mov     rcx, [rax]
0x180001a3e  test    rcx, rcx
0x180001a41  jz      short loc_180001A51
0x180001a43  inc     rdx
0x180001a46  cmp     [rcx+rdx], bl
0x180001a49  jnz     short loc_180001A43
0x180001a4b  lea     r8d, [rdx+1]
0x180001a4f  jmp     short loc_180001A54
0x180001a51  mov     rcx, rdi
0x180001a54  mov     rax, [rbp+90h+arg_28]
0x180001a5b  xor     r9d, r9d
0x180001a5e  mov     [rsp+190h+var_130], rax
0x180001a63  mov     rdx, r11
0x180001a66  mov     rax, [rbp+90h+arg_20]
0x180001a6d  mov     [rsp+190h+var_140], rax
0x180001a72  lea     rax, [rsp+190h+var_160]
0x180001a77  mov     [rsp+190h+var_120], rcx
0x180001a7c  mov     rcx, r10
0x180001a7f  mov     [rsp+190h+var_118], r8d
0x180001a84  xor     r8d, r8d
0x180001a87  mov     [rsp+190h+var_168], rax
0x180001a8c  mov     [rsp+190h+var_170], 14h
0x180001a94  mov     [rsp+190h+var_114], ebx
0x180001a98  mov     [rsp+190h+var_128], 4
0x180001aa1  mov     [rsp+190h+var_138], 8
0x180001aaa  call    _tlgWriteTransfer_EventWriteTransfer
0x180001aaf  mov     rcx, [rbp+90h+var_20]
0x180001ab3  xor     rcx, rsp; StackCookie
0x180001ab6  call    __security_check_cookie
0x180001abb  mov     rbx, [rsp+190h+arg_10]
0x180001ac3  add     rsp, 180h
0x180001aca  pop     r14
0x180001acc  pop     rdi
0x180001acd  pop     rbp
0x180001ace  retn
```
