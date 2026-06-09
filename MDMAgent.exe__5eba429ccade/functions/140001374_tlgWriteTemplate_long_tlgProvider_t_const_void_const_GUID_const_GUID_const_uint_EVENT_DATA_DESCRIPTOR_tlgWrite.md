# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001374`
- end: `0x14000161f`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const WCHAR **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const WCHAR **, __int64, const unsigned __int16 **, const WCHAR **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140016644`

## callees

- `0x140001374`
- `0x140001f48`
- `0x140002930`

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
  _BYTE v47[32]; // [rsp+30h] [rbp-D0h] BYREF
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
    v28 = &byte_14001ACA1;
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
    v34 = &byte_14001ACA1;
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
    v37 = &byte_14001ACA1;
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
    v42 = &byte_14001ACA1;
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
    v45 = &byte_14001ACA1;
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
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 18, v47);
}

```

## disassembly

```asm
0x140001374  mov     [rsp-8+arg_10], rbx
0x140001379  push    rbp
0x14000137a  push    rsi
0x14000137b  push    rdi
0x14000137c  lea     rbp, [rsp-60h]
0x140001381  sub     rsp, 160h
0x140001388  mov     rax, cs:__security_cookie
0x14000138f  xor     rax, rsp
0x140001392  mov     [rbp+70h+var_20], rax
0x140001396  mov     rax, [rbp+70h+arg_98]
0x14000139d  mov     r11, rdx
0x1400013a0  mov     r10, rcx
0x1400013a3  xor     ebx, ebx
0x1400013a5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400013a9  mov     r9d, 2
0x1400013af  mov     rdx, [rax]
0x1400013b2  test    rdx, rdx
0x1400013b5  jz      short loc_1400013CC
0x1400013b7  mov     rax, rcx
0x1400013ba  inc     rax
0x1400013bd  cmp     [rdx+rax*2], bx
0x1400013c1  jnz     short loc_1400013BA
0x1400013c3  lea     eax, ds:2[rax*2]
0x1400013ca  jmp     short loc_1400013D6
0x1400013cc  lea     rdx, sourceString
0x1400013d3  mov     eax, r9d
0x1400013d6  mov     [rbp+70h+var_28], eax
0x1400013d9  lea     rdi, byte_14001ACA1
0x1400013e0  mov     rax, [rbp+70h+arg_90]
0x1400013e7  mov     r8d, 1
0x1400013ed  mov     [rbp+70h+var_30], rdx
0x1400013f1  mov     [rbp+70h+var_24], ebx
0x1400013f4  mov     rdx, [rax]
0x1400013f7  test    rdx, rdx
0x1400013fa  jz      short loc_14000140B
0x1400013fc  mov     rax, rcx
0x1400013ff  inc     rax
0x140001402  cmp     [rdx+rax], bl
0x140001405  jnz     short loc_1400013FF
0x140001407  inc     eax
0x140001409  jmp     short loc_140001411
0x14000140b  mov     rdx, rdi
0x14000140e  mov     eax, r8d
0x140001411  mov     [rbp+70h+var_38], eax
0x140001414  mov     rax, [rbp+70h+arg_88]
0x14000141b  mov     [rbp+70h+var_50], rax
0x14000141f  mov     rax, [rbp+70h+arg_80]
0x140001426  mov     [rbp+70h+var_40], rdx
0x14000142a  mov     [rbp+70h+var_34], ebx
0x14000142d  mov     [rbp+70h+var_48], 4
0x140001435  mov     rdx, [rax]
0x140001438  test    rdx, rdx
0x14000143b  jz      short loc_140001452
0x14000143d  mov     rax, rcx
0x140001440  inc     rax
0x140001443  cmp     [rdx+rax*2], bx
0x140001447  jnz     short loc_140001440
0x140001449  lea     eax, ds:2[rax*2]
0x140001450  jmp     short loc_14000145C
0x140001452  lea     rdx, sourceString
0x140001459  mov     eax, r9d
0x14000145c  mov     [rbp+70h+var_58], eax
0x14000145f  mov     rax, [rbp+70h+arg_78]
0x140001466  mov     [rbp+70h+var_60], rdx
0x14000146a  mov     [rbp+70h+var_54], ebx
0x14000146d  mov     rdx, [rax]
0x140001470  test    rdx, rdx
0x140001473  jz      short loc_140001484
0x140001475  mov     rax, rcx
0x140001478  inc     rax
0x14000147b  cmp     [rdx+rax], bl
0x14000147e  jnz     short loc_140001478
0x140001480  inc     eax
0x140001482  jmp     short loc_14000148A
0x140001484  mov     rdx, rdi
0x140001487  mov     eax, r8d
0x14000148a  mov     [rbp+70h+var_68], eax
0x14000148d  mov     rax, [rbp+70h+arg_70]
0x140001494  mov     [rbp+70h+var_80], rax
0x140001498  mov     rax, [rbp+70h+arg_68]
0x14000149f  mov     [rbp+70h+var_70], rdx
0x1400014a3  mov     [rbp+70h+var_64], ebx
0x1400014a6  mov     [rbp+70h+var_78], 4
0x1400014ae  mov     rdx, [rax]
0x1400014b1  test    rdx, rdx
0x1400014b4  jz      short loc_1400014C5
0x1400014b6  mov     rax, rcx
0x1400014b9  inc     rax
0x1400014bc  cmp     [rdx+rax], bl
0x1400014bf  jnz     short loc_1400014B9
0x1400014c1  inc     eax
0x1400014c3  jmp     short loc_1400014CB
0x1400014c5  mov     rdx, rdi
0x1400014c8  mov     eax, r8d
0x1400014cb  mov     [rbp+70h+var_88], eax
0x1400014ce  mov     rax, [rbp+70h+arg_60]
0x1400014d5  mov     [rbp+70h+var_A0], rax
0x1400014d9  mov     rax, [rbp+70h+arg_58]
0x1400014e0  mov     [rbp+70h+var_90], rdx
0x1400014e4  mov     [rbp+70h+var_84], ebx
0x1400014e7  mov     [rbp+70h+var_98], 4
0x1400014ef  mov     rdx, [rax]
0x1400014f2  test    rdx, rdx
0x1400014f5  jz      short loc_14000150D
0x1400014f7  mov     rax, rcx
0x1400014fa  inc     rax
0x1400014fd  cmp     [rdx+rax*2], bx
0x140001501  jnz     short loc_1400014FA
0x140001503  lea     r9d, ds:2[rax*2]
0x14000150b  jmp     short loc_140001514
0x14000150d  lea     rdx, sourceString
0x140001514  mov     rax, [rbp+70h+arg_50]
0x14000151b  mov     [rbp+70h+var_C0], rax
0x14000151f  mov     rax, [rbp+70h+arg_48]
0x140001526  mov     [rbp+70h+var_B0], rdx
0x14000152a  mov     [rbp+70h+var_A8], r9d
0x14000152e  mov     [rbp+70h+var_A4], ebx
0x140001531  mov     rdx, [rax]
0x140001534  mov     [rbp+70h+var_B8], 4
0x14000153c  test    rdx, rdx
0x14000153f  jz      short loc_140001550
0x140001541  mov     rax, rcx
0x140001544  inc     rax
0x140001547  cmp     [rdx+rax], bl
0x14000154a  jnz     short loc_140001544
0x14000154c  inc     eax
0x14000154e  jmp     short loc_140001556
0x140001550  mov     rdx, rdi
0x140001553  mov     eax, r8d
0x140001556  mov     [rbp+70h+var_C8], eax
0x140001559  mov     rax, [rbp+70h+arg_40]
0x140001560  mov     [rbp+70h+var_E0], rax
0x140001564  mov     rax, [rbp+70h+arg_38]
0x14000156b  mov     [rbp+70h+var_D0], rdx
0x14000156f  mov     [rbp+70h+var_C4], ebx
0x140001572  mov     [rbp+70h+var_D8], 4
0x14000157a  mov     rdx, [rax]
0x14000157d  test    rdx, rdx
0x140001580  jz      short loc_140001590
0x140001582  inc     rcx
0x140001585  cmp     [rdx+rcx], bl
0x140001588  jnz     short loc_140001582
0x14000158a  lea     r8d, [rcx+1]
0x14000158e  jmp     short loc_140001593
0x140001590  mov     rdx, rdi
0x140001593  mov     rax, [rbp+70h+arg_30]
0x14000159a  xor     r9d, r9d
0x14000159d  mov     [rsp+170h+var_100], rax
0x1400015a2  mov     rcx, r10
0x1400015a5  mov     rax, [rbp+70h+arg_28]
0x1400015ac  mov     [rsp+170h+var_110], rax
0x1400015b1  mov     rax, [rbp+70h+arg_20]
0x1400015b8  mov     [rsp+170h+var_120], rax
0x1400015bd  lea     rax, [rsp+170h+var_140]
0x1400015c2  mov     [rbp+70h+var_F0], rdx
0x1400015c6  mov     rdx, r11
0x1400015c9  mov     [rbp+70h+var_E8], r8d
0x1400015cd  xor     r8d, r8d
0x1400015d0  mov     [rsp+170h+var_148], rax
0x1400015d5  mov     [rsp+170h+var_150], 12h
0x1400015dd  mov     [rbp+70h+var_E4], ebx
0x1400015e0  mov     [rsp+170h+var_F8], 4
0x1400015e9  mov     [rsp+170h+var_108], 8
0x1400015f2  mov     [rsp+170h+var_118], 8
0x1400015fb  call    _tlgWriteTransfer_EventWriteTransfer
0x140001600  mov     rcx, [rbp+70h+var_20]
0x140001604  xor     rcx, rsp; StackCookie
0x140001607  call    __security_check_cookie
0x14000160c  mov     rbx, [rsp+170h+arg_10]
0x140001614  add     rsp, 160h
0x14000161b  pop     rdi
0x14000161c  pop     rsi
0x14000161d  pop     rbp
0x14000161e  retn
```
