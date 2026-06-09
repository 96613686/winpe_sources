# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x140001a48`
- end: `0x140001d37`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z`
- size: `751`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c000`

## callees

- `0x14000113c`
- `0x140001a48`
- `0x1400023d0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const wchar_t **a7,
        __int64 a8,
        const wchar_t **a9,
        __int64 a10,
        void **a11,
        __int64 a12,
        const wchar_t **a13,
        __int64 a14,
        const wchar_t **a15,
        void **a16,
        __int64 a17,
        const wchar_t **a18,
        void **a19,
        __int64 a20,
        __int64 a21,
        const wchar_t **a22)
{
  __int64 v24; // rdx
  int v25; // r8d
  const wchar_t *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int v29; // r9d
  _WORD *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  const wchar_t *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  _WORD *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const wchar_t *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const wchar_t *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  _WORD *v45; // rcx
  __int64 v46; // rax
  const wchar_t *v47; // rcx
  __int64 v48; // rax
  int v49; // eax
  const wchar_t *v50; // rcx
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B0h]
  __int64 v54; // [rsp+58h] [rbp-A8h]
  __int64 v55; // [rsp+60h] [rbp-A0h]
  __int64 v56; // [rsp+68h] [rbp-98h]
  const wchar_t *v57; // [rsp+70h] [rbp-90h]
  int v58; // [rsp+78h] [rbp-88h]
  int v59; // [rsp+7Ch] [rbp-84h]
  __int64 v60; // [rsp+80h] [rbp-80h]
  __int64 v61; // [rsp+88h] [rbp-78h]
  const wchar_t *v62; // [rsp+90h] [rbp-70h]
  int v63; // [rsp+98h] [rbp-68h]
  int v64; // [rsp+9Ch] [rbp-64h]
  __int64 v65; // [rsp+A0h] [rbp-60h]
  __int64 v66; // [rsp+A8h] [rbp-58h]
  _WORD *v67; // [rsp+B0h] [rbp-50h]
  int v68; // [rsp+B8h] [rbp-48h]
  int v69; // [rsp+BCh] [rbp-44h]
  __int64 v70; // [rsp+C0h] [rbp-40h]
  __int64 v71; // [rsp+C8h] [rbp-38h]
  const wchar_t *v72; // [rsp+D0h] [rbp-30h]
  int v73; // [rsp+D8h] [rbp-28h]
  int v74; // [rsp+DCh] [rbp-24h]
  __int64 v75; // [rsp+E0h] [rbp-20h]
  __int64 v76; // [rsp+E8h] [rbp-18h]
  const wchar_t *v77; // [rsp+F0h] [rbp-10h]
  int v78; // [rsp+F8h] [rbp-8h]
  int v79; // [rsp+FCh] [rbp-4h]
  _WORD *v80; // [rsp+100h] [rbp+0h]
  int v81; // [rsp+108h] [rbp+8h]
  int v82; // [rsp+10Ch] [rbp+Ch]
  __int64 v83; // [rsp+110h] [rbp+10h]
  __int64 v84; // [rsp+118h] [rbp+18h]
  const wchar_t *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  _WORD *v88; // [rsp+130h] [rbp+30h]
  int v89; // [rsp+138h] [rbp+38h]
  int v90; // [rsp+13Ch] [rbp+3Ch]
  __int64 v91; // [rsp+140h] [rbp+40h]
  __int64 v92; // [rsp+148h] [rbp+48h]
  __int64 v93; // [rsp+150h] [rbp+50h]
  __int64 v94; // [rsp+158h] [rbp+58h]
  const wchar_t *v95; // [rsp+160h] [rbp+60h]
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
    v26 = &word_140013F31;
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
    while ( v30[v31] );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &unk_140014A6C;
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
    v33 = &word_140013F31;
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
    while ( v36[v37] );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v36 = &unk_140014A6C;
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
    v39 = &word_140013F31;
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
    v42 = &word_140013F31;
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
    while ( v45[v46] );
    v29 = 2 * v46 + 2;
  }
  else
  {
    v45 = &unk_140014A6C;
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
    v47 = &word_140013F31;
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
    v50 = &word_140013F31;
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
0x140001a48  mov     [rsp-8+arg_10], rbx
0x140001a4d  push    rbp
0x140001a4e  push    rdi
0x140001a4f  push    r14
0x140001a51  lea     rbp, [rsp-80h]
0x140001a56  sub     rsp, 180h
0x140001a5d  mov     rax, cs:__security_cookie
0x140001a64  xor     rax, rsp
0x140001a67  mov     [rbp+90h+var_20], rax
0x140001a6b  mov     rax, [rbp+90h+arg_A8]
0x140001a72  lea     rdi, word_140013F31
0x140001a79  mov     r11, rdx
0x140001a7c  mov     r10, rcx
0x140001a7f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140001a83  xor     ebx, ebx
0x140001a85  mov     r8d, 1
0x140001a8b  mov     rcx, [rax]
0x140001a8e  test    rcx, rcx
0x140001a91  jz      short loc_140001AA2
0x140001a93  mov     rax, rdx
0x140001a96  inc     rax
0x140001a99  cmp     [rcx+rax], bl
0x140001a9c  jnz     short loc_140001A96
0x140001a9e  inc     eax
0x140001aa0  jmp     short loc_140001AA8
0x140001aa2  mov     rcx, rdi
0x140001aa5  mov     eax, r8d
0x140001aa8  mov     [rbp+90h+var_28], eax
0x140001aab  mov     r9d, 2
0x140001ab1  mov     rax, [rbp+90h+arg_A0]
0x140001ab8  mov     [rbp+90h+var_40], rax
0x140001abc  mov     rax, [rbp+90h+arg_98]
0x140001ac3  mov     [rbp+90h+var_50], rax
0x140001ac7  mov     rax, [rbp+90h+arg_90]
0x140001ace  mov     [rbp+90h+var_30], rcx
0x140001ad2  mov     [rbp+90h+var_24], ebx
0x140001ad5  mov     [rbp+90h+var_38], 4
0x140001add  mov     rcx, [rax]
0x140001ae0  mov     [rbp+90h+var_48], 4
0x140001ae8  test    rcx, rcx
0x140001aeb  jz      short loc_140001B02
0x140001aed  mov     rax, rdx
0x140001af0  inc     rax
0x140001af3  cmp     [rcx+rax*2], bx
0x140001af7  jnz     short loc_140001AF0
0x140001af9  lea     eax, ds:2[rax*2]
0x140001b00  jmp     short loc_140001B0C
0x140001b02  lea     rcx, unk_140014A6C
0x140001b09  mov     eax, r9d
0x140001b0c  mov     [rbp+90h+var_58], eax
0x140001b0f  mov     rax, [rbp+90h+arg_88]
0x140001b16  mov     [rbp+90h+var_60], rcx
0x140001b1a  mov     [rbp+90h+var_54], ebx
0x140001b1d  mov     rcx, [rax]
0x140001b20  test    rcx, rcx
0x140001b23  jz      short loc_140001B34
0x140001b25  mov     rax, rdx
0x140001b28  inc     rax
0x140001b2b  cmp     [rcx+rax], bl
0x140001b2e  jnz     short loc_140001B28
0x140001b30  inc     eax
0x140001b32  jmp     short loc_140001B3A
0x140001b34  mov     rcx, rdi
0x140001b37  mov     eax, r8d
0x140001b3a  mov     [rbp+90h+var_68], eax
0x140001b3d  mov     rax, [rbp+90h+arg_80]
0x140001b44  mov     [rbp+90h+var_80], rax
0x140001b48  mov     rax, [rbp+90h+arg_78]
0x140001b4f  mov     [rbp+90h+var_70], rcx
0x140001b53  mov     [rbp+90h+var_64], ebx
0x140001b56  mov     [rbp+90h+var_78], 4
0x140001b5e  mov     rcx, [rax]
0x140001b61  test    rcx, rcx
0x140001b64  jz      short loc_140001B7B
0x140001b66  mov     rax, rdx
0x140001b69  inc     rax
0x140001b6c  cmp     [rcx+rax*2], bx
0x140001b70  jnz     short loc_140001B69
0x140001b72  lea     eax, ds:2[rax*2]
0x140001b79  jmp     short loc_140001B85
0x140001b7b  lea     rcx, unk_140014A6C
0x140001b82  mov     eax, r9d
0x140001b85  mov     [rbp+90h+var_88], eax
0x140001b88  mov     rax, [rbp+90h+arg_70]
0x140001b8f  mov     [rbp+90h+var_90], rcx
0x140001b93  mov     [rbp+90h+var_84], ebx
0x140001b96  mov     rcx, [rax]
0x140001b99  test    rcx, rcx
0x140001b9c  jz      short loc_140001BAD
0x140001b9e  mov     rax, rdx
0x140001ba1  inc     rax
0x140001ba4  cmp     [rcx+rax], bl
0x140001ba7  jnz     short loc_140001BA1
0x140001ba9  inc     eax
0x140001bab  jmp     short loc_140001BB3
0x140001bad  mov     rcx, rdi
0x140001bb0  mov     eax, r8d
0x140001bb3  mov     [rbp+90h+var_98], eax
0x140001bb6  mov     rax, [rbp+90h+arg_68]
0x140001bbd  mov     [rbp+90h+var_B0], rax
0x140001bc1  mov     rax, [rbp+90h+arg_60]
0x140001bc8  mov     [rbp+90h+var_A0], rcx
0x140001bcc  mov     [rbp+90h+var_94], ebx
0x140001bcf  mov     [rbp+90h+var_A8], 4
0x140001bd7  mov     rcx, [rax]
0x140001bda  test    rcx, rcx
0x140001bdd  jz      short loc_140001BEE
0x140001bdf  mov     rax, rdx
0x140001be2  inc     rax
0x140001be5  cmp     [rcx+rax], bl
0x140001be8  jnz     short loc_140001BE2
0x140001bea  inc     eax
0x140001bec  jmp     short loc_140001BF4
0x140001bee  mov     rcx, rdi
0x140001bf1  mov     eax, r8d
0x140001bf4  mov     [rbp+90h+var_B8], eax
0x140001bf7  mov     rax, [rbp+90h+arg_58]
0x140001bfe  mov     [rbp+90h+var_D0], rax
0x140001c02  mov     rax, [rbp+90h+arg_50]
0x140001c09  mov     [rbp+90h+var_C0], rcx
0x140001c0d  mov     [rbp+90h+var_B4], ebx
0x140001c10  mov     [rbp+90h+var_C8], 4
0x140001c18  mov     rcx, [rax]
0x140001c1b  test    rcx, rcx
0x140001c1e  jz      short loc_140001C36
0x140001c20  mov     rax, rdx
0x140001c23  inc     rax
0x140001c26  cmp     [rcx+rax*2], bx
0x140001c2a  jnz     short loc_140001C23
0x140001c2c  lea     r9d, ds:2[rax*2]
0x140001c34  jmp     short loc_140001C3D
0x140001c36  lea     rcx, unk_140014A6C
0x140001c3d  mov     rax, [rbp+90h+arg_48]
0x140001c44  mov     [rbp+90h+var_F0], rax
0x140001c48  mov     rax, [rbp+90h+arg_40]
0x140001c4f  mov     [rbp+90h+var_E0], rcx
0x140001c53  mov     [rbp+90h+var_D8], r9d
0x140001c57  mov     [rbp+90h+var_D4], ebx
0x140001c5a  mov     rcx, [rax]
0x140001c5d  mov     [rbp+90h+var_E8], 4
0x140001c65  test    rcx, rcx
0x140001c68  jz      short loc_140001C79
0x140001c6a  mov     rax, rdx
0x140001c6d  inc     rax
0x140001c70  cmp     [rcx+rax], bl
0x140001c73  jnz     short loc_140001C6D
0x140001c75  inc     eax
0x140001c77  jmp     short loc_140001C7F
0x140001c79  mov     rcx, rdi
0x140001c7c  mov     eax, r8d
0x140001c7f  mov     [rbp+90h+var_F8], eax
0x140001c82  mov     rax, [rbp+90h+arg_38]
0x140001c89  mov     [rbp+90h+var_110], rax
0x140001c8d  mov     rax, [rbp+90h+arg_30]
0x140001c94  mov     [rbp+90h+var_100], rcx
0x140001c98  mov     [rbp+90h+var_F4], ebx
0x140001c9b  mov     [rbp+90h+var_108], 4
0x140001ca3  mov     rcx, [rax]
0x140001ca6  test    rcx, rcx
0x140001ca9  jz      short loc_140001CB9
0x140001cab  inc     rdx
0x140001cae  cmp     [rcx+rdx], bl
0x140001cb1  jnz     short loc_140001CAB
0x140001cb3  lea     r8d, [rdx+1]
0x140001cb7  jmp     short loc_140001CBC
0x140001cb9  mov     rcx, rdi
0x140001cbc  mov     rax, [rbp+90h+arg_28]
0x140001cc3  xor     r9d, r9d
0x140001cc6  mov     [rsp+190h+var_130], rax
0x140001ccb  mov     rdx, r11
0x140001cce  mov     rax, [rbp+90h+arg_20]
0x140001cd5  mov     [rsp+190h+var_140], rax
0x140001cda  lea     rax, [rsp+190h+var_160]
0x140001cdf  mov     [rsp+190h+var_120], rcx
0x140001ce4  mov     rcx, r10
0x140001ce7  mov     [rsp+190h+var_118], r8d
0x140001cec  xor     r8d, r8d
0x140001cef  mov     [rsp+190h+var_168], rax
0x140001cf4  mov     [rsp+190h+var_170], 14h
0x140001cfc  mov     [rsp+190h+var_114], ebx
0x140001d00  mov     [rsp+190h+var_128], 4
0x140001d09  mov     [rsp+190h+var_138], 8
0x140001d12  call    _tlgWriteTransfer_EventWriteTransfer
0x140001d17  mov     rcx, [rbp+90h+var_20]
0x140001d1b  xor     rcx, rsp; StackCookie
0x140001d1e  call    __security_check_cookie
0x140001d23  mov     rbx, [rsp+190h+arg_10]
0x140001d2b  add     rsp, 180h
0x140001d32  pop     r14
0x140001d34  pop     rdi
0x140001d35  pop     rbp
0x140001d36  retn
```
