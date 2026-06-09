# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000120c`
- end: `0x1800014de`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$01@@U1@U?$_tlgWrapSz@D@@U2@U3@U3@U3@U2@U3@U3@U3@U3@U1@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$01@@3AEBU?$_tlgWrapSz@D@@455545555353@Z`
- size: `722`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **, const unsigned __int16 **, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009040`

## callees

- `0x18000120c`
- `0x180001bdc`
- `0x180002bc0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        const unsigned __int16 **a10,
        __int64 a11,
        const unsigned __int16 **a12,
        const unsigned __int16 **a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        const unsigned __int16 **a17,
        const unsigned __int16 **a18,
        const unsigned __int16 **a19,
        __int64 a20,
        const unsigned __int16 **a21,
        __int64 a22)
{
  __int64 v23; // rcx
  int v25; // edx
  const unsigned __int16 *v26; // r8
  __int64 v27; // rax
  int v28; // eax
  const unsigned __int16 *v29; // r8
  __int64 v30; // rax
  int v31; // eax
  const unsigned __int16 *v32; // r8
  __int64 v33; // rax
  int v34; // eax
  const unsigned __int16 *v35; // r8
  __int64 v36; // rax
  int v37; // eax
  const unsigned __int16 *v38; // r8
  __int64 v39; // rax
  int v40; // eax
  const unsigned __int16 *v41; // r8
  __int64 v42; // rax
  int v43; // eax
  const unsigned __int16 *v44; // r8
  __int64 v45; // rax
  int v46; // eax
  const unsigned __int16 *v47; // r8
  __int64 v48; // rax
  int v49; // eax
  const unsigned __int16 *v50; // r8
  _BYTE v52[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B0h]
  __int64 v54; // [rsp+58h] [rbp-A8h]
  __int64 v55; // [rsp+60h] [rbp-A0h]
  __int64 v56; // [rsp+68h] [rbp-98h]
  __int64 v57; // [rsp+70h] [rbp-90h]
  __int64 v58; // [rsp+78h] [rbp-88h]
  __int64 v59; // [rsp+80h] [rbp-80h]
  __int64 v60; // [rsp+88h] [rbp-78h]
  __int64 v61; // [rsp+90h] [rbp-70h]
  __int64 v62; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v63; // [rsp+A0h] [rbp-60h]
  int v64; // [rsp+A8h] [rbp-58h]
  int v65; // [rsp+ACh] [rbp-54h]
  __int64 v66; // [rsp+B0h] [rbp-50h]
  __int64 v67; // [rsp+B8h] [rbp-48h]
  const unsigned __int16 *v68; // [rsp+C0h] [rbp-40h]
  int v69; // [rsp+C8h] [rbp-38h]
  int v70; // [rsp+CCh] [rbp-34h]
  const unsigned __int16 *v71; // [rsp+D0h] [rbp-30h]
  int v72; // [rsp+D8h] [rbp-28h]
  int v73; // [rsp+DCh] [rbp-24h]
  const unsigned __int16 *v74; // [rsp+E0h] [rbp-20h]
  int v75; // [rsp+E8h] [rbp-18h]
  int v76; // [rsp+ECh] [rbp-14h]
  __int64 v77; // [rsp+F0h] [rbp-10h]
  __int64 v78; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v79; // [rsp+100h] [rbp+0h]
  int v80; // [rsp+108h] [rbp+8h]
  int v81; // [rsp+10Ch] [rbp+Ch]
  const unsigned __int16 *v82; // [rsp+110h] [rbp+10h]
  int v83; // [rsp+118h] [rbp+18h]
  int v84; // [rsp+11Ch] [rbp+1Ch]
  const unsigned __int16 *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  const unsigned __int16 *v88; // [rsp+130h] [rbp+30h]
  int v89; // [rsp+138h] [rbp+38h]
  int v90; // [rsp+13Ch] [rbp+3Ch]
  __int64 v91; // [rsp+140h] [rbp+40h]
  __int64 v92; // [rsp+148h] [rbp+48h]
  const unsigned __int16 *v93; // [rsp+150h] [rbp+50h]
  int v94; // [rsp+158h] [rbp+58h]
  int v95; // [rsp+15Ch] [rbp+5Ch]
  __int64 v96; // [rsp+160h] [rbp+60h]
  __int64 v97; // [rsp+168h] [rbp+68h]

  v96 = a22;
  v23 = -1;
  v97 = 4;
  v25 = 1;
  v26 = *a21;
  if ( *a21 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *((_BYTE *)v26 + v27) );
    v28 = v27 + 1;
  }
  else
  {
    v26 = &byte_180013B63;
    v28 = 1;
  }
  v94 = v28;
  v91 = a20;
  v93 = v26;
  v95 = 0;
  v92 = 4;
  v29 = *a19;
  if ( *a19 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *((_BYTE *)v29 + v30) );
    v31 = v30 + 1;
  }
  else
  {
    v29 = &byte_180013B63;
    v31 = 1;
  }
  v89 = v31;
  v88 = v29;
  v90 = 0;
  v32 = *a18;
  if ( *a18 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *((_BYTE *)v32 + v33) );
    v34 = v33 + 1;
  }
  else
  {
    v32 = &byte_180013B63;
    v34 = 1;
  }
  v86 = v34;
  v85 = v32;
  v87 = 0;
  v35 = *a17;
  if ( *a17 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_BYTE *)v35 + v36) );
    v37 = v36 + 1;
  }
  else
  {
    v35 = &byte_180013B63;
    v37 = 1;
  }
  v83 = v37;
  v82 = v35;
  v84 = 0;
  v38 = *a16;
  if ( *a16 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *((_BYTE *)v38 + v39) );
    v40 = v39 + 1;
  }
  else
  {
    v38 = &byte_180013B63;
    v40 = 1;
  }
  v80 = v40;
  v77 = a15;
  v79 = v38;
  v81 = 0;
  v78 = 2;
  v41 = *a14;
  if ( *a14 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *((_BYTE *)v41 + v42) );
    v43 = v42 + 1;
  }
  else
  {
    v41 = &byte_180013B63;
    v43 = 1;
  }
  v75 = v43;
  v74 = v41;
  v76 = 0;
  v44 = *a13;
  if ( *a13 )
  {
    v45 = -1;
    do
      ++v45;
    while ( *((_BYTE *)v44 + v45) );
    v46 = v45 + 1;
  }
  else
  {
    v44 = &byte_180013B63;
    v46 = 1;
  }
  v72 = v46;
  v71 = v44;
  v73 = 0;
  v47 = *a12;
  if ( *a12 )
  {
    v48 = -1;
    do
      ++v48;
    while ( *((_BYTE *)v47 + v48) );
    v49 = v48 + 1;
  }
  else
  {
    v47 = &byte_180013B63;
    v49 = 1;
  }
  v69 = v49;
  v66 = a11;
  v68 = v47;
  v70 = 0;
  v67 = 2;
  v50 = *a10;
  if ( *a10 )
  {
    do
      ++v23;
    while ( *((_BYTE *)v50 + v23) );
    v25 = v23 + 1;
  }
  else
  {
    v50 = &byte_180013B63;
  }
  v61 = a9;
  v59 = a8;
  v57 = a7;
  v55 = a6;
  v53 = a5;
  v63 = v50;
  v64 = v25;
  v65 = 0;
  v62 = 4;
  v60 = 2;
  v58 = 4;
  v56 = 4;
  v54 = 4;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 20, v52);
}

```

## disassembly

```asm
0x18000120c  mov     [rsp-8+arg_10], rbx
0x180001211  mov     [rsp-8+arg_18], rsi
0x180001216  push    rbp
0x180001217  lea     rbp, [rsp-80h]
0x18000121c  sub     rsp, 180h
0x180001223  mov     rax, cs:__security_cookie
0x18000122a  xor     rax, rsp
0x18000122d  mov     [rbp+80h+var_10], rax
0x180001231  mov     rax, [rbp+80h+arg_A8]
0x180001238  lea     rbx, byte_180013B63
0x18000123f  xor     r9d, r9d
0x180001242  mov     [rbp+80h+var_20], rax
0x180001246  mov     rax, [rbp+80h+arg_A0]
0x18000124d  mov     r10, rcx
0x180001250  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001254  mov     [rbp+80h+var_18], 4
0x18000125c  mov     r11, rdx
0x18000125f  lea     edx, [r9+1]
0x180001263  mov     r8, [rax]
0x180001266  test    r8, r8
0x180001269  jz      short loc_18000127B
0x18000126b  mov     rax, rcx
0x18000126e  inc     rax
0x180001271  cmp     [r8+rax], r9b
0x180001275  jnz     short loc_18000126E
0x180001277  inc     eax
0x180001279  jmp     short loc_180001280
0x18000127b  mov     r8, rbx
0x18000127e  mov     eax, edx
0x180001280  mov     [rbp+80h+var_28], eax
0x180001283  mov     rax, [rbp+80h+arg_98]
0x18000128a  mov     [rbp+80h+var_40], rax
0x18000128e  mov     rax, [rbp+80h+arg_90]
0x180001295  mov     [rbp+80h+var_30], r8
0x180001299  mov     [rbp+80h+var_24], r9d
0x18000129d  mov     [rbp+80h+var_38], 4
0x1800012a5  mov     r8, [rax]
0x1800012a8  test    r8, r8
0x1800012ab  jz      short loc_1800012BD
0x1800012ad  mov     rax, rcx
0x1800012b0  inc     rax
0x1800012b3  cmp     [r8+rax], r9b
0x1800012b7  jnz     short loc_1800012B0
0x1800012b9  inc     eax
0x1800012bb  jmp     short loc_1800012C2
0x1800012bd  mov     r8, rbx
0x1800012c0  mov     eax, edx
0x1800012c2  mov     [rbp+80h+var_48], eax
0x1800012c5  mov     rax, [rbp+80h+arg_88]
0x1800012cc  mov     [rbp+80h+var_50], r8
0x1800012d0  mov     [rbp+80h+var_44], r9d
0x1800012d4  mov     r8, [rax]
0x1800012d7  test    r8, r8
0x1800012da  jz      short loc_1800012EC
0x1800012dc  mov     rax, rcx
0x1800012df  inc     rax
0x1800012e2  cmp     [r8+rax], r9b
0x1800012e6  jnz     short loc_1800012DF
0x1800012e8  inc     eax
0x1800012ea  jmp     short loc_1800012F1
0x1800012ec  mov     r8, rbx
0x1800012ef  mov     eax, edx
0x1800012f1  mov     [rbp+80h+var_58], eax
0x1800012f4  mov     rax, [rbp+80h+arg_80]
0x1800012fb  mov     [rbp+80h+var_60], r8
0x1800012ff  mov     [rbp+80h+var_54], r9d
0x180001303  mov     r8, [rax]
0x180001306  test    r8, r8
0x180001309  jz      short loc_18000131B
0x18000130b  mov     rax, rcx
0x18000130e  inc     rax
0x180001311  cmp     [r8+rax], r9b
0x180001315  jnz     short loc_18000130E
0x180001317  inc     eax
0x180001319  jmp     short loc_180001320
0x18000131b  mov     r8, rbx
0x18000131e  mov     eax, edx
0x180001320  mov     [rbp+80h+var_68], eax
0x180001323  mov     rax, [rbp+80h+arg_78]
0x18000132a  mov     [rbp+80h+var_70], r8
0x18000132e  mov     [rbp+80h+var_64], r9d
0x180001332  mov     r8, [rax]
0x180001335  test    r8, r8
0x180001338  jz      short loc_18000134A
0x18000133a  mov     rax, rcx
0x18000133d  inc     rax
0x180001340  cmp     [r8+rax], r9b
0x180001344  jnz     short loc_18000133D
0x180001346  inc     eax
0x180001348  jmp     short loc_18000134F
0x18000134a  mov     r8, rbx
0x18000134d  mov     eax, edx
0x18000134f  mov     [rbp+80h+var_78], eax
0x180001352  mov     rax, [rbp+80h+arg_70]
0x180001359  mov     [rbp+80h+var_90], rax
0x18000135d  mov     rax, [rbp+80h+arg_68]
0x180001364  mov     [rbp+80h+var_80], r8
0x180001368  mov     [rbp+80h+var_74], r9d
0x18000136c  mov     [rbp+80h+var_88], 2
0x180001374  mov     r8, [rax]
0x180001377  test    r8, r8
0x18000137a  jz      short loc_18000138C
0x18000137c  mov     rax, rcx
0x18000137f  inc     rax
0x180001382  cmp     [r8+rax], r9b
0x180001386  jnz     short loc_18000137F
0x180001388  inc     eax
0x18000138a  jmp     short loc_180001391
0x18000138c  mov     r8, rbx
0x18000138f  mov     eax, edx
0x180001391  mov     [rbp+80h+var_98], eax
0x180001394  mov     rax, [rbp+80h+arg_60]
0x18000139b  mov     [rbp+80h+var_A0], r8
0x18000139f  mov     [rbp+80h+var_94], r9d
0x1800013a3  mov     r8, [rax]
0x1800013a6  test    r8, r8
0x1800013a9  jz      short loc_1800013BB
0x1800013ab  mov     rax, rcx
0x1800013ae  inc     rax
0x1800013b1  cmp     [r8+rax], r9b
0x1800013b5  jnz     short loc_1800013AE
0x1800013b7  inc     eax
0x1800013b9  jmp     short loc_1800013C0
0x1800013bb  mov     r8, rbx
0x1800013be  mov     eax, edx
0x1800013c0  mov     [rbp+80h+var_A8], eax
0x1800013c3  mov     rax, [rbp+80h+arg_58]
0x1800013ca  mov     [rbp+80h+var_B0], r8
0x1800013ce  mov     [rbp+80h+var_A4], r9d
0x1800013d2  mov     r8, [rax]
0x1800013d5  test    r8, r8
0x1800013d8  jz      short loc_1800013EA
0x1800013da  mov     rax, rcx
0x1800013dd  inc     rax
0x1800013e0  cmp     [r8+rax], r9b
0x1800013e4  jnz     short loc_1800013DD
0x1800013e6  inc     eax
0x1800013e8  jmp     short loc_1800013EF
0x1800013ea  mov     r8, rbx
0x1800013ed  mov     eax, edx
0x1800013ef  mov     [rbp+80h+var_B8], eax
0x1800013f2  mov     rax, [rbp+80h+arg_50]
0x1800013f9  mov     [rbp+80h+var_D0], rax
0x1800013fd  mov     rax, [rbp+80h+arg_48]
0x180001404  mov     [rbp+80h+var_C0], r8
0x180001408  mov     [rbp+80h+var_B4], r9d
0x18000140c  mov     [rbp+80h+var_C8], 2
0x180001414  mov     r8, [rax]
0x180001417  test    r8, r8
0x18000141a  jz      short loc_18000142A
0x18000141c  inc     rcx
0x18000141f  cmp     [r8+rcx], r9b
0x180001423  jnz     short loc_18000141C
0x180001425  lea     edx, [rcx+1]
0x180001428  jmp     short loc_18000142D
0x18000142a  mov     r8, rbx
0x18000142d  mov     rax, [rbp+80h+arg_40]
0x180001434  mov     rcx, r10
0x180001437  mov     [rbp+80h+var_F0], rax
0x18000143b  mov     rax, [rbp+80h+arg_38]
0x180001442  mov     [rbp+80h+var_100], rax
0x180001446  mov     rax, [rbp+80h+arg_30]
0x18000144d  mov     [rsp+180h+var_110], rax
0x180001452  mov     rax, [rbp+80h+arg_28]
0x180001459  mov     [rsp+180h+var_120], rax
0x18000145e  mov     rax, [rbp+80h+arg_20]
0x180001465  mov     [rsp+180h+var_130], rax
0x18000146a  lea     rax, [rsp+180h+var_150]
0x18000146f  mov     [rbp+80h+var_E0], r8
0x180001473  xor     r8d, r8d
0x180001476  mov     [rbp+80h+var_D8], edx
0x180001479  mov     rdx, r11
0x18000147c  mov     [rsp+180h+var_158], rax
0x180001481  mov     [rsp+180h+var_160], 14h
0x180001489  mov     [rbp+80h+var_D4], r9d
0x18000148d  mov     [rbp+80h+var_E8], 4
0x180001495  mov     [rbp+80h+var_F8], 2
0x18000149d  mov     [rsp+180h+var_108], 4
0x1800014a6  mov     [rsp+180h+var_118], 4
0x1800014af  mov     [rsp+180h+var_128], 4
0x1800014b8  call    _tlgWriteTransfer_EventWriteTransfer
0x1800014bd  mov     rcx, [rbp+80h+var_10]
0x1800014c1  xor     rcx, rsp; StackCookie
0x1800014c4  call    __security_check_cookie
0x1800014c9  lea     r11, [rsp+180h+var_s0]
0x1800014d1  mov     rbx, [r11+20h]
0x1800014d5  mov     rsi, [r11+28h]
0x1800014d9  mov     rsp, r11
0x1800014dc  pop     rbp
0x1800014dd  retn
```
