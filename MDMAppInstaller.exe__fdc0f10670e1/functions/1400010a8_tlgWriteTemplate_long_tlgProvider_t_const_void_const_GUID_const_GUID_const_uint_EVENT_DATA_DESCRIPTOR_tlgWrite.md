# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1400010a8`
- end: `0x140001353`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const OLECHAR **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const OLECHAR **, __int64, const unsigned __int16 **, const OLECHAR **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400078cc`

## callees

- `0x1400010a8`
- `0x1400017d8`
- `0x14001a8d0`

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
        const OLECHAR **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        const OLECHAR **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        const OLECHAR **a20)
{
  __int64 v22; // rcx
  int v23; // r9d
  const OLECHAR *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  const OLECHAR *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  const OLECHAR *v40; // rdx
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
  const OLECHAR *v64; // [rsp+C0h] [rbp-40h]
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
  const OLECHAR *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  const OLECHAR *v85; // [rsp+140h] [rbp+40h]
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
    v24 = &word_14001E5B4;
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
    v28 = &byte_14001E239;
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
    v31 = &word_14001E5B4;
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
    v34 = &byte_14001E239;
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
    v37 = &byte_14001E239;
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
    v40 = &word_14001E5B4;
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
    v42 = &byte_14001E239;
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
    v45 = &byte_14001E239;
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
0x1400010a8  mov     [rsp-8+arg_10], rbx
0x1400010ad  push    rbp
0x1400010ae  push    rsi
0x1400010af  push    rdi
0x1400010b0  lea     rbp, [rsp-60h]
0x1400010b5  sub     rsp, 160h
0x1400010bc  mov     rax, cs:__security_cookie
0x1400010c3  xor     rax, rsp
0x1400010c6  mov     [rbp+70h+var_20], rax
0x1400010ca  mov     rax, [rbp+70h+arg_98]
0x1400010d1  mov     r11, rdx
0x1400010d4  mov     r10, rcx
0x1400010d7  xor     ebx, ebx
0x1400010d9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400010dd  mov     r9d, 2
0x1400010e3  mov     rdx, [rax]
0x1400010e6  test    rdx, rdx
0x1400010e9  jz      short loc_140001100
0x1400010eb  mov     rax, rcx
0x1400010ee  inc     rax
0x1400010f1  cmp     [rdx+rax*2], bx
0x1400010f5  jnz     short loc_1400010EE
0x1400010f7  lea     eax, ds:2[rax*2]
0x1400010fe  jmp     short loc_14000110A
0x140001100  lea     rdx, word_14001E5B4
0x140001107  mov     eax, r9d
0x14000110a  mov     [rbp+70h+var_28], eax
0x14000110d  lea     rdi, byte_14001E239
0x140001114  mov     rax, [rbp+70h+arg_90]
0x14000111b  mov     r8d, 1
0x140001121  mov     [rbp+70h+var_30], rdx
0x140001125  mov     [rbp+70h+var_24], ebx
0x140001128  mov     rdx, [rax]
0x14000112b  test    rdx, rdx
0x14000112e  jz      short loc_14000113F
0x140001130  mov     rax, rcx
0x140001133  inc     rax
0x140001136  cmp     [rdx+rax], bl
0x140001139  jnz     short loc_140001133
0x14000113b  inc     eax
0x14000113d  jmp     short loc_140001145
0x14000113f  mov     rdx, rdi
0x140001142  mov     eax, r8d
0x140001145  mov     [rbp+70h+var_38], eax
0x140001148  mov     rax, [rbp+70h+arg_88]
0x14000114f  mov     [rbp+70h+var_50], rax
0x140001153  mov     rax, [rbp+70h+arg_80]
0x14000115a  mov     [rbp+70h+var_40], rdx
0x14000115e  mov     [rbp+70h+var_34], ebx
0x140001161  mov     [rbp+70h+var_48], 4
0x140001169  mov     rdx, [rax]
0x14000116c  test    rdx, rdx
0x14000116f  jz      short loc_140001186
0x140001171  mov     rax, rcx
0x140001174  inc     rax
0x140001177  cmp     [rdx+rax*2], bx
0x14000117b  jnz     short loc_140001174
0x14000117d  lea     eax, ds:2[rax*2]
0x140001184  jmp     short loc_140001190
0x140001186  lea     rdx, word_14001E5B4
0x14000118d  mov     eax, r9d
0x140001190  mov     [rbp+70h+var_58], eax
0x140001193  mov     rax, [rbp+70h+arg_78]
0x14000119a  mov     [rbp+70h+var_60], rdx
0x14000119e  mov     [rbp+70h+var_54], ebx
0x1400011a1  mov     rdx, [rax]
0x1400011a4  test    rdx, rdx
0x1400011a7  jz      short loc_1400011B8
0x1400011a9  mov     rax, rcx
0x1400011ac  inc     rax
0x1400011af  cmp     [rdx+rax], bl
0x1400011b2  jnz     short loc_1400011AC
0x1400011b4  inc     eax
0x1400011b6  jmp     short loc_1400011BE
0x1400011b8  mov     rdx, rdi
0x1400011bb  mov     eax, r8d
0x1400011be  mov     [rbp+70h+var_68], eax
0x1400011c1  mov     rax, [rbp+70h+arg_70]
0x1400011c8  mov     [rbp+70h+var_80], rax
0x1400011cc  mov     rax, [rbp+70h+arg_68]
0x1400011d3  mov     [rbp+70h+var_70], rdx
0x1400011d7  mov     [rbp+70h+var_64], ebx
0x1400011da  mov     [rbp+70h+var_78], 4
0x1400011e2  mov     rdx, [rax]
0x1400011e5  test    rdx, rdx
0x1400011e8  jz      short loc_1400011F9
0x1400011ea  mov     rax, rcx
0x1400011ed  inc     rax
0x1400011f0  cmp     [rdx+rax], bl
0x1400011f3  jnz     short loc_1400011ED
0x1400011f5  inc     eax
0x1400011f7  jmp     short loc_1400011FF
0x1400011f9  mov     rdx, rdi
0x1400011fc  mov     eax, r8d
0x1400011ff  mov     [rbp+70h+var_88], eax
0x140001202  mov     rax, [rbp+70h+arg_60]
0x140001209  mov     [rbp+70h+var_A0], rax
0x14000120d  mov     rax, [rbp+70h+arg_58]
0x140001214  mov     [rbp+70h+var_90], rdx
0x140001218  mov     [rbp+70h+var_84], ebx
0x14000121b  mov     [rbp+70h+var_98], 4
0x140001223  mov     rdx, [rax]
0x140001226  test    rdx, rdx
0x140001229  jz      short loc_140001241
0x14000122b  mov     rax, rcx
0x14000122e  inc     rax
0x140001231  cmp     [rdx+rax*2], bx
0x140001235  jnz     short loc_14000122E
0x140001237  lea     r9d, ds:2[rax*2]
0x14000123f  jmp     short loc_140001248
0x140001241  lea     rdx, word_14001E5B4
0x140001248  mov     rax, [rbp+70h+arg_50]
0x14000124f  mov     [rbp+70h+var_C0], rax
0x140001253  mov     rax, [rbp+70h+arg_48]
0x14000125a  mov     [rbp+70h+var_B0], rdx
0x14000125e  mov     [rbp+70h+var_A8], r9d
0x140001262  mov     [rbp+70h+var_A4], ebx
0x140001265  mov     rdx, [rax]
0x140001268  mov     [rbp+70h+var_B8], 4
0x140001270  test    rdx, rdx
0x140001273  jz      short loc_140001284
0x140001275  mov     rax, rcx
0x140001278  inc     rax
0x14000127b  cmp     [rdx+rax], bl
0x14000127e  jnz     short loc_140001278
0x140001280  inc     eax
0x140001282  jmp     short loc_14000128A
0x140001284  mov     rdx, rdi
0x140001287  mov     eax, r8d
0x14000128a  mov     [rbp+70h+var_C8], eax
0x14000128d  mov     rax, [rbp+70h+arg_40]
0x140001294  mov     [rbp+70h+var_E0], rax
0x140001298  mov     rax, [rbp+70h+arg_38]
0x14000129f  mov     [rbp+70h+var_D0], rdx
0x1400012a3  mov     [rbp+70h+var_C4], ebx
0x1400012a6  mov     [rbp+70h+var_D8], 4
0x1400012ae  mov     rdx, [rax]
0x1400012b1  test    rdx, rdx
0x1400012b4  jz      short loc_1400012C4
0x1400012b6  inc     rcx
0x1400012b9  cmp     [rdx+rcx], bl
0x1400012bc  jnz     short loc_1400012B6
0x1400012be  lea     r8d, [rcx+1]
0x1400012c2  jmp     short loc_1400012C7
0x1400012c4  mov     rdx, rdi
0x1400012c7  mov     rax, [rbp+70h+arg_30]
0x1400012ce  xor     r9d, r9d
0x1400012d1  mov     [rsp+170h+var_100], rax
0x1400012d6  mov     rcx, r10
0x1400012d9  mov     rax, [rbp+70h+arg_28]
0x1400012e0  mov     [rsp+170h+var_110], rax
0x1400012e5  mov     rax, [rbp+70h+arg_20]
0x1400012ec  mov     [rsp+170h+var_120], rax
0x1400012f1  lea     rax, [rsp+170h+var_140]
0x1400012f6  mov     [rbp+70h+var_F0], rdx
0x1400012fa  mov     rdx, r11
0x1400012fd  mov     [rbp+70h+var_E8], r8d
0x140001301  xor     r8d, r8d
0x140001304  mov     [rsp+170h+var_148], rax
0x140001309  mov     [rsp+170h+var_150], 12h
0x140001311  mov     [rbp+70h+var_E4], ebx
0x140001314  mov     [rsp+170h+var_F8], 4
0x14000131d  mov     [rsp+170h+var_108], 8
0x140001326  mov     [rsp+170h+var_118], 8
0x14000132f  call    _tlgWriteTransfer_EventWriteTransfer
0x140001334  mov     rcx, [rbp+70h+var_20]
0x140001338  xor     rcx, rsp; StackCookie
0x14000133b  call    __security_check_cookie
0x140001340  mov     rbx, [rsp+170h+arg_10]
0x140001348  add     rsp, 160h
0x14000134f  pop     rdi
0x140001350  pop     rsi
0x140001351  pop     rbp
0x140001352  retn
```
