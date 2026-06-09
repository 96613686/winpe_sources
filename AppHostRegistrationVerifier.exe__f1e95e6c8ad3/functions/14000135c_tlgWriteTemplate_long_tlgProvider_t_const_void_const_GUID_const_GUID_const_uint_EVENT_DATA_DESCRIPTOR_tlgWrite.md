# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x14000135c`
- end: `0x1400015f7`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `667`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d610`

## callees

- `0x14000135c`
- `0x140001b78`
- `0x140002210`

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
        int **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        int **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        int **a19)
{
  __int64 v21; // rdx
  int v23; // r9d
  int *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  int *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  int *v40; // rcx
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
  int *v62; // [rsp+B0h] [rbp-50h]
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
  int *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  __int64 v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v80; // [rsp+120h] [rbp+20h]
  int v81; // [rsp+128h] [rbp+28h]
  int v82; // [rsp+12Ch] [rbp+2Ch]
  int *v83; // [rsp+130h] [rbp+30h]
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
    v24 = &dword_1400140E4;
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
    v28 = &byte_1400140E0;
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
    v31 = &dword_1400140E4;
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
    v34 = &byte_1400140E0;
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
    v37 = &byte_1400140E0;
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
    v40 = &dword_1400140E4;
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
    v42 = &byte_1400140E0;
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
    v45 = &byte_1400140E0;
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
0x14000135c  push    rbp
0x14000135e  push    rbx
0x14000135f  push    rsi
0x140001360  push    rdi
0x140001361  push    r14
0x140001363  lea     rbp, [rsp-50h]
0x140001368  sub     rsp, 150h
0x14000136f  mov     rax, cs:__security_cookie
0x140001376  xor     rax, rsp
0x140001379  mov     [rbp+70h+var_30], rax
0x14000137d  mov     rax, [rbp+70h+arg_90]
0x140001384  mov     r11, rdx
0x140001387  mov     r10, rcx
0x14000138a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000138e  xor     edi, edi
0x140001390  mov     rbx, r8
0x140001393  mov     r9d, 2
0x140001399  mov     rcx, [rax]
0x14000139c  test    rcx, rcx
0x14000139f  jz      short loc_1400013B6
0x1400013a1  mov     rax, rdx
0x1400013a4  inc     rax
0x1400013a7  cmp     [rcx+rax*2], di
0x1400013ab  jnz     short loc_1400013A4
0x1400013ad  lea     eax, ds:2[rax*2]
0x1400013b4  jmp     short loc_1400013C0
0x1400013b6  lea     rcx, dword_1400140E4
0x1400013bd  mov     eax, r9d
0x1400013c0  mov     [rbp+70h+var_38], eax
0x1400013c3  lea     rsi, byte_1400140E0
0x1400013ca  mov     rax, [rbp+70h+arg_88]
0x1400013d1  mov     r8d, 1
0x1400013d7  mov     [rbp+70h+var_40], rcx
0x1400013db  mov     [rbp+70h+var_34], edi
0x1400013de  mov     rcx, [rax]
0x1400013e1  test    rcx, rcx
0x1400013e4  jz      short loc_1400013F6
0x1400013e6  mov     rax, rdx
0x1400013e9  inc     rax
0x1400013ec  cmp     [rcx+rax], dil
0x1400013f0  jnz     short loc_1400013E9
0x1400013f2  inc     eax
0x1400013f4  jmp     short loc_1400013FC
0x1400013f6  mov     rcx, rsi
0x1400013f9  mov     eax, r8d
0x1400013fc  mov     [rbp+70h+var_48], eax
0x1400013ff  mov     rax, [rbp+70h+arg_80]
0x140001406  mov     [rbp+70h+var_60], rax
0x14000140a  mov     rax, [rbp+70h+arg_78]
0x140001411  mov     [rbp+70h+var_50], rcx
0x140001415  mov     [rbp+70h+var_44], edi
0x140001418  mov     [rbp+70h+var_58], 4
0x140001420  mov     rcx, [rax]
0x140001423  test    rcx, rcx
0x140001426  jz      short loc_14000143D
0x140001428  mov     rax, rdx
0x14000142b  inc     rax
0x14000142e  cmp     [rcx+rax*2], di
0x140001432  jnz     short loc_14000142B
0x140001434  lea     eax, ds:2[rax*2]
0x14000143b  jmp     short loc_140001447
0x14000143d  lea     rcx, dword_1400140E4
0x140001444  mov     eax, r9d
0x140001447  mov     [rbp+70h+var_68], eax
0x14000144a  mov     rax, [rbp+70h+arg_70]
0x140001451  mov     [rbp+70h+var_70], rcx
0x140001455  mov     [rbp+70h+var_64], edi
0x140001458  mov     rcx, [rax]
0x14000145b  test    rcx, rcx
0x14000145e  jz      short loc_140001470
0x140001460  mov     rax, rdx
0x140001463  inc     rax
0x140001466  cmp     [rcx+rax], dil
0x14000146a  jnz     short loc_140001463
0x14000146c  inc     eax
0x14000146e  jmp     short loc_140001476
0x140001470  mov     rcx, rsi
0x140001473  mov     eax, r8d
0x140001476  mov     [rbp+70h+var_78], eax
0x140001479  mov     rax, [rbp+70h+arg_68]
0x140001480  mov     [rbp+70h+var_90], rax
0x140001484  mov     rax, [rbp+70h+arg_60]
0x14000148b  mov     [rbp+70h+var_80], rcx
0x14000148f  mov     [rbp+70h+var_74], edi
0x140001492  mov     [rbp+70h+var_88], 4
0x14000149a  mov     rcx, [rax]
0x14000149d  test    rcx, rcx
0x1400014a0  jz      short loc_1400014B2
0x1400014a2  mov     rax, rdx
0x1400014a5  inc     rax
0x1400014a8  cmp     [rcx+rax], dil
0x1400014ac  jnz     short loc_1400014A5
0x1400014ae  inc     eax
0x1400014b0  jmp     short loc_1400014B8
0x1400014b2  mov     rcx, rsi
0x1400014b5  mov     eax, r8d
0x1400014b8  mov     [rbp+70h+var_98], eax
0x1400014bb  mov     rax, [rbp+70h+arg_58]
0x1400014c2  mov     [rbp+70h+var_B0], rax
0x1400014c6  mov     rax, [rbp+70h+arg_50]
0x1400014cd  mov     [rbp+70h+var_A0], rcx
0x1400014d1  mov     [rbp+70h+var_94], edi
0x1400014d4  mov     [rbp+70h+var_A8], 4
0x1400014dc  mov     rcx, [rax]
0x1400014df  test    rcx, rcx
0x1400014e2  jz      short loc_1400014FA
0x1400014e4  mov     rax, rdx
0x1400014e7  inc     rax
0x1400014ea  cmp     [rcx+rax*2], di
0x1400014ee  jnz     short loc_1400014E7
0x1400014f0  lea     r9d, ds:2[rax*2]
0x1400014f8  jmp     short loc_140001501
0x1400014fa  lea     rcx, dword_1400140E4
0x140001501  mov     rax, [rbp+70h+arg_48]
0x140001508  mov     [rbp+70h+var_D0], rax
0x14000150c  mov     rax, [rbp+70h+arg_40]
0x140001513  mov     [rbp+70h+var_C0], rcx
0x140001517  mov     [rbp+70h+var_B8], r9d
0x14000151b  mov     [rbp+70h+var_B4], edi
0x14000151e  mov     rcx, [rax]
0x140001521  mov     [rbp+70h+var_C8], 4
0x140001529  test    rcx, rcx
0x14000152c  jz      short loc_14000153E
0x14000152e  mov     rax, rdx
0x140001531  inc     rax
0x140001534  cmp     [rcx+rax], dil
0x140001538  jnz     short loc_140001531
0x14000153a  inc     eax
0x14000153c  jmp     short loc_140001544
0x14000153e  mov     rcx, rsi
0x140001541  mov     eax, r8d
0x140001544  mov     [rbp+70h+var_D8], eax
0x140001547  mov     rax, [rbp+70h+arg_38]
0x14000154e  mov     [rbp+70h+var_F0], rax
0x140001552  mov     rax, [rbp+70h+arg_30]
0x140001559  mov     [rbp+70h+var_E0], rcx
0x14000155d  mov     [rbp+70h+var_D4], edi
0x140001560  mov     [rbp+70h+var_E8], 4
0x140001568  mov     rcx, [rax]
0x14000156b  test    rcx, rcx
0x14000156e  jz      short loc_14000157F
0x140001570  inc     rdx
0x140001573  cmp     [rcx+rdx], dil
0x140001577  jnz     short loc_140001570
0x140001579  lea     r8d, [rdx+1]
0x14000157d  jmp     short loc_140001582
0x14000157f  mov     rcx, rsi
0x140001582  mov     rax, [rbp+70h+arg_28]
0x140001589  xor     r9d, r9d
0x14000158c  mov     [rsp+170h+var_110], rax
0x140001591  mov     rdx, r11
0x140001594  mov     rax, [rbp+70h+arg_20]
0x14000159b  mov     [rsp+170h+var_120], rax
0x1400015a0  lea     rax, [rsp+170h+var_140]
0x1400015a5  mov     [rsp+170h+var_100], rcx
0x1400015aa  mov     rcx, r10
0x1400015ad  mov     [rsp+170h+var_F8], r8d
0x1400015b2  mov     r8, rbx
0x1400015b5  mov     [rsp+170h+var_148], rax
0x1400015ba  mov     [rsp+170h+var_150], 11h
0x1400015c2  mov     [rsp+170h+var_F4], edi
0x1400015c6  mov     [rsp+170h+var_108], 4
0x1400015cf  mov     [rsp+170h+var_118], 8
0x1400015d8  call    _tlgWriteTransfer_EventWriteTransfer
0x1400015dd  mov     rcx, [rbp+70h+var_30]
0x1400015e1  xor     rcx, rsp; StackCookie
0x1400015e4  call    __security_check_cookie
0x1400015e9  add     rsp, 150h
0x1400015f0  pop     r14
0x1400015f2  pop     rdi
0x1400015f3  pop     rsi
0x1400015f4  pop     rbx
0x1400015f5  pop     rbp
0x1400015f6  retn
```
