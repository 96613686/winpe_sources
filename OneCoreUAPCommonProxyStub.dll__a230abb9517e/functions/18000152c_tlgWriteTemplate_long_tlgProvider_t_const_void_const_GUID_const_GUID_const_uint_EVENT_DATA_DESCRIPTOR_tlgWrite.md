# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x18000152c`
- end: `0x1800017d7`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008d1c`

## callees

- `0x18000152c`
- `0x180001bb4`
- `0x180003c80`

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
        char **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        char **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        char **a20)
{
  __int64 v22; // rcx
  int v23; // r9d
  char *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  char *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  char *v40; // rdx
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
  char *v64; // [rsp+C0h] [rbp-40h]
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
  char *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  char *v85; // [rsp+140h] [rbp+40h]
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
    while ( *(_WORD *)&v24[2 * v25] );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = byte_1804F7828;
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
    v28 = &word_1804F782A;
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
    while ( *(_WORD *)&v31[2 * v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = byte_1804F7828;
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
    v34 = &word_1804F782A;
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
    v37 = &word_1804F782A;
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
    while ( *(_WORD *)&v40[2 * v41] );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = byte_1804F7828;
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
    v42 = &word_1804F782A;
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
    v45 = &word_1804F782A;
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
0x18000152c  mov     [rsp-8+arg_10], rbx
0x180001531  push    rbp
0x180001532  push    rsi
0x180001533  push    rdi
0x180001534  lea     rbp, [rsp-60h]
0x180001539  sub     rsp, 160h
0x180001540  mov     rax, cs:__security_cookie
0x180001547  xor     rax, rsp
0x18000154a  mov     [rbp+70h+var_20], rax
0x18000154e  mov     rax, [rbp+70h+arg_98]
0x180001555  mov     r11, rdx
0x180001558  mov     r10, rcx
0x18000155b  xor     ebx, ebx
0x18000155d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001561  mov     r9d, 2
0x180001567  mov     rdx, [rax]
0x18000156a  test    rdx, rdx
0x18000156d  jz      short loc_180001584
0x18000156f  mov     rax, rcx
0x180001572  inc     rax
0x180001575  cmp     [rdx+rax*2], bx
0x180001579  jnz     short loc_180001572
0x18000157b  lea     eax, ds:2[rax*2]
0x180001582  jmp     short loc_18000158E
0x180001584  lea     rdx, byte_1804F7828
0x18000158b  mov     eax, r9d
0x18000158e  mov     [rbp+70h+var_28], eax
0x180001591  lea     rdi, word_1804F782A
0x180001598  mov     rax, [rbp+70h+arg_90]
0x18000159f  mov     r8d, 1
0x1800015a5  mov     [rbp+70h+var_30], rdx
0x1800015a9  mov     [rbp+70h+var_24], ebx
0x1800015ac  mov     rdx, [rax]
0x1800015af  test    rdx, rdx
0x1800015b2  jz      short loc_1800015C3
0x1800015b4  mov     rax, rcx
0x1800015b7  inc     rax
0x1800015ba  cmp     [rdx+rax], bl
0x1800015bd  jnz     short loc_1800015B7
0x1800015bf  inc     eax
0x1800015c1  jmp     short loc_1800015C9
0x1800015c3  mov     rdx, rdi
0x1800015c6  mov     eax, r8d
0x1800015c9  mov     [rbp+70h+var_38], eax
0x1800015cc  mov     rax, [rbp+70h+arg_88]
0x1800015d3  mov     [rbp+70h+var_50], rax
0x1800015d7  mov     rax, [rbp+70h+arg_80]
0x1800015de  mov     [rbp+70h+var_40], rdx
0x1800015e2  mov     [rbp+70h+var_34], ebx
0x1800015e5  mov     [rbp+70h+var_48], 4
0x1800015ed  mov     rdx, [rax]
0x1800015f0  test    rdx, rdx
0x1800015f3  jz      short loc_18000160A
0x1800015f5  mov     rax, rcx
0x1800015f8  inc     rax
0x1800015fb  cmp     [rdx+rax*2], bx
0x1800015ff  jnz     short loc_1800015F8
0x180001601  lea     eax, ds:2[rax*2]
0x180001608  jmp     short loc_180001614
0x18000160a  lea     rdx, byte_1804F7828
0x180001611  mov     eax, r9d
0x180001614  mov     [rbp+70h+var_58], eax
0x180001617  mov     rax, [rbp+70h+arg_78]
0x18000161e  mov     [rbp+70h+var_60], rdx
0x180001622  mov     [rbp+70h+var_54], ebx
0x180001625  mov     rdx, [rax]
0x180001628  test    rdx, rdx
0x18000162b  jz      short loc_18000163C
0x18000162d  mov     rax, rcx
0x180001630  inc     rax
0x180001633  cmp     [rdx+rax], bl
0x180001636  jnz     short loc_180001630
0x180001638  inc     eax
0x18000163a  jmp     short loc_180001642
0x18000163c  mov     rdx, rdi
0x18000163f  mov     eax, r8d
0x180001642  mov     [rbp+70h+var_68], eax
0x180001645  mov     rax, [rbp+70h+arg_70]
0x18000164c  mov     [rbp+70h+var_80], rax
0x180001650  mov     rax, [rbp+70h+arg_68]
0x180001657  mov     [rbp+70h+var_70], rdx
0x18000165b  mov     [rbp+70h+var_64], ebx
0x18000165e  mov     [rbp+70h+var_78], 4
0x180001666  mov     rdx, [rax]
0x180001669  test    rdx, rdx
0x18000166c  jz      short loc_18000167D
0x18000166e  mov     rax, rcx
0x180001671  inc     rax
0x180001674  cmp     [rdx+rax], bl
0x180001677  jnz     short loc_180001671
0x180001679  inc     eax
0x18000167b  jmp     short loc_180001683
0x18000167d  mov     rdx, rdi
0x180001680  mov     eax, r8d
0x180001683  mov     [rbp+70h+var_88], eax
0x180001686  mov     rax, [rbp+70h+arg_60]
0x18000168d  mov     [rbp+70h+var_A0], rax
0x180001691  mov     rax, [rbp+70h+arg_58]
0x180001698  mov     [rbp+70h+var_90], rdx
0x18000169c  mov     [rbp+70h+var_84], ebx
0x18000169f  mov     [rbp+70h+var_98], 4
0x1800016a7  mov     rdx, [rax]
0x1800016aa  test    rdx, rdx
0x1800016ad  jz      short loc_1800016C5
0x1800016af  mov     rax, rcx
0x1800016b2  inc     rax
0x1800016b5  cmp     [rdx+rax*2], bx
0x1800016b9  jnz     short loc_1800016B2
0x1800016bb  lea     r9d, ds:2[rax*2]
0x1800016c3  jmp     short loc_1800016CC
0x1800016c5  lea     rdx, byte_1804F7828
0x1800016cc  mov     rax, [rbp+70h+arg_50]
0x1800016d3  mov     [rbp+70h+var_C0], rax
0x1800016d7  mov     rax, [rbp+70h+arg_48]
0x1800016de  mov     [rbp+70h+var_B0], rdx
0x1800016e2  mov     [rbp+70h+var_A8], r9d
0x1800016e6  mov     [rbp+70h+var_A4], ebx
0x1800016e9  mov     rdx, [rax]
0x1800016ec  mov     [rbp+70h+var_B8], 4
0x1800016f4  test    rdx, rdx
0x1800016f7  jz      short loc_180001708
0x1800016f9  mov     rax, rcx
0x1800016fc  inc     rax
0x1800016ff  cmp     [rdx+rax], bl
0x180001702  jnz     short loc_1800016FC
0x180001704  inc     eax
0x180001706  jmp     short loc_18000170E
0x180001708  mov     rdx, rdi
0x18000170b  mov     eax, r8d
0x18000170e  mov     [rbp+70h+var_C8], eax
0x180001711  mov     rax, [rbp+70h+arg_40]
0x180001718  mov     [rbp+70h+var_E0], rax
0x18000171c  mov     rax, [rbp+70h+arg_38]
0x180001723  mov     [rbp+70h+var_D0], rdx
0x180001727  mov     [rbp+70h+var_C4], ebx
0x18000172a  mov     [rbp+70h+var_D8], 4
0x180001732  mov     rdx, [rax]
0x180001735  test    rdx, rdx
0x180001738  jz      short loc_180001748
0x18000173a  inc     rcx
0x18000173d  cmp     [rdx+rcx], bl
0x180001740  jnz     short loc_18000173A
0x180001742  lea     r8d, [rcx+1]
0x180001746  jmp     short loc_18000174B
0x180001748  mov     rdx, rdi
0x18000174b  mov     rax, [rbp+70h+arg_30]
0x180001752  xor     r9d, r9d
0x180001755  mov     [rsp+170h+var_100], rax
0x18000175a  mov     rcx, r10
0x18000175d  mov     rax, [rbp+70h+arg_28]
0x180001764  mov     [rsp+170h+var_110], rax
0x180001769  mov     rax, [rbp+70h+arg_20]
0x180001770  mov     [rsp+170h+var_120], rax
0x180001775  lea     rax, [rsp+170h+var_140]
0x18000177a  mov     [rbp+70h+var_F0], rdx
0x18000177e  mov     rdx, r11
0x180001781  mov     [rbp+70h+var_E8], r8d
0x180001785  xor     r8d, r8d
0x180001788  mov     [rsp+170h+var_148], rax
0x18000178d  mov     [rsp+170h+var_150], 12h
0x180001795  mov     [rbp+70h+var_E4], ebx
0x180001798  mov     [rsp+170h+var_F8], 4
0x1800017a1  mov     [rsp+170h+var_108], 8
0x1800017aa  mov     [rsp+170h+var_118], 8
0x1800017b3  call    _tlgWriteTransfer_EventWriteTransfer
0x1800017b8  mov     rcx, [rbp+70h+var_20]
0x1800017bc  xor     rcx, rsp; StackCookie
0x1800017bf  call    __security_check_cookie
0x1800017c4  mov     rbx, [rsp+170h+arg_10]
0x1800017cc  add     rsp, 160h
0x1800017d3  pop     rdi
0x1800017d4  pop     rsi
0x1800017d5  pop     rbp
0x1800017d6  retn
```
