# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800019f0`
- end: `0x180001c8b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `667`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, char **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, char **, __int64, const unsigned __int16 **, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000aab0`
- `0x18000ae98`

## callees

- `0x18000163c`
- `0x1800019f0`
- `0x180002550`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
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
        char **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        char **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        char **a19)
{
  __int64 v21; // rdx
  int v23; // r9d
  char *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  char *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  char *v40; // rcx
  __int64 v41; // rax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rcx
  _BYTE v47[32]; // [rsp+30h] [rbp-D0h] BYREF
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
  char *v62; // [rsp+B0h] [rbp-50h]
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
  char *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  __int64 v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v80; // [rsp+120h] [rbp+20h]
  int v81; // [rsp+128h] [rbp+28h]
  int v82; // [rsp+12Ch] [rbp+2Ch]
  char *v83; // [rsp+130h] [rbp+30h]
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
    while ( *(_WORD *)&v24[2 * v25] );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = byte_1800159FC;
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
    v28 = &word_1800159FE;
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
    while ( *(_WORD *)&v31[2 * v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = byte_1800159FC;
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
    v34 = &word_1800159FE;
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
    v37 = &word_1800159FE;
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
    while ( *(_WORD *)&v40[2 * v41] );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = byte_1800159FC;
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
    v42 = &word_1800159FE;
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
    v45 = &word_1800159FE;
  }
  v50 = a6;
  v48 = a5;
  v52 = v45;
  v53 = v27;
  v54 = 0;
  v51 = 4;
  v49 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 17, v47);
}

```

## disassembly

```asm
0x1800019f0  push    rbp
0x1800019f2  push    rbx
0x1800019f3  push    rsi
0x1800019f4  push    rdi
0x1800019f5  push    r14
0x1800019f7  lea     rbp, [rsp-50h]
0x1800019fc  sub     rsp, 150h
0x180001a03  mov     rax, cs:__security_cookie
0x180001a0a  xor     rax, rsp
0x180001a0d  mov     [rbp+70h+var_30], rax
0x180001a11  mov     rax, [rbp+70h+arg_90]
0x180001a18  mov     r11, rdx
0x180001a1b  mov     r10, rcx
0x180001a1e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001a22  xor     edi, edi
0x180001a24  mov     rbx, r8
0x180001a27  mov     r9d, 2
0x180001a2d  mov     rcx, [rax]
0x180001a30  test    rcx, rcx
0x180001a33  jz      short loc_180001A4A
0x180001a35  mov     rax, rdx
0x180001a38  inc     rax
0x180001a3b  cmp     [rcx+rax*2], di
0x180001a3f  jnz     short loc_180001A38
0x180001a41  lea     eax, ds:2[rax*2]
0x180001a48  jmp     short loc_180001A54
0x180001a4a  lea     rcx, byte_1800159FC
0x180001a51  mov     eax, r9d
0x180001a54  mov     [rbp+70h+var_38], eax
0x180001a57  lea     rsi, word_1800159FE
0x180001a5e  mov     rax, [rbp+70h+arg_88]
0x180001a65  mov     r8d, 1
0x180001a6b  mov     [rbp+70h+var_40], rcx
0x180001a6f  mov     [rbp+70h+var_34], edi
0x180001a72  mov     rcx, [rax]
0x180001a75  test    rcx, rcx
0x180001a78  jz      short loc_180001A8A
0x180001a7a  mov     rax, rdx
0x180001a7d  inc     rax
0x180001a80  cmp     [rcx+rax], dil
0x180001a84  jnz     short loc_180001A7D
0x180001a86  inc     eax
0x180001a88  jmp     short loc_180001A90
0x180001a8a  mov     rcx, rsi
0x180001a8d  mov     eax, r8d
0x180001a90  mov     [rbp+70h+var_48], eax
0x180001a93  mov     rax, [rbp+70h+arg_80]
0x180001a9a  mov     [rbp+70h+var_60], rax
0x180001a9e  mov     rax, [rbp+70h+arg_78]
0x180001aa5  mov     [rbp+70h+var_50], rcx
0x180001aa9  mov     [rbp+70h+var_44], edi
0x180001aac  mov     [rbp+70h+var_58], 4
0x180001ab4  mov     rcx, [rax]
0x180001ab7  test    rcx, rcx
0x180001aba  jz      short loc_180001AD1
0x180001abc  mov     rax, rdx
0x180001abf  inc     rax
0x180001ac2  cmp     [rcx+rax*2], di
0x180001ac6  jnz     short loc_180001ABF
0x180001ac8  lea     eax, ds:2[rax*2]
0x180001acf  jmp     short loc_180001ADB
0x180001ad1  lea     rcx, byte_1800159FC
0x180001ad8  mov     eax, r9d
0x180001adb  mov     [rbp+70h+var_68], eax
0x180001ade  mov     rax, [rbp+70h+arg_70]
0x180001ae5  mov     [rbp+70h+var_70], rcx
0x180001ae9  mov     [rbp+70h+var_64], edi
0x180001aec  mov     rcx, [rax]
0x180001aef  test    rcx, rcx
0x180001af2  jz      short loc_180001B04
0x180001af4  mov     rax, rdx
0x180001af7  inc     rax
0x180001afa  cmp     [rcx+rax], dil
0x180001afe  jnz     short loc_180001AF7
0x180001b00  inc     eax
0x180001b02  jmp     short loc_180001B0A
0x180001b04  mov     rcx, rsi
0x180001b07  mov     eax, r8d
0x180001b0a  mov     [rbp+70h+var_78], eax
0x180001b0d  mov     rax, [rbp+70h+arg_68]
0x180001b14  mov     [rbp+70h+var_90], rax
0x180001b18  mov     rax, [rbp+70h+arg_60]
0x180001b1f  mov     [rbp+70h+var_80], rcx
0x180001b23  mov     [rbp+70h+var_74], edi
0x180001b26  mov     [rbp+70h+var_88], 4
0x180001b2e  mov     rcx, [rax]
0x180001b31  test    rcx, rcx
0x180001b34  jz      short loc_180001B46
0x180001b36  mov     rax, rdx
0x180001b39  inc     rax
0x180001b3c  cmp     [rcx+rax], dil
0x180001b40  jnz     short loc_180001B39
0x180001b42  inc     eax
0x180001b44  jmp     short loc_180001B4C
0x180001b46  mov     rcx, rsi
0x180001b49  mov     eax, r8d
0x180001b4c  mov     [rbp+70h+var_98], eax
0x180001b4f  mov     rax, [rbp+70h+arg_58]
0x180001b56  mov     [rbp+70h+var_B0], rax
0x180001b5a  mov     rax, [rbp+70h+arg_50]
0x180001b61  mov     [rbp+70h+var_A0], rcx
0x180001b65  mov     [rbp+70h+var_94], edi
0x180001b68  mov     [rbp+70h+var_A8], 4
0x180001b70  mov     rcx, [rax]
0x180001b73  test    rcx, rcx
0x180001b76  jz      short loc_180001B8E
0x180001b78  mov     rax, rdx
0x180001b7b  inc     rax
0x180001b7e  cmp     [rcx+rax*2], di
0x180001b82  jnz     short loc_180001B7B
0x180001b84  lea     r9d, ds:2[rax*2]
0x180001b8c  jmp     short loc_180001B95
0x180001b8e  lea     rcx, byte_1800159FC
0x180001b95  mov     rax, [rbp+70h+arg_48]
0x180001b9c  mov     [rbp+70h+var_D0], rax
0x180001ba0  mov     rax, [rbp+70h+arg_40]
0x180001ba7  mov     [rbp+70h+var_C0], rcx
0x180001bab  mov     [rbp+70h+var_B8], r9d
0x180001baf  mov     [rbp+70h+var_B4], edi
0x180001bb2  mov     rcx, [rax]
0x180001bb5  mov     [rbp+70h+var_C8], 4
0x180001bbd  test    rcx, rcx
0x180001bc0  jz      short loc_180001BD2
0x180001bc2  mov     rax, rdx
0x180001bc5  inc     rax
0x180001bc8  cmp     [rcx+rax], dil
0x180001bcc  jnz     short loc_180001BC5
0x180001bce  inc     eax
0x180001bd0  jmp     short loc_180001BD8
0x180001bd2  mov     rcx, rsi
0x180001bd5  mov     eax, r8d
0x180001bd8  mov     [rbp+70h+var_D8], eax
0x180001bdb  mov     rax, [rbp+70h+arg_38]
0x180001be2  mov     [rbp+70h+var_F0], rax
0x180001be6  mov     rax, [rbp+70h+arg_30]
0x180001bed  mov     [rbp+70h+var_E0], rcx
0x180001bf1  mov     [rbp+70h+var_D4], edi
0x180001bf4  mov     [rbp+70h+var_E8], 4
0x180001bfc  mov     rcx, [rax]
0x180001bff  test    rcx, rcx
0x180001c02  jz      short loc_180001C13
0x180001c04  inc     rdx
0x180001c07  cmp     [rcx+rdx], dil
0x180001c0b  jnz     short loc_180001C04
0x180001c0d  lea     r8d, [rdx+1]
0x180001c11  jmp     short loc_180001C16
0x180001c13  mov     rcx, rsi
0x180001c16  mov     rax, [rbp+70h+arg_28]
0x180001c1d  xor     r9d, r9d
0x180001c20  mov     [rsp+170h+var_110], rax
0x180001c25  mov     rdx, r11
0x180001c28  mov     rax, [rbp+70h+arg_20]
0x180001c2f  mov     [rsp+170h+var_120], rax
0x180001c34  lea     rax, [rsp+170h+var_140]
0x180001c39  mov     [rsp+170h+var_100], rcx
0x180001c3e  mov     rcx, r10
0x180001c41  mov     [rsp+170h+var_F8], r8d
0x180001c46  mov     r8, rbx
0x180001c49  mov     [rsp+170h+var_148], rax
0x180001c4e  mov     [rsp+170h+var_150], 11h
0x180001c56  mov     [rsp+170h+var_F4], edi
0x180001c5a  mov     [rsp+170h+var_108], 4
0x180001c63  mov     [rsp+170h+var_118], 8
0x180001c6c  call    _tlgWriteTransfer_EventWriteTransfer
0x180001c71  mov     rcx, [rbp+70h+var_30]
0x180001c75  xor     rcx, rsp; StackCookie
0x180001c78  call    __security_check_cookie
0x180001c7d  add     rsp, 150h
0x180001c84  pop     r14
0x180001c86  pop     rdi
0x180001c87  pop     rsi
0x180001c88  pop     rbx
0x180001c89  pop     rbp
0x180001c8a  retn
```
