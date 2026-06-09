# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1800013d8`
- end: `0x1800016c7`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `751`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800089b0`

## callees

- `0x1800013d8`
- `0x180001858`
- `0x180001ed0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
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
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+30h] [rbp-D0h] BYREF
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
    v26 = &word_180012E8A;
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
    v30 = &dword_180012E8C;
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
    v33 = &word_180012E8A;
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
    v36 = &dword_180012E8C;
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
    v39 = &word_180012E8A;
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
    v42 = &word_180012E8A;
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
    v45 = &dword_180012E8C;
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
    v47 = &word_180012E8A;
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
    v50 = &word_180012E8A;
  }
  v55 = a6;
  v53 = a5;
  v57 = v50;
  v58 = v25;
  v59 = 0;
  v56 = 4;
  v54 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0x14u, &v52);
}

```

## disassembly

```asm
0x1800013d8  mov     [rsp-8+arg_10], rbx
0x1800013dd  push    rbp
0x1800013de  push    rdi
0x1800013df  push    r14
0x1800013e1  lea     rbp, [rsp-80h]
0x1800013e6  sub     rsp, 180h
0x1800013ed  mov     rax, cs:__security_cookie
0x1800013f4  xor     rax, rsp
0x1800013f7  mov     [rbp+90h+var_20], rax
0x1800013fb  mov     rax, [rbp+90h+arg_A8]
0x180001402  lea     rdi, word_180012E8A
0x180001409  mov     r11, rdx
0x18000140c  mov     r10, rcx
0x18000140f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001413  xor     ebx, ebx
0x180001415  mov     r8d, 1
0x18000141b  mov     rcx, [rax]
0x18000141e  test    rcx, rcx
0x180001421  jz      short loc_180001432
0x180001423  mov     rax, rdx
0x180001426  inc     rax
0x180001429  cmp     [rcx+rax], bl
0x18000142c  jnz     short loc_180001426
0x18000142e  inc     eax
0x180001430  jmp     short loc_180001438
0x180001432  mov     rcx, rdi
0x180001435  mov     eax, r8d
0x180001438  mov     [rbp+90h+var_28], eax
0x18000143b  mov     r9d, 2
0x180001441  mov     rax, [rbp+90h+arg_A0]
0x180001448  mov     [rbp+90h+var_40], rax
0x18000144c  mov     rax, [rbp+90h+arg_98]
0x180001453  mov     [rbp+90h+var_50], rax
0x180001457  mov     rax, [rbp+90h+arg_90]
0x18000145e  mov     [rbp+90h+var_30], rcx
0x180001462  mov     [rbp+90h+var_24], ebx
0x180001465  mov     [rbp+90h+var_38], 4
0x18000146d  mov     rcx, [rax]
0x180001470  mov     [rbp+90h+var_48], 4
0x180001478  test    rcx, rcx
0x18000147b  jz      short loc_180001492
0x18000147d  mov     rax, rdx
0x180001480  inc     rax
0x180001483  cmp     [rcx+rax*2], bx
0x180001487  jnz     short loc_180001480
0x180001489  lea     eax, ds:2[rax*2]
0x180001490  jmp     short loc_18000149C
0x180001492  lea     rcx, dword_180012E8C
0x180001499  mov     eax, r9d
0x18000149c  mov     [rbp+90h+var_58], eax
0x18000149f  mov     rax, [rbp+90h+arg_88]
0x1800014a6  mov     [rbp+90h+var_60], rcx
0x1800014aa  mov     [rbp+90h+var_54], ebx
0x1800014ad  mov     rcx, [rax]
0x1800014b0  test    rcx, rcx
0x1800014b3  jz      short loc_1800014C4
0x1800014b5  mov     rax, rdx
0x1800014b8  inc     rax
0x1800014bb  cmp     [rcx+rax], bl
0x1800014be  jnz     short loc_1800014B8
0x1800014c0  inc     eax
0x1800014c2  jmp     short loc_1800014CA
0x1800014c4  mov     rcx, rdi
0x1800014c7  mov     eax, r8d
0x1800014ca  mov     [rbp+90h+var_68], eax
0x1800014cd  mov     rax, [rbp+90h+arg_80]
0x1800014d4  mov     [rbp+90h+var_80], rax
0x1800014d8  mov     rax, [rbp+90h+arg_78]
0x1800014df  mov     [rbp+90h+var_70], rcx
0x1800014e3  mov     [rbp+90h+var_64], ebx
0x1800014e6  mov     [rbp+90h+var_78], 4
0x1800014ee  mov     rcx, [rax]
0x1800014f1  test    rcx, rcx
0x1800014f4  jz      short loc_18000150B
0x1800014f6  mov     rax, rdx
0x1800014f9  inc     rax
0x1800014fc  cmp     [rcx+rax*2], bx
0x180001500  jnz     short loc_1800014F9
0x180001502  lea     eax, ds:2[rax*2]
0x180001509  jmp     short loc_180001515
0x18000150b  lea     rcx, dword_180012E8C
0x180001512  mov     eax, r9d
0x180001515  mov     [rbp+90h+var_88], eax
0x180001518  mov     rax, [rbp+90h+arg_70]
0x18000151f  mov     [rbp+90h+var_90], rcx
0x180001523  mov     [rbp+90h+var_84], ebx
0x180001526  mov     rcx, [rax]
0x180001529  test    rcx, rcx
0x18000152c  jz      short loc_18000153D
0x18000152e  mov     rax, rdx
0x180001531  inc     rax
0x180001534  cmp     [rcx+rax], bl
0x180001537  jnz     short loc_180001531
0x180001539  inc     eax
0x18000153b  jmp     short loc_180001543
0x18000153d  mov     rcx, rdi
0x180001540  mov     eax, r8d
0x180001543  mov     [rbp+90h+var_98], eax
0x180001546  mov     rax, [rbp+90h+arg_68]
0x18000154d  mov     [rbp+90h+var_B0], rax
0x180001551  mov     rax, [rbp+90h+arg_60]
0x180001558  mov     [rbp+90h+var_A0], rcx
0x18000155c  mov     [rbp+90h+var_94], ebx
0x18000155f  mov     [rbp+90h+var_A8], 4
0x180001567  mov     rcx, [rax]
0x18000156a  test    rcx, rcx
0x18000156d  jz      short loc_18000157E
0x18000156f  mov     rax, rdx
0x180001572  inc     rax
0x180001575  cmp     [rcx+rax], bl
0x180001578  jnz     short loc_180001572
0x18000157a  inc     eax
0x18000157c  jmp     short loc_180001584
0x18000157e  mov     rcx, rdi
0x180001581  mov     eax, r8d
0x180001584  mov     [rbp+90h+var_B8], eax
0x180001587  mov     rax, [rbp+90h+arg_58]
0x18000158e  mov     [rbp+90h+var_D0], rax
0x180001592  mov     rax, [rbp+90h+arg_50]
0x180001599  mov     [rbp+90h+var_C0], rcx
0x18000159d  mov     [rbp+90h+var_B4], ebx
0x1800015a0  mov     [rbp+90h+var_C8], 4
0x1800015a8  mov     rcx, [rax]
0x1800015ab  test    rcx, rcx
0x1800015ae  jz      short loc_1800015C6
0x1800015b0  mov     rax, rdx
0x1800015b3  inc     rax
0x1800015b6  cmp     [rcx+rax*2], bx
0x1800015ba  jnz     short loc_1800015B3
0x1800015bc  lea     r9d, ds:2[rax*2]
0x1800015c4  jmp     short loc_1800015CD
0x1800015c6  lea     rcx, dword_180012E8C
0x1800015cd  mov     rax, [rbp+90h+arg_48]
0x1800015d4  mov     [rbp+90h+var_F0], rax
0x1800015d8  mov     rax, [rbp+90h+arg_40]
0x1800015df  mov     [rbp+90h+var_E0], rcx
0x1800015e3  mov     [rbp+90h+var_D8], r9d
0x1800015e7  mov     [rbp+90h+var_D4], ebx
0x1800015ea  mov     rcx, [rax]
0x1800015ed  mov     [rbp+90h+var_E8], 4
0x1800015f5  test    rcx, rcx
0x1800015f8  jz      short loc_180001609
0x1800015fa  mov     rax, rdx
0x1800015fd  inc     rax
0x180001600  cmp     [rcx+rax], bl
0x180001603  jnz     short loc_1800015FD
0x180001605  inc     eax
0x180001607  jmp     short loc_18000160F
0x180001609  mov     rcx, rdi
0x18000160c  mov     eax, r8d
0x18000160f  mov     [rbp+90h+var_F8], eax
0x180001612  mov     rax, [rbp+90h+arg_38]
0x180001619  mov     [rbp+90h+var_110], rax
0x18000161d  mov     rax, [rbp+90h+arg_30]
0x180001624  mov     [rbp+90h+var_100], rcx
0x180001628  mov     [rbp+90h+var_F4], ebx
0x18000162b  mov     [rbp+90h+var_108], 4
0x180001633  mov     rcx, [rax]
0x180001636  test    rcx, rcx
0x180001639  jz      short loc_180001649
0x18000163b  inc     rdx
0x18000163e  cmp     [rcx+rdx], bl
0x180001641  jnz     short loc_18000163B
0x180001643  lea     r8d, [rdx+1]
0x180001647  jmp     short loc_18000164C
0x180001649  mov     rcx, rdi
0x18000164c  mov     rax, [rbp+90h+arg_28]
0x180001653  xor     r9d, r9d
0x180001656  mov     [rsp+190h+var_130], rax
0x18000165b  mov     rdx, r11
0x18000165e  mov     rax, [rbp+90h+arg_20]
0x180001665  mov     [rsp+190h+var_140], rax
0x18000166a  lea     rax, [rsp+190h+var_160]
0x18000166f  mov     [rsp+190h+var_120], rcx
0x180001674  mov     rcx, r10
0x180001677  mov     [rsp+190h+var_118], r8d
0x18000167c  xor     r8d, r8d
0x18000167f  mov     [rsp+190h+var_168], rax
0x180001684  mov     [rsp+190h+var_170], 14h
0x18000168c  mov     [rsp+190h+var_114], ebx
0x180001690  mov     [rsp+190h+var_128], 4
0x180001699  mov     [rsp+190h+var_138], 8
0x1800016a2  call    _tlgWriteTransfer_EventWriteTransfer
0x1800016a7  mov     rcx, [rbp+90h+var_20]
0x1800016ab  xor     rcx, rsp; StackCookie
0x1800016ae  call    __security_check_cookie
0x1800016b3  mov     rbx, [rsp+190h+arg_10]
0x1800016bb  add     rsp, 180h
0x1800016c2  pop     r14
0x1800016c4  pop     rdi
0x1800016c5  pop     rbp
0x1800016c6  retn
```
