# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x18000221c`
- end: `0x1800024b7`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `667`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, __int64 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64 **, __int64, const unsigned __int16 **, __int64 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e590`

## callees

- `0x180001bdc`
- `0x18000221c`
- `0x180002bc0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
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
        __int64 **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        __int64 **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        __int64 **a19)
{
  __int64 v21; // rdx
  int v23; // r9d
  __int64 *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  __int64 *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  __int64 *v40; // rcx
  __int64 v41; // rax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rcx
  _BYTE v47[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v52; // [rsp+70h] [rbp-90h]
  int v53; // [rsp+78h] [rbp-88h]
  int v54; // [rsp+7Ch] [rbp-84h]
  __int64 v55; // [rsp+80h] [rbp-80h]
  __int64 v56; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v57; // [rsp+90h] [rbp-70h]
  int v58; // [rsp+98h] [rbp-68h]
  int v59; // [rsp+9Ch] [rbp-64h]
  __int64 v60; // [rsp+A0h] [rbp-60h]
  __int64 v61; // [rsp+A8h] [rbp-58h]
  __int64 *v62; // [rsp+B0h] [rbp-50h]
  int v63; // [rsp+B8h] [rbp-48h]
  int v64; // [rsp+BCh] [rbp-44h]
  __int64 v65; // [rsp+C0h] [rbp-40h]
  __int64 v66; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v67; // [rsp+D0h] [rbp-30h]
  int v68; // [rsp+D8h] [rbp-28h]
  int v69; // [rsp+DCh] [rbp-24h]
  __int64 v70; // [rsp+E0h] [rbp-20h]
  __int64 v71; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v72; // [rsp+F0h] [rbp-10h]
  int v73; // [rsp+F8h] [rbp-8h]
  int v74; // [rsp+FCh] [rbp-4h]
  __int64 *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  __int64 v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v80; // [rsp+120h] [rbp+20h]
  int v81; // [rsp+128h] [rbp+28h]
  int v82; // [rsp+12Ch] [rbp+2Ch]
  __int64 *v83; // [rsp+130h] [rbp+30h]
  int v84; // [rsp+138h] [rbp+38h]
  int v85; // [rsp+13Ch] [rbp+3Ch]

  v21 = -1;
  v23 = 2;
  v24 = *a19;
  if ( *a19 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *((_WORD *)v24 + v25) );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &qword_1800142D0;
    v26 = 2;
  }
  v84 = v26;
  v27 = 1;
  v83 = v24;
  v85 = 0;
  v28 = *a18;
  if ( *a18 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_BYTE *)v28 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &byte_180013B63;
    v30 = 1;
  }
  v81 = v30;
  v78 = a17;
  v80 = v28;
  v82 = 0;
  v79 = 4;
  v31 = *a16;
  if ( *a16 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *((_WORD *)v31 + v32) );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &qword_1800142D0;
    v33 = 2;
  }
  v76 = v33;
  v75 = v31;
  v77 = 0;
  v34 = *a15;
  if ( *a15 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &byte_180013B63;
    v36 = 1;
  }
  v73 = v36;
  v70 = a14;
  v72 = v34;
  v74 = 0;
  v71 = 4;
  v37 = *a13;
  if ( *a13 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_BYTE *)v37 + v38) );
    v39 = v38 + 1;
  }
  else
  {
    v37 = &byte_180013B63;
    v39 = 1;
  }
  v68 = v39;
  v65 = a12;
  v67 = v37;
  v69 = 0;
  v66 = 4;
  v40 = *a11;
  if ( *a11 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_WORD *)v40 + v41) );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = &qword_1800142D0;
  }
  v60 = a10;
  v62 = v40;
  v63 = v23;
  v64 = 0;
  v42 = *a9;
  v61 = 4;
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
    v42 = &byte_180013B63;
    v44 = 1;
  }
  v58 = v44;
  v55 = a8;
  v57 = v42;
  v59 = 0;
  v56 = 4;
  v45 = *a7;
  if ( *a7 )
  {
    do
      ++v21;
    while ( *((_BYTE *)v45 + v21) );
    v27 = v21 + 1;
  }
  else
  {
    v45 = &byte_180013B63;
  }
  v50 = a6;
  v48 = a5;
  v52 = v45;
  v53 = v27;
  v54 = 0;
  v51 = 4;
  v49 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 17, v47);
}

```

## disassembly

```asm
0x18000221c  push    rbp
0x18000221e  push    rbx
0x18000221f  push    rsi
0x180002220  push    rdi
0x180002221  push    r14
0x180002223  lea     rbp, [rsp-50h]
0x180002228  sub     rsp, 150h
0x18000222f  mov     rax, cs:__security_cookie
0x180002236  xor     rax, rsp
0x180002239  mov     [rbp+70h+var_30], rax
0x18000223d  mov     rax, [rbp+70h+arg_90]
0x180002244  mov     r11, rdx
0x180002247  mov     r10, rcx
0x18000224a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000224e  xor     edi, edi
0x180002250  mov     rbx, r8
0x180002253  mov     r9d, 2
0x180002259  mov     rcx, [rax]
0x18000225c  test    rcx, rcx
0x18000225f  jz      short loc_180002276
0x180002261  mov     rax, rdx
0x180002264  inc     rax
0x180002267  cmp     [rcx+rax*2], di
0x18000226b  jnz     short loc_180002264
0x18000226d  lea     eax, ds:2[rax*2]
0x180002274  jmp     short loc_180002280
0x180002276  lea     rcx, qword_1800142D0
0x18000227d  mov     eax, r9d
0x180002280  mov     [rbp+70h+var_38], eax
0x180002283  lea     rsi, byte_180013B63
0x18000228a  mov     rax, [rbp+70h+arg_88]
0x180002291  mov     r8d, 1
0x180002297  mov     [rbp+70h+var_40], rcx
0x18000229b  mov     [rbp+70h+var_34], edi
0x18000229e  mov     rcx, [rax]
0x1800022a1  test    rcx, rcx
0x1800022a4  jz      short loc_1800022B6
0x1800022a6  mov     rax, rdx
0x1800022a9  inc     rax
0x1800022ac  cmp     [rcx+rax], dil
0x1800022b0  jnz     short loc_1800022A9
0x1800022b2  inc     eax
0x1800022b4  jmp     short loc_1800022BC
0x1800022b6  mov     rcx, rsi
0x1800022b9  mov     eax, r8d
0x1800022bc  mov     [rbp+70h+var_48], eax
0x1800022bf  mov     rax, [rbp+70h+arg_80]
0x1800022c6  mov     [rbp+70h+var_60], rax
0x1800022ca  mov     rax, [rbp+70h+arg_78]
0x1800022d1  mov     [rbp+70h+var_50], rcx
0x1800022d5  mov     [rbp+70h+var_44], edi
0x1800022d8  mov     [rbp+70h+var_58], 4
0x1800022e0  mov     rcx, [rax]
0x1800022e3  test    rcx, rcx
0x1800022e6  jz      short loc_1800022FD
0x1800022e8  mov     rax, rdx
0x1800022eb  inc     rax
0x1800022ee  cmp     [rcx+rax*2], di
0x1800022f2  jnz     short loc_1800022EB
0x1800022f4  lea     eax, ds:2[rax*2]
0x1800022fb  jmp     short loc_180002307
0x1800022fd  lea     rcx, qword_1800142D0
0x180002304  mov     eax, r9d
0x180002307  mov     [rbp+70h+var_68], eax
0x18000230a  mov     rax, [rbp+70h+arg_70]
0x180002311  mov     [rbp+70h+var_70], rcx
0x180002315  mov     [rbp+70h+var_64], edi
0x180002318  mov     rcx, [rax]
0x18000231b  test    rcx, rcx
0x18000231e  jz      short loc_180002330
0x180002320  mov     rax, rdx
0x180002323  inc     rax
0x180002326  cmp     [rcx+rax], dil
0x18000232a  jnz     short loc_180002323
0x18000232c  inc     eax
0x18000232e  jmp     short loc_180002336
0x180002330  mov     rcx, rsi
0x180002333  mov     eax, r8d
0x180002336  mov     [rbp+70h+var_78], eax
0x180002339  mov     rax, [rbp+70h+arg_68]
0x180002340  mov     [rbp+70h+var_90], rax
0x180002344  mov     rax, [rbp+70h+arg_60]
0x18000234b  mov     [rbp+70h+var_80], rcx
0x18000234f  mov     [rbp+70h+var_74], edi
0x180002352  mov     [rbp+70h+var_88], 4
0x18000235a  mov     rcx, [rax]
0x18000235d  test    rcx, rcx
0x180002360  jz      short loc_180002372
0x180002362  mov     rax, rdx
0x180002365  inc     rax
0x180002368  cmp     [rcx+rax], dil
0x18000236c  jnz     short loc_180002365
0x18000236e  inc     eax
0x180002370  jmp     short loc_180002378
0x180002372  mov     rcx, rsi
0x180002375  mov     eax, r8d
0x180002378  mov     [rbp+70h+var_98], eax
0x18000237b  mov     rax, [rbp+70h+arg_58]
0x180002382  mov     [rbp+70h+var_B0], rax
0x180002386  mov     rax, [rbp+70h+arg_50]
0x18000238d  mov     [rbp+70h+var_A0], rcx
0x180002391  mov     [rbp+70h+var_94], edi
0x180002394  mov     [rbp+70h+var_A8], 4
0x18000239c  mov     rcx, [rax]
0x18000239f  test    rcx, rcx
0x1800023a2  jz      short loc_1800023BA
0x1800023a4  mov     rax, rdx
0x1800023a7  inc     rax
0x1800023aa  cmp     [rcx+rax*2], di
0x1800023ae  jnz     short loc_1800023A7
0x1800023b0  lea     r9d, ds:2[rax*2]
0x1800023b8  jmp     short loc_1800023C1
0x1800023ba  lea     rcx, qword_1800142D0
0x1800023c1  mov     rax, [rbp+70h+arg_48]
0x1800023c8  mov     [rbp+70h+var_D0], rax
0x1800023cc  mov     rax, [rbp+70h+arg_40]
0x1800023d3  mov     [rbp+70h+var_C0], rcx
0x1800023d7  mov     [rbp+70h+var_B8], r9d
0x1800023db  mov     [rbp+70h+var_B4], edi
0x1800023de  mov     rcx, [rax]
0x1800023e1  mov     [rbp+70h+var_C8], 4
0x1800023e9  test    rcx, rcx
0x1800023ec  jz      short loc_1800023FE
0x1800023ee  mov     rax, rdx
0x1800023f1  inc     rax
0x1800023f4  cmp     [rcx+rax], dil
0x1800023f8  jnz     short loc_1800023F1
0x1800023fa  inc     eax
0x1800023fc  jmp     short loc_180002404
0x1800023fe  mov     rcx, rsi
0x180002401  mov     eax, r8d
0x180002404  mov     [rbp+70h+var_D8], eax
0x180002407  mov     rax, [rbp+70h+arg_38]
0x18000240e  mov     [rbp+70h+var_F0], rax
0x180002412  mov     rax, [rbp+70h+arg_30]
0x180002419  mov     [rbp+70h+var_E0], rcx
0x18000241d  mov     [rbp+70h+var_D4], edi
0x180002420  mov     [rbp+70h+var_E8], 4
0x180002428  mov     rcx, [rax]
0x18000242b  test    rcx, rcx
0x18000242e  jz      short loc_18000243F
0x180002430  inc     rdx
0x180002433  cmp     [rcx+rdx], dil
0x180002437  jnz     short loc_180002430
0x180002439  lea     r8d, [rdx+1]
0x18000243d  jmp     short loc_180002442
0x18000243f  mov     rcx, rsi
0x180002442  mov     rax, [rbp+70h+arg_28]
0x180002449  xor     r9d, r9d
0x18000244c  mov     [rsp+170h+var_110], rax
0x180002451  mov     rdx, r11
0x180002454  mov     rax, [rbp+70h+arg_20]
0x18000245b  mov     [rsp+170h+var_120], rax
0x180002460  lea     rax, [rsp+170h+var_140]
0x180002465  mov     [rsp+170h+var_100], rcx
0x18000246a  mov     rcx, r10
0x18000246d  mov     [rsp+170h+var_F8], r8d
0x180002472  mov     r8, rbx
0x180002475  mov     [rsp+170h+var_148], rax
0x18000247a  mov     [rsp+170h+var_150], 11h
0x180002482  mov     [rsp+170h+var_F4], edi
0x180002486  mov     [rsp+170h+var_108], 4
0x18000248f  mov     [rsp+170h+var_118], 8
0x180002498  call    _tlgWriteTransfer_EventWriteTransfer
0x18000249d  mov     rcx, [rbp+70h+var_30]
0x1800024a1  xor     rcx, rsp; StackCookie
0x1800024a4  call    __security_check_cookie
0x1800024a9  add     rsp, 150h
0x1800024b0  pop     r14
0x1800024b2  pop     rdi
0x1800024b3  pop     rsi
0x1800024b4  pop     rbx
0x1800024b5  pop     rbp
0x1800024b6  retn
```
