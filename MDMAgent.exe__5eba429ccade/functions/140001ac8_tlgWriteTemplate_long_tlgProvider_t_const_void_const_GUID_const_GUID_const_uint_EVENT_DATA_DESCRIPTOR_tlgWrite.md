# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x140001ac8`
- end: `0x140001db8`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const WCHAR **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const WCHAR **, __int64, const unsigned __int16 **, const WCHAR **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140016010`
- `0x1400167b4`

## callees

- `0x140001ac8`
- `0x140001f48`
- `0x140002930`

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
    v27 = &byte_14001ACA1;
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
    v34 = &byte_14001ACA1;
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
    v40 = &byte_14001ACA1;
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
    v43 = &byte_14001ACA1;
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
    v48 = &byte_14001ACA1;
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
    v51 = &byte_14001ACA1;
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
0x140001ac8  push    rbp
0x140001aca  push    rbx
0x140001acb  push    rsi
0x140001acc  push    rdi
0x140001acd  push    r15
0x140001acf  lea     rbp, [rsp-80h]
0x140001ad4  sub     rsp, 180h
0x140001adb  mov     rax, cs:__security_cookie
0x140001ae2  xor     rax, rsp
0x140001ae5  mov     [rbp+0A0h+var_30], rax
0x140001ae9  mov     rax, [rbp+0A0h+arg_A8]
0x140001af0  lea     rsi, byte_14001ACA1
0x140001af7  mov     r11, rdx
0x140001afa  mov     r10, rcx
0x140001afd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140001b01  xor     edi, edi
0x140001b03  mov     rbx, r8
0x140001b06  mov     r8d, 1
0x140001b0c  mov     rcx, [rax]
0x140001b0f  test    rcx, rcx
0x140001b12  jz      short loc_140001B24
0x140001b14  mov     rax, rdx
0x140001b17  inc     rax
0x140001b1a  cmp     [rcx+rax], dil
0x140001b1e  jnz     short loc_140001B17
0x140001b20  inc     eax
0x140001b22  jmp     short loc_140001B2A
0x140001b24  mov     rcx, rsi
0x140001b27  mov     eax, r8d
0x140001b2a  mov     [rbp+0A0h+var_38], eax
0x140001b2d  mov     r9d, 2
0x140001b33  mov     rax, [rbp+0A0h+arg_A0]
0x140001b3a  mov     [rbp+0A0h+var_50], rax
0x140001b3e  mov     rax, [rbp+0A0h+arg_98]
0x140001b45  mov     [rbp+0A0h+var_60], rax
0x140001b49  mov     rax, [rbp+0A0h+arg_90]
0x140001b50  mov     [rbp+0A0h+var_40], rcx
0x140001b54  mov     [rbp+0A0h+var_34], edi
0x140001b57  mov     [rbp+0A0h+var_48], 4
0x140001b5f  mov     rcx, [rax]
0x140001b62  mov     [rbp+0A0h+var_58], 4
0x140001b6a  test    rcx, rcx
0x140001b6d  jz      short loc_140001B84
0x140001b6f  mov     rax, rdx
0x140001b72  inc     rax
0x140001b75  cmp     [rcx+rax*2], di
0x140001b79  jnz     short loc_140001B72
0x140001b7b  lea     eax, ds:2[rax*2]
0x140001b82  jmp     short loc_140001B8E
0x140001b84  lea     rcx, sourceString
0x140001b8b  mov     eax, r9d
0x140001b8e  mov     [rbp+0A0h+var_68], eax
0x140001b91  mov     rax, [rbp+0A0h+arg_88]
0x140001b98  mov     [rbp+0A0h+var_70], rcx
0x140001b9c  mov     [rbp+0A0h+var_64], edi
0x140001b9f  mov     rcx, [rax]
0x140001ba2  test    rcx, rcx
0x140001ba5  jz      short loc_140001BB7
0x140001ba7  mov     rax, rdx
0x140001baa  inc     rax
0x140001bad  cmp     [rcx+rax], dil
0x140001bb1  jnz     short loc_140001BAA
0x140001bb3  inc     eax
0x140001bb5  jmp     short loc_140001BBD
0x140001bb7  mov     rcx, rsi
0x140001bba  mov     eax, r8d
0x140001bbd  mov     [rbp+0A0h+var_78], eax
0x140001bc0  mov     rax, [rbp+0A0h+arg_80]
0x140001bc7  mov     [rbp+0A0h+var_90], rax
0x140001bcb  mov     rax, [rbp+0A0h+arg_78]
0x140001bd2  mov     [rbp+0A0h+var_80], rcx
0x140001bd6  mov     [rbp+0A0h+var_74], edi
0x140001bd9  mov     [rbp+0A0h+var_88], 4
0x140001be1  mov     rcx, [rax]
0x140001be4  test    rcx, rcx
0x140001be7  jz      short loc_140001BFE
0x140001be9  mov     rax, rdx
0x140001bec  inc     rax
0x140001bef  cmp     [rcx+rax*2], di
0x140001bf3  jnz     short loc_140001BEC
0x140001bf5  lea     eax, ds:2[rax*2]
0x140001bfc  jmp     short loc_140001C08
0x140001bfe  lea     rcx, sourceString
0x140001c05  mov     eax, r9d
0x140001c08  mov     [rbp+0A0h+var_98], eax
0x140001c0b  mov     rax, [rbp+0A0h+arg_70]
0x140001c12  mov     [rbp+0A0h+var_A0], rcx
0x140001c16  mov     [rbp+0A0h+var_94], edi
0x140001c19  mov     rcx, [rax]
0x140001c1c  test    rcx, rcx
0x140001c1f  jz      short loc_140001C31
0x140001c21  mov     rax, rdx
0x140001c24  inc     rax
0x140001c27  cmp     [rcx+rax], dil
0x140001c2b  jnz     short loc_140001C24
0x140001c2d  inc     eax
0x140001c2f  jmp     short loc_140001C37
0x140001c31  mov     rcx, rsi
0x140001c34  mov     eax, r8d
0x140001c37  mov     [rbp+0A0h+var_A8], eax
0x140001c3a  mov     rax, [rbp+0A0h+arg_68]
0x140001c41  mov     [rbp+0A0h+var_C0], rax
0x140001c45  mov     rax, [rbp+0A0h+arg_60]
0x140001c4c  mov     [rbp+0A0h+var_B0], rcx
0x140001c50  mov     [rbp+0A0h+var_A4], edi
0x140001c53  mov     [rbp+0A0h+var_B8], 4
0x140001c5b  mov     rcx, [rax]
0x140001c5e  test    rcx, rcx
0x140001c61  jz      short loc_140001C73
0x140001c63  mov     rax, rdx
0x140001c66  inc     rax
0x140001c69  cmp     [rcx+rax], dil
0x140001c6d  jnz     short loc_140001C66
0x140001c6f  inc     eax
0x140001c71  jmp     short loc_140001C79
0x140001c73  mov     rcx, rsi
0x140001c76  mov     eax, r8d
0x140001c79  mov     [rbp+0A0h+var_C8], eax
0x140001c7c  mov     rax, [rbp+0A0h+arg_58]
0x140001c83  mov     [rbp+0A0h+var_E0], rax
0x140001c87  mov     rax, [rbp+0A0h+arg_50]
0x140001c8e  mov     [rbp+0A0h+var_D0], rcx
0x140001c92  mov     [rbp+0A0h+var_C4], edi
0x140001c95  mov     [rbp+0A0h+var_D8], 4
0x140001c9d  mov     rcx, [rax]
0x140001ca0  test    rcx, rcx
0x140001ca3  jz      short loc_140001CBB
0x140001ca5  mov     rax, rdx
0x140001ca8  inc     rax
0x140001cab  cmp     [rcx+rax*2], di
0x140001caf  jnz     short loc_140001CA8
0x140001cb1  lea     r9d, ds:2[rax*2]
0x140001cb9  jmp     short loc_140001CC2
0x140001cbb  lea     rcx, sourceString
0x140001cc2  mov     rax, [rbp+0A0h+arg_48]
0x140001cc9  mov     [rbp+0A0h+var_100], rax
0x140001ccd  mov     rax, [rbp+0A0h+arg_40]
0x140001cd4  mov     [rbp+0A0h+var_F0], rcx
0x140001cd8  mov     [rbp+0A0h+var_E8], r9d
0x140001cdc  mov     [rbp+0A0h+var_E4], edi
0x140001cdf  mov     rcx, [rax]
0x140001ce2  mov     [rbp+0A0h+var_F8], 4
0x140001cea  test    rcx, rcx
0x140001ced  jz      short loc_140001CFF
0x140001cef  mov     rax, rdx
0x140001cf2  inc     rax
0x140001cf5  cmp     [rcx+rax], dil
0x140001cf9  jnz     short loc_140001CF2
0x140001cfb  inc     eax
0x140001cfd  jmp     short loc_140001D05
0x140001cff  mov     rcx, rsi
0x140001d02  mov     eax, r8d
0x140001d05  mov     [rbp+0A0h+var_108], eax
0x140001d08  mov     rax, [rbp+0A0h+arg_38]
0x140001d0f  mov     [rbp+0A0h+var_120], rax
0x140001d13  mov     rax, [rbp+0A0h+arg_30]
0x140001d1a  mov     [rbp+0A0h+var_110], rcx
0x140001d1e  mov     [rbp+0A0h+var_104], edi
0x140001d21  mov     [rbp+0A0h+var_118], 4
0x140001d29  mov     rcx, [rax]
0x140001d2c  test    rcx, rcx
0x140001d2f  jz      short loc_140001D40
0x140001d31  inc     rdx
0x140001d34  cmp     [rcx+rdx], dil
0x140001d38  jnz     short loc_140001D31
0x140001d3a  lea     r8d, [rdx+1]
0x140001d3e  jmp     short loc_140001D43
0x140001d40  mov     rcx, rsi
0x140001d43  mov     rax, [rbp+0A0h+arg_28]
0x140001d4a  xor     r9d, r9d
0x140001d4d  mov     [rsp+1A0h+var_140], rax
0x140001d52  mov     rdx, r11
0x140001d55  mov     rax, [rbp+0A0h+arg_20]
0x140001d5c  mov     [rsp+1A0h+var_150], rax
0x140001d61  lea     rax, [rsp+1A0h+var_170]
0x140001d66  mov     [rsp+1A0h+var_130], rcx
0x140001d6b  mov     rcx, r10
0x140001d6e  mov     [rsp+1A0h+var_128], r8d
0x140001d73  mov     r8, rbx
0x140001d76  mov     [rsp+1A0h+var_178], rax
0x140001d7b  mov     [rsp+1A0h+var_180], 14h
0x140001d83  mov     [rsp+1A0h+var_124], edi
0x140001d87  mov     [rsp+1A0h+var_138], 4
0x140001d90  mov     [rsp+1A0h+var_148], 8
0x140001d99  call    _tlgWriteTransfer_EventWriteTransfer
0x140001d9e  mov     rcx, [rbp+0A0h+var_30]
0x140001da2  xor     rcx, rsp; StackCookie
0x140001da5  call    __security_check_cookie
0x140001daa  add     rsp, 180h
0x140001db1  pop     r15
0x140001db3  pop     rdi
0x140001db4  pop     rsi
0x140001db5  pop     rbx
0x140001db6  pop     rbp
0x140001db7  retn
```
