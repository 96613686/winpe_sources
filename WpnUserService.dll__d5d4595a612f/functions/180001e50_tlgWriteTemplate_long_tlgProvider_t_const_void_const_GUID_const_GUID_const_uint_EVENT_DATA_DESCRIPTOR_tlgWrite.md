# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001e50`
- end: `0x180002146`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645664@Z`
- size: `758`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, __int64 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64 **, __int64, const unsigned __int16 **, __int64 **, __int64 **, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f628`
- `0x18000f908`

## callees

- `0x180001bdc`
- `0x180001e50`
- `0x180002bc0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
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
        __int64 **a21,
        __int64 a22)
{
  __int64 v24; // rdx
  int v26; // r9d
  __int64 *v27; // rcx
  __int64 v28; // rax
  int v29; // eax
  __int64 *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  int v33; // r8d
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
  _BYTE v53[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v54; // [rsp+50h] [rbp-B0h]
  __int64 v55; // [rsp+58h] [rbp-A8h]
  __int64 v56; // [rsp+60h] [rbp-A0h]
  __int64 v57; // [rsp+68h] [rbp-98h]
  __int64 v58; // [rsp+70h] [rbp-90h]
  __int64 v59; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v60; // [rsp+80h] [rbp-80h]
  int v61; // [rsp+88h] [rbp-78h]
  int v62; // [rsp+8Ch] [rbp-74h]
  __int64 v63; // [rsp+90h] [rbp-70h]
  __int64 v64; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v65; // [rsp+A0h] [rbp-60h]
  int v66; // [rsp+A8h] [rbp-58h]
  int v67; // [rsp+ACh] [rbp-54h]
  __int64 v68; // [rsp+B0h] [rbp-50h]
  __int64 v69; // [rsp+B8h] [rbp-48h]
  __int64 *v70; // [rsp+C0h] [rbp-40h]
  int v71; // [rsp+C8h] [rbp-38h]
  int v72; // [rsp+CCh] [rbp-34h]
  __int64 v73; // [rsp+D0h] [rbp-30h]
  __int64 v74; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v75; // [rsp+E0h] [rbp-20h]
  int v76; // [rsp+E8h] [rbp-18h]
  int v77; // [rsp+ECh] [rbp-14h]
  __int64 v78; // [rsp+F0h] [rbp-10h]
  __int64 v79; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v80; // [rsp+100h] [rbp+0h]
  int v81; // [rsp+108h] [rbp+8h]
  int v82; // [rsp+10Ch] [rbp+Ch]
  __int64 *v83; // [rsp+110h] [rbp+10h]
  int v84; // [rsp+118h] [rbp+18h]
  int v85; // [rsp+11Ch] [rbp+1Ch]
  __int64 v86; // [rsp+120h] [rbp+20h]
  __int64 v87; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v88; // [rsp+130h] [rbp+30h]
  int v89; // [rsp+138h] [rbp+38h]
  int v90; // [rsp+13Ch] [rbp+3Ch]
  __int64 *v91; // [rsp+140h] [rbp+40h]
  int v92; // [rsp+148h] [rbp+48h]
  int v93; // [rsp+14Ch] [rbp+4Ch]
  __int64 *v94; // [rsp+150h] [rbp+50h]
  int v95; // [rsp+158h] [rbp+58h]
  int v96; // [rsp+15Ch] [rbp+5Ch]
  __int64 v97; // [rsp+160h] [rbp+60h]
  __int64 v98; // [rsp+168h] [rbp+68h]

  v97 = a22;
  v24 = -1;
  v98 = 4;
  v26 = 2;
  v27 = *a21;
  if ( *a21 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *((_WORD *)v27 + v28) );
    v29 = 2 * v28 + 2;
  }
  else
  {
    v27 = &qword_1800142D0;
    v29 = 2;
  }
  v95 = v29;
  v94 = v27;
  v96 = 0;
  v30 = *a20;
  if ( *a20 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *((_WORD *)v30 + v31) );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &qword_1800142D0;
    v32 = 2;
  }
  v92 = v32;
  v33 = 1;
  v91 = v30;
  v93 = 0;
  v34 = *a19;
  if ( *a19 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &byte_180013B63;
    v36 = 1;
  }
  v89 = v36;
  v86 = a18;
  v88 = v34;
  v90 = 0;
  v87 = 4;
  v37 = *a17;
  if ( *a17 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_WORD *)v37 + v38) );
    v39 = 2 * v38 + 2;
  }
  else
  {
    v37 = &qword_1800142D0;
    v39 = 2;
  }
  v84 = v39;
  v83 = v37;
  v85 = 0;
  v40 = *a16;
  if ( *a16 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_BYTE *)v40 + v41) );
    v42 = v41 + 1;
  }
  else
  {
    v40 = &byte_180013B63;
    v42 = 1;
  }
  v81 = v42;
  v78 = a15;
  v80 = v40;
  v82 = 0;
  v79 = 4;
  v43 = *a14;
  if ( *a14 )
  {
    v44 = -1;
    do
      ++v44;
    while ( *((_BYTE *)v43 + v44) );
    v45 = v44 + 1;
  }
  else
  {
    v43 = &byte_180013B63;
    v45 = 1;
  }
  v76 = v45;
  v73 = a13;
  v75 = v43;
  v77 = 0;
  v74 = 4;
  v46 = *a12;
  if ( *a12 )
  {
    v47 = -1;
    do
      ++v47;
    while ( *((_WORD *)v46 + v47) );
    v26 = 2 * v47 + 2;
  }
  else
  {
    v46 = &qword_1800142D0;
  }
  v68 = a11;
  v70 = v46;
  v71 = v26;
  v72 = 0;
  v48 = *a10;
  v69 = 4;
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
    v48 = &byte_180013B63;
    v50 = 1;
  }
  v66 = v50;
  v63 = a9;
  v65 = v48;
  v67 = 0;
  v64 = 4;
  v51 = *a8;
  if ( *a8 )
  {
    do
      ++v24;
    while ( *((_BYTE *)v51 + v24) );
    v33 = v24 + 1;
  }
  else
  {
    v51 = &byte_180013B63;
  }
  v58 = a7;
  v56 = a6;
  v54 = a5;
  v60 = v51;
  v61 = v33;
  v62 = 0;
  v59 = 4;
  v57 = 8;
  v55 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 20, v53);
}

```

## disassembly

```asm
0x180001e50  push    rbp
0x180001e52  push    rbx
0x180001e53  push    rsi
0x180001e54  push    rdi
0x180001e55  push    r15
0x180001e57  lea     rbp, [rsp-80h]
0x180001e5c  sub     rsp, 180h
0x180001e63  mov     rax, cs:__security_cookie
0x180001e6a  xor     rax, rsp
0x180001e6d  mov     [rbp+0A0h+var_30], rax
0x180001e71  mov     rax, [rbp+0A0h+arg_A8]
0x180001e78  xor     edi, edi
0x180001e7a  mov     [rbp+0A0h+var_40], rax
0x180001e7e  mov     r11, rdx
0x180001e81  mov     rax, [rbp+0A0h+arg_A0]
0x180001e88  mov     r10, rcx
0x180001e8b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001e8f  mov     [rbp+0A0h+var_38], 4
0x180001e97  mov     rbx, r8
0x180001e9a  lea     r9d, [rdi+2]
0x180001e9e  mov     rcx, [rax]
0x180001ea1  test    rcx, rcx
0x180001ea4  jz      short loc_180001EBB
0x180001ea6  mov     rax, rdx
0x180001ea9  inc     rax
0x180001eac  cmp     [rcx+rax*2], di
0x180001eb0  jnz     short loc_180001EA9
0x180001eb2  lea     eax, ds:2[rax*2]
0x180001eb9  jmp     short loc_180001EC5
0x180001ebb  lea     rcx, qword_1800142D0
0x180001ec2  mov     eax, r9d
0x180001ec5  mov     [rbp+0A0h+var_48], eax
0x180001ec8  mov     rax, [rbp+0A0h+arg_98]
0x180001ecf  mov     [rbp+0A0h+var_50], rcx
0x180001ed3  mov     [rbp+0A0h+var_44], edi
0x180001ed6  mov     rcx, [rax]
0x180001ed9  test    rcx, rcx
0x180001edc  jz      short loc_180001EF3
0x180001ede  mov     rax, rdx
0x180001ee1  inc     rax
0x180001ee4  cmp     [rcx+rax*2], di
0x180001ee8  jnz     short loc_180001EE1
0x180001eea  lea     eax, ds:2[rax*2]
0x180001ef1  jmp     short loc_180001EFD
0x180001ef3  lea     rcx, qword_1800142D0
0x180001efa  mov     eax, r9d
0x180001efd  mov     [rbp+0A0h+var_58], eax
0x180001f00  lea     rsi, byte_180013B63
0x180001f07  mov     rax, [rbp+0A0h+arg_90]
0x180001f0e  mov     r8d, 1
0x180001f14  mov     [rbp+0A0h+var_60], rcx
0x180001f18  mov     [rbp+0A0h+var_54], edi
0x180001f1b  mov     rcx, [rax]
0x180001f1e  test    rcx, rcx
0x180001f21  jz      short loc_180001F33
0x180001f23  mov     rax, rdx
0x180001f26  inc     rax
0x180001f29  cmp     [rcx+rax], dil
0x180001f2d  jnz     short loc_180001F26
0x180001f2f  inc     eax
0x180001f31  jmp     short loc_180001F39
0x180001f33  mov     rcx, rsi
0x180001f36  mov     eax, r8d
0x180001f39  mov     [rbp+0A0h+var_68], eax
0x180001f3c  mov     rax, [rbp+0A0h+arg_88]
0x180001f43  mov     [rbp+0A0h+var_80], rax
0x180001f47  mov     rax, [rbp+0A0h+arg_80]
0x180001f4e  mov     [rbp+0A0h+var_70], rcx
0x180001f52  mov     [rbp+0A0h+var_64], edi
0x180001f55  mov     [rbp+0A0h+var_78], 4
0x180001f5d  mov     rcx, [rax]
0x180001f60  test    rcx, rcx
0x180001f63  jz      short loc_180001F7A
0x180001f65  mov     rax, rdx
0x180001f68  inc     rax
0x180001f6b  cmp     [rcx+rax*2], di
0x180001f6f  jnz     short loc_180001F68
0x180001f71  lea     eax, ds:2[rax*2]
0x180001f78  jmp     short loc_180001F84
0x180001f7a  lea     rcx, qword_1800142D0
0x180001f81  mov     eax, r9d
0x180001f84  mov     [rbp+0A0h+var_88], eax
0x180001f87  mov     rax, [rbp+0A0h+arg_78]
0x180001f8e  mov     [rbp+0A0h+var_90], rcx
0x180001f92  mov     [rbp+0A0h+var_84], edi
0x180001f95  mov     rcx, [rax]
0x180001f98  test    rcx, rcx
0x180001f9b  jz      short loc_180001FAD
0x180001f9d  mov     rax, rdx
0x180001fa0  inc     rax
0x180001fa3  cmp     [rcx+rax], dil
0x180001fa7  jnz     short loc_180001FA0
0x180001fa9  inc     eax
0x180001fab  jmp     short loc_180001FB3
0x180001fad  mov     rcx, rsi
0x180001fb0  mov     eax, r8d
0x180001fb3  mov     [rbp+0A0h+var_98], eax
0x180001fb6  mov     rax, [rbp+0A0h+arg_70]
0x180001fbd  mov     [rbp+0A0h+var_B0], rax
0x180001fc1  mov     rax, [rbp+0A0h+arg_68]
0x180001fc8  mov     [rbp+0A0h+var_A0], rcx
0x180001fcc  mov     [rbp+0A0h+var_94], edi
0x180001fcf  mov     [rbp+0A0h+var_A8], 4
0x180001fd7  mov     rcx, [rax]
0x180001fda  test    rcx, rcx
0x180001fdd  jz      short loc_180001FEF
0x180001fdf  mov     rax, rdx
0x180001fe2  inc     rax
0x180001fe5  cmp     [rcx+rax], dil
0x180001fe9  jnz     short loc_180001FE2
0x180001feb  inc     eax
0x180001fed  jmp     short loc_180001FF5
0x180001fef  mov     rcx, rsi
0x180001ff2  mov     eax, r8d
0x180001ff5  mov     [rbp+0A0h+var_B8], eax
0x180001ff8  mov     rax, [rbp+0A0h+arg_60]
0x180001fff  mov     [rbp+0A0h+var_D0], rax
0x180002003  mov     rax, [rbp+0A0h+arg_58]
0x18000200a  mov     [rbp+0A0h+var_C0], rcx
0x18000200e  mov     [rbp+0A0h+var_B4], edi
0x180002011  mov     [rbp+0A0h+var_C8], 4
0x180002019  mov     rcx, [rax]
0x18000201c  test    rcx, rcx
0x18000201f  jz      short loc_180002037
0x180002021  mov     rax, rdx
0x180002024  inc     rax
0x180002027  cmp     [rcx+rax*2], di
0x18000202b  jnz     short loc_180002024
0x18000202d  lea     r9d, ds:2[rax*2]
0x180002035  jmp     short loc_18000203E
0x180002037  lea     rcx, qword_1800142D0
0x18000203e  mov     rax, [rbp+0A0h+arg_50]
0x180002045  mov     [rbp+0A0h+var_F0], rax
0x180002049  mov     rax, [rbp+0A0h+arg_48]
0x180002050  mov     [rbp+0A0h+var_E0], rcx
0x180002054  mov     [rbp+0A0h+var_D8], r9d
0x180002058  mov     [rbp+0A0h+var_D4], edi
0x18000205b  mov     rcx, [rax]
0x18000205e  mov     [rbp+0A0h+var_E8], 4
0x180002066  test    rcx, rcx
0x180002069  jz      short loc_18000207B
0x18000206b  mov     rax, rdx
0x18000206e  inc     rax
0x180002071  cmp     [rcx+rax], dil
0x180002075  jnz     short loc_18000206E
0x180002077  inc     eax
0x180002079  jmp     short loc_180002081
0x18000207b  mov     rcx, rsi
0x18000207e  mov     eax, r8d
0x180002081  mov     [rbp+0A0h+var_F8], eax
0x180002084  mov     rax, [rbp+0A0h+arg_40]
0x18000208b  mov     [rbp+0A0h+var_110], rax
0x18000208f  mov     rax, [rbp+0A0h+arg_38]
0x180002096  mov     [rbp+0A0h+var_100], rcx
0x18000209a  mov     [rbp+0A0h+var_F4], edi
0x18000209d  mov     [rbp+0A0h+var_108], 4
0x1800020a5  mov     rcx, [rax]
0x1800020a8  test    rcx, rcx
0x1800020ab  jz      short loc_1800020BC
0x1800020ad  inc     rdx
0x1800020b0  cmp     [rcx+rdx], dil
0x1800020b4  jnz     short loc_1800020AD
0x1800020b6  lea     r8d, [rdx+1]
0x1800020ba  jmp     short loc_1800020BF
0x1800020bc  mov     rcx, rsi
0x1800020bf  mov     rax, [rbp+0A0h+arg_30]
0x1800020c6  xor     r9d, r9d
0x1800020c9  mov     [rsp+1A0h+var_130], rax
0x1800020ce  mov     rdx, r11
0x1800020d1  mov     rax, [rbp+0A0h+arg_28]
0x1800020d8  mov     [rsp+1A0h+var_140], rax
0x1800020dd  mov     rax, [rbp+0A0h+arg_20]
0x1800020e4  mov     [rsp+1A0h+var_150], rax
0x1800020e9  lea     rax, [rsp+1A0h+var_170]
0x1800020ee  mov     [rbp+0A0h+var_120], rcx
0x1800020f2  mov     rcx, r10
0x1800020f5  mov     [rbp+0A0h+var_118], r8d
0x1800020f9  mov     r8, rbx
0x1800020fc  mov     [rsp+1A0h+var_178], rax
0x180002101  mov     [rsp+1A0h+var_180], 14h
0x180002109  mov     [rbp+0A0h+var_114], edi
0x18000210c  mov     [rsp+1A0h+var_128], 4
0x180002115  mov     [rsp+1A0h+var_138], 8
0x18000211e  mov     [rsp+1A0h+var_148], 8
0x180002127  call    _tlgWriteTransfer_EventWriteTransfer
0x18000212c  mov     rcx, [rbp+0A0h+var_30]
0x180002130  xor     rcx, rsp; StackCookie
0x180002133  call    __security_check_cookie
0x180002138  add     rsp, 180h
0x18000213f  pop     r15
0x180002141  pop     rdi
0x180002142  pop     rsi
0x180002143  pop     rbx
0x180002144  pop     rbp
0x180002145  retn
```
