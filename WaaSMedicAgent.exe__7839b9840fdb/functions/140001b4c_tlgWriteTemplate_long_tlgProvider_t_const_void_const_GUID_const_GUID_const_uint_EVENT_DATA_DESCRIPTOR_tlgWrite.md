# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001b4c`
- end: `0x140001e1e`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$01@@U1@U?$_tlgWrapSz@D@@U2@U3@U3@U3@U2@U3@U3@U3@U3@U1@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$01@@3AEBU?$_tlgWrapSz@D@@455545555353@Z`
- size: `722`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **, const unsigned __int16 **, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c6f0`

## callees

- `0x14000198c`
- `0x140001b4c`
- `0x140002a30`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        const unsigned __int16 **a10,
        __int64 a11,
        const unsigned __int16 **a12,
        const unsigned __int16 **a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        const unsigned __int16 **a17,
        const unsigned __int16 **a18,
        const unsigned __int16 **a19,
        __int64 a20,
        const unsigned __int16 **a21,
        __int64 a22)
{
  __int64 v23; // rcx
  int v25; // edx
  const unsigned __int16 *v26; // r8
  __int64 v27; // rax
  int v28; // eax
  const unsigned __int16 *v29; // r8
  __int64 v30; // rax
  int v31; // eax
  const unsigned __int16 *v32; // r8
  __int64 v33; // rax
  int v34; // eax
  const unsigned __int16 *v35; // r8
  __int64 v36; // rax
  int v37; // eax
  const unsigned __int16 *v38; // r8
  __int64 v39; // rax
  int v40; // eax
  const unsigned __int16 *v41; // r8
  __int64 v42; // rax
  int v43; // eax
  const unsigned __int16 *v44; // r8
  __int64 v45; // rax
  int v46; // eax
  const unsigned __int16 *v47; // r8
  __int64 v48; // rax
  int v49; // eax
  const unsigned __int16 *v50; // r8
  _BYTE v52[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B0h]
  __int64 v54; // [rsp+58h] [rbp-A8h]
  __int64 v55; // [rsp+60h] [rbp-A0h]
  __int64 v56; // [rsp+68h] [rbp-98h]
  __int64 v57; // [rsp+70h] [rbp-90h]
  __int64 v58; // [rsp+78h] [rbp-88h]
  __int64 v59; // [rsp+80h] [rbp-80h]
  __int64 v60; // [rsp+88h] [rbp-78h]
  __int64 v61; // [rsp+90h] [rbp-70h]
  __int64 v62; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v63; // [rsp+A0h] [rbp-60h]
  int v64; // [rsp+A8h] [rbp-58h]
  int v65; // [rsp+ACh] [rbp-54h]
  __int64 v66; // [rsp+B0h] [rbp-50h]
  __int64 v67; // [rsp+B8h] [rbp-48h]
  const unsigned __int16 *v68; // [rsp+C0h] [rbp-40h]
  int v69; // [rsp+C8h] [rbp-38h]
  int v70; // [rsp+CCh] [rbp-34h]
  const unsigned __int16 *v71; // [rsp+D0h] [rbp-30h]
  int v72; // [rsp+D8h] [rbp-28h]
  int v73; // [rsp+DCh] [rbp-24h]
  const unsigned __int16 *v74; // [rsp+E0h] [rbp-20h]
  int v75; // [rsp+E8h] [rbp-18h]
  int v76; // [rsp+ECh] [rbp-14h]
  __int64 v77; // [rsp+F0h] [rbp-10h]
  __int64 v78; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v79; // [rsp+100h] [rbp+0h]
  int v80; // [rsp+108h] [rbp+8h]
  int v81; // [rsp+10Ch] [rbp+Ch]
  const unsigned __int16 *v82; // [rsp+110h] [rbp+10h]
  int v83; // [rsp+118h] [rbp+18h]
  int v84; // [rsp+11Ch] [rbp+1Ch]
  const unsigned __int16 *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  const unsigned __int16 *v88; // [rsp+130h] [rbp+30h]
  int v89; // [rsp+138h] [rbp+38h]
  int v90; // [rsp+13Ch] [rbp+3Ch]
  __int64 v91; // [rsp+140h] [rbp+40h]
  __int64 v92; // [rsp+148h] [rbp+48h]
  const unsigned __int16 *v93; // [rsp+150h] [rbp+50h]
  int v94; // [rsp+158h] [rbp+58h]
  int v95; // [rsp+15Ch] [rbp+5Ch]
  __int64 v96; // [rsp+160h] [rbp+60h]
  __int64 v97; // [rsp+168h] [rbp+68h]

  v96 = a22;
  v23 = -1;
  v97 = 4;
  v25 = 1;
  v26 = *a21;
  if ( *a21 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *((_BYTE *)v26 + v27) );
    v28 = v27 + 1;
  }
  else
  {
    v26 = &qword_1400150C8;
    v28 = 1;
  }
  v94 = v28;
  v91 = a20;
  v93 = v26;
  v95 = 0;
  v92 = 4;
  v29 = *a19;
  if ( *a19 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *((_BYTE *)v29 + v30) );
    v31 = v30 + 1;
  }
  else
  {
    v29 = &qword_1400150C8;
    v31 = 1;
  }
  v89 = v31;
  v88 = v29;
  v90 = 0;
  v32 = *a18;
  if ( *a18 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *((_BYTE *)v32 + v33) );
    v34 = v33 + 1;
  }
  else
  {
    v32 = &qword_1400150C8;
    v34 = 1;
  }
  v86 = v34;
  v85 = v32;
  v87 = 0;
  v35 = *a17;
  if ( *a17 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_BYTE *)v35 + v36) );
    v37 = v36 + 1;
  }
  else
  {
    v35 = &qword_1400150C8;
    v37 = 1;
  }
  v83 = v37;
  v82 = v35;
  v84 = 0;
  v38 = *a16;
  if ( *a16 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *((_BYTE *)v38 + v39) );
    v40 = v39 + 1;
  }
  else
  {
    v38 = &qword_1400150C8;
    v40 = 1;
  }
  v80 = v40;
  v77 = a15;
  v79 = v38;
  v81 = 0;
  v78 = 2;
  v41 = *a14;
  if ( *a14 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *((_BYTE *)v41 + v42) );
    v43 = v42 + 1;
  }
  else
  {
    v41 = &qword_1400150C8;
    v43 = 1;
  }
  v75 = v43;
  v74 = v41;
  v76 = 0;
  v44 = *a13;
  if ( *a13 )
  {
    v45 = -1;
    do
      ++v45;
    while ( *((_BYTE *)v44 + v45) );
    v46 = v45 + 1;
  }
  else
  {
    v44 = &qword_1400150C8;
    v46 = 1;
  }
  v72 = v46;
  v71 = v44;
  v73 = 0;
  v47 = *a12;
  if ( *a12 )
  {
    v48 = -1;
    do
      ++v48;
    while ( *((_BYTE *)v47 + v48) );
    v49 = v48 + 1;
  }
  else
  {
    v47 = &qword_1400150C8;
    v49 = 1;
  }
  v69 = v49;
  v66 = a11;
  v68 = v47;
  v70 = 0;
  v67 = 2;
  v50 = *a10;
  if ( *a10 )
  {
    do
      ++v23;
    while ( *((_BYTE *)v50 + v23) );
    v25 = v23 + 1;
  }
  else
  {
    v50 = &qword_1400150C8;
  }
  v61 = a9;
  v59 = a8;
  v57 = a7;
  v55 = a6;
  v53 = a5;
  v63 = v50;
  v64 = v25;
  v65 = 0;
  v62 = 4;
  v60 = 2;
  v58 = 4;
  v56 = 4;
  v54 = 4;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 20, v52);
}

```

## disassembly

```asm
0x140001b4c  mov     [rsp-8+arg_10], rbx
0x140001b51  mov     [rsp-8+arg_18], rsi
0x140001b56  push    rbp
0x140001b57  lea     rbp, [rsp-80h]
0x140001b5c  sub     rsp, 180h
0x140001b63  mov     rax, cs:__security_cookie
0x140001b6a  xor     rax, rsp
0x140001b6d  mov     [rbp+80h+var_10], rax
0x140001b71  mov     rax, [rbp+80h+arg_A8]
0x140001b78  lea     rbx, qword_1400150C8
0x140001b7f  xor     r9d, r9d
0x140001b82  mov     [rbp+80h+var_20], rax
0x140001b86  mov     rax, [rbp+80h+arg_A0]
0x140001b8d  mov     r10, rcx
0x140001b90  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001b94  mov     [rbp+80h+var_18], 4
0x140001b9c  mov     r11, rdx
0x140001b9f  lea     edx, [r9+1]
0x140001ba3  mov     r8, [rax]
0x140001ba6  test    r8, r8
0x140001ba9  jz      short loc_140001BBB
0x140001bab  mov     rax, rcx
0x140001bae  inc     rax
0x140001bb1  cmp     [r8+rax], r9b
0x140001bb5  jnz     short loc_140001BAE
0x140001bb7  inc     eax
0x140001bb9  jmp     short loc_140001BC0
0x140001bbb  mov     r8, rbx
0x140001bbe  mov     eax, edx
0x140001bc0  mov     [rbp+80h+var_28], eax
0x140001bc3  mov     rax, [rbp+80h+arg_98]
0x140001bca  mov     [rbp+80h+var_40], rax
0x140001bce  mov     rax, [rbp+80h+arg_90]
0x140001bd5  mov     [rbp+80h+var_30], r8
0x140001bd9  mov     [rbp+80h+var_24], r9d
0x140001bdd  mov     [rbp+80h+var_38], 4
0x140001be5  mov     r8, [rax]
0x140001be8  test    r8, r8
0x140001beb  jz      short loc_140001BFD
0x140001bed  mov     rax, rcx
0x140001bf0  inc     rax
0x140001bf3  cmp     [r8+rax], r9b
0x140001bf7  jnz     short loc_140001BF0
0x140001bf9  inc     eax
0x140001bfb  jmp     short loc_140001C02
0x140001bfd  mov     r8, rbx
0x140001c00  mov     eax, edx
0x140001c02  mov     [rbp+80h+var_48], eax
0x140001c05  mov     rax, [rbp+80h+arg_88]
0x140001c0c  mov     [rbp+80h+var_50], r8
0x140001c10  mov     [rbp+80h+var_44], r9d
0x140001c14  mov     r8, [rax]
0x140001c17  test    r8, r8
0x140001c1a  jz      short loc_140001C2C
0x140001c1c  mov     rax, rcx
0x140001c1f  inc     rax
0x140001c22  cmp     [r8+rax], r9b
0x140001c26  jnz     short loc_140001C1F
0x140001c28  inc     eax
0x140001c2a  jmp     short loc_140001C31
0x140001c2c  mov     r8, rbx
0x140001c2f  mov     eax, edx
0x140001c31  mov     [rbp+80h+var_58], eax
0x140001c34  mov     rax, [rbp+80h+arg_80]
0x140001c3b  mov     [rbp+80h+var_60], r8
0x140001c3f  mov     [rbp+80h+var_54], r9d
0x140001c43  mov     r8, [rax]
0x140001c46  test    r8, r8
0x140001c49  jz      short loc_140001C5B
0x140001c4b  mov     rax, rcx
0x140001c4e  inc     rax
0x140001c51  cmp     [r8+rax], r9b
0x140001c55  jnz     short loc_140001C4E
0x140001c57  inc     eax
0x140001c59  jmp     short loc_140001C60
0x140001c5b  mov     r8, rbx
0x140001c5e  mov     eax, edx
0x140001c60  mov     [rbp+80h+var_68], eax
0x140001c63  mov     rax, [rbp+80h+arg_78]
0x140001c6a  mov     [rbp+80h+var_70], r8
0x140001c6e  mov     [rbp+80h+var_64], r9d
0x140001c72  mov     r8, [rax]
0x140001c75  test    r8, r8
0x140001c78  jz      short loc_140001C8A
0x140001c7a  mov     rax, rcx
0x140001c7d  inc     rax
0x140001c80  cmp     [r8+rax], r9b
0x140001c84  jnz     short loc_140001C7D
0x140001c86  inc     eax
0x140001c88  jmp     short loc_140001C8F
0x140001c8a  mov     r8, rbx
0x140001c8d  mov     eax, edx
0x140001c8f  mov     [rbp+80h+var_78], eax
0x140001c92  mov     rax, [rbp+80h+arg_70]
0x140001c99  mov     [rbp+80h+var_90], rax
0x140001c9d  mov     rax, [rbp+80h+arg_68]
0x140001ca4  mov     [rbp+80h+var_80], r8
0x140001ca8  mov     [rbp+80h+var_74], r9d
0x140001cac  mov     [rbp+80h+var_88], 2
0x140001cb4  mov     r8, [rax]
0x140001cb7  test    r8, r8
0x140001cba  jz      short loc_140001CCC
0x140001cbc  mov     rax, rcx
0x140001cbf  inc     rax
0x140001cc2  cmp     [r8+rax], r9b
0x140001cc6  jnz     short loc_140001CBF
0x140001cc8  inc     eax
0x140001cca  jmp     short loc_140001CD1
0x140001ccc  mov     r8, rbx
0x140001ccf  mov     eax, edx
0x140001cd1  mov     [rbp+80h+var_98], eax
0x140001cd4  mov     rax, [rbp+80h+arg_60]
0x140001cdb  mov     [rbp+80h+var_A0], r8
0x140001cdf  mov     [rbp+80h+var_94], r9d
0x140001ce3  mov     r8, [rax]
0x140001ce6  test    r8, r8
0x140001ce9  jz      short loc_140001CFB
0x140001ceb  mov     rax, rcx
0x140001cee  inc     rax
0x140001cf1  cmp     [r8+rax], r9b
0x140001cf5  jnz     short loc_140001CEE
0x140001cf7  inc     eax
0x140001cf9  jmp     short loc_140001D00
0x140001cfb  mov     r8, rbx
0x140001cfe  mov     eax, edx
0x140001d00  mov     [rbp+80h+var_A8], eax
0x140001d03  mov     rax, [rbp+80h+arg_58]
0x140001d0a  mov     [rbp+80h+var_B0], r8
0x140001d0e  mov     [rbp+80h+var_A4], r9d
0x140001d12  mov     r8, [rax]
0x140001d15  test    r8, r8
0x140001d18  jz      short loc_140001D2A
0x140001d1a  mov     rax, rcx
0x140001d1d  inc     rax
0x140001d20  cmp     [r8+rax], r9b
0x140001d24  jnz     short loc_140001D1D
0x140001d26  inc     eax
0x140001d28  jmp     short loc_140001D2F
0x140001d2a  mov     r8, rbx
0x140001d2d  mov     eax, edx
0x140001d2f  mov     [rbp+80h+var_B8], eax
0x140001d32  mov     rax, [rbp+80h+arg_50]
0x140001d39  mov     [rbp+80h+var_D0], rax
0x140001d3d  mov     rax, [rbp+80h+arg_48]
0x140001d44  mov     [rbp+80h+var_C0], r8
0x140001d48  mov     [rbp+80h+var_B4], r9d
0x140001d4c  mov     [rbp+80h+var_C8], 2
0x140001d54  mov     r8, [rax]
0x140001d57  test    r8, r8
0x140001d5a  jz      short loc_140001D6A
0x140001d5c  inc     rcx
0x140001d5f  cmp     [r8+rcx], r9b
0x140001d63  jnz     short loc_140001D5C
0x140001d65  lea     edx, [rcx+1]
0x140001d68  jmp     short loc_140001D6D
0x140001d6a  mov     r8, rbx
0x140001d6d  mov     rax, [rbp+80h+arg_40]
0x140001d74  mov     rcx, r10
0x140001d77  mov     [rbp+80h+var_F0], rax
0x140001d7b  mov     rax, [rbp+80h+arg_38]
0x140001d82  mov     [rbp+80h+var_100], rax
0x140001d86  mov     rax, [rbp+80h+arg_30]
0x140001d8d  mov     [rsp+180h+var_110], rax
0x140001d92  mov     rax, [rbp+80h+arg_28]
0x140001d99  mov     [rsp+180h+var_120], rax
0x140001d9e  mov     rax, [rbp+80h+arg_20]
0x140001da5  mov     [rsp+180h+var_130], rax
0x140001daa  lea     rax, [rsp+180h+var_150]
0x140001daf  mov     [rbp+80h+var_E0], r8
0x140001db3  xor     r8d, r8d
0x140001db6  mov     [rbp+80h+var_D8], edx
0x140001db9  mov     rdx, r11
0x140001dbc  mov     [rsp+180h+var_158], rax
0x140001dc1  mov     [rsp+180h+var_160], 14h
0x140001dc9  mov     [rbp+80h+var_D4], r9d
0x140001dcd  mov     [rbp+80h+var_E8], 4
0x140001dd5  mov     [rbp+80h+var_F8], 2
0x140001ddd  mov     [rsp+180h+var_108], 4
0x140001de6  mov     [rsp+180h+var_118], 4
0x140001def  mov     [rsp+180h+var_128], 4
0x140001df8  call    _tlgWriteTransfer_EventWriteTransfer
0x140001dfd  mov     rcx, [rbp+80h+var_10]
0x140001e01  xor     rcx, rsp; StackCookie
0x140001e04  call    __security_check_cookie
0x140001e09  lea     r11, [rsp+180h+var_s0]
0x140001e11  mov     rbx, [r11+20h]
0x140001e15  mov     rsi, [r11+28h]
0x140001e19  mov     rsp, r11
0x140001e1c  pop     rbp
0x140001e1d  retn
```
