# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001a3c`
- end: `0x140001cd7`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `667`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140008e10`

## callees

- `0x140001a3c`
- `0x140002318`
- `0x140002f40`

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
        __int64 **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        __int64 **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        __int64 **a19)
{
  __int64 v21; // rdx
  int v23; // r9d
  __int64 *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  __int64 *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  __int64 *v40; // rcx
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
  __int64 *v62; // [rsp+B0h] [rbp-50h]
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
  __int64 *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  __int64 v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v80; // [rsp+120h] [rbp+20h]
  int v81; // [rsp+128h] [rbp+28h]
  int v82; // [rsp+12Ch] [rbp+2Ch]
  __int64 *v83; // [rsp+130h] [rbp+30h]
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
    while ( *((_WORD *)v24 + v25) );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &qword_14001C2F8;
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
    v28 = &byte_14001C2F5;
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
    while ( *((_WORD *)v31 + v32) );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &qword_14001C2F8;
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
    v34 = &byte_14001C2F5;
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
    v37 = &byte_14001C2F5;
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
    while ( *((_WORD *)v40 + v41) );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = &qword_14001C2F8;
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
    v42 = &byte_14001C2F5;
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
    v45 = &byte_14001C2F5;
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
0x140001a3c  push    rbp
0x140001a3e  push    rbx
0x140001a3f  push    rsi
0x140001a40  push    rdi
0x140001a41  push    r14
0x140001a43  lea     rbp, [rsp-50h]
0x140001a48  sub     rsp, 150h
0x140001a4f  mov     rax, cs:__security_cookie
0x140001a56  xor     rax, rsp
0x140001a59  mov     [rbp+70h+var_30], rax
0x140001a5d  mov     rax, [rbp+70h+arg_90]
0x140001a64  mov     r11, rdx
0x140001a67  mov     r10, rcx
0x140001a6a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140001a6e  xor     edi, edi
0x140001a70  mov     rbx, r8
0x140001a73  mov     r9d, 2
0x140001a79  mov     rcx, [rax]
0x140001a7c  test    rcx, rcx
0x140001a7f  jz      short loc_140001A96
0x140001a81  mov     rax, rdx
0x140001a84  inc     rax
0x140001a87  cmp     [rcx+rax*2], di
0x140001a8b  jnz     short loc_140001A84
0x140001a8d  lea     eax, ds:2[rax*2]
0x140001a94  jmp     short loc_140001AA0
0x140001a96  lea     rcx, qword_14001C2F8
0x140001a9d  mov     eax, r9d
0x140001aa0  mov     [rbp+70h+var_38], eax
0x140001aa3  lea     rsi, byte_14001C2F5
0x140001aaa  mov     rax, [rbp+70h+arg_88]
0x140001ab1  mov     r8d, 1
0x140001ab7  mov     [rbp+70h+var_40], rcx
0x140001abb  mov     [rbp+70h+var_34], edi
0x140001abe  mov     rcx, [rax]
0x140001ac1  test    rcx, rcx
0x140001ac4  jz      short loc_140001AD6
0x140001ac6  mov     rax, rdx
0x140001ac9  inc     rax
0x140001acc  cmp     [rcx+rax], dil
0x140001ad0  jnz     short loc_140001AC9
0x140001ad2  inc     eax
0x140001ad4  jmp     short loc_140001ADC
0x140001ad6  mov     rcx, rsi
0x140001ad9  mov     eax, r8d
0x140001adc  mov     [rbp+70h+var_48], eax
0x140001adf  mov     rax, [rbp+70h+arg_80]
0x140001ae6  mov     [rbp+70h+var_60], rax
0x140001aea  mov     rax, [rbp+70h+arg_78]
0x140001af1  mov     [rbp+70h+var_50], rcx
0x140001af5  mov     [rbp+70h+var_44], edi
0x140001af8  mov     [rbp+70h+var_58], 4
0x140001b00  mov     rcx, [rax]
0x140001b03  test    rcx, rcx
0x140001b06  jz      short loc_140001B1D
0x140001b08  mov     rax, rdx
0x140001b0b  inc     rax
0x140001b0e  cmp     [rcx+rax*2], di
0x140001b12  jnz     short loc_140001B0B
0x140001b14  lea     eax, ds:2[rax*2]
0x140001b1b  jmp     short loc_140001B27
0x140001b1d  lea     rcx, qword_14001C2F8
0x140001b24  mov     eax, r9d
0x140001b27  mov     [rbp+70h+var_68], eax
0x140001b2a  mov     rax, [rbp+70h+arg_70]
0x140001b31  mov     [rbp+70h+var_70], rcx
0x140001b35  mov     [rbp+70h+var_64], edi
0x140001b38  mov     rcx, [rax]
0x140001b3b  test    rcx, rcx
0x140001b3e  jz      short loc_140001B50
0x140001b40  mov     rax, rdx
0x140001b43  inc     rax
0x140001b46  cmp     [rcx+rax], dil
0x140001b4a  jnz     short loc_140001B43
0x140001b4c  inc     eax
0x140001b4e  jmp     short loc_140001B56
0x140001b50  mov     rcx, rsi
0x140001b53  mov     eax, r8d
0x140001b56  mov     [rbp+70h+var_78], eax
0x140001b59  mov     rax, [rbp+70h+arg_68]
0x140001b60  mov     [rbp+70h+var_90], rax
0x140001b64  mov     rax, [rbp+70h+arg_60]
0x140001b6b  mov     [rbp+70h+var_80], rcx
0x140001b6f  mov     [rbp+70h+var_74], edi
0x140001b72  mov     [rbp+70h+var_88], 4
0x140001b7a  mov     rcx, [rax]
0x140001b7d  test    rcx, rcx
0x140001b80  jz      short loc_140001B92
0x140001b82  mov     rax, rdx
0x140001b85  inc     rax
0x140001b88  cmp     [rcx+rax], dil
0x140001b8c  jnz     short loc_140001B85
0x140001b8e  inc     eax
0x140001b90  jmp     short loc_140001B98
0x140001b92  mov     rcx, rsi
0x140001b95  mov     eax, r8d
0x140001b98  mov     [rbp+70h+var_98], eax
0x140001b9b  mov     rax, [rbp+70h+arg_58]
0x140001ba2  mov     [rbp+70h+var_B0], rax
0x140001ba6  mov     rax, [rbp+70h+arg_50]
0x140001bad  mov     [rbp+70h+var_A0], rcx
0x140001bb1  mov     [rbp+70h+var_94], edi
0x140001bb4  mov     [rbp+70h+var_A8], 4
0x140001bbc  mov     rcx, [rax]
0x140001bbf  test    rcx, rcx
0x140001bc2  jz      short loc_140001BDA
0x140001bc4  mov     rax, rdx
0x140001bc7  inc     rax
0x140001bca  cmp     [rcx+rax*2], di
0x140001bce  jnz     short loc_140001BC7
0x140001bd0  lea     r9d, ds:2[rax*2]
0x140001bd8  jmp     short loc_140001BE1
0x140001bda  lea     rcx, qword_14001C2F8
0x140001be1  mov     rax, [rbp+70h+arg_48]
0x140001be8  mov     [rbp+70h+var_D0], rax
0x140001bec  mov     rax, [rbp+70h+arg_40]
0x140001bf3  mov     [rbp+70h+var_C0], rcx
0x140001bf7  mov     [rbp+70h+var_B8], r9d
0x140001bfb  mov     [rbp+70h+var_B4], edi
0x140001bfe  mov     rcx, [rax]
0x140001c01  mov     [rbp+70h+var_C8], 4
0x140001c09  test    rcx, rcx
0x140001c0c  jz      short loc_140001C1E
0x140001c0e  mov     rax, rdx
0x140001c11  inc     rax
0x140001c14  cmp     [rcx+rax], dil
0x140001c18  jnz     short loc_140001C11
0x140001c1a  inc     eax
0x140001c1c  jmp     short loc_140001C24
0x140001c1e  mov     rcx, rsi
0x140001c21  mov     eax, r8d
0x140001c24  mov     [rbp+70h+var_D8], eax
0x140001c27  mov     rax, [rbp+70h+arg_38]
0x140001c2e  mov     [rbp+70h+var_F0], rax
0x140001c32  mov     rax, [rbp+70h+arg_30]
0x140001c39  mov     [rbp+70h+var_E0], rcx
0x140001c3d  mov     [rbp+70h+var_D4], edi
0x140001c40  mov     [rbp+70h+var_E8], 4
0x140001c48  mov     rcx, [rax]
0x140001c4b  test    rcx, rcx
0x140001c4e  jz      short loc_140001C5F
0x140001c50  inc     rdx
0x140001c53  cmp     [rcx+rdx], dil
0x140001c57  jnz     short loc_140001C50
0x140001c59  lea     r8d, [rdx+1]
0x140001c5d  jmp     short loc_140001C62
0x140001c5f  mov     rcx, rsi
0x140001c62  mov     rax, [rbp+70h+arg_28]
0x140001c69  xor     r9d, r9d
0x140001c6c  mov     [rsp+170h+var_110], rax
0x140001c71  mov     rdx, r11
0x140001c74  mov     rax, [rbp+70h+arg_20]
0x140001c7b  mov     [rsp+170h+var_120], rax
0x140001c80  lea     rax, [rsp+170h+var_140]
0x140001c85  mov     [rsp+170h+var_100], rcx
0x140001c8a  mov     rcx, r10
0x140001c8d  mov     [rsp+170h+var_F8], r8d
0x140001c92  mov     r8, rbx
0x140001c95  mov     [rsp+170h+var_148], rax
0x140001c9a  mov     [rsp+170h+var_150], 11h
0x140001ca2  mov     [rsp+170h+var_F4], edi
0x140001ca6  mov     [rsp+170h+var_108], 4
0x140001caf  mov     [rsp+170h+var_118], 8
0x140001cb8  call    _tlgWriteTransfer_EventWriteTransfer
0x140001cbd  mov     rcx, [rbp+70h+var_30]
0x140001cc1  xor     rcx, rsp; StackCookie
0x140001cc4  call    __security_check_cookie
0x140001cc9  add     rsp, 150h
0x140001cd0  pop     r14
0x140001cd2  pop     rdi
0x140001cd3  pop     rsi
0x140001cd4  pop     rbx
0x140001cd5  pop     rbp
0x140001cd6  retn
```
