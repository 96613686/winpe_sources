# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1400012dc`
- end: `0x1400015cb`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `751`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, __int64 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64 **, __int64, const unsigned __int16 **, __int64 **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400087bc`

## callees

- `0x1400012dc`
- `0x14000172c`
- `0x1400094d0`

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
  int v25; // r8d
  const unsigned __int16 *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int v29; // r9d
  __int64 *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  __int64 *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  __int64 *v45; // rcx
  __int64 v46; // rax
  const unsigned __int16 *v47; // rcx
  __int64 v48; // rax
  int v49; // eax
  const unsigned __int16 *v50; // rcx
  _BYTE v52[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B0h]
  __int64 v54; // [rsp+58h] [rbp-A8h]
  __int64 v55; // [rsp+60h] [rbp-A0h]
  __int64 v56; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v57; // [rsp+70h] [rbp-90h]
  int v58; // [rsp+78h] [rbp-88h]
  int v59; // [rsp+7Ch] [rbp-84h]
  __int64 v60; // [rsp+80h] [rbp-80h]
  __int64 v61; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v62; // [rsp+90h] [rbp-70h]
  int v63; // [rsp+98h] [rbp-68h]
  int v64; // [rsp+9Ch] [rbp-64h]
  __int64 v65; // [rsp+A0h] [rbp-60h]
  __int64 v66; // [rsp+A8h] [rbp-58h]
  __int64 *v67; // [rsp+B0h] [rbp-50h]
  int v68; // [rsp+B8h] [rbp-48h]
  int v69; // [rsp+BCh] [rbp-44h]
  __int64 v70; // [rsp+C0h] [rbp-40h]
  __int64 v71; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v72; // [rsp+D0h] [rbp-30h]
  int v73; // [rsp+D8h] [rbp-28h]
  int v74; // [rsp+DCh] [rbp-24h]
  __int64 v75; // [rsp+E0h] [rbp-20h]
  __int64 v76; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v77; // [rsp+F0h] [rbp-10h]
  int v78; // [rsp+F8h] [rbp-8h]
  int v79; // [rsp+FCh] [rbp-4h]
  __int64 *v80; // [rsp+100h] [rbp+0h]
  int v81; // [rsp+108h] [rbp+8h]
  int v82; // [rsp+10Ch] [rbp+Ch]
  __int64 v83; // [rsp+110h] [rbp+10h]
  __int64 v84; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  __int64 *v88; // [rsp+130h] [rbp+30h]
  int v89; // [rsp+138h] [rbp+38h]
  int v90; // [rsp+13Ch] [rbp+3Ch]
  __int64 v91; // [rsp+140h] [rbp+40h]
  __int64 v92; // [rsp+148h] [rbp+48h]
  __int64 v93; // [rsp+150h] [rbp+50h]
  __int64 v94; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v95; // [rsp+160h] [rbp+60h]
  int v96; // [rsp+168h] [rbp+68h]
  int v97; // [rsp+16Ch] [rbp+6Ch]

  v24 = -1;
  v25 = 1;
  v26 = *a22;
  if ( *a22 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *((_BYTE *)v26 + v27) );
    v28 = v27 + 1;
  }
  else
  {
    v26 = &qword_14000D150;
    v28 = 1;
  }
  v96 = v28;
  v29 = 2;
  v93 = a21;
  v91 = a20;
  v95 = v26;
  v97 = 0;
  v94 = 4;
  v30 = *a19;
  v92 = 4;
  if ( v30 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *((_WORD *)v30 + v31) );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &qword_14000D868;
    v32 = 2;
  }
  v89 = v32;
  v88 = v30;
  v90 = 0;
  v33 = *a18;
  if ( *a18 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_BYTE *)v33 + v34) );
    v35 = v34 + 1;
  }
  else
  {
    v33 = &qword_14000D150;
    v35 = 1;
  }
  v86 = v35;
  v83 = a17;
  v85 = v33;
  v87 = 0;
  v84 = 4;
  v36 = *a16;
  if ( *a16 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_WORD *)v36 + v37) );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v36 = &qword_14000D868;
    v38 = 2;
  }
  v81 = v38;
  v80 = v36;
  v82 = 0;
  v39 = *a15;
  if ( *a15 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_BYTE *)v39 + v40) );
    v41 = v40 + 1;
  }
  else
  {
    v39 = &qword_14000D150;
    v41 = 1;
  }
  v78 = v41;
  v75 = a14;
  v77 = v39;
  v79 = 0;
  v76 = 4;
  v42 = *a13;
  if ( *a13 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &qword_14000D150;
    v44 = 1;
  }
  v73 = v44;
  v70 = a12;
  v72 = v42;
  v74 = 0;
  v71 = 4;
  v45 = *a11;
  if ( *a11 )
  {
    v46 = -1;
    do
      ++v46;
    while ( *((_WORD *)v45 + v46) );
    v29 = 2 * v46 + 2;
  }
  else
  {
    v45 = &qword_14000D868;
  }
  v65 = a10;
  v67 = v45;
  v68 = v29;
  v69 = 0;
  v47 = *a9;
  v66 = 4;
  if ( v47 )
  {
    v48 = -1;
    do
      ++v48;
    while ( *((_BYTE *)v47 + v48) );
    v49 = v48 + 1;
  }
  else
  {
    v47 = &qword_14000D150;
    v49 = 1;
  }
  v63 = v49;
  v60 = a8;
  v62 = v47;
  v64 = 0;
  v61 = 4;
  v50 = *a7;
  if ( *a7 )
  {
    do
      ++v24;
    while ( *((_BYTE *)v50 + v24) );
    v25 = v24 + 1;
  }
  else
  {
    v50 = &qword_14000D150;
  }
  v55 = a6;
  v53 = a5;
  v57 = v50;
  v58 = v25;
  v59 = 0;
  v56 = 4;
  v54 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 20, v52);
}

```

## disassembly

```asm
0x1400012dc  mov     [rsp-8+arg_10], rbx
0x1400012e1  push    rbp
0x1400012e2  push    rdi
0x1400012e3  push    r14
0x1400012e5  lea     rbp, [rsp-80h]
0x1400012ea  sub     rsp, 180h
0x1400012f1  mov     rax, cs:__security_cookie
0x1400012f8  xor     rax, rsp
0x1400012fb  mov     [rbp+90h+var_20], rax
0x1400012ff  mov     rax, [rbp+90h+arg_A8]
0x140001306  lea     rdi, qword_14000D150
0x14000130d  mov     r11, rdx
0x140001310  mov     r10, rcx
0x140001313  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140001317  xor     ebx, ebx
0x140001319  mov     r8d, 1
0x14000131f  mov     rcx, [rax]
0x140001322  test    rcx, rcx
0x140001325  jz      short loc_140001336
0x140001327  mov     rax, rdx
0x14000132a  inc     rax
0x14000132d  cmp     [rcx+rax], bl
0x140001330  jnz     short loc_14000132A
0x140001332  inc     eax
0x140001334  jmp     short loc_14000133C
0x140001336  mov     rcx, rdi
0x140001339  mov     eax, r8d
0x14000133c  mov     [rbp+90h+var_28], eax
0x14000133f  mov     r9d, 2
0x140001345  mov     rax, [rbp+90h+arg_A0]
0x14000134c  mov     [rbp+90h+var_40], rax
0x140001350  mov     rax, [rbp+90h+arg_98]
0x140001357  mov     [rbp+90h+var_50], rax
0x14000135b  mov     rax, [rbp+90h+arg_90]
0x140001362  mov     [rbp+90h+var_30], rcx
0x140001366  mov     [rbp+90h+var_24], ebx
0x140001369  mov     [rbp+90h+var_38], 4
0x140001371  mov     rcx, [rax]
0x140001374  mov     [rbp+90h+var_48], 4
0x14000137c  test    rcx, rcx
0x14000137f  jz      short loc_140001396
0x140001381  mov     rax, rdx
0x140001384  inc     rax
0x140001387  cmp     [rcx+rax*2], bx
0x14000138b  jnz     short loc_140001384
0x14000138d  lea     eax, ds:2[rax*2]
0x140001394  jmp     short loc_1400013A0
0x140001396  lea     rcx, qword_14000D868
0x14000139d  mov     eax, r9d
0x1400013a0  mov     [rbp+90h+var_58], eax
0x1400013a3  mov     rax, [rbp+90h+arg_88]
0x1400013aa  mov     [rbp+90h+var_60], rcx
0x1400013ae  mov     [rbp+90h+var_54], ebx
0x1400013b1  mov     rcx, [rax]
0x1400013b4  test    rcx, rcx
0x1400013b7  jz      short loc_1400013C8
0x1400013b9  mov     rax, rdx
0x1400013bc  inc     rax
0x1400013bf  cmp     [rcx+rax], bl
0x1400013c2  jnz     short loc_1400013BC
0x1400013c4  inc     eax
0x1400013c6  jmp     short loc_1400013CE
0x1400013c8  mov     rcx, rdi
0x1400013cb  mov     eax, r8d
0x1400013ce  mov     [rbp+90h+var_68], eax
0x1400013d1  mov     rax, [rbp+90h+arg_80]
0x1400013d8  mov     [rbp+90h+var_80], rax
0x1400013dc  mov     rax, [rbp+90h+arg_78]
0x1400013e3  mov     [rbp+90h+var_70], rcx
0x1400013e7  mov     [rbp+90h+var_64], ebx
0x1400013ea  mov     [rbp+90h+var_78], 4
0x1400013f2  mov     rcx, [rax]
0x1400013f5  test    rcx, rcx
0x1400013f8  jz      short loc_14000140F
0x1400013fa  mov     rax, rdx
0x1400013fd  inc     rax
0x140001400  cmp     [rcx+rax*2], bx
0x140001404  jnz     short loc_1400013FD
0x140001406  lea     eax, ds:2[rax*2]
0x14000140d  jmp     short loc_140001419
0x14000140f  lea     rcx, qword_14000D868
0x140001416  mov     eax, r9d
0x140001419  mov     [rbp+90h+var_88], eax
0x14000141c  mov     rax, [rbp+90h+arg_70]
0x140001423  mov     [rbp+90h+var_90], rcx
0x140001427  mov     [rbp+90h+var_84], ebx
0x14000142a  mov     rcx, [rax]
0x14000142d  test    rcx, rcx
0x140001430  jz      short loc_140001441
0x140001432  mov     rax, rdx
0x140001435  inc     rax
0x140001438  cmp     [rcx+rax], bl
0x14000143b  jnz     short loc_140001435
0x14000143d  inc     eax
0x14000143f  jmp     short loc_140001447
0x140001441  mov     rcx, rdi
0x140001444  mov     eax, r8d
0x140001447  mov     [rbp+90h+var_98], eax
0x14000144a  mov     rax, [rbp+90h+arg_68]
0x140001451  mov     [rbp+90h+var_B0], rax
0x140001455  mov     rax, [rbp+90h+arg_60]
0x14000145c  mov     [rbp+90h+var_A0], rcx
0x140001460  mov     [rbp+90h+var_94], ebx
0x140001463  mov     [rbp+90h+var_A8], 4
0x14000146b  mov     rcx, [rax]
0x14000146e  test    rcx, rcx
0x140001471  jz      short loc_140001482
0x140001473  mov     rax, rdx
0x140001476  inc     rax
0x140001479  cmp     [rcx+rax], bl
0x14000147c  jnz     short loc_140001476
0x14000147e  inc     eax
0x140001480  jmp     short loc_140001488
0x140001482  mov     rcx, rdi
0x140001485  mov     eax, r8d
0x140001488  mov     [rbp+90h+var_B8], eax
0x14000148b  mov     rax, [rbp+90h+arg_58]
0x140001492  mov     [rbp+90h+var_D0], rax
0x140001496  mov     rax, [rbp+90h+arg_50]
0x14000149d  mov     [rbp+90h+var_C0], rcx
0x1400014a1  mov     [rbp+90h+var_B4], ebx
0x1400014a4  mov     [rbp+90h+var_C8], 4
0x1400014ac  mov     rcx, [rax]
0x1400014af  test    rcx, rcx
0x1400014b2  jz      short loc_1400014CA
0x1400014b4  mov     rax, rdx
0x1400014b7  inc     rax
0x1400014ba  cmp     [rcx+rax*2], bx
0x1400014be  jnz     short loc_1400014B7
0x1400014c0  lea     r9d, ds:2[rax*2]
0x1400014c8  jmp     short loc_1400014D1
0x1400014ca  lea     rcx, qword_14000D868
0x1400014d1  mov     rax, [rbp+90h+arg_48]
0x1400014d8  mov     [rbp+90h+var_F0], rax
0x1400014dc  mov     rax, [rbp+90h+arg_40]
0x1400014e3  mov     [rbp+90h+var_E0], rcx
0x1400014e7  mov     [rbp+90h+var_D8], r9d
0x1400014eb  mov     [rbp+90h+var_D4], ebx
0x1400014ee  mov     rcx, [rax]
0x1400014f1  mov     [rbp+90h+var_E8], 4
0x1400014f9  test    rcx, rcx
0x1400014fc  jz      short loc_14000150D
0x1400014fe  mov     rax, rdx
0x140001501  inc     rax
0x140001504  cmp     [rcx+rax], bl
0x140001507  jnz     short loc_140001501
0x140001509  inc     eax
0x14000150b  jmp     short loc_140001513
0x14000150d  mov     rcx, rdi
0x140001510  mov     eax, r8d
0x140001513  mov     [rbp+90h+var_F8], eax
0x140001516  mov     rax, [rbp+90h+arg_38]
0x14000151d  mov     [rbp+90h+var_110], rax
0x140001521  mov     rax, [rbp+90h+arg_30]
0x140001528  mov     [rbp+90h+var_100], rcx
0x14000152c  mov     [rbp+90h+var_F4], ebx
0x14000152f  mov     [rbp+90h+var_108], 4
0x140001537  mov     rcx, [rax]
0x14000153a  test    rcx, rcx
0x14000153d  jz      short loc_14000154D
0x14000153f  inc     rdx
0x140001542  cmp     [rcx+rdx], bl
0x140001545  jnz     short loc_14000153F
0x140001547  lea     r8d, [rdx+1]
0x14000154b  jmp     short loc_140001550
0x14000154d  mov     rcx, rdi
0x140001550  mov     rax, [rbp+90h+arg_28]
0x140001557  xor     r9d, r9d
0x14000155a  mov     [rsp+190h+var_130], rax
0x14000155f  mov     rdx, r11
0x140001562  mov     rax, [rbp+90h+arg_20]
0x140001569  mov     [rsp+190h+var_140], rax
0x14000156e  lea     rax, [rsp+190h+var_160]
0x140001573  mov     [rsp+190h+var_120], rcx
0x140001578  mov     rcx, r10
0x14000157b  mov     [rsp+190h+var_118], r8d
0x140001580  xor     r8d, r8d
0x140001583  mov     [rsp+190h+var_168], rax
0x140001588  mov     [rsp+190h+var_170], 14h
0x140001590  mov     [rsp+190h+var_114], ebx
0x140001594  mov     [rsp+190h+var_128], 4
0x14000159d  mov     [rsp+190h+var_138], 8
0x1400015a6  call    _tlgWriteTransfer_EventWriteTransfer
0x1400015ab  mov     rcx, [rbp+90h+var_20]
0x1400015af  xor     rcx, rsp; StackCookie
0x1400015b2  call    __security_check_cookie
0x1400015b7  mov     rbx, [rsp+190h+arg_10]
0x1400015bf  add     rsp, 180h
0x1400015c6  pop     r14
0x1400015c8  pop     rdi
0x1400015c9  pop     rbp
0x1400015ca  retn
```
