# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x140001acc`
- end: `0x140001dbd`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `753`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140016cb0`
- `0x14001745c`

## callees

- `0x140001acc`
- `0x140001f60`
- `0x1400029c0`

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
        const WCHAR **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        const WCHAR **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        const WCHAR **a19,
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
  const WCHAR *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const WCHAR *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  const WCHAR *v46; // rcx
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
  const WCHAR *v68; // [rsp+B0h] [rbp-50h]
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
  const WCHAR *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+12Ch] [rbp+2Ch]
  const WCHAR *v89; // [rsp+130h] [rbp+30h]
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
    v27 = &byte_14001BCA1;
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
    v31 = &sourceString;
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
    v34 = &byte_14001BCA1;
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
    v37 = &sourceString;
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
    v40 = &byte_14001BCA1;
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
    v43 = &byte_14001BCA1;
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
    v46 = &sourceString;
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
    v48 = &byte_14001BCA1;
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
    v51 = &byte_14001BCA1;
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
0x140001acc  push    rbp
0x140001ace  push    rbx
0x140001acf  push    rsi
0x140001ad0  push    rdi
0x140001ad1  push    r15
0x140001ad3  lea     rbp, [rsp-80h]
0x140001ad8  sub     rsp, 180h
0x140001adf  mov     rax, cs:__security_cookie
0x140001ae6  xor     rax, rsp
0x140001ae9  mov     [rbp+0A0h+var_30], rax
0x140001aed  mov     rax, [rbp+0A0h+arg_A8]
0x140001af4  lea     rsi, byte_14001BCA1
0x140001afb  mov     r11, rdx
0x140001afe  mov     r10, rcx
0x140001b01  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140001b05  xor     edi, edi
0x140001b07  mov     rbx, r8
0x140001b0a  mov     r8d, 1
0x140001b10  mov     rcx, [rax]
0x140001b13  test    rcx, rcx
0x140001b16  jz      short loc_140001B28
0x140001b18  mov     rax, rdx
0x140001b1b  inc     rax
0x140001b1e  cmp     [rcx+rax], dil
0x140001b22  jnz     short loc_140001B1B
0x140001b24  inc     eax
0x140001b26  jmp     short loc_140001B2E
0x140001b28  mov     rcx, rsi
0x140001b2b  mov     eax, r8d
0x140001b2e  mov     [rbp+0A0h+var_38], eax
0x140001b31  mov     r9d, 2
0x140001b37  mov     rax, [rbp+0A0h+arg_A0]
0x140001b3e  mov     [rbp+0A0h+var_50], rax
0x140001b42  mov     rax, [rbp+0A0h+arg_98]
0x140001b49  mov     [rbp+0A0h+var_60], rax
0x140001b4d  mov     rax, [rbp+0A0h+arg_90]
0x140001b54  mov     [rbp+0A0h+var_40], rcx
0x140001b58  mov     [rbp+0A0h+var_34], edi
0x140001b5b  mov     [rbp+0A0h+var_48], 4
0x140001b63  mov     rcx, [rax]
0x140001b66  mov     [rbp+0A0h+var_58], 4
0x140001b6e  test    rcx, rcx
0x140001b71  jz      short loc_140001B88
0x140001b73  mov     rax, rdx
0x140001b76  inc     rax
0x140001b79  cmp     [rcx+rax*2], di
0x140001b7d  jnz     short loc_140001B76
0x140001b7f  lea     eax, ds:2[rax*2]
0x140001b86  jmp     short loc_140001B92
0x140001b88  lea     rcx, sourceString
0x140001b8f  mov     eax, r9d
0x140001b92  mov     [rbp+0A0h+var_68], eax
0x140001b95  mov     rax, [rbp+0A0h+arg_88]
0x140001b9c  mov     [rbp+0A0h+var_70], rcx
0x140001ba0  mov     [rbp+0A0h+var_64], edi
0x140001ba3  mov     rcx, [rax]
0x140001ba6  test    rcx, rcx
0x140001ba9  jz      short loc_140001BBB
0x140001bab  mov     rax, rdx
0x140001bae  inc     rax
0x140001bb1  cmp     [rcx+rax], dil
0x140001bb5  jnz     short loc_140001BAE
0x140001bb7  inc     eax
0x140001bb9  jmp     short loc_140001BC1
0x140001bbb  mov     rcx, rsi
0x140001bbe  mov     eax, r8d
0x140001bc1  mov     [rbp+0A0h+var_78], eax
0x140001bc4  mov     rax, [rbp+0A0h+arg_80]
0x140001bcb  mov     [rbp+0A0h+var_90], rax
0x140001bcf  mov     rax, [rbp+0A0h+arg_78]
0x140001bd6  mov     [rbp+0A0h+var_80], rcx
0x140001bda  mov     [rbp+0A0h+var_74], edi
0x140001bdd  mov     [rbp+0A0h+var_88], 4
0x140001be5  mov     rcx, [rax]
0x140001be8  test    rcx, rcx
0x140001beb  jz      short loc_140001C02
0x140001bed  mov     rax, rdx
0x140001bf0  inc     rax
0x140001bf3  cmp     [rcx+rax*2], di
0x140001bf7  jnz     short loc_140001BF0
0x140001bf9  lea     eax, ds:2[rax*2]
0x140001c00  jmp     short loc_140001C0C
0x140001c02  lea     rcx, sourceString
0x140001c09  mov     eax, r9d
0x140001c0c  mov     [rbp+0A0h+var_98], eax
0x140001c0f  mov     rax, [rbp+0A0h+arg_70]
0x140001c16  mov     [rbp+0A0h+var_A0], rcx
0x140001c1a  mov     [rbp+0A0h+var_94], edi
0x140001c1d  mov     rcx, [rax]
0x140001c20  test    rcx, rcx
0x140001c23  jz      short loc_140001C35
0x140001c25  mov     rax, rdx
0x140001c28  inc     rax
0x140001c2b  cmp     [rcx+rax], dil
0x140001c2f  jnz     short loc_140001C28
0x140001c31  inc     eax
0x140001c33  jmp     short loc_140001C3B
0x140001c35  mov     rcx, rsi
0x140001c38  mov     eax, r8d
0x140001c3b  mov     [rbp+0A0h+var_A8], eax
0x140001c3e  mov     rax, [rbp+0A0h+arg_68]
0x140001c45  mov     [rbp+0A0h+var_C0], rax
0x140001c49  mov     rax, [rbp+0A0h+arg_60]
0x140001c50  mov     [rbp+0A0h+var_B0], rcx
0x140001c54  mov     [rbp+0A0h+var_A4], edi
0x140001c57  mov     [rbp+0A0h+var_B8], 4
0x140001c5f  mov     rcx, [rax]
0x140001c62  test    rcx, rcx
0x140001c65  jz      short loc_140001C77
0x140001c67  mov     rax, rdx
0x140001c6a  inc     rax
0x140001c6d  cmp     [rcx+rax], dil
0x140001c71  jnz     short loc_140001C6A
0x140001c73  inc     eax
0x140001c75  jmp     short loc_140001C7D
0x140001c77  mov     rcx, rsi
0x140001c7a  mov     eax, r8d
0x140001c7d  mov     [rbp+0A0h+var_C8], eax
0x140001c80  mov     rax, [rbp+0A0h+arg_58]
0x140001c87  mov     [rbp+0A0h+var_E0], rax
0x140001c8b  mov     rax, [rbp+0A0h+arg_50]
0x140001c92  mov     [rbp+0A0h+var_D0], rcx
0x140001c96  mov     [rbp+0A0h+var_C4], edi
0x140001c99  mov     [rbp+0A0h+var_D8], 4
0x140001ca1  mov     rcx, [rax]
0x140001ca4  test    rcx, rcx
0x140001ca7  jz      short loc_140001CBF
0x140001ca9  mov     rax, rdx
0x140001cac  inc     rax
0x140001caf  cmp     [rcx+rax*2], di
0x140001cb3  jnz     short loc_140001CAC
0x140001cb5  lea     r9d, ds:2[rax*2]
0x140001cbd  jmp     short loc_140001CC6
0x140001cbf  lea     rcx, sourceString
0x140001cc6  mov     rax, [rbp+0A0h+arg_48]
0x140001ccd  mov     [rbp+0A0h+var_100], rax
0x140001cd1  mov     rax, [rbp+0A0h+arg_40]
0x140001cd8  mov     [rbp+0A0h+var_F0], rcx
0x140001cdc  mov     [rbp+0A0h+var_E8], r9d
0x140001ce0  mov     [rbp+0A0h+var_E4], edi
0x140001ce3  mov     rcx, [rax]
0x140001ce6  mov     [rbp+0A0h+var_F8], 4
0x140001cee  test    rcx, rcx
0x140001cf1  jz      short loc_140001D03
0x140001cf3  mov     rax, rdx
0x140001cf6  inc     rax
0x140001cf9  cmp     [rcx+rax], dil
0x140001cfd  jnz     short loc_140001CF6
0x140001cff  inc     eax
0x140001d01  jmp     short loc_140001D09
0x140001d03  mov     rcx, rsi
0x140001d06  mov     eax, r8d
0x140001d09  mov     [rbp+0A0h+var_108], eax
0x140001d0c  mov     rax, [rbp+0A0h+arg_38]
0x140001d13  mov     [rbp+0A0h+var_120], rax
0x140001d17  mov     rax, [rbp+0A0h+arg_30]
0x140001d1e  mov     [rbp+0A0h+var_110], rcx
0x140001d22  mov     [rbp+0A0h+var_104], edi
0x140001d25  mov     [rbp+0A0h+var_118], 4
0x140001d2d  mov     rcx, [rax]
0x140001d30  test    rcx, rcx
0x140001d33  jz      short loc_140001D44
0x140001d35  inc     rdx
0x140001d38  cmp     [rcx+rdx], dil
0x140001d3c  jnz     short loc_140001D35
0x140001d3e  lea     r8d, [rdx+1]
0x140001d42  jmp     short loc_140001D47
0x140001d44  mov     rcx, rsi
0x140001d47  mov     rax, [rbp+0A0h+arg_28]
0x140001d4e  xor     r9d, r9d
0x140001d51  mov     [rsp+1A0h+var_140], rax
0x140001d56  mov     rdx, r11
0x140001d59  mov     rax, [rbp+0A0h+arg_20]
0x140001d60  mov     [rsp+1A0h+var_150], rax
0x140001d65  lea     rax, [rsp+1A0h+var_170]
0x140001d6a  mov     [rsp+1A0h+var_130], rcx
0x140001d6f  mov     rcx, r10
0x140001d72  mov     [rsp+1A0h+var_128], r8d
0x140001d77  mov     r8, rbx
0x140001d7a  mov     [rsp+1A0h+var_178], rax
0x140001d7f  mov     [rsp+1A0h+var_180], 14h
0x140001d87  mov     [rsp+1A0h+var_124], edi
0x140001d8b  mov     [rsp+1A0h+var_138], 4
0x140001d94  mov     [rsp+1A0h+var_148], 8
0x140001d9d  call    _tlgWriteTransfer_EventWriteTransfer
0x140001da2  mov     rcx, [rbp+0A0h+var_30]
0x140001da6  xor     rcx, rsp; StackCookie
0x140001da9  call    __security_check_cookie
0x140001dae  add     rsp, 180h
0x140001db5  pop     r15
0x140001db7  pop     rdi
0x140001db8  pop     rsi
0x140001db9  pop     rbx
0x140001dba  pop     rbp
0x140001dbb  retn
```
