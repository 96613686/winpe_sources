# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001828`
- end: `0x140001ac4`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `668`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140016cb0`
- `0x140017098`

## callees

- `0x140001828`
- `0x140001f60`
- `0x1400029c0`

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
        const WCHAR **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        const WCHAR **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        const WCHAR **a19)
{
  __int64 v21; // rdx
  int v23; // r9d
  const WCHAR *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  const WCHAR *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const WCHAR *v40; // rcx
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
  const WCHAR *v62; // [rsp+B0h] [rbp-50h]
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
  const WCHAR *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  __int64 v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v80; // [rsp+120h] [rbp+20h]
  int v81; // [rsp+128h] [rbp+28h]
  int v82; // [rsp+12Ch] [rbp+2Ch]
  const WCHAR *v83; // [rsp+130h] [rbp+30h]
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
    v24 = &sourceString;
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
    v28 = &byte_14001BCA1;
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
    v31 = &sourceString;
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
    v34 = &byte_14001BCA1;
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
    v37 = &byte_14001BCA1;
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
    v40 = &sourceString;
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
    v42 = &byte_14001BCA1;
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
    v45 = &byte_14001BCA1;
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
0x140001828  push    rbp
0x14000182a  push    rbx
0x14000182b  push    rsi
0x14000182c  push    rdi
0x14000182d  push    r14
0x14000182f  lea     rbp, [rsp-50h]
0x140001834  sub     rsp, 150h
0x14000183b  mov     rax, cs:__security_cookie
0x140001842  xor     rax, rsp
0x140001845  mov     [rbp+70h+var_30], rax
0x140001849  mov     rax, [rbp+70h+arg_90]
0x140001850  mov     r11, rdx
0x140001853  mov     r10, rcx
0x140001856  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000185a  xor     edi, edi
0x14000185c  mov     rbx, r8
0x14000185f  mov     r9d, 2
0x140001865  mov     rcx, [rax]
0x140001868  test    rcx, rcx
0x14000186b  jz      short loc_140001882
0x14000186d  mov     rax, rdx
0x140001870  inc     rax
0x140001873  cmp     [rcx+rax*2], di
0x140001877  jnz     short loc_140001870
0x140001879  lea     eax, ds:2[rax*2]
0x140001880  jmp     short loc_14000188C
0x140001882  lea     rcx, sourceString
0x140001889  mov     eax, r9d
0x14000188c  mov     [rbp+70h+var_38], eax
0x14000188f  lea     rsi, byte_14001BCA1
0x140001896  mov     rax, [rbp+70h+arg_88]
0x14000189d  mov     r8d, 1
0x1400018a3  mov     [rbp+70h+var_40], rcx
0x1400018a7  mov     [rbp+70h+var_34], edi
0x1400018aa  mov     rcx, [rax]
0x1400018ad  test    rcx, rcx
0x1400018b0  jz      short loc_1400018C2
0x1400018b2  mov     rax, rdx
0x1400018b5  inc     rax
0x1400018b8  cmp     [rcx+rax], dil
0x1400018bc  jnz     short loc_1400018B5
0x1400018be  inc     eax
0x1400018c0  jmp     short loc_1400018C8
0x1400018c2  mov     rcx, rsi
0x1400018c5  mov     eax, r8d
0x1400018c8  mov     [rbp+70h+var_48], eax
0x1400018cb  mov     rax, [rbp+70h+arg_80]
0x1400018d2  mov     [rbp+70h+var_60], rax
0x1400018d6  mov     rax, [rbp+70h+arg_78]
0x1400018dd  mov     [rbp+70h+var_50], rcx
0x1400018e1  mov     [rbp+70h+var_44], edi
0x1400018e4  mov     [rbp+70h+var_58], 4
0x1400018ec  mov     rcx, [rax]
0x1400018ef  test    rcx, rcx
0x1400018f2  jz      short loc_140001909
0x1400018f4  mov     rax, rdx
0x1400018f7  inc     rax
0x1400018fa  cmp     [rcx+rax*2], di
0x1400018fe  jnz     short loc_1400018F7
0x140001900  lea     eax, ds:2[rax*2]
0x140001907  jmp     short loc_140001913
0x140001909  lea     rcx, sourceString
0x140001910  mov     eax, r9d
0x140001913  mov     [rbp+70h+var_68], eax
0x140001916  mov     rax, [rbp+70h+arg_70]
0x14000191d  mov     [rbp+70h+var_70], rcx
0x140001921  mov     [rbp+70h+var_64], edi
0x140001924  mov     rcx, [rax]
0x140001927  test    rcx, rcx
0x14000192a  jz      short loc_14000193C
0x14000192c  mov     rax, rdx
0x14000192f  inc     rax
0x140001932  cmp     [rcx+rax], dil
0x140001936  jnz     short loc_14000192F
0x140001938  inc     eax
0x14000193a  jmp     short loc_140001942
0x14000193c  mov     rcx, rsi
0x14000193f  mov     eax, r8d
0x140001942  mov     [rbp+70h+var_78], eax
0x140001945  mov     rax, [rbp+70h+arg_68]
0x14000194c  mov     [rbp+70h+var_90], rax
0x140001950  mov     rax, [rbp+70h+arg_60]
0x140001957  mov     [rbp+70h+var_80], rcx
0x14000195b  mov     [rbp+70h+var_74], edi
0x14000195e  mov     [rbp+70h+var_88], 4
0x140001966  mov     rcx, [rax]
0x140001969  test    rcx, rcx
0x14000196c  jz      short loc_14000197E
0x14000196e  mov     rax, rdx
0x140001971  inc     rax
0x140001974  cmp     [rcx+rax], dil
0x140001978  jnz     short loc_140001971
0x14000197a  inc     eax
0x14000197c  jmp     short loc_140001984
0x14000197e  mov     rcx, rsi
0x140001981  mov     eax, r8d
0x140001984  mov     [rbp+70h+var_98], eax
0x140001987  mov     rax, [rbp+70h+arg_58]
0x14000198e  mov     [rbp+70h+var_B0], rax
0x140001992  mov     rax, [rbp+70h+arg_50]
0x140001999  mov     [rbp+70h+var_A0], rcx
0x14000199d  mov     [rbp+70h+var_94], edi
0x1400019a0  mov     [rbp+70h+var_A8], 4
0x1400019a8  mov     rcx, [rax]
0x1400019ab  test    rcx, rcx
0x1400019ae  jz      short loc_1400019C6
0x1400019b0  mov     rax, rdx
0x1400019b3  inc     rax
0x1400019b6  cmp     [rcx+rax*2], di
0x1400019ba  jnz     short loc_1400019B3
0x1400019bc  lea     r9d, ds:2[rax*2]
0x1400019c4  jmp     short loc_1400019CD
0x1400019c6  lea     rcx, sourceString
0x1400019cd  mov     rax, [rbp+70h+arg_48]
0x1400019d4  mov     [rbp+70h+var_D0], rax
0x1400019d8  mov     rax, [rbp+70h+arg_40]
0x1400019df  mov     [rbp+70h+var_C0], rcx
0x1400019e3  mov     [rbp+70h+var_B8], r9d
0x1400019e7  mov     [rbp+70h+var_B4], edi
0x1400019ea  mov     rcx, [rax]
0x1400019ed  mov     [rbp+70h+var_C8], 4
0x1400019f5  test    rcx, rcx
0x1400019f8  jz      short loc_140001A0A
0x1400019fa  mov     rax, rdx
0x1400019fd  inc     rax
0x140001a00  cmp     [rcx+rax], dil
0x140001a04  jnz     short loc_1400019FD
0x140001a06  inc     eax
0x140001a08  jmp     short loc_140001A10
0x140001a0a  mov     rcx, rsi
0x140001a0d  mov     eax, r8d
0x140001a10  mov     [rbp+70h+var_D8], eax
0x140001a13  mov     rax, [rbp+70h+arg_38]
0x140001a1a  mov     [rbp+70h+var_F0], rax
0x140001a1e  mov     rax, [rbp+70h+arg_30]
0x140001a25  mov     [rbp+70h+var_E0], rcx
0x140001a29  mov     [rbp+70h+var_D4], edi
0x140001a2c  mov     [rbp+70h+var_E8], 4
0x140001a34  mov     rcx, [rax]
0x140001a37  test    rcx, rcx
0x140001a3a  jz      short loc_140001A4B
0x140001a3c  inc     rdx
0x140001a3f  cmp     [rcx+rdx], dil
0x140001a43  jnz     short loc_140001A3C
0x140001a45  lea     r8d, [rdx+1]
0x140001a49  jmp     short loc_140001A4E
0x140001a4b  mov     rcx, rsi
0x140001a4e  mov     rax, [rbp+70h+arg_28]
0x140001a55  xor     r9d, r9d
0x140001a58  mov     [rsp+170h+var_110], rax
0x140001a5d  mov     rdx, r11
0x140001a60  mov     rax, [rbp+70h+arg_20]
0x140001a67  mov     [rsp+170h+var_120], rax
0x140001a6c  lea     rax, [rsp+170h+var_140]
0x140001a71  mov     [rsp+170h+var_100], rcx
0x140001a76  mov     rcx, r10
0x140001a79  mov     [rsp+170h+var_F8], r8d
0x140001a7e  mov     r8, rbx
0x140001a81  mov     [rsp+170h+var_148], rax
0x140001a86  mov     [rsp+170h+var_150], 11h
0x140001a8e  mov     [rsp+170h+var_F4], edi
0x140001a92  mov     [rsp+170h+var_108], 4
0x140001a9b  mov     [rsp+170h+var_118], 8
0x140001aa4  call    _tlgWriteTransfer_EventWriteTransfer
0x140001aa9  mov     rcx, [rbp+70h+var_30]
0x140001aad  xor     rcx, rsp; StackCookie
0x140001ab0  call    __security_check_cookie
0x140001ab5  add     rsp, 150h
0x140001abc  pop     r14
0x140001abe  pop     rdi
0x140001abf  pop     rsi
0x140001ac0  pop     rbx
0x140001ac1  pop     rbp
0x140001ac2  retn
```
