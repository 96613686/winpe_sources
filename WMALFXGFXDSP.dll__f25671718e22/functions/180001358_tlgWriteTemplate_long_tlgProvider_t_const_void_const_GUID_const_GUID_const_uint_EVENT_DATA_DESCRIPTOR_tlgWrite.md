# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001358`
- end: `0x180001647`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `751`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180078d80`

## callees

- `0x180001358`
- `0x1800017d8`
- `0x180015190`

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
        char **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        char **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        char **a19,
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
  char *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  char *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  char *v45; // rcx
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
  char *v67; // [rsp+B0h] [rbp-50h]
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
  char *v80; // [rsp+100h] [rbp+0h]
  int v81; // [rsp+108h] [rbp+8h]
  int v82; // [rsp+10Ch] [rbp+Ch]
  __int64 v83; // [rsp+110h] [rbp+10h]
  __int64 v84; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  char *v88; // [rsp+130h] [rbp+30h]
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
    v26 = &qword_1801AFCA0;
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
    while ( *(_WORD *)&v30[2 * v31] );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = byte_1801AFC98;
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
    v33 = &qword_1801AFCA0;
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
    while ( *(_WORD *)&v36[2 * v37] );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v36 = byte_1801AFC98;
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
    v39 = &qword_1801AFCA0;
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
    v42 = &qword_1801AFCA0;
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
    while ( *(_WORD *)&v45[2 * v46] );
    v29 = 2 * v46 + 2;
  }
  else
  {
    v45 = byte_1801AFC98;
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
    v47 = &qword_1801AFCA0;
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
    v50 = &qword_1801AFCA0;
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
0x180001358  mov     [rsp-8+arg_10], rbx
0x18000135d  push    rbp
0x18000135e  push    rdi
0x18000135f  push    r14
0x180001361  lea     rbp, [rsp-80h]
0x180001366  sub     rsp, 180h
0x18000136d  mov     rax, cs:__security_cookie
0x180001374  xor     rax, rsp
0x180001377  mov     [rbp+90h+var_20], rax
0x18000137b  mov     rax, [rbp+90h+arg_A8]
0x180001382  lea     rdi, qword_1801AFCA0
0x180001389  mov     r11, rdx
0x18000138c  mov     r10, rcx
0x18000138f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001393  xor     ebx, ebx
0x180001395  mov     r8d, 1
0x18000139b  mov     rcx, [rax]
0x18000139e  test    rcx, rcx
0x1800013a1  jz      short loc_1800013B2
0x1800013a3  mov     rax, rdx
0x1800013a6  inc     rax
0x1800013a9  cmp     [rcx+rax], bl
0x1800013ac  jnz     short loc_1800013A6
0x1800013ae  inc     eax
0x1800013b0  jmp     short loc_1800013B8
0x1800013b2  mov     rcx, rdi
0x1800013b5  mov     eax, r8d
0x1800013b8  mov     [rbp+90h+var_28], eax
0x1800013bb  mov     r9d, 2
0x1800013c1  mov     rax, [rbp+90h+arg_A0]
0x1800013c8  mov     [rbp+90h+var_40], rax
0x1800013cc  mov     rax, [rbp+90h+arg_98]
0x1800013d3  mov     [rbp+90h+var_50], rax
0x1800013d7  mov     rax, [rbp+90h+arg_90]
0x1800013de  mov     [rbp+90h+var_30], rcx
0x1800013e2  mov     [rbp+90h+var_24], ebx
0x1800013e5  mov     [rbp+90h+var_38], 4
0x1800013ed  mov     rcx, [rax]
0x1800013f0  mov     [rbp+90h+var_48], 4
0x1800013f8  test    rcx, rcx
0x1800013fb  jz      short loc_180001412
0x1800013fd  mov     rax, rdx
0x180001400  inc     rax
0x180001403  cmp     [rcx+rax*2], bx
0x180001407  jnz     short loc_180001400
0x180001409  lea     eax, ds:2[rax*2]
0x180001410  jmp     short loc_18000141C
0x180001412  lea     rcx, byte_1801AFC98
0x180001419  mov     eax, r9d
0x18000141c  mov     [rbp+90h+var_58], eax
0x18000141f  mov     rax, [rbp+90h+arg_88]
0x180001426  mov     [rbp+90h+var_60], rcx
0x18000142a  mov     [rbp+90h+var_54], ebx
0x18000142d  mov     rcx, [rax]
0x180001430  test    rcx, rcx
0x180001433  jz      short loc_180001444
0x180001435  mov     rax, rdx
0x180001438  inc     rax
0x18000143b  cmp     [rcx+rax], bl
0x18000143e  jnz     short loc_180001438
0x180001440  inc     eax
0x180001442  jmp     short loc_18000144A
0x180001444  mov     rcx, rdi
0x180001447  mov     eax, r8d
0x18000144a  mov     [rbp+90h+var_68], eax
0x18000144d  mov     rax, [rbp+90h+arg_80]
0x180001454  mov     [rbp+90h+var_80], rax
0x180001458  mov     rax, [rbp+90h+arg_78]
0x18000145f  mov     [rbp+90h+var_70], rcx
0x180001463  mov     [rbp+90h+var_64], ebx
0x180001466  mov     [rbp+90h+var_78], 4
0x18000146e  mov     rcx, [rax]
0x180001471  test    rcx, rcx
0x180001474  jz      short loc_18000148B
0x180001476  mov     rax, rdx
0x180001479  inc     rax
0x18000147c  cmp     [rcx+rax*2], bx
0x180001480  jnz     short loc_180001479
0x180001482  lea     eax, ds:2[rax*2]
0x180001489  jmp     short loc_180001495
0x18000148b  lea     rcx, byte_1801AFC98
0x180001492  mov     eax, r9d
0x180001495  mov     [rbp+90h+var_88], eax
0x180001498  mov     rax, [rbp+90h+arg_70]
0x18000149f  mov     [rbp+90h+var_90], rcx
0x1800014a3  mov     [rbp+90h+var_84], ebx
0x1800014a6  mov     rcx, [rax]
0x1800014a9  test    rcx, rcx
0x1800014ac  jz      short loc_1800014BD
0x1800014ae  mov     rax, rdx
0x1800014b1  inc     rax
0x1800014b4  cmp     [rcx+rax], bl
0x1800014b7  jnz     short loc_1800014B1
0x1800014b9  inc     eax
0x1800014bb  jmp     short loc_1800014C3
0x1800014bd  mov     rcx, rdi
0x1800014c0  mov     eax, r8d
0x1800014c3  mov     [rbp+90h+var_98], eax
0x1800014c6  mov     rax, [rbp+90h+arg_68]
0x1800014cd  mov     [rbp+90h+var_B0], rax
0x1800014d1  mov     rax, [rbp+90h+arg_60]
0x1800014d8  mov     [rbp+90h+var_A0], rcx
0x1800014dc  mov     [rbp+90h+var_94], ebx
0x1800014df  mov     [rbp+90h+var_A8], 4
0x1800014e7  mov     rcx, [rax]
0x1800014ea  test    rcx, rcx
0x1800014ed  jz      short loc_1800014FE
0x1800014ef  mov     rax, rdx
0x1800014f2  inc     rax
0x1800014f5  cmp     [rcx+rax], bl
0x1800014f8  jnz     short loc_1800014F2
0x1800014fa  inc     eax
0x1800014fc  jmp     short loc_180001504
0x1800014fe  mov     rcx, rdi
0x180001501  mov     eax, r8d
0x180001504  mov     [rbp+90h+var_B8], eax
0x180001507  mov     rax, [rbp+90h+arg_58]
0x18000150e  mov     [rbp+90h+var_D0], rax
0x180001512  mov     rax, [rbp+90h+arg_50]
0x180001519  mov     [rbp+90h+var_C0], rcx
0x18000151d  mov     [rbp+90h+var_B4], ebx
0x180001520  mov     [rbp+90h+var_C8], 4
0x180001528  mov     rcx, [rax]
0x18000152b  test    rcx, rcx
0x18000152e  jz      short loc_180001546
0x180001530  mov     rax, rdx
0x180001533  inc     rax
0x180001536  cmp     [rcx+rax*2], bx
0x18000153a  jnz     short loc_180001533
0x18000153c  lea     r9d, ds:2[rax*2]
0x180001544  jmp     short loc_18000154D
0x180001546  lea     rcx, byte_1801AFC98
0x18000154d  mov     rax, [rbp+90h+arg_48]
0x180001554  mov     [rbp+90h+var_F0], rax
0x180001558  mov     rax, [rbp+90h+arg_40]
0x18000155f  mov     [rbp+90h+var_E0], rcx
0x180001563  mov     [rbp+90h+var_D8], r9d
0x180001567  mov     [rbp+90h+var_D4], ebx
0x18000156a  mov     rcx, [rax]
0x18000156d  mov     [rbp+90h+var_E8], 4
0x180001575  test    rcx, rcx
0x180001578  jz      short loc_180001589
0x18000157a  mov     rax, rdx
0x18000157d  inc     rax
0x180001580  cmp     [rcx+rax], bl
0x180001583  jnz     short loc_18000157D
0x180001585  inc     eax
0x180001587  jmp     short loc_18000158F
0x180001589  mov     rcx, rdi
0x18000158c  mov     eax, r8d
0x18000158f  mov     [rbp+90h+var_F8], eax
0x180001592  mov     rax, [rbp+90h+arg_38]
0x180001599  mov     [rbp+90h+var_110], rax
0x18000159d  mov     rax, [rbp+90h+arg_30]
0x1800015a4  mov     [rbp+90h+var_100], rcx
0x1800015a8  mov     [rbp+90h+var_F4], ebx
0x1800015ab  mov     [rbp+90h+var_108], 4
0x1800015b3  mov     rcx, [rax]
0x1800015b6  test    rcx, rcx
0x1800015b9  jz      short loc_1800015C9
0x1800015bb  inc     rdx
0x1800015be  cmp     [rcx+rdx], bl
0x1800015c1  jnz     short loc_1800015BB
0x1800015c3  lea     r8d, [rdx+1]
0x1800015c7  jmp     short loc_1800015CC
0x1800015c9  mov     rcx, rdi
0x1800015cc  mov     rax, [rbp+90h+arg_28]
0x1800015d3  xor     r9d, r9d
0x1800015d6  mov     [rsp+190h+var_130], rax
0x1800015db  mov     rdx, r11
0x1800015de  mov     rax, [rbp+90h+arg_20]
0x1800015e5  mov     [rsp+190h+var_140], rax
0x1800015ea  lea     rax, [rsp+190h+var_160]
0x1800015ef  mov     [rsp+190h+var_120], rcx
0x1800015f4  mov     rcx, r10
0x1800015f7  mov     [rsp+190h+var_118], r8d
0x1800015fc  xor     r8d, r8d
0x1800015ff  mov     [rsp+190h+var_168], rax
0x180001604  mov     [rsp+190h+var_170], 14h
0x18000160c  mov     [rsp+190h+var_114], ebx
0x180001610  mov     [rsp+190h+var_128], 4
0x180001619  mov     [rsp+190h+var_138], 8
0x180001622  call    _tlgWriteTransfer_EventWriteTransfer
0x180001627  mov     rcx, [rbp+90h+var_20]
0x18000162b  xor     rcx, rsp; StackCookie
0x18000162e  call    __security_check_cookie
0x180001633  mov     rbx, [rsp+190h+arg_10]
0x18000163b  add     rsp, 180h
0x180001642  pop     r14
0x180001644  pop     rdi
0x180001645  pop     rbp
0x180001646  retn
```
