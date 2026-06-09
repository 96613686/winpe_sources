# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x18000137c`
- end: `0x18000166b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `751`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005c3c`

## callees

- `0x18000137c`
- `0x1800016fc`
- `0x180001cb0`

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
        int **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        int **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        int **a19,
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
  int *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  int *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  int *v45; // rcx
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
  int *v67; // [rsp+B0h] [rbp-50h]
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
  int *v80; // [rsp+100h] [rbp+0h]
  int v81; // [rsp+108h] [rbp+8h]
  int v82; // [rsp+10Ch] [rbp+Ch]
  __int64 v83; // [rsp+110h] [rbp+10h]
  __int64 v84; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  int *v88; // [rsp+130h] [rbp+30h]
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
    v26 = &byte_18000DE48;
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
    v30 = &dword_18000DE4C;
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
    v33 = &byte_18000DE48;
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
    v36 = &dword_18000DE4C;
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
    v39 = &byte_18000DE48;
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
    v42 = &byte_18000DE48;
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
    v45 = &dword_18000DE4C;
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
    v47 = &byte_18000DE48;
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
    v50 = &byte_18000DE48;
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
0x18000137c  mov     [rsp-8+arg_10], rbx
0x180001381  push    rbp
0x180001382  push    rdi
0x180001383  push    r14
0x180001385  lea     rbp, [rsp-80h]
0x18000138a  sub     rsp, 180h
0x180001391  mov     rax, cs:__security_cookie
0x180001398  xor     rax, rsp
0x18000139b  mov     [rbp+90h+var_20], rax
0x18000139f  mov     rax, [rbp+90h+arg_A8]
0x1800013a6  lea     rdi, byte_18000DE48
0x1800013ad  mov     r11, rdx
0x1800013b0  mov     r10, rcx
0x1800013b3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800013b7  xor     ebx, ebx
0x1800013b9  mov     r8d, 1
0x1800013bf  mov     rcx, [rax]
0x1800013c2  test    rcx, rcx
0x1800013c5  jz      short loc_1800013D6
0x1800013c7  mov     rax, rdx
0x1800013ca  inc     rax
0x1800013cd  cmp     [rcx+rax], bl
0x1800013d0  jnz     short loc_1800013CA
0x1800013d2  inc     eax
0x1800013d4  jmp     short loc_1800013DC
0x1800013d6  mov     rcx, rdi
0x1800013d9  mov     eax, r8d
0x1800013dc  mov     [rbp+90h+var_28], eax
0x1800013df  mov     r9d, 2
0x1800013e5  mov     rax, [rbp+90h+arg_A0]
0x1800013ec  mov     [rbp+90h+var_40], rax
0x1800013f0  mov     rax, [rbp+90h+arg_98]
0x1800013f7  mov     [rbp+90h+var_50], rax
0x1800013fb  mov     rax, [rbp+90h+arg_90]
0x180001402  mov     [rbp+90h+var_30], rcx
0x180001406  mov     [rbp+90h+var_24], ebx
0x180001409  mov     [rbp+90h+var_38], 4
0x180001411  mov     rcx, [rax]
0x180001414  mov     [rbp+90h+var_48], 4
0x18000141c  test    rcx, rcx
0x18000141f  jz      short loc_180001436
0x180001421  mov     rax, rdx
0x180001424  inc     rax
0x180001427  cmp     [rcx+rax*2], bx
0x18000142b  jnz     short loc_180001424
0x18000142d  lea     eax, ds:2[rax*2]
0x180001434  jmp     short loc_180001440
0x180001436  lea     rcx, dword_18000DE4C
0x18000143d  mov     eax, r9d
0x180001440  mov     [rbp+90h+var_58], eax
0x180001443  mov     rax, [rbp+90h+arg_88]
0x18000144a  mov     [rbp+90h+var_60], rcx
0x18000144e  mov     [rbp+90h+var_54], ebx
0x180001451  mov     rcx, [rax]
0x180001454  test    rcx, rcx
0x180001457  jz      short loc_180001468
0x180001459  mov     rax, rdx
0x18000145c  inc     rax
0x18000145f  cmp     [rcx+rax], bl
0x180001462  jnz     short loc_18000145C
0x180001464  inc     eax
0x180001466  jmp     short loc_18000146E
0x180001468  mov     rcx, rdi
0x18000146b  mov     eax, r8d
0x18000146e  mov     [rbp+90h+var_68], eax
0x180001471  mov     rax, [rbp+90h+arg_80]
0x180001478  mov     [rbp+90h+var_80], rax
0x18000147c  mov     rax, [rbp+90h+arg_78]
0x180001483  mov     [rbp+90h+var_70], rcx
0x180001487  mov     [rbp+90h+var_64], ebx
0x18000148a  mov     [rbp+90h+var_78], 4
0x180001492  mov     rcx, [rax]
0x180001495  test    rcx, rcx
0x180001498  jz      short loc_1800014AF
0x18000149a  mov     rax, rdx
0x18000149d  inc     rax
0x1800014a0  cmp     [rcx+rax*2], bx
0x1800014a4  jnz     short loc_18000149D
0x1800014a6  lea     eax, ds:2[rax*2]
0x1800014ad  jmp     short loc_1800014B9
0x1800014af  lea     rcx, dword_18000DE4C
0x1800014b6  mov     eax, r9d
0x1800014b9  mov     [rbp+90h+var_88], eax
0x1800014bc  mov     rax, [rbp+90h+arg_70]
0x1800014c3  mov     [rbp+90h+var_90], rcx
0x1800014c7  mov     [rbp+90h+var_84], ebx
0x1800014ca  mov     rcx, [rax]
0x1800014cd  test    rcx, rcx
0x1800014d0  jz      short loc_1800014E1
0x1800014d2  mov     rax, rdx
0x1800014d5  inc     rax
0x1800014d8  cmp     [rcx+rax], bl
0x1800014db  jnz     short loc_1800014D5
0x1800014dd  inc     eax
0x1800014df  jmp     short loc_1800014E7
0x1800014e1  mov     rcx, rdi
0x1800014e4  mov     eax, r8d
0x1800014e7  mov     [rbp+90h+var_98], eax
0x1800014ea  mov     rax, [rbp+90h+arg_68]
0x1800014f1  mov     [rbp+90h+var_B0], rax
0x1800014f5  mov     rax, [rbp+90h+arg_60]
0x1800014fc  mov     [rbp+90h+var_A0], rcx
0x180001500  mov     [rbp+90h+var_94], ebx
0x180001503  mov     [rbp+90h+var_A8], 4
0x18000150b  mov     rcx, [rax]
0x18000150e  test    rcx, rcx
0x180001511  jz      short loc_180001522
0x180001513  mov     rax, rdx
0x180001516  inc     rax
0x180001519  cmp     [rcx+rax], bl
0x18000151c  jnz     short loc_180001516
0x18000151e  inc     eax
0x180001520  jmp     short loc_180001528
0x180001522  mov     rcx, rdi
0x180001525  mov     eax, r8d
0x180001528  mov     [rbp+90h+var_B8], eax
0x18000152b  mov     rax, [rbp+90h+arg_58]
0x180001532  mov     [rbp+90h+var_D0], rax
0x180001536  mov     rax, [rbp+90h+arg_50]
0x18000153d  mov     [rbp+90h+var_C0], rcx
0x180001541  mov     [rbp+90h+var_B4], ebx
0x180001544  mov     [rbp+90h+var_C8], 4
0x18000154c  mov     rcx, [rax]
0x18000154f  test    rcx, rcx
0x180001552  jz      short loc_18000156A
0x180001554  mov     rax, rdx
0x180001557  inc     rax
0x18000155a  cmp     [rcx+rax*2], bx
0x18000155e  jnz     short loc_180001557
0x180001560  lea     r9d, ds:2[rax*2]
0x180001568  jmp     short loc_180001571
0x18000156a  lea     rcx, dword_18000DE4C
0x180001571  mov     rax, [rbp+90h+arg_48]
0x180001578  mov     [rbp+90h+var_F0], rax
0x18000157c  mov     rax, [rbp+90h+arg_40]
0x180001583  mov     [rbp+90h+var_E0], rcx
0x180001587  mov     [rbp+90h+var_D8], r9d
0x18000158b  mov     [rbp+90h+var_D4], ebx
0x18000158e  mov     rcx, [rax]
0x180001591  mov     [rbp+90h+var_E8], 4
0x180001599  test    rcx, rcx
0x18000159c  jz      short loc_1800015AD
0x18000159e  mov     rax, rdx
0x1800015a1  inc     rax
0x1800015a4  cmp     [rcx+rax], bl
0x1800015a7  jnz     short loc_1800015A1
0x1800015a9  inc     eax
0x1800015ab  jmp     short loc_1800015B3
0x1800015ad  mov     rcx, rdi
0x1800015b0  mov     eax, r8d
0x1800015b3  mov     [rbp+90h+var_F8], eax
0x1800015b6  mov     rax, [rbp+90h+arg_38]
0x1800015bd  mov     [rbp+90h+var_110], rax
0x1800015c1  mov     rax, [rbp+90h+arg_30]
0x1800015c8  mov     [rbp+90h+var_100], rcx
0x1800015cc  mov     [rbp+90h+var_F4], ebx
0x1800015cf  mov     [rbp+90h+var_108], 4
0x1800015d7  mov     rcx, [rax]
0x1800015da  test    rcx, rcx
0x1800015dd  jz      short loc_1800015ED
0x1800015df  inc     rdx
0x1800015e2  cmp     [rcx+rdx], bl
0x1800015e5  jnz     short loc_1800015DF
0x1800015e7  lea     r8d, [rdx+1]
0x1800015eb  jmp     short loc_1800015F0
0x1800015ed  mov     rcx, rdi
0x1800015f0  mov     rax, [rbp+90h+arg_28]
0x1800015f7  xor     r9d, r9d
0x1800015fa  mov     [rsp+190h+var_130], rax
0x1800015ff  mov     rdx, r11
0x180001602  mov     rax, [rbp+90h+arg_20]
0x180001609  mov     [rsp+190h+var_140], rax
0x18000160e  lea     rax, [rsp+190h+var_160]
0x180001613  mov     [rsp+190h+var_120], rcx
0x180001618  mov     rcx, r10
0x18000161b  mov     [rsp+190h+var_118], r8d
0x180001620  xor     r8d, r8d
0x180001623  mov     [rsp+190h+var_168], rax
0x180001628  mov     [rsp+190h+var_170], 14h
0x180001630  mov     [rsp+190h+var_114], ebx
0x180001634  mov     [rsp+190h+var_128], 4
0x18000163d  mov     [rsp+190h+var_138], 8
0x180001646  call    _tlgWriteTransfer_EventWriteTransfer
0x18000164b  mov     rcx, [rbp+90h+var_20]
0x18000164f  xor     rcx, rsp; StackCookie
0x180001652  call    __security_check_cookie
0x180001657  mov     rbx, [rsp+190h+arg_10]
0x18000165f  add     rsp, 180h
0x180001666  pop     r14
0x180001668  pop     rdi
0x180001669  pop     rbp
0x18000166a  retn
```
