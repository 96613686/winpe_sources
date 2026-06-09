# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001d24`
- end: `0x180002047`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564454@Z`
- size: `803`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ac60`
- `0x18000af58`
- `0x18000b590`

## callees

- `0x180001640`
- `0x180001d24`
- `0x180002910`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
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
  v104 = 4;
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
0x180001d24  push    rbp
0x180001d26  push    rbx
0x180001d27  push    rsi
0x180001d28  push    rdi
0x180001d29  push    r15
0x180001d2b  lea     rbp, [rsp-0A0h]
0x180001d33  sub     rsp, 1A0h
0x180001d3a  mov     rax, cs:__security_cookie
0x180001d41  xor     rax, rsp
0x180001d44  mov     [rbp+0C0h+var_30], rax
0x180001d4b  mov     rax, [rbp+0C0h+arg_B8]
0x180001d52  lea     rsi, qword_180012910
0x180001d59  xor     edi, edi
0x180001d5b  mov     [rbp+0C0h+var_40], rax
0x180001d62  mov     rax, [rbp+0C0h+arg_B0]
0x180001d69  mov     r11, rdx
0x180001d6c  mov     r10, rcx
0x180001d6f  mov     [rbp+0C0h+var_38], 4
0x180001d7a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001d7e  mov     rbx, r8
0x180001d81  lea     r8d, [rdi+1]
0x180001d85  mov     rcx, [rax]
0x180001d88  test    rcx, rcx
0x180001d8b  jz      short loc_180001D9D
0x180001d8d  mov     rax, rdx
0x180001d90  inc     rax
0x180001d93  cmp     [rcx+rax], dil
0x180001d97  jnz     short loc_180001D90
0x180001d99  inc     eax
0x180001d9b  jmp     short loc_180001DA3
0x180001d9d  mov     rcx, rsi
0x180001da0  mov     eax, r8d
0x180001da3  mov     [rbp+0C0h+var_48], eax
0x180001da6  mov     r9d, 2
0x180001dac  mov     rax, [rbp+0C0h+arg_A8]
0x180001db3  mov     [rbp+0C0h+var_60], rax
0x180001db7  mov     rax, [rbp+0C0h+arg_A0]
0x180001dbe  mov     [rbp+0C0h+var_70], rax
0x180001dc2  mov     rax, [rbp+0C0h+arg_98]
0x180001dc9  mov     [rbp+0C0h+var_50], rcx
0x180001dcd  mov     [rbp+0C0h+var_44], edi
0x180001dd0  mov     [rbp+0C0h+var_58], 4
0x180001dd8  mov     rcx, [rax]
0x180001ddb  mov     [rbp+0C0h+var_68], 4
0x180001de3  test    rcx, rcx
0x180001de6  jz      short loc_180001DFD
0x180001de8  mov     rax, rdx
0x180001deb  inc     rax
0x180001dee  cmp     [rcx+rax*2], di
0x180001df2  jnz     short loc_180001DEB
0x180001df4  lea     eax, ds:2[rax*2]
0x180001dfb  jmp     short loc_180001E07
0x180001dfd  lea     rcx, qword_180012C50
0x180001e04  mov     eax, r9d
0x180001e07  mov     [rbp+0C0h+var_78], eax
0x180001e0a  mov     rax, [rbp+0C0h+arg_90]
0x180001e11  mov     [rbp+0C0h+var_80], rcx
0x180001e15  mov     [rbp+0C0h+var_74], edi
0x180001e18  mov     rcx, [rax]
0x180001e1b  test    rcx, rcx
0x180001e1e  jz      short loc_180001E30
0x180001e20  mov     rax, rdx
0x180001e23  inc     rax
0x180001e26  cmp     [rcx+rax], dil
0x180001e2a  jnz     short loc_180001E23
0x180001e2c  inc     eax
0x180001e2e  jmp     short loc_180001E36
0x180001e30  mov     rcx, rsi
0x180001e33  mov     eax, r8d
0x180001e36  mov     [rbp+0C0h+var_88], eax
0x180001e39  mov     rax, [rbp+0C0h+arg_88]
0x180001e40  mov     [rbp+0C0h+var_A0], rax
0x180001e44  mov     rax, [rbp+0C0h+arg_80]
0x180001e4b  mov     [rbp+0C0h+var_90], rcx
0x180001e4f  mov     [rbp+0C0h+var_84], edi
0x180001e52  mov     [rbp+0C0h+var_98], 4
0x180001e5a  mov     rcx, [rax]
0x180001e5d  test    rcx, rcx
0x180001e60  jz      short loc_180001E77
0x180001e62  mov     rax, rdx
0x180001e65  inc     rax
0x180001e68  cmp     [rcx+rax*2], di
0x180001e6c  jnz     short loc_180001E65
0x180001e6e  lea     eax, ds:2[rax*2]
0x180001e75  jmp     short loc_180001E81
0x180001e77  lea     rcx, qword_180012C50
0x180001e7e  mov     eax, r9d
0x180001e81  mov     [rbp+0C0h+var_A8], eax
0x180001e84  mov     rax, [rbp+0C0h+arg_78]
0x180001e8b  mov     [rbp+0C0h+var_B0], rcx
0x180001e8f  mov     [rbp+0C0h+var_A4], edi
0x180001e92  mov     rcx, [rax]
0x180001e95  test    rcx, rcx
0x180001e98  jz      short loc_180001EAA
0x180001e9a  mov     rax, rdx
0x180001e9d  inc     rax
0x180001ea0  cmp     [rcx+rax], dil
0x180001ea4  jnz     short loc_180001E9D
0x180001ea6  inc     eax
0x180001ea8  jmp     short loc_180001EB0
0x180001eaa  mov     rcx, rsi
0x180001ead  mov     eax, r8d
0x180001eb0  mov     [rbp+0C0h+var_B8], eax
0x180001eb3  mov     rax, [rbp+0C0h+arg_70]
0x180001eba  mov     [rbp+0C0h+var_D0], rax
0x180001ebe  mov     rax, [rbp+0C0h+arg_68]
0x180001ec5  mov     [rbp+0C0h+var_C0], rcx
0x180001ec9  mov     [rbp+0C0h+var_B4], edi
0x180001ecc  mov     [rbp+0C0h+var_C8], 4
0x180001ed4  mov     rcx, [rax]
0x180001ed7  test    rcx, rcx
0x180001eda  jz      short loc_180001EEC
0x180001edc  mov     rax, rdx
0x180001edf  inc     rax
0x180001ee2  cmp     [rcx+rax], dil
0x180001ee6  jnz     short loc_180001EDF
0x180001ee8  inc     eax
0x180001eea  jmp     short loc_180001EF2
0x180001eec  mov     rcx, rsi
0x180001eef  mov     eax, r8d
0x180001ef2  mov     [rbp+0C0h+var_D8], eax
0x180001ef5  mov     rax, [rbp+0C0h+arg_60]
0x180001efc  mov     [rbp+0C0h+var_F0], rax
0x180001f00  mov     rax, [rbp+0C0h+arg_58]
0x180001f07  mov     [rbp+0C0h+var_E0], rcx
0x180001f0b  mov     [rbp+0C0h+var_D4], edi
0x180001f0e  mov     [rbp+0C0h+var_E8], 4
0x180001f16  mov     rcx, [rax]
0x180001f19  test    rcx, rcx
0x180001f1c  jz      short loc_180001F34
0x180001f1e  mov     rax, rdx
0x180001f21  inc     rax
0x180001f24  cmp     [rcx+rax*2], di
0x180001f28  jnz     short loc_180001F21
0x180001f2a  lea     r9d, ds:2[rax*2]
0x180001f32  jmp     short loc_180001F3B
0x180001f34  lea     rcx, qword_180012C50
0x180001f3b  mov     rax, [rbp+0C0h+arg_50]
0x180001f42  mov     [rbp+0C0h+var_110], rax
0x180001f46  mov     rax, [rbp+0C0h+arg_48]
0x180001f4d  mov     [rbp+0C0h+var_100], rcx
0x180001f51  mov     [rbp+0C0h+var_F8], r9d
0x180001f55  mov     [rbp+0C0h+var_F4], edi
0x180001f58  mov     rcx, [rax]
0x180001f5b  mov     [rbp+0C0h+var_108], 4
0x180001f63  test    rcx, rcx
0x180001f66  jz      short loc_180001F78
0x180001f68  mov     rax, rdx
0x180001f6b  inc     rax
0x180001f6e  cmp     [rcx+rax], dil
0x180001f72  jnz     short loc_180001F6B
0x180001f74  inc     eax
0x180001f76  jmp     short loc_180001F7E
0x180001f78  mov     rcx, rsi
0x180001f7b  mov     eax, r8d
0x180001f7e  mov     [rbp+0C0h+var_118], eax
0x180001f81  mov     rax, [rbp+0C0h+arg_40]
0x180001f88  mov     [rbp+0C0h+var_130], rax
0x180001f8c  mov     rax, [rbp+0C0h+arg_38]
0x180001f93  mov     [rbp+0C0h+var_120], rcx
0x180001f97  mov     [rbp+0C0h+var_114], edi
0x180001f9a  mov     [rbp+0C0h+var_128], 4
0x180001fa2  mov     rcx, [rax]
0x180001fa5  test    rcx, rcx
0x180001fa8  jz      short loc_180001FB9
0x180001faa  inc     rdx
0x180001fad  cmp     [rcx+rdx], dil
0x180001fb1  jnz     short loc_180001FAA
0x180001fb3  lea     r8d, [rdx+1]
0x180001fb7  jmp     short loc_180001FBC
0x180001fb9  mov     rcx, rsi
0x180001fbc  mov     rax, [rbp+0C0h+arg_30]
0x180001fc3  xor     r9d, r9d
0x180001fc6  mov     [rsp+1C0h+var_150], rax
0x180001fcb  mov     rdx, r11
0x180001fce  mov     rax, [rbp+0C0h+arg_28]
0x180001fd5  mov     [rsp+1C0h+var_160], rax
0x180001fda  mov     rax, [rbp+0C0h+arg_20]
0x180001fe1  mov     [rsp+1C0h+var_170], rax
0x180001fe6  lea     rax, [rsp+1C0h+var_190]
0x180001feb  mov     [rbp+0C0h+var_140], rcx
0x180001fef  mov     rcx, r10
0x180001ff2  mov     [rbp+0C0h+var_138], r8d
0x180001ff6  mov     r8, rbx
0x180001ff9  mov     [rsp+1C0h+var_198], rax
0x180001ffe  mov     [rsp+1C0h+var_1A0], 16h
0x180002006  mov     [rbp+0C0h+var_134], edi
0x180002009  mov     [rsp+1C0h+var_148], 4
0x180002012  mov     [rsp+1C0h+var_158], 8
0x18000201b  mov     [rsp+1C0h+var_168], 8
0x180002024  call    _tlgWriteTransfer_EventWriteTransfer
0x180002029  mov     rcx, [rbp+0C0h+var_30]
0x180002030  xor     rcx, rsp; StackCookie
0x180002033  call    __security_check_cookie
0x180002038  add     rsp, 1A0h
0x18000203f  pop     r15
0x180002041  pop     rdi
0x180002042  pop     rsi
0x180002043  pop     rbx
0x180002044  pop     rbp
0x180002045  retn
```
