# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001378`
- end: `0x140001624`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400172ec`

## callees

- `0x140001378`
- `0x140001f60`
- `0x1400029c0`

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
        const WCHAR **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        const WCHAR **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        const WCHAR **a20)
{
  __int64 v22; // rcx
  int v23; // r9d
  const WCHAR *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  const WCHAR *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  const WCHAR *v40; // rdx
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
  const WCHAR *v64; // [rsp+C0h] [rbp-40h]
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
  const WCHAR *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  const WCHAR *v85; // [rsp+140h] [rbp+40h]
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
    while ( v24[v25] );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &sourceString;
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
    v28 = &byte_14001BCA1;
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
    while ( v31[v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &sourceString;
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
    v34 = &byte_14001BCA1;
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
    v37 = &byte_14001BCA1;
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
    while ( v40[v41] );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = &sourceString;
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
    v42 = &byte_14001BCA1;
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
    v45 = &byte_14001BCA1;
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
0x140001378  mov     [rsp-8+arg_10], rbx
0x14000137d  push    rbp
0x14000137e  push    rsi
0x14000137f  push    rdi
0x140001380  lea     rbp, [rsp-60h]
0x140001385  sub     rsp, 160h
0x14000138c  mov     rax, cs:__security_cookie
0x140001393  xor     rax, rsp
0x140001396  mov     [rbp+70h+var_20], rax
0x14000139a  mov     rax, [rbp+70h+arg_98]
0x1400013a1  mov     r11, rdx
0x1400013a4  mov     r10, rcx
0x1400013a7  xor     ebx, ebx
0x1400013a9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400013ad  mov     r9d, 2
0x1400013b3  mov     rdx, [rax]
0x1400013b6  test    rdx, rdx
0x1400013b9  jz      short loc_1400013D0
0x1400013bb  mov     rax, rcx
0x1400013be  inc     rax
0x1400013c1  cmp     [rdx+rax*2], bx
0x1400013c5  jnz     short loc_1400013BE
0x1400013c7  lea     eax, ds:2[rax*2]
0x1400013ce  jmp     short loc_1400013DA
0x1400013d0  lea     rdx, sourceString
0x1400013d7  mov     eax, r9d
0x1400013da  mov     [rbp+70h+var_28], eax
0x1400013dd  lea     rdi, byte_14001BCA1
0x1400013e4  mov     rax, [rbp+70h+arg_90]
0x1400013eb  mov     r8d, 1
0x1400013f1  mov     [rbp+70h+var_30], rdx
0x1400013f5  mov     [rbp+70h+var_24], ebx
0x1400013f8  mov     rdx, [rax]
0x1400013fb  test    rdx, rdx
0x1400013fe  jz      short loc_14000140F
0x140001400  mov     rax, rcx
0x140001403  inc     rax
0x140001406  cmp     [rdx+rax], bl
0x140001409  jnz     short loc_140001403
0x14000140b  inc     eax
0x14000140d  jmp     short loc_140001415
0x14000140f  mov     rdx, rdi
0x140001412  mov     eax, r8d
0x140001415  mov     [rbp+70h+var_38], eax
0x140001418  mov     rax, [rbp+70h+arg_88]
0x14000141f  mov     [rbp+70h+var_50], rax
0x140001423  mov     rax, [rbp+70h+arg_80]
0x14000142a  mov     [rbp+70h+var_40], rdx
0x14000142e  mov     [rbp+70h+var_34], ebx
0x140001431  mov     [rbp+70h+var_48], 4
0x140001439  mov     rdx, [rax]
0x14000143c  test    rdx, rdx
0x14000143f  jz      short loc_140001456
0x140001441  mov     rax, rcx
0x140001444  inc     rax
0x140001447  cmp     [rdx+rax*2], bx
0x14000144b  jnz     short loc_140001444
0x14000144d  lea     eax, ds:2[rax*2]
0x140001454  jmp     short loc_140001460
0x140001456  lea     rdx, sourceString
0x14000145d  mov     eax, r9d
0x140001460  mov     [rbp+70h+var_58], eax
0x140001463  mov     rax, [rbp+70h+arg_78]
0x14000146a  mov     [rbp+70h+var_60], rdx
0x14000146e  mov     [rbp+70h+var_54], ebx
0x140001471  mov     rdx, [rax]
0x140001474  test    rdx, rdx
0x140001477  jz      short loc_140001488
0x140001479  mov     rax, rcx
0x14000147c  inc     rax
0x14000147f  cmp     [rdx+rax], bl
0x140001482  jnz     short loc_14000147C
0x140001484  inc     eax
0x140001486  jmp     short loc_14000148E
0x140001488  mov     rdx, rdi
0x14000148b  mov     eax, r8d
0x14000148e  mov     [rbp+70h+var_68], eax
0x140001491  mov     rax, [rbp+70h+arg_70]
0x140001498  mov     [rbp+70h+var_80], rax
0x14000149c  mov     rax, [rbp+70h+arg_68]
0x1400014a3  mov     [rbp+70h+var_70], rdx
0x1400014a7  mov     [rbp+70h+var_64], ebx
0x1400014aa  mov     [rbp+70h+var_78], 4
0x1400014b2  mov     rdx, [rax]
0x1400014b5  test    rdx, rdx
0x1400014b8  jz      short loc_1400014C9
0x1400014ba  mov     rax, rcx
0x1400014bd  inc     rax
0x1400014c0  cmp     [rdx+rax], bl
0x1400014c3  jnz     short loc_1400014BD
0x1400014c5  inc     eax
0x1400014c7  jmp     short loc_1400014CF
0x1400014c9  mov     rdx, rdi
0x1400014cc  mov     eax, r8d
0x1400014cf  mov     [rbp+70h+var_88], eax
0x1400014d2  mov     rax, [rbp+70h+arg_60]
0x1400014d9  mov     [rbp+70h+var_A0], rax
0x1400014dd  mov     rax, [rbp+70h+arg_58]
0x1400014e4  mov     [rbp+70h+var_90], rdx
0x1400014e8  mov     [rbp+70h+var_84], ebx
0x1400014eb  mov     [rbp+70h+var_98], 4
0x1400014f3  mov     rdx, [rax]
0x1400014f6  test    rdx, rdx
0x1400014f9  jz      short loc_140001511
0x1400014fb  mov     rax, rcx
0x1400014fe  inc     rax
0x140001501  cmp     [rdx+rax*2], bx
0x140001505  jnz     short loc_1400014FE
0x140001507  lea     r9d, ds:2[rax*2]
0x14000150f  jmp     short loc_140001518
0x140001511  lea     rdx, sourceString
0x140001518  mov     rax, [rbp+70h+arg_50]
0x14000151f  mov     [rbp+70h+var_C0], rax
0x140001523  mov     rax, [rbp+70h+arg_48]
0x14000152a  mov     [rbp+70h+var_B0], rdx
0x14000152e  mov     [rbp+70h+var_A8], r9d
0x140001532  mov     [rbp+70h+var_A4], ebx
0x140001535  mov     rdx, [rax]
0x140001538  mov     [rbp+70h+var_B8], 4
0x140001540  test    rdx, rdx
0x140001543  jz      short loc_140001554
0x140001545  mov     rax, rcx
0x140001548  inc     rax
0x14000154b  cmp     [rdx+rax], bl
0x14000154e  jnz     short loc_140001548
0x140001550  inc     eax
0x140001552  jmp     short loc_14000155A
0x140001554  mov     rdx, rdi
0x140001557  mov     eax, r8d
0x14000155a  mov     [rbp+70h+var_C8], eax
0x14000155d  mov     rax, [rbp+70h+arg_40]
0x140001564  mov     [rbp+70h+var_E0], rax
0x140001568  mov     rax, [rbp+70h+arg_38]
0x14000156f  mov     [rbp+70h+var_D0], rdx
0x140001573  mov     [rbp+70h+var_C4], ebx
0x140001576  mov     [rbp+70h+var_D8], 4
0x14000157e  mov     rdx, [rax]
0x140001581  test    rdx, rdx
0x140001584  jz      short loc_140001594
0x140001586  inc     rcx
0x140001589  cmp     [rdx+rcx], bl
0x14000158c  jnz     short loc_140001586
0x14000158e  lea     r8d, [rcx+1]
0x140001592  jmp     short loc_140001597
0x140001594  mov     rdx, rdi
0x140001597  mov     rax, [rbp+70h+arg_30]
0x14000159e  xor     r9d, r9d
0x1400015a1  mov     [rsp+170h+var_100], rax
0x1400015a6  mov     rcx, r10
0x1400015a9  mov     rax, [rbp+70h+arg_28]
0x1400015b0  mov     [rsp+170h+var_110], rax
0x1400015b5  mov     rax, [rbp+70h+arg_20]
0x1400015bc  mov     [rsp+170h+var_120], rax
0x1400015c1  lea     rax, [rsp+170h+var_140]
0x1400015c6  mov     [rbp+70h+var_F0], rdx
0x1400015ca  mov     rdx, r11
0x1400015cd  mov     [rbp+70h+var_E8], r8d
0x1400015d1  xor     r8d, r8d
0x1400015d4  mov     [rsp+170h+var_148], rax
0x1400015d9  mov     [rsp+170h+var_150], 12h
0x1400015e1  mov     [rbp+70h+var_E4], ebx
0x1400015e4  mov     [rsp+170h+var_F8], 4
0x1400015ed  mov     [rsp+170h+var_108], 8
0x1400015f6  mov     [rsp+170h+var_118], 8
0x1400015ff  call    _tlgWriteTransfer_EventWriteTransfer
0x140001604  mov     rcx, [rbp+70h+var_20]
0x140001608  xor     rcx, rsp; StackCookie
0x14000160b  call    __security_check_cookie
0x140001610  mov     rbx, [rsp+170h+arg_10]
0x140001618  add     rsp, 160h
0x14000161f  pop     rdi
0x140001620  pop     rsi
0x140001621  pop     rbp
0x140001622  retn
```
