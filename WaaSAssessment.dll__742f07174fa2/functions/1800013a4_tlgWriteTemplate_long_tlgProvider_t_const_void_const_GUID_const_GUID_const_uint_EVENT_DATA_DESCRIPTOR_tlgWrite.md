# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800013a4`
- end: `0x18000164f`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001526c`

## callees

- `0x1800013a4`
- `0x180001a8c`
- `0x180019760`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
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
  __int64 v22; // rcx
  int v23; // r9d
  int *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  int *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  int *v40; // rdx
  __int64 v41; // rax
  const unsigned __int16 *v42; // rdx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rdx
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  __int64 v52; // [rsp+70h] [rbp-90h]
  __int64 v53; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v54; // [rsp+80h] [rbp-80h]
  int v55; // [rsp+88h] [rbp-78h]
  int v56; // [rsp+8Ch] [rbp-74h]
  __int64 v57; // [rsp+90h] [rbp-70h]
  __int64 v58; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v59; // [rsp+A0h] [rbp-60h]
  int v60; // [rsp+A8h] [rbp-58h]
  int v61; // [rsp+ACh] [rbp-54h]
  __int64 v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+B8h] [rbp-48h]
  int *v64; // [rsp+C0h] [rbp-40h]
  int v65; // [rsp+C8h] [rbp-38h]
  int v66; // [rsp+CCh] [rbp-34h]
  __int64 v67; // [rsp+D0h] [rbp-30h]
  __int64 v68; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v69; // [rsp+E0h] [rbp-20h]
  int v70; // [rsp+E8h] [rbp-18h]
  int v71; // [rsp+ECh] [rbp-14h]
  __int64 v72; // [rsp+F0h] [rbp-10h]
  __int64 v73; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v74; // [rsp+100h] [rbp+0h]
  int v75; // [rsp+108h] [rbp+8h]
  int v76; // [rsp+10Ch] [rbp+Ch]
  int *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  int *v85; // [rsp+140h] [rbp+40h]
  int v86; // [rsp+148h] [rbp+48h]
  int v87; // [rsp+14Ch] [rbp+4Ch]

  v22 = -1;
  v23 = 2;
  v24 = *a20;
  if ( *a20 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *((_WORD *)v24 + v25) );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &dword_18001D62C;
    v26 = 2;
  }
  v86 = v26;
  v27 = 1;
  v85 = v24;
  v87 = 0;
  v28 = *a19;
  if ( *a19 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_BYTE *)v28 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &word_18001F07E;
    v30 = 1;
  }
  v83 = v30;
  v80 = a18;
  v82 = v28;
  v84 = 0;
  v81 = 4;
  v31 = *a17;
  if ( *a17 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *((_WORD *)v31 + v32) );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &dword_18001D62C;
    v33 = 2;
  }
  v78 = v33;
  v77 = v31;
  v79 = 0;
  v34 = *a16;
  if ( *a16 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &word_18001F07E;
    v36 = 1;
  }
  v75 = v36;
  v72 = a15;
  v74 = v34;
  v76 = 0;
  v73 = 4;
  v37 = *a14;
  if ( *a14 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_BYTE *)v37 + v38) );
    v39 = v38 + 1;
  }
  else
  {
    v37 = &word_18001F07E;
    v39 = 1;
  }
  v70 = v39;
  v67 = a13;
  v69 = v37;
  v71 = 0;
  v68 = 4;
  v40 = *a12;
  if ( *a12 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_WORD *)v40 + v41) );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = &dword_18001D62C;
  }
  v62 = a11;
  v64 = v40;
  v65 = v23;
  v66 = 0;
  v42 = *a10;
  v63 = 4;
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
    v42 = &word_18001F07E;
    v44 = 1;
  }
  v60 = v44;
  v57 = a9;
  v59 = v42;
  v61 = 0;
  v58 = 4;
  v45 = *a8;
  if ( *a8 )
  {
    do
      ++v22;
    while ( *((_BYTE *)v45 + v22) );
    v27 = v22 + 1;
  }
  else
  {
    v45 = &word_18001F07E;
  }
  v52 = a7;
  v50 = a6;
  v48 = a5;
  v54 = v45;
  v55 = v27;
  v56 = 0;
  v53 = 4;
  v51 = 8;
  v49 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0x12u, &v47);
}

```

## disassembly

```asm
0x1800013a4  mov     [rsp-8+arg_10], rbx
0x1800013a9  push    rbp
0x1800013aa  push    rsi
0x1800013ab  push    rdi
0x1800013ac  lea     rbp, [rsp-60h]
0x1800013b1  sub     rsp, 160h
0x1800013b8  mov     rax, cs:__security_cookie
0x1800013bf  xor     rax, rsp
0x1800013c2  mov     [rbp+70h+var_20], rax
0x1800013c6  mov     rax, [rbp+70h+arg_98]
0x1800013cd  mov     r11, rdx
0x1800013d0  mov     r10, rcx
0x1800013d3  xor     ebx, ebx
0x1800013d5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800013d9  mov     r9d, 2
0x1800013df  mov     rdx, [rax]
0x1800013e2  test    rdx, rdx
0x1800013e5  jz      short loc_1800013FC
0x1800013e7  mov     rax, rcx
0x1800013ea  inc     rax
0x1800013ed  cmp     [rdx+rax*2], bx
0x1800013f1  jnz     short loc_1800013EA
0x1800013f3  lea     eax, ds:2[rax*2]
0x1800013fa  jmp     short loc_180001406
0x1800013fc  lea     rdx, dword_18001D62C
0x180001403  mov     eax, r9d
0x180001406  mov     [rbp+70h+var_28], eax
0x180001409  lea     rdi, word_18001F07E
0x180001410  mov     rax, [rbp+70h+arg_90]
0x180001417  mov     r8d, 1
0x18000141d  mov     [rbp+70h+var_30], rdx
0x180001421  mov     [rbp+70h+var_24], ebx
0x180001424  mov     rdx, [rax]
0x180001427  test    rdx, rdx
0x18000142a  jz      short loc_18000143B
0x18000142c  mov     rax, rcx
0x18000142f  inc     rax
0x180001432  cmp     [rdx+rax], bl
0x180001435  jnz     short loc_18000142F
0x180001437  inc     eax
0x180001439  jmp     short loc_180001441
0x18000143b  mov     rdx, rdi
0x18000143e  mov     eax, r8d
0x180001441  mov     [rbp+70h+var_38], eax
0x180001444  mov     rax, [rbp+70h+arg_88]
0x18000144b  mov     [rbp+70h+var_50], rax
0x18000144f  mov     rax, [rbp+70h+arg_80]
0x180001456  mov     [rbp+70h+var_40], rdx
0x18000145a  mov     [rbp+70h+var_34], ebx
0x18000145d  mov     [rbp+70h+var_48], 4
0x180001465  mov     rdx, [rax]
0x180001468  test    rdx, rdx
0x18000146b  jz      short loc_180001482
0x18000146d  mov     rax, rcx
0x180001470  inc     rax
0x180001473  cmp     [rdx+rax*2], bx
0x180001477  jnz     short loc_180001470
0x180001479  lea     eax, ds:2[rax*2]
0x180001480  jmp     short loc_18000148C
0x180001482  lea     rdx, dword_18001D62C
0x180001489  mov     eax, r9d
0x18000148c  mov     [rbp+70h+var_58], eax
0x18000148f  mov     rax, [rbp+70h+arg_78]
0x180001496  mov     [rbp+70h+var_60], rdx
0x18000149a  mov     [rbp+70h+var_54], ebx
0x18000149d  mov     rdx, [rax]
0x1800014a0  test    rdx, rdx
0x1800014a3  jz      short loc_1800014B4
0x1800014a5  mov     rax, rcx
0x1800014a8  inc     rax
0x1800014ab  cmp     [rdx+rax], bl
0x1800014ae  jnz     short loc_1800014A8
0x1800014b0  inc     eax
0x1800014b2  jmp     short loc_1800014BA
0x1800014b4  mov     rdx, rdi
0x1800014b7  mov     eax, r8d
0x1800014ba  mov     [rbp+70h+var_68], eax
0x1800014bd  mov     rax, [rbp+70h+arg_70]
0x1800014c4  mov     [rbp+70h+var_80], rax
0x1800014c8  mov     rax, [rbp+70h+arg_68]
0x1800014cf  mov     [rbp+70h+var_70], rdx
0x1800014d3  mov     [rbp+70h+var_64], ebx
0x1800014d6  mov     [rbp+70h+var_78], 4
0x1800014de  mov     rdx, [rax]
0x1800014e1  test    rdx, rdx
0x1800014e4  jz      short loc_1800014F5
0x1800014e6  mov     rax, rcx
0x1800014e9  inc     rax
0x1800014ec  cmp     [rdx+rax], bl
0x1800014ef  jnz     short loc_1800014E9
0x1800014f1  inc     eax
0x1800014f3  jmp     short loc_1800014FB
0x1800014f5  mov     rdx, rdi
0x1800014f8  mov     eax, r8d
0x1800014fb  mov     [rbp+70h+var_88], eax
0x1800014fe  mov     rax, [rbp+70h+arg_60]
0x180001505  mov     [rbp+70h+var_A0], rax
0x180001509  mov     rax, [rbp+70h+arg_58]
0x180001510  mov     [rbp+70h+var_90], rdx
0x180001514  mov     [rbp+70h+var_84], ebx
0x180001517  mov     [rbp+70h+var_98], 4
0x18000151f  mov     rdx, [rax]
0x180001522  test    rdx, rdx
0x180001525  jz      short loc_18000153D
0x180001527  mov     rax, rcx
0x18000152a  inc     rax
0x18000152d  cmp     [rdx+rax*2], bx
0x180001531  jnz     short loc_18000152A
0x180001533  lea     r9d, ds:2[rax*2]
0x18000153b  jmp     short loc_180001544
0x18000153d  lea     rdx, dword_18001D62C
0x180001544  mov     rax, [rbp+70h+arg_50]
0x18000154b  mov     [rbp+70h+var_C0], rax
0x18000154f  mov     rax, [rbp+70h+arg_48]
0x180001556  mov     [rbp+70h+var_B0], rdx
0x18000155a  mov     [rbp+70h+var_A8], r9d
0x18000155e  mov     [rbp+70h+var_A4], ebx
0x180001561  mov     rdx, [rax]
0x180001564  mov     [rbp+70h+var_B8], 4
0x18000156c  test    rdx, rdx
0x18000156f  jz      short loc_180001580
0x180001571  mov     rax, rcx
0x180001574  inc     rax
0x180001577  cmp     [rdx+rax], bl
0x18000157a  jnz     short loc_180001574
0x18000157c  inc     eax
0x18000157e  jmp     short loc_180001586
0x180001580  mov     rdx, rdi
0x180001583  mov     eax, r8d
0x180001586  mov     [rbp+70h+var_C8], eax
0x180001589  mov     rax, [rbp+70h+arg_40]
0x180001590  mov     [rbp+70h+var_E0], rax
0x180001594  mov     rax, [rbp+70h+arg_38]
0x18000159b  mov     [rbp+70h+var_D0], rdx
0x18000159f  mov     [rbp+70h+var_C4], ebx
0x1800015a2  mov     [rbp+70h+var_D8], 4
0x1800015aa  mov     rdx, [rax]
0x1800015ad  test    rdx, rdx
0x1800015b0  jz      short loc_1800015C0
0x1800015b2  inc     rcx
0x1800015b5  cmp     [rdx+rcx], bl
0x1800015b8  jnz     short loc_1800015B2
0x1800015ba  lea     r8d, [rcx+1]
0x1800015be  jmp     short loc_1800015C3
0x1800015c0  mov     rdx, rdi
0x1800015c3  mov     rax, [rbp+70h+arg_30]
0x1800015ca  xor     r9d, r9d
0x1800015cd  mov     [rsp+170h+var_100], rax
0x1800015d2  mov     rcx, r10
0x1800015d5  mov     rax, [rbp+70h+arg_28]
0x1800015dc  mov     [rsp+170h+var_110], rax
0x1800015e1  mov     rax, [rbp+70h+arg_20]
0x1800015e8  mov     [rsp+170h+var_120], rax
0x1800015ed  lea     rax, [rsp+170h+var_140]
0x1800015f2  mov     [rbp+70h+var_F0], rdx
0x1800015f6  mov     rdx, r11
0x1800015f9  mov     [rbp+70h+var_E8], r8d
0x1800015fd  xor     r8d, r8d
0x180001600  mov     [rsp+170h+var_148], rax
0x180001605  mov     [rsp+170h+var_150], 12h
0x18000160d  mov     [rbp+70h+var_E4], ebx
0x180001610  mov     [rsp+170h+var_F8], 4
0x180001619  mov     [rsp+170h+var_108], 8
0x180001622  mov     [rsp+170h+var_118], 8
0x18000162b  call    _tlgWriteTransfer_EventWriteTransfer
0x180001630  mov     rcx, [rbp+70h+var_20]
0x180001634  xor     rcx, rsp; StackCookie
0x180001637  call    __security_check_cookie
0x18000163c  mov     rbx, [rsp+170h+arg_10]
0x180001644  add     rsp, 160h
0x18000164b  pop     rdi
0x18000164c  pop     rsi
0x18000164d  pop     rbp
0x18000164e  retn
```
