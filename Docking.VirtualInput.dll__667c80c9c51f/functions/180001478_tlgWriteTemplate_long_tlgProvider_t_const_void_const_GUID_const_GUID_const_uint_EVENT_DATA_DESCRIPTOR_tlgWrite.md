# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001478`
- end: `0x18000172c`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `692`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180009e54`
- `0x1800117d0`
- `0x1800179c0`

## callees

- `0x180001478`
- `0x180001c98`
- `0x1800036a0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
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
        __int64 **a20)
{
  __int64 v22; // rdx
  int v25; // r9d
  __int64 *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int v29; // r8d
  const unsigned __int16 *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  __int64 *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  const unsigned __int16 *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  __int64 *v42; // rcx
  __int64 v43; // rax
  const unsigned __int16 *v44; // rcx
  __int64 v45; // rax
  int v46; // eax
  const unsigned __int16 *v47; // rcx
  struct _EVENT_DATA_DESCRIPTOR v49; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v50; // [rsp+50h] [rbp-B0h]
  __int64 v51; // [rsp+58h] [rbp-A8h]
  __int64 v52; // [rsp+60h] [rbp-A0h]
  __int64 v53; // [rsp+68h] [rbp-98h]
  __int64 v54; // [rsp+70h] [rbp-90h]
  __int64 v55; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v56; // [rsp+80h] [rbp-80h]
  int v57; // [rsp+88h] [rbp-78h]
  int v58; // [rsp+8Ch] [rbp-74h]
  __int64 v59; // [rsp+90h] [rbp-70h]
  __int64 v60; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v61; // [rsp+A0h] [rbp-60h]
  int v62; // [rsp+A8h] [rbp-58h]
  int v63; // [rsp+ACh] [rbp-54h]
  __int64 v64; // [rsp+B0h] [rbp-50h]
  __int64 v65; // [rsp+B8h] [rbp-48h]
  __int64 *v66; // [rsp+C0h] [rbp-40h]
  int v67; // [rsp+C8h] [rbp-38h]
  int v68; // [rsp+CCh] [rbp-34h]
  __int64 v69; // [rsp+D0h] [rbp-30h]
  __int64 v70; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v71; // [rsp+E0h] [rbp-20h]
  int v72; // [rsp+E8h] [rbp-18h]
  int v73; // [rsp+ECh] [rbp-14h]
  __int64 v74; // [rsp+F0h] [rbp-10h]
  __int64 v75; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v76; // [rsp+100h] [rbp+0h]
  int v77; // [rsp+108h] [rbp+8h]
  int v78; // [rsp+10Ch] [rbp+Ch]
  __int64 *v79; // [rsp+110h] [rbp+10h]
  int v80; // [rsp+118h] [rbp+18h]
  int v81; // [rsp+11Ch] [rbp+1Ch]
  __int64 v82; // [rsp+120h] [rbp+20h]
  __int64 v83; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v84; // [rsp+130h] [rbp+30h]
  int v85; // [rsp+138h] [rbp+38h]
  int v86; // [rsp+13Ch] [rbp+3Ch]
  __int64 *v87; // [rsp+140h] [rbp+40h]
  int v88; // [rsp+148h] [rbp+48h]
  int v89; // [rsp+14Ch] [rbp+4Ch]

  v22 = -1;
  v25 = 2;
  v26 = *a20;
  if ( *a20 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *((_WORD *)v26 + v27) );
    v28 = 2 * v27 + 2;
  }
  else
  {
    v26 = &qword_18001F2D0;
    v28 = 2;
  }
  v88 = v28;
  v29 = 1;
  v87 = v26;
  v89 = 0;
  v30 = *a19;
  if ( *a19 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *((_BYTE *)v30 + v31) );
    v32 = v31 + 1;
  }
  else
  {
    v30 = &word_18001EE3A;
    v32 = 1;
  }
  v85 = v32;
  v82 = a18;
  v84 = v30;
  v86 = 0;
  v83 = 4;
  v33 = *a17;
  if ( *a17 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_WORD *)v33 + v34) );
    v35 = 2 * v34 + 2;
  }
  else
  {
    v33 = &qword_18001F2D0;
    v35 = 2;
  }
  v80 = v35;
  v79 = v33;
  v81 = 0;
  v36 = *a16;
  if ( *a16 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_BYTE *)v36 + v37) );
    v38 = v37 + 1;
  }
  else
  {
    v36 = &word_18001EE3A;
    v38 = 1;
  }
  v77 = v38;
  v74 = a15;
  v76 = v36;
  v78 = 0;
  v75 = 4;
  v39 = *a14;
  if ( *a14 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_BYTE *)v39 + v40) );
    v41 = v40 + 1;
  }
  else
  {
    v39 = &word_18001EE3A;
    v41 = 1;
  }
  v72 = v41;
  v69 = a13;
  v71 = v39;
  v73 = 0;
  v70 = 4;
  v42 = *a12;
  if ( *a12 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_WORD *)v42 + v43) );
    v25 = 2 * v43 + 2;
  }
  else
  {
    v42 = &qword_18001F2D0;
  }
  v64 = a11;
  v66 = v42;
  v67 = v25;
  v68 = 0;
  v44 = *a10;
  v65 = 4;
  if ( v44 )
  {
    v45 = -1;
    do
      ++v45;
    while ( *((_BYTE *)v44 + v45) );
    v46 = v45 + 1;
  }
  else
  {
    v44 = &word_18001EE3A;
    v46 = 1;
  }
  v62 = v46;
  v59 = a9;
  v61 = v44;
  v63 = 0;
  v60 = 4;
  v47 = *a8;
  if ( *a8 )
  {
    do
      ++v22;
    while ( *((_BYTE *)v47 + v22) );
    v29 = v22 + 1;
  }
  else
  {
    v47 = &word_18001EE3A;
  }
  v54 = a7;
  v52 = a6;
  v50 = a5;
  v56 = v47;
  v57 = v29;
  v58 = 0;
  v55 = 4;
  v53 = 8;
  v51 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4, 0x12u, &v49);
}

```

## disassembly

```asm
0x180001478  push    rbp
0x18000147a  push    rbx
0x18000147b  push    rsi
0x18000147c  push    rdi
0x18000147d  push    r14
0x18000147f  push    r15
0x180001481  lea     rbp, [rsp-68h]
0x180001486  sub     rsp, 168h
0x18000148d  mov     rax, cs:__security_cookie
0x180001494  xor     rax, rsp
0x180001497  mov     [rbp+90h+var_40], rax
0x18000149b  mov     rax, [rbp+90h+arg_98]
0x1800014a2  mov     r11, rdx
0x1800014a5  mov     r10, rcx
0x1800014a8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800014ac  xor     esi, esi
0x1800014ae  mov     rdi, r9
0x1800014b1  mov     rbx, r8
0x1800014b4  mov     r9d, 2
0x1800014ba  mov     rcx, [rax]
0x1800014bd  test    rcx, rcx
0x1800014c0  jz      short loc_1800014D7
0x1800014c2  mov     rax, rdx
0x1800014c5  inc     rax
0x1800014c8  cmp     [rcx+rax*2], si
0x1800014cc  jnz     short loc_1800014C5
0x1800014ce  lea     eax, ds:2[rax*2]
0x1800014d5  jmp     short loc_1800014E1
0x1800014d7  lea     rcx, qword_18001F2D0
0x1800014de  mov     eax, r9d
0x1800014e1  mov     [rbp+90h+var_48], eax
0x1800014e4  lea     r14, word_18001EE3A
0x1800014eb  mov     rax, [rbp+90h+arg_90]
0x1800014f2  mov     r8d, 1
0x1800014f8  mov     [rbp+90h+var_50], rcx
0x1800014fc  mov     [rbp+90h+var_44], esi
0x1800014ff  mov     rcx, [rax]
0x180001502  test    rcx, rcx
0x180001505  jz      short loc_180001517
0x180001507  mov     rax, rdx
0x18000150a  inc     rax
0x18000150d  cmp     [rcx+rax], sil
0x180001511  jnz     short loc_18000150A
0x180001513  inc     eax
0x180001515  jmp     short loc_18000151D
0x180001517  mov     rcx, r14
0x18000151a  mov     eax, r8d
0x18000151d  mov     [rbp+90h+var_58], eax
0x180001520  mov     rax, [rbp+90h+arg_88]
0x180001527  mov     [rbp+90h+var_70], rax
0x18000152b  mov     rax, [rbp+90h+arg_80]
0x180001532  mov     [rbp+90h+var_60], rcx
0x180001536  mov     [rbp+90h+var_54], esi
0x180001539  mov     [rbp+90h+var_68], 4
0x180001541  mov     rcx, [rax]
0x180001544  test    rcx, rcx
0x180001547  jz      short loc_18000155E
0x180001549  mov     rax, rdx
0x18000154c  inc     rax
0x18000154f  cmp     [rcx+rax*2], si
0x180001553  jnz     short loc_18000154C
0x180001555  lea     eax, ds:2[rax*2]
0x18000155c  jmp     short loc_180001568
0x18000155e  lea     rcx, qword_18001F2D0
0x180001565  mov     eax, r9d
0x180001568  mov     [rbp+90h+var_78], eax
0x18000156b  mov     rax, [rbp+90h+arg_78]
0x180001572  mov     [rbp+90h+var_80], rcx
0x180001576  mov     [rbp+90h+var_74], esi
0x180001579  mov     rcx, [rax]
0x18000157c  test    rcx, rcx
0x18000157f  jz      short loc_180001591
0x180001581  mov     rax, rdx
0x180001584  inc     rax
0x180001587  cmp     [rcx+rax], sil
0x18000158b  jnz     short loc_180001584
0x18000158d  inc     eax
0x18000158f  jmp     short loc_180001597
0x180001591  mov     rcx, r14
0x180001594  mov     eax, r8d
0x180001597  mov     [rbp+90h+var_88], eax
0x18000159a  mov     rax, [rbp+90h+arg_70]
0x1800015a1  mov     [rbp+90h+var_A0], rax
0x1800015a5  mov     rax, [rbp+90h+arg_68]
0x1800015ac  mov     [rbp+90h+var_90], rcx
0x1800015b0  mov     [rbp+90h+var_84], esi
0x1800015b3  mov     [rbp+90h+var_98], 4
0x1800015bb  mov     rcx, [rax]
0x1800015be  test    rcx, rcx
0x1800015c1  jz      short loc_1800015D3
0x1800015c3  mov     rax, rdx
0x1800015c6  inc     rax
0x1800015c9  cmp     [rcx+rax], sil
0x1800015cd  jnz     short loc_1800015C6
0x1800015cf  inc     eax
0x1800015d1  jmp     short loc_1800015D9
0x1800015d3  mov     rcx, r14
0x1800015d6  mov     eax, r8d
0x1800015d9  mov     [rbp+90h+var_A8], eax
0x1800015dc  mov     rax, [rbp+90h+arg_60]
0x1800015e3  mov     [rbp+90h+var_C0], rax
0x1800015e7  mov     rax, [rbp+90h+arg_58]
0x1800015ee  mov     [rbp+90h+var_B0], rcx
0x1800015f2  mov     [rbp+90h+var_A4], esi
0x1800015f5  mov     [rbp+90h+var_B8], 4
0x1800015fd  mov     rcx, [rax]
0x180001600  test    rcx, rcx
0x180001603  jz      short loc_18000161B
0x180001605  mov     rax, rdx
0x180001608  inc     rax
0x18000160b  cmp     [rcx+rax*2], si
0x18000160f  jnz     short loc_180001608
0x180001611  lea     r9d, ds:2[rax*2]
0x180001619  jmp     short loc_180001622
0x18000161b  lea     rcx, qword_18001F2D0
0x180001622  mov     rax, [rbp+90h+arg_50]
0x180001629  mov     [rbp+90h+var_E0], rax
0x18000162d  mov     rax, [rbp+90h+arg_48]
0x180001634  mov     [rbp+90h+var_D0], rcx
0x180001638  mov     [rbp+90h+var_C8], r9d
0x18000163c  mov     [rbp+90h+var_C4], esi
0x18000163f  mov     rcx, [rax]
0x180001642  mov     [rbp+90h+var_D8], 4
0x18000164a  test    rcx, rcx
0x18000164d  jz      short loc_18000165F
0x18000164f  mov     rax, rdx
0x180001652  inc     rax
0x180001655  cmp     [rcx+rax], sil
0x180001659  jnz     short loc_180001652
0x18000165b  inc     eax
0x18000165d  jmp     short loc_180001665
0x18000165f  mov     rcx, r14
0x180001662  mov     eax, r8d
0x180001665  mov     [rbp+90h+var_E8], eax
0x180001668  mov     rax, [rbp+90h+arg_40]
0x18000166f  mov     [rbp+90h+var_100], rax
0x180001673  mov     rax, [rbp+90h+arg_38]
0x18000167a  mov     [rbp+90h+var_F0], rcx
0x18000167e  mov     [rbp+90h+var_E4], esi
0x180001681  mov     [rbp+90h+var_F8], 4
0x180001689  mov     rcx, [rax]
0x18000168c  test    rcx, rcx
0x18000168f  jz      short loc_1800016A0
0x180001691  inc     rdx
0x180001694  cmp     [rcx+rdx], sil
0x180001698  jnz     short loc_180001691
0x18000169a  lea     r8d, [rdx+1]
0x18000169e  jmp     short loc_1800016A3
0x1800016a0  mov     rcx, r14
0x1800016a3  mov     rax, [rbp+90h+arg_30]
0x1800016aa  mov     r9, rdi
0x1800016ad  mov     [rsp+190h+var_120], rax
0x1800016b2  mov     rdx, r11
0x1800016b5  mov     rax, [rbp+90h+arg_28]
0x1800016bc  mov     [rsp+190h+var_130], rax
0x1800016c1  mov     rax, [rbp+90h+arg_20]
0x1800016c8  mov     [rsp+190h+var_140], rax
0x1800016cd  lea     rax, [rsp+190h+var_160]
0x1800016d2  mov     [rbp+90h+var_110], rcx
0x1800016d6  mov     rcx, r10
0x1800016d9  mov     [rbp+90h+var_108], r8d
0x1800016dd  mov     r8, rbx
0x1800016e0  mov     [rsp+190h+var_168], rax
0x1800016e5  mov     [rsp+190h+var_170], 12h
0x1800016ed  mov     [rbp+90h+var_104], esi
0x1800016f0  mov     [rsp+190h+var_118], 4
0x1800016f9  mov     [rsp+190h+var_128], 8
0x180001702  mov     [rsp+190h+var_138], 8
0x18000170b  call    _tlgWriteTransfer_EventWriteTransfer
0x180001710  mov     rcx, [rbp+90h+var_40]
0x180001714  xor     rcx, rsp; StackCookie
0x180001717  call    __security_check_cookie
0x18000171c  add     rsp, 168h
0x180001723  pop     r15
0x180001725  pop     r14
0x180001727  pop     rdi
0x180001728  pop     rsi
0x180001729  pop     rbx
0x18000172a  pop     rbp
0x18000172b  retn
```
