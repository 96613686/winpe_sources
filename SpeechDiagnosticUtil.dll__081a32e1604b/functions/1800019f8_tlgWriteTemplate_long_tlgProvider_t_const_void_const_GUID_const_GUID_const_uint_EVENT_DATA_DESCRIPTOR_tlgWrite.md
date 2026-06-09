# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800019f8`
- end: `0x180001d1b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564453@Z`
- size: `803`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a964`
- `0x18000b888`

## callees

- `0x180001640`
- `0x1800019f8`
- `0x180002910`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const unsigned __int16 **a8,
        __int64 a9,
        const unsigned __int16 **a10,
        __int64 a11,
        __int64 **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        __int64 **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        __int64 **a20,
        __int64 a21,
        __int64 a22,
        const unsigned __int16 **a23,
        __int64 a24)
{
  __int64 v26; // rdx
  int v28; // r8d
  const unsigned __int16 *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  int v32; // r9d
  __int64 *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  const unsigned __int16 *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  __int64 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rcx
  __int64 v46; // rax
  int v47; // eax
  __int64 *v48; // rcx
  __int64 v49; // rax
  const unsigned __int16 *v50; // rcx
  __int64 v51; // rax
  int v52; // eax
  const unsigned __int16 *v53; // rcx
  struct _EVENT_DATA_DESCRIPTOR v55; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v56; // [rsp+50h] [rbp-B0h]
  __int64 v57; // [rsp+58h] [rbp-A8h]
  __int64 v58; // [rsp+60h] [rbp-A0h]
  __int64 v59; // [rsp+68h] [rbp-98h]
  __int64 v60; // [rsp+70h] [rbp-90h]
  __int64 v61; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v62; // [rsp+80h] [rbp-80h]
  int v63; // [rsp+88h] [rbp-78h]
  int v64; // [rsp+8Ch] [rbp-74h]
  __int64 v65; // [rsp+90h] [rbp-70h]
  __int64 v66; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v67; // [rsp+A0h] [rbp-60h]
  int v68; // [rsp+A8h] [rbp-58h]
  int v69; // [rsp+ACh] [rbp-54h]
  __int64 v70; // [rsp+B0h] [rbp-50h]
  __int64 v71; // [rsp+B8h] [rbp-48h]
  __int64 *v72; // [rsp+C0h] [rbp-40h]
  int v73; // [rsp+C8h] [rbp-38h]
  int v74; // [rsp+CCh] [rbp-34h]
  __int64 v75; // [rsp+D0h] [rbp-30h]
  __int64 v76; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v77; // [rsp+E0h] [rbp-20h]
  int v78; // [rsp+E8h] [rbp-18h]
  int v79; // [rsp+ECh] [rbp-14h]
  __int64 v80; // [rsp+F0h] [rbp-10h]
  __int64 v81; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v82; // [rsp+100h] [rbp+0h]
  int v83; // [rsp+108h] [rbp+8h]
  int v84; // [rsp+10Ch] [rbp+Ch]
  __int64 *v85; // [rsp+110h] [rbp+10h]
  int v86; // [rsp+118h] [rbp+18h]
  int v87; // [rsp+11Ch] [rbp+1Ch]
  __int64 v88; // [rsp+120h] [rbp+20h]
  __int64 v89; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v90; // [rsp+130h] [rbp+30h]
  int v91; // [rsp+138h] [rbp+38h]
  int v92; // [rsp+13Ch] [rbp+3Ch]
  __int64 *v93; // [rsp+140h] [rbp+40h]
  int v94; // [rsp+148h] [rbp+48h]
  int v95; // [rsp+14Ch] [rbp+4Ch]
  __int64 v96; // [rsp+150h] [rbp+50h]
  __int64 v97; // [rsp+158h] [rbp+58h]
  __int64 v98; // [rsp+160h] [rbp+60h]
  __int64 v99; // [rsp+168h] [rbp+68h]
  const unsigned __int16 *v100; // [rsp+170h] [rbp+70h]
  int v101; // [rsp+178h] [rbp+78h]
  int v102; // [rsp+17Ch] [rbp+7Ch]
  __int64 v103; // [rsp+180h] [rbp+80h]
  __int64 v104; // [rsp+188h] [rbp+88h]

  v103 = a24;
  v104 = 8;
  v26 = -1;
  v28 = 1;
  v29 = *a23;
  if ( *a23 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *((_BYTE *)v29 + v30) );
    v31 = v30 + 1;
  }
  else
  {
    v29 = &qword_180012910;
    v31 = 1;
  }
  v101 = v31;
  v32 = 2;
  v98 = a22;
  v96 = a21;
  v100 = v29;
  v102 = 0;
  v99 = 4;
  v33 = *a20;
  v97 = 4;
  if ( v33 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_WORD *)v33 + v34) );
    v35 = 2 * v34 + 2;
  }
  else
  {
    v33 = qword_180012C50;
    v35 = 2;
  }
  v94 = v35;
  v93 = v33;
  v95 = 0;
  v36 = *a19;
  if ( *a19 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_BYTE *)v36 + v37) );
    v38 = v37 + 1;
  }
  else
  {
    v36 = &qword_180012910;
    v38 = 1;
  }
  v91 = v38;
  v88 = a18;
  v90 = v36;
  v92 = 0;
  v89 = 4;
  v39 = *a17;
  if ( *a17 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_WORD *)v39 + v40) );
    v41 = 2 * v40 + 2;
  }
  else
  {
    v39 = qword_180012C50;
    v41 = 2;
  }
  v86 = v41;
  v85 = v39;
  v87 = 0;
  v42 = *a16;
  if ( *a16 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &qword_180012910;
    v44 = 1;
  }
  v83 = v44;
  v80 = a15;
  v82 = v42;
  v84 = 0;
  v81 = 4;
  v45 = *a14;
  if ( *a14 )
  {
    v46 = -1;
    do
      ++v46;
    while ( *((_BYTE *)v45 + v46) );
    v47 = v46 + 1;
  }
  else
  {
    v45 = &qword_180012910;
    v47 = 1;
  }
  v78 = v47;
  v75 = a13;
  v77 = v45;
  v79 = 0;
  v76 = 4;
  v48 = *a12;
  if ( *a12 )
  {
    v49 = -1;
    do
      ++v49;
    while ( *((_WORD *)v48 + v49) );
    v32 = 2 * v49 + 2;
  }
  else
  {
    v48 = qword_180012C50;
  }
  v70 = a11;
  v72 = v48;
  v73 = v32;
  v74 = 0;
  v50 = *a10;
  v71 = 4;
  if ( v50 )
  {
    v51 = -1;
    do
      ++v51;
    while ( *((_BYTE *)v50 + v51) );
    v52 = v51 + 1;
  }
  else
  {
    v50 = &qword_180012910;
    v52 = 1;
  }
  v68 = v52;
  v65 = a9;
  v67 = v50;
  v69 = 0;
  v66 = 4;
  v53 = *a8;
  if ( *a8 )
  {
    do
      ++v26;
    while ( *((_BYTE *)v53 + v26) );
    v28 = v26 + 1;
  }
  else
  {
    v53 = &qword_180012910;
  }
  v60 = a7;
  v58 = a6;
  v56 = a5;
  v62 = v53;
  v63 = v28;
  v64 = 0;
  v61 = 4;
  v59 = 8;
  v57 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x16u, &v55);
}

```

## disassembly

```asm
0x1800019f8  push    rbp
0x1800019fa  push    rbx
0x1800019fb  push    rsi
0x1800019fc  push    rdi
0x1800019fd  push    r15
0x1800019ff  lea     rbp, [rsp-0A0h]
0x180001a07  sub     rsp, 1A0h
0x180001a0e  mov     rax, cs:__security_cookie
0x180001a15  xor     rax, rsp
0x180001a18  mov     [rbp+0C0h+var_30], rax
0x180001a1f  mov     rax, [rbp+0C0h+arg_B8]
0x180001a26  lea     rsi, qword_180012910
0x180001a2d  xor     edi, edi
0x180001a2f  mov     [rbp+0C0h+var_40], rax
0x180001a36  mov     rax, [rbp+0C0h+arg_B0]
0x180001a3d  mov     r11, rdx
0x180001a40  mov     r10, rcx
0x180001a43  mov     [rbp+0C0h+var_38], 8
0x180001a4e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001a52  mov     rbx, r8
0x180001a55  lea     r8d, [rdi+1]
0x180001a59  mov     rcx, [rax]
0x180001a5c  test    rcx, rcx
0x180001a5f  jz      short loc_180001A71
0x180001a61  mov     rax, rdx
0x180001a64  inc     rax
0x180001a67  cmp     [rcx+rax], dil
0x180001a6b  jnz     short loc_180001A64
0x180001a6d  inc     eax
0x180001a6f  jmp     short loc_180001A77
0x180001a71  mov     rcx, rsi
0x180001a74  mov     eax, r8d
0x180001a77  mov     [rbp+0C0h+var_48], eax
0x180001a7a  mov     r9d, 2
0x180001a80  mov     rax, [rbp+0C0h+arg_A8]
0x180001a87  mov     [rbp+0C0h+var_60], rax
0x180001a8b  mov     rax, [rbp+0C0h+arg_A0]
0x180001a92  mov     [rbp+0C0h+var_70], rax
0x180001a96  mov     rax, [rbp+0C0h+arg_98]
0x180001a9d  mov     [rbp+0C0h+var_50], rcx
0x180001aa1  mov     [rbp+0C0h+var_44], edi
0x180001aa4  mov     [rbp+0C0h+var_58], 4
0x180001aac  mov     rcx, [rax]
0x180001aaf  mov     [rbp+0C0h+var_68], 4
0x180001ab7  test    rcx, rcx
0x180001aba  jz      short loc_180001AD1
0x180001abc  mov     rax, rdx
0x180001abf  inc     rax
0x180001ac2  cmp     [rcx+rax*2], di
0x180001ac6  jnz     short loc_180001ABF
0x180001ac8  lea     eax, ds:2[rax*2]
0x180001acf  jmp     short loc_180001ADB
0x180001ad1  lea     rcx, qword_180012C50
0x180001ad8  mov     eax, r9d
0x180001adb  mov     [rbp+0C0h+var_78], eax
0x180001ade  mov     rax, [rbp+0C0h+arg_90]
0x180001ae5  mov     [rbp+0C0h+var_80], rcx
0x180001ae9  mov     [rbp+0C0h+var_74], edi
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
0x180001b0a  mov     [rbp+0C0h+var_88], eax
0x180001b0d  mov     rax, [rbp+0C0h+arg_88]
0x180001b14  mov     [rbp+0C0h+var_A0], rax
0x180001b18  mov     rax, [rbp+0C0h+arg_80]
0x180001b1f  mov     [rbp+0C0h+var_90], rcx
0x180001b23  mov     [rbp+0C0h+var_84], edi
0x180001b26  mov     [rbp+0C0h+var_98], 4
0x180001b2e  mov     rcx, [rax]
0x180001b31  test    rcx, rcx
0x180001b34  jz      short loc_180001B4B
0x180001b36  mov     rax, rdx
0x180001b39  inc     rax
0x180001b3c  cmp     [rcx+rax*2], di
0x180001b40  jnz     short loc_180001B39
0x180001b42  lea     eax, ds:2[rax*2]
0x180001b49  jmp     short loc_180001B55
0x180001b4b  lea     rcx, qword_180012C50
0x180001b52  mov     eax, r9d
0x180001b55  mov     [rbp+0C0h+var_A8], eax
0x180001b58  mov     rax, [rbp+0C0h+arg_78]
0x180001b5f  mov     [rbp+0C0h+var_B0], rcx
0x180001b63  mov     [rbp+0C0h+var_A4], edi
0x180001b66  mov     rcx, [rax]
0x180001b69  test    rcx, rcx
0x180001b6c  jz      short loc_180001B7E
0x180001b6e  mov     rax, rdx
0x180001b71  inc     rax
0x180001b74  cmp     [rcx+rax], dil
0x180001b78  jnz     short loc_180001B71
0x180001b7a  inc     eax
0x180001b7c  jmp     short loc_180001B84
0x180001b7e  mov     rcx, rsi
0x180001b81  mov     eax, r8d
0x180001b84  mov     [rbp+0C0h+var_B8], eax
0x180001b87  mov     rax, [rbp+0C0h+arg_70]
0x180001b8e  mov     [rbp+0C0h+var_D0], rax
0x180001b92  mov     rax, [rbp+0C0h+arg_68]
0x180001b99  mov     [rbp+0C0h+var_C0], rcx
0x180001b9d  mov     [rbp+0C0h+var_B4], edi
0x180001ba0  mov     [rbp+0C0h+var_C8], 4
0x180001ba8  mov     rcx, [rax]
0x180001bab  test    rcx, rcx
0x180001bae  jz      short loc_180001BC0
0x180001bb0  mov     rax, rdx
0x180001bb3  inc     rax
0x180001bb6  cmp     [rcx+rax], dil
0x180001bba  jnz     short loc_180001BB3
0x180001bbc  inc     eax
0x180001bbe  jmp     short loc_180001BC6
0x180001bc0  mov     rcx, rsi
0x180001bc3  mov     eax, r8d
0x180001bc6  mov     [rbp+0C0h+var_D8], eax
0x180001bc9  mov     rax, [rbp+0C0h+arg_60]
0x180001bd0  mov     [rbp+0C0h+var_F0], rax
0x180001bd4  mov     rax, [rbp+0C0h+arg_58]
0x180001bdb  mov     [rbp+0C0h+var_E0], rcx
0x180001bdf  mov     [rbp+0C0h+var_D4], edi
0x180001be2  mov     [rbp+0C0h+var_E8], 4
0x180001bea  mov     rcx, [rax]
0x180001bed  test    rcx, rcx
0x180001bf0  jz      short loc_180001C08
0x180001bf2  mov     rax, rdx
0x180001bf5  inc     rax
0x180001bf8  cmp     [rcx+rax*2], di
0x180001bfc  jnz     short loc_180001BF5
0x180001bfe  lea     r9d, ds:2[rax*2]
0x180001c06  jmp     short loc_180001C0F
0x180001c08  lea     rcx, qword_180012C50
0x180001c0f  mov     rax, [rbp+0C0h+arg_50]
0x180001c16  mov     [rbp+0C0h+var_110], rax
0x180001c1a  mov     rax, [rbp+0C0h+arg_48]
0x180001c21  mov     [rbp+0C0h+var_100], rcx
0x180001c25  mov     [rbp+0C0h+var_F8], r9d
0x180001c29  mov     [rbp+0C0h+var_F4], edi
0x180001c2c  mov     rcx, [rax]
0x180001c2f  mov     [rbp+0C0h+var_108], 4
0x180001c37  test    rcx, rcx
0x180001c3a  jz      short loc_180001C4C
0x180001c3c  mov     rax, rdx
0x180001c3f  inc     rax
0x180001c42  cmp     [rcx+rax], dil
0x180001c46  jnz     short loc_180001C3F
0x180001c48  inc     eax
0x180001c4a  jmp     short loc_180001C52
0x180001c4c  mov     rcx, rsi
0x180001c4f  mov     eax, r8d
0x180001c52  mov     [rbp+0C0h+var_118], eax
0x180001c55  mov     rax, [rbp+0C0h+arg_40]
0x180001c5c  mov     [rbp+0C0h+var_130], rax
0x180001c60  mov     rax, [rbp+0C0h+arg_38]
0x180001c67  mov     [rbp+0C0h+var_120], rcx
0x180001c6b  mov     [rbp+0C0h+var_114], edi
0x180001c6e  mov     [rbp+0C0h+var_128], 4
0x180001c76  mov     rcx, [rax]
0x180001c79  test    rcx, rcx
0x180001c7c  jz      short loc_180001C8D
0x180001c7e  inc     rdx
0x180001c81  cmp     [rcx+rdx], dil
0x180001c85  jnz     short loc_180001C7E
0x180001c87  lea     r8d, [rdx+1]
0x180001c8b  jmp     short loc_180001C90
0x180001c8d  mov     rcx, rsi
0x180001c90  mov     rax, [rbp+0C0h+arg_30]
0x180001c97  xor     r9d, r9d
0x180001c9a  mov     [rsp+1C0h+var_150], rax
0x180001c9f  mov     rdx, r11
0x180001ca2  mov     rax, [rbp+0C0h+arg_28]
0x180001ca9  mov     [rsp+1C0h+var_160], rax
0x180001cae  mov     rax, [rbp+0C0h+arg_20]
0x180001cb5  mov     [rsp+1C0h+var_170], rax
0x180001cba  lea     rax, [rsp+1C0h+var_190]
0x180001cbf  mov     [rbp+0C0h+var_140], rcx
0x180001cc3  mov     rcx, r10
0x180001cc6  mov     [rbp+0C0h+var_138], r8d
0x180001cca  mov     r8, rbx
0x180001ccd  mov     [rsp+1C0h+var_198], rax
0x180001cd2  mov     [rsp+1C0h+var_1A0], 16h
0x180001cda  mov     [rbp+0C0h+var_134], edi
0x180001cdd  mov     [rsp+1C0h+var_148], 4
0x180001ce6  mov     [rsp+1C0h+var_158], 8
0x180001cef  mov     [rsp+1C0h+var_168], 8
0x180001cf8  call    _tlgWriteTransfer_EventWriteTransfer
0x180001cfd  mov     rcx, [rbp+0C0h+var_30]
0x180001d04  xor     rcx, rsp; StackCookie
0x180001d07  call    __security_check_cookie
0x180001d0c  add     rsp, 1A0h
0x180001d13  pop     r15
0x180001d15  pop     rdi
0x180001d16  pop     rsi
0x180001d17  pop     rbx
0x180001d18  pop     rbp
0x180001d19  retn
```
