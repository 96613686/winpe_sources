# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800013a4`
- end: `0x180001651`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `685`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002d758`
- `0x18002e980`

## callees

- `0x1800013a4`
- `0x180001c7c`
- `0x1800350e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
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
        int **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        int **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        int **a20)
{
  __int64 v22; // rdx
  int v24; // r9d
  int *v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  int v28; // r8d
  const unsigned __int16 *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  int *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  const unsigned __int16 *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  const unsigned __int16 *v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  int *v41; // rcx
  __int64 v42; // rax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  const unsigned __int16 *v46; // rcx
  _BYTE v48[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v49; // [rsp+50h] [rbp-B0h]
  __int64 v50; // [rsp+58h] [rbp-A8h]
  __int64 v51; // [rsp+60h] [rbp-A0h]
  __int64 v52; // [rsp+68h] [rbp-98h]
  __int64 v53; // [rsp+70h] [rbp-90h]
  __int64 v54; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v55; // [rsp+80h] [rbp-80h]
  int v56; // [rsp+88h] [rbp-78h]
  int v57; // [rsp+8Ch] [rbp-74h]
  __int64 v58; // [rsp+90h] [rbp-70h]
  __int64 v59; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v60; // [rsp+A0h] [rbp-60h]
  int v61; // [rsp+A8h] [rbp-58h]
  int v62; // [rsp+ACh] [rbp-54h]
  __int64 v63; // [rsp+B0h] [rbp-50h]
  __int64 v64; // [rsp+B8h] [rbp-48h]
  int *v65; // [rsp+C0h] [rbp-40h]
  int v66; // [rsp+C8h] [rbp-38h]
  int v67; // [rsp+CCh] [rbp-34h]
  __int64 v68; // [rsp+D0h] [rbp-30h]
  __int64 v69; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v70; // [rsp+E0h] [rbp-20h]
  int v71; // [rsp+E8h] [rbp-18h]
  int v72; // [rsp+ECh] [rbp-14h]
  __int64 v73; // [rsp+F0h] [rbp-10h]
  __int64 v74; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  int *v78; // [rsp+110h] [rbp+10h]
  int v79; // [rsp+118h] [rbp+18h]
  int v80; // [rsp+11Ch] [rbp+1Ch]
  __int64 v81; // [rsp+120h] [rbp+20h]
  __int64 v82; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v83; // [rsp+130h] [rbp+30h]
  int v84; // [rsp+138h] [rbp+38h]
  int v85; // [rsp+13Ch] [rbp+3Ch]
  int *v86; // [rsp+140h] [rbp+40h]
  int v87; // [rsp+148h] [rbp+48h]
  int v88; // [rsp+14Ch] [rbp+4Ch]

  v22 = -1;
  v24 = 2;
  v25 = *a20;
  if ( *a20 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *((_WORD *)v25 + v26) );
    v27 = 2 * v26 + 2;
  }
  else
  {
    v25 = &dword_18003D19C;
    v27 = 2;
  }
  v87 = v27;
  v28 = 1;
  v86 = v25;
  v88 = 0;
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
    v29 = &byte_18003D198;
    v31 = 1;
  }
  v84 = v31;
  v81 = a18;
  v83 = v29;
  v85 = 0;
  v82 = 4;
  v32 = *a17;
  if ( *a17 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *((_WORD *)v32 + v33) );
    v34 = 2 * v33 + 2;
  }
  else
  {
    v32 = &dword_18003D19C;
    v34 = 2;
  }
  v79 = v34;
  v78 = v32;
  v80 = 0;
  v35 = *a16;
  if ( *a16 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_BYTE *)v35 + v36) );
    v37 = v36 + 1;
  }
  else
  {
    v35 = &byte_18003D198;
    v37 = 1;
  }
  v76 = v37;
  v73 = a15;
  v75 = v35;
  v77 = 0;
  v74 = 4;
  v38 = *a14;
  if ( *a14 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *((_BYTE *)v38 + v39) );
    v40 = v39 + 1;
  }
  else
  {
    v38 = &byte_18003D198;
    v40 = 1;
  }
  v71 = v40;
  v68 = a13;
  v70 = v38;
  v72 = 0;
  v69 = 4;
  v41 = *a12;
  if ( *a12 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *((_WORD *)v41 + v42) );
    v24 = 2 * v42 + 2;
  }
  else
  {
    v41 = &dword_18003D19C;
  }
  v63 = a11;
  v65 = v41;
  v66 = v24;
  v67 = 0;
  v43 = *a10;
  v64 = 4;
  if ( v43 )
  {
    v44 = -1;
    do
      ++v44;
    while ( *((_BYTE *)v43 + v44) );
    v45 = v44 + 1;
  }
  else
  {
    v43 = &byte_18003D198;
    v45 = 1;
  }
  v61 = v45;
  v58 = a9;
  v60 = v43;
  v62 = 0;
  v59 = 4;
  v46 = *a8;
  if ( *a8 )
  {
    do
      ++v22;
    while ( *((_BYTE *)v46 + v22) );
    v28 = v22 + 1;
  }
  else
  {
    v46 = &byte_18003D198;
  }
  v53 = a7;
  v51 = a6;
  v49 = a5;
  v55 = v46;
  v56 = v28;
  v57 = 0;
  v54 = 4;
  v52 = 8;
  v50 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 18, v48);
}

```

## disassembly

```asm
0x1800013a4  push    rbp
0x1800013a6  push    rbx
0x1800013a7  push    rsi
0x1800013a8  push    rdi
0x1800013a9  push    r14
0x1800013ab  lea     rbp, [rsp-60h]
0x1800013b0  sub     rsp, 160h
0x1800013b7  mov     rax, cs:__security_cookie
0x1800013be  xor     rax, rsp
0x1800013c1  mov     [rbp+80h+var_30], rax
0x1800013c5  mov     rax, [rbp+80h+arg_98]
0x1800013cc  mov     r11, rdx
0x1800013cf  mov     r10, rcx
0x1800013d2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800013d6  xor     edi, edi
0x1800013d8  mov     rbx, r8
0x1800013db  mov     r9d, 2
0x1800013e1  mov     rcx, [rax]
0x1800013e4  test    rcx, rcx
0x1800013e7  jz      short loc_1800013FE
0x1800013e9  mov     rax, rdx
0x1800013ec  inc     rax
0x1800013ef  cmp     [rcx+rax*2], di
0x1800013f3  jnz     short loc_1800013EC
0x1800013f5  lea     eax, ds:2[rax*2]
0x1800013fc  jmp     short loc_180001408
0x1800013fe  lea     rcx, dword_18003D19C
0x180001405  mov     eax, r9d
0x180001408  mov     [rbp+80h+var_38], eax
0x18000140b  lea     rsi, byte_18003D198
0x180001412  mov     rax, [rbp+80h+arg_90]
0x180001419  mov     r8d, 1
0x18000141f  mov     [rbp+80h+var_40], rcx
0x180001423  mov     [rbp+80h+var_34], edi
0x180001426  mov     rcx, [rax]
0x180001429  test    rcx, rcx
0x18000142c  jz      short loc_18000143E
0x18000142e  mov     rax, rdx
0x180001431  inc     rax
0x180001434  cmp     [rcx+rax], dil
0x180001438  jnz     short loc_180001431
0x18000143a  inc     eax
0x18000143c  jmp     short loc_180001444
0x18000143e  mov     rcx, rsi
0x180001441  mov     eax, r8d
0x180001444  mov     [rbp+80h+var_48], eax
0x180001447  mov     rax, [rbp+80h+arg_88]
0x18000144e  mov     [rbp+80h+var_60], rax
0x180001452  mov     rax, [rbp+80h+arg_80]
0x180001459  mov     [rbp+80h+var_50], rcx
0x18000145d  mov     [rbp+80h+var_44], edi
0x180001460  mov     [rbp+80h+var_58], 4
0x180001468  mov     rcx, [rax]
0x18000146b  test    rcx, rcx
0x18000146e  jz      short loc_180001485
0x180001470  mov     rax, rdx
0x180001473  inc     rax
0x180001476  cmp     [rcx+rax*2], di
0x18000147a  jnz     short loc_180001473
0x18000147c  lea     eax, ds:2[rax*2]
0x180001483  jmp     short loc_18000148F
0x180001485  lea     rcx, dword_18003D19C
0x18000148c  mov     eax, r9d
0x18000148f  mov     [rbp+80h+var_68], eax
0x180001492  mov     rax, [rbp+80h+arg_78]
0x180001499  mov     [rbp+80h+var_70], rcx
0x18000149d  mov     [rbp+80h+var_64], edi
0x1800014a0  mov     rcx, [rax]
0x1800014a3  test    rcx, rcx
0x1800014a6  jz      short loc_1800014B8
0x1800014a8  mov     rax, rdx
0x1800014ab  inc     rax
0x1800014ae  cmp     [rcx+rax], dil
0x1800014b2  jnz     short loc_1800014AB
0x1800014b4  inc     eax
0x1800014b6  jmp     short loc_1800014BE
0x1800014b8  mov     rcx, rsi
0x1800014bb  mov     eax, r8d
0x1800014be  mov     [rbp+80h+var_78], eax
0x1800014c1  mov     rax, [rbp+80h+arg_70]
0x1800014c8  mov     [rbp+80h+var_90], rax
0x1800014cc  mov     rax, [rbp+80h+arg_68]
0x1800014d3  mov     [rbp+80h+var_80], rcx
0x1800014d7  mov     [rbp+80h+var_74], edi
0x1800014da  mov     [rbp+80h+var_88], 4
0x1800014e2  mov     rcx, [rax]
0x1800014e5  test    rcx, rcx
0x1800014e8  jz      short loc_1800014FA
0x1800014ea  mov     rax, rdx
0x1800014ed  inc     rax
0x1800014f0  cmp     [rcx+rax], dil
0x1800014f4  jnz     short loc_1800014ED
0x1800014f6  inc     eax
0x1800014f8  jmp     short loc_180001500
0x1800014fa  mov     rcx, rsi
0x1800014fd  mov     eax, r8d
0x180001500  mov     [rbp+80h+var_98], eax
0x180001503  mov     rax, [rbp+80h+arg_60]
0x18000150a  mov     [rbp+80h+var_B0], rax
0x18000150e  mov     rax, [rbp+80h+arg_58]
0x180001515  mov     [rbp+80h+var_A0], rcx
0x180001519  mov     [rbp+80h+var_94], edi
0x18000151c  mov     [rbp+80h+var_A8], 4
0x180001524  mov     rcx, [rax]
0x180001527  test    rcx, rcx
0x18000152a  jz      short loc_180001542
0x18000152c  mov     rax, rdx
0x18000152f  inc     rax
0x180001532  cmp     [rcx+rax*2], di
0x180001536  jnz     short loc_18000152F
0x180001538  lea     r9d, ds:2[rax*2]
0x180001540  jmp     short loc_180001549
0x180001542  lea     rcx, dword_18003D19C
0x180001549  mov     rax, [rbp+80h+arg_50]
0x180001550  mov     [rbp+80h+var_D0], rax
0x180001554  mov     rax, [rbp+80h+arg_48]
0x18000155b  mov     [rbp+80h+var_C0], rcx
0x18000155f  mov     [rbp+80h+var_B8], r9d
0x180001563  mov     [rbp+80h+var_B4], edi
0x180001566  mov     rcx, [rax]
0x180001569  mov     [rbp+80h+var_C8], 4
0x180001571  test    rcx, rcx
0x180001574  jz      short loc_180001586
0x180001576  mov     rax, rdx
0x180001579  inc     rax
0x18000157c  cmp     [rcx+rax], dil
0x180001580  jnz     short loc_180001579
0x180001582  inc     eax
0x180001584  jmp     short loc_18000158C
0x180001586  mov     rcx, rsi
0x180001589  mov     eax, r8d
0x18000158c  mov     [rbp+80h+var_D8], eax
0x18000158f  mov     rax, [rbp+80h+arg_40]
0x180001596  mov     [rbp+80h+var_F0], rax
0x18000159a  mov     rax, [rbp+80h+arg_38]
0x1800015a1  mov     [rbp+80h+var_E0], rcx
0x1800015a5  mov     [rbp+80h+var_D4], edi
0x1800015a8  mov     [rbp+80h+var_E8], 4
0x1800015b0  mov     rcx, [rax]
0x1800015b3  test    rcx, rcx
0x1800015b6  jz      short loc_1800015C7
0x1800015b8  inc     rdx
0x1800015bb  cmp     [rcx+rdx], dil
0x1800015bf  jnz     short loc_1800015B8
0x1800015c1  lea     r8d, [rdx+1]
0x1800015c5  jmp     short loc_1800015CA
0x1800015c7  mov     rcx, rsi
0x1800015ca  mov     rax, [rbp+80h+arg_30]
0x1800015d1  xor     r9d, r9d
0x1800015d4  mov     [rsp+180h+var_110], rax
0x1800015d9  mov     rdx, r11
0x1800015dc  mov     rax, [rbp+80h+arg_28]
0x1800015e3  mov     [rsp+180h+var_120], rax
0x1800015e8  mov     rax, [rbp+80h+arg_20]
0x1800015ef  mov     [rsp+180h+var_130], rax
0x1800015f4  lea     rax, [rsp+180h+var_150]
0x1800015f9  mov     [rbp+80h+var_100], rcx
0x1800015fd  mov     rcx, r10
0x180001600  mov     [rbp+80h+var_F8], r8d
0x180001604  mov     r8, rbx
0x180001607  mov     [rsp+180h+var_158], rax
0x18000160c  mov     [rsp+180h+var_160], 12h
0x180001614  mov     [rbp+80h+var_F4], edi
0x180001617  mov     [rsp+180h+var_108], 4
0x180001620  mov     [rsp+180h+var_118], 8
0x180001629  mov     [rsp+180h+var_128], 8
0x180001632  call    _tlgWriteTransfer_EventWriteTransfer
0x180001637  mov     rcx, [rbp+80h+var_30]
0x18000163b  xor     rcx, rsp; StackCookie
0x18000163e  call    __security_check_cookie
0x180001643  add     rsp, 160h
0x18000164a  pop     r14
0x18000164c  pop     rdi
0x18000164d  pop     rsi
0x18000164e  pop     rbx
0x18000164f  pop     rbp
0x180001650  retn
```
