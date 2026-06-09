# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x140001ce0`
- end: `0x140001fd0`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140008e10`
- `0x14000a0b4`

## callees

- `0x140001ce0`
- `0x140002318`
- `0x140002f40`

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
    v27 = &byte_14001C2F5;
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
    v31 = &qword_14001C2F8;
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
    v34 = &byte_14001C2F5;
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
    v37 = &qword_14001C2F8;
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
    v40 = &byte_14001C2F5;
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
    v43 = &byte_14001C2F5;
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
    v46 = &qword_14001C2F8;
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
    v48 = &byte_14001C2F5;
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
    v51 = &byte_14001C2F5;
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
0x140001ce0  push    rbp
0x140001ce2  push    rbx
0x140001ce3  push    rsi
0x140001ce4  push    rdi
0x140001ce5  push    r15
0x140001ce7  lea     rbp, [rsp-80h]
0x140001cec  sub     rsp, 180h
0x140001cf3  mov     rax, cs:__security_cookie
0x140001cfa  xor     rax, rsp
0x140001cfd  mov     [rbp+0A0h+var_30], rax
0x140001d01  mov     rax, [rbp+0A0h+arg_A8]
0x140001d08  lea     rsi, byte_14001C2F5
0x140001d0f  mov     r11, rdx
0x140001d12  mov     r10, rcx
0x140001d15  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140001d19  xor     edi, edi
0x140001d1b  mov     rbx, r8
0x140001d1e  mov     r8d, 1
0x140001d24  mov     rcx, [rax]
0x140001d27  test    rcx, rcx
0x140001d2a  jz      short loc_140001D3C
0x140001d2c  mov     rax, rdx
0x140001d2f  inc     rax
0x140001d32  cmp     [rcx+rax], dil
0x140001d36  jnz     short loc_140001D2F
0x140001d38  inc     eax
0x140001d3a  jmp     short loc_140001D42
0x140001d3c  mov     rcx, rsi
0x140001d3f  mov     eax, r8d
0x140001d42  mov     [rbp+0A0h+var_38], eax
0x140001d45  mov     r9d, 2
0x140001d4b  mov     rax, [rbp+0A0h+arg_A0]
0x140001d52  mov     [rbp+0A0h+var_50], rax
0x140001d56  mov     rax, [rbp+0A0h+arg_98]
0x140001d5d  mov     [rbp+0A0h+var_60], rax
0x140001d61  mov     rax, [rbp+0A0h+arg_90]
0x140001d68  mov     [rbp+0A0h+var_40], rcx
0x140001d6c  mov     [rbp+0A0h+var_34], edi
0x140001d6f  mov     [rbp+0A0h+var_48], 4
0x140001d77  mov     rcx, [rax]
0x140001d7a  mov     [rbp+0A0h+var_58], 4
0x140001d82  test    rcx, rcx
0x140001d85  jz      short loc_140001D9C
0x140001d87  mov     rax, rdx
0x140001d8a  inc     rax
0x140001d8d  cmp     [rcx+rax*2], di
0x140001d91  jnz     short loc_140001D8A
0x140001d93  lea     eax, ds:2[rax*2]
0x140001d9a  jmp     short loc_140001DA6
0x140001d9c  lea     rcx, qword_14001C2F8
0x140001da3  mov     eax, r9d
0x140001da6  mov     [rbp+0A0h+var_68], eax
0x140001da9  mov     rax, [rbp+0A0h+arg_88]
0x140001db0  mov     [rbp+0A0h+var_70], rcx
0x140001db4  mov     [rbp+0A0h+var_64], edi
0x140001db7  mov     rcx, [rax]
0x140001dba  test    rcx, rcx
0x140001dbd  jz      short loc_140001DCF
0x140001dbf  mov     rax, rdx
0x140001dc2  inc     rax
0x140001dc5  cmp     [rcx+rax], dil
0x140001dc9  jnz     short loc_140001DC2
0x140001dcb  inc     eax
0x140001dcd  jmp     short loc_140001DD5
0x140001dcf  mov     rcx, rsi
0x140001dd2  mov     eax, r8d
0x140001dd5  mov     [rbp+0A0h+var_78], eax
0x140001dd8  mov     rax, [rbp+0A0h+arg_80]
0x140001ddf  mov     [rbp+0A0h+var_90], rax
0x140001de3  mov     rax, [rbp+0A0h+arg_78]
0x140001dea  mov     [rbp+0A0h+var_80], rcx
0x140001dee  mov     [rbp+0A0h+var_74], edi
0x140001df1  mov     [rbp+0A0h+var_88], 4
0x140001df9  mov     rcx, [rax]
0x140001dfc  test    rcx, rcx
0x140001dff  jz      short loc_140001E16
0x140001e01  mov     rax, rdx
0x140001e04  inc     rax
0x140001e07  cmp     [rcx+rax*2], di
0x140001e0b  jnz     short loc_140001E04
0x140001e0d  lea     eax, ds:2[rax*2]
0x140001e14  jmp     short loc_140001E20
0x140001e16  lea     rcx, qword_14001C2F8
0x140001e1d  mov     eax, r9d
0x140001e20  mov     [rbp+0A0h+var_98], eax
0x140001e23  mov     rax, [rbp+0A0h+arg_70]
0x140001e2a  mov     [rbp+0A0h+var_A0], rcx
0x140001e2e  mov     [rbp+0A0h+var_94], edi
0x140001e31  mov     rcx, [rax]
0x140001e34  test    rcx, rcx
0x140001e37  jz      short loc_140001E49
0x140001e39  mov     rax, rdx
0x140001e3c  inc     rax
0x140001e3f  cmp     [rcx+rax], dil
0x140001e43  jnz     short loc_140001E3C
0x140001e45  inc     eax
0x140001e47  jmp     short loc_140001E4F
0x140001e49  mov     rcx, rsi
0x140001e4c  mov     eax, r8d
0x140001e4f  mov     [rbp+0A0h+var_A8], eax
0x140001e52  mov     rax, [rbp+0A0h+arg_68]
0x140001e59  mov     [rbp+0A0h+var_C0], rax
0x140001e5d  mov     rax, [rbp+0A0h+arg_60]
0x140001e64  mov     [rbp+0A0h+var_B0], rcx
0x140001e68  mov     [rbp+0A0h+var_A4], edi
0x140001e6b  mov     [rbp+0A0h+var_B8], 4
0x140001e73  mov     rcx, [rax]
0x140001e76  test    rcx, rcx
0x140001e79  jz      short loc_140001E8B
0x140001e7b  mov     rax, rdx
0x140001e7e  inc     rax
0x140001e81  cmp     [rcx+rax], dil
0x140001e85  jnz     short loc_140001E7E
0x140001e87  inc     eax
0x140001e89  jmp     short loc_140001E91
0x140001e8b  mov     rcx, rsi
0x140001e8e  mov     eax, r8d
0x140001e91  mov     [rbp+0A0h+var_C8], eax
0x140001e94  mov     rax, [rbp+0A0h+arg_58]
0x140001e9b  mov     [rbp+0A0h+var_E0], rax
0x140001e9f  mov     rax, [rbp+0A0h+arg_50]
0x140001ea6  mov     [rbp+0A0h+var_D0], rcx
0x140001eaa  mov     [rbp+0A0h+var_C4], edi
0x140001ead  mov     [rbp+0A0h+var_D8], 4
0x140001eb5  mov     rcx, [rax]
0x140001eb8  test    rcx, rcx
0x140001ebb  jz      short loc_140001ED3
0x140001ebd  mov     rax, rdx
0x140001ec0  inc     rax
0x140001ec3  cmp     [rcx+rax*2], di
0x140001ec7  jnz     short loc_140001EC0
0x140001ec9  lea     r9d, ds:2[rax*2]
0x140001ed1  jmp     short loc_140001EDA
0x140001ed3  lea     rcx, qword_14001C2F8
0x140001eda  mov     rax, [rbp+0A0h+arg_48]
0x140001ee1  mov     [rbp+0A0h+var_100], rax
0x140001ee5  mov     rax, [rbp+0A0h+arg_40]
0x140001eec  mov     [rbp+0A0h+var_F0], rcx
0x140001ef0  mov     [rbp+0A0h+var_E8], r9d
0x140001ef4  mov     [rbp+0A0h+var_E4], edi
0x140001ef7  mov     rcx, [rax]
0x140001efa  mov     [rbp+0A0h+var_F8], 4
0x140001f02  test    rcx, rcx
0x140001f05  jz      short loc_140001F17
0x140001f07  mov     rax, rdx
0x140001f0a  inc     rax
0x140001f0d  cmp     [rcx+rax], dil
0x140001f11  jnz     short loc_140001F0A
0x140001f13  inc     eax
0x140001f15  jmp     short loc_140001F1D
0x140001f17  mov     rcx, rsi
0x140001f1a  mov     eax, r8d
0x140001f1d  mov     [rbp+0A0h+var_108], eax
0x140001f20  mov     rax, [rbp+0A0h+arg_38]
0x140001f27  mov     [rbp+0A0h+var_120], rax
0x140001f2b  mov     rax, [rbp+0A0h+arg_30]
0x140001f32  mov     [rbp+0A0h+var_110], rcx
0x140001f36  mov     [rbp+0A0h+var_104], edi
0x140001f39  mov     [rbp+0A0h+var_118], 4
0x140001f41  mov     rcx, [rax]
0x140001f44  test    rcx, rcx
0x140001f47  jz      short loc_140001F58
0x140001f49  inc     rdx
0x140001f4c  cmp     [rcx+rdx], dil
0x140001f50  jnz     short loc_140001F49
0x140001f52  lea     r8d, [rdx+1]
0x140001f56  jmp     short loc_140001F5B
0x140001f58  mov     rcx, rsi
0x140001f5b  mov     rax, [rbp+0A0h+arg_28]
0x140001f62  xor     r9d, r9d
0x140001f65  mov     [rsp+1A0h+var_140], rax
0x140001f6a  mov     rdx, r11
0x140001f6d  mov     rax, [rbp+0A0h+arg_20]
0x140001f74  mov     [rsp+1A0h+var_150], rax
0x140001f79  lea     rax, [rsp+1A0h+var_170]
0x140001f7e  mov     [rsp+1A0h+var_130], rcx
0x140001f83  mov     rcx, r10
0x140001f86  mov     [rsp+1A0h+var_128], r8d
0x140001f8b  mov     r8, rbx
0x140001f8e  mov     [rsp+1A0h+var_178], rax
0x140001f93  mov     [rsp+1A0h+var_180], 14h
0x140001f9b  mov     [rsp+1A0h+var_124], edi
0x140001f9f  mov     [rsp+1A0h+var_138], 4
0x140001fa8  mov     [rsp+1A0h+var_148], 8
0x140001fb1  call    _tlgWriteTransfer_EventWriteTransfer
0x140001fb6  mov     rcx, [rbp+0A0h+var_30]
0x140001fba  xor     rcx, rsp; StackCookie
0x140001fbd  call    __security_check_cookie
0x140001fc2  add     rsp, 180h
0x140001fc9  pop     r15
0x140001fcb  pop     rdi
0x140001fcc  pop     rsi
0x140001fcd  pop     rbx
0x140001fce  pop     rbp
0x140001fcf  retn
```
