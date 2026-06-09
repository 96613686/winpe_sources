# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001e94`
- end: `0x14000212f`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `667`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a070`

## callees

- `0x140001e94`
- `0x1400025b8`
- `0x1400033b0`

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
        const unsigned __int16 **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        const unsigned __int16 **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        const unsigned __int16 **a19)
{
  __int64 v21; // rdx
  int v23; // r9d
  const unsigned __int16 *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  const unsigned __int16 *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rcx
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
  const unsigned __int16 *v62; // [rsp+B0h] [rbp-50h]
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
  const unsigned __int16 *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  __int64 v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v80; // [rsp+120h] [rbp+20h]
  int v81; // [rsp+128h] [rbp+28h]
  int v82; // [rsp+12Ch] [rbp+2Ch]
  const unsigned __int16 *v83; // [rsp+130h] [rbp+30h]
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
    while ( v24[v25] );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &qword_140010DA8;
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
    v28 = &dword_140010DA4;
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
    while ( v31[v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &qword_140010DA8;
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
    v34 = &dword_140010DA4;
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
    v37 = &dword_140010DA4;
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
    while ( v40[v41] );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = &qword_140010DA8;
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
    v42 = &dword_140010DA4;
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
    v45 = &dword_140010DA4;
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
0x140001e94  push    rbp
0x140001e96  push    rbx
0x140001e97  push    rsi
0x140001e98  push    rdi
0x140001e99  push    r14
0x140001e9b  lea     rbp, [rsp-50h]
0x140001ea0  sub     rsp, 150h
0x140001ea7  mov     rax, cs:__security_cookie
0x140001eae  xor     rax, rsp
0x140001eb1  mov     [rbp+70h+var_30], rax
0x140001eb5  mov     rax, [rbp+70h+arg_90]
0x140001ebc  mov     r11, rdx
0x140001ebf  mov     r10, rcx
0x140001ec2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140001ec6  xor     edi, edi
0x140001ec8  mov     rbx, r8
0x140001ecb  mov     r9d, 2
0x140001ed1  mov     rcx, [rax]
0x140001ed4  test    rcx, rcx
0x140001ed7  jz      short loc_140001EEE
0x140001ed9  mov     rax, rdx
0x140001edc  inc     rax
0x140001edf  cmp     [rcx+rax*2], di
0x140001ee3  jnz     short loc_140001EDC
0x140001ee5  lea     eax, ds:2[rax*2]
0x140001eec  jmp     short loc_140001EF8
0x140001eee  lea     rcx, qword_140010DA8
0x140001ef5  mov     eax, r9d
0x140001ef8  mov     [rbp+70h+var_38], eax
0x140001efb  lea     rsi, dword_140010DA4
0x140001f02  mov     rax, [rbp+70h+arg_88]
0x140001f09  mov     r8d, 1
0x140001f0f  mov     [rbp+70h+var_40], rcx
0x140001f13  mov     [rbp+70h+var_34], edi
0x140001f16  mov     rcx, [rax]
0x140001f19  test    rcx, rcx
0x140001f1c  jz      short loc_140001F2E
0x140001f1e  mov     rax, rdx
0x140001f21  inc     rax
0x140001f24  cmp     [rcx+rax], dil
0x140001f28  jnz     short loc_140001F21
0x140001f2a  inc     eax
0x140001f2c  jmp     short loc_140001F34
0x140001f2e  mov     rcx, rsi
0x140001f31  mov     eax, r8d
0x140001f34  mov     [rbp+70h+var_48], eax
0x140001f37  mov     rax, [rbp+70h+arg_80]
0x140001f3e  mov     [rbp+70h+var_60], rax
0x140001f42  mov     rax, [rbp+70h+arg_78]
0x140001f49  mov     [rbp+70h+var_50], rcx
0x140001f4d  mov     [rbp+70h+var_44], edi
0x140001f50  mov     [rbp+70h+var_58], 4
0x140001f58  mov     rcx, [rax]
0x140001f5b  test    rcx, rcx
0x140001f5e  jz      short loc_140001F75
0x140001f60  mov     rax, rdx
0x140001f63  inc     rax
0x140001f66  cmp     [rcx+rax*2], di
0x140001f6a  jnz     short loc_140001F63
0x140001f6c  lea     eax, ds:2[rax*2]
0x140001f73  jmp     short loc_140001F7F
0x140001f75  lea     rcx, qword_140010DA8
0x140001f7c  mov     eax, r9d
0x140001f7f  mov     [rbp+70h+var_68], eax
0x140001f82  mov     rax, [rbp+70h+arg_70]
0x140001f89  mov     [rbp+70h+var_70], rcx
0x140001f8d  mov     [rbp+70h+var_64], edi
0x140001f90  mov     rcx, [rax]
0x140001f93  test    rcx, rcx
0x140001f96  jz      short loc_140001FA8
0x140001f98  mov     rax, rdx
0x140001f9b  inc     rax
0x140001f9e  cmp     [rcx+rax], dil
0x140001fa2  jnz     short loc_140001F9B
0x140001fa4  inc     eax
0x140001fa6  jmp     short loc_140001FAE
0x140001fa8  mov     rcx, rsi
0x140001fab  mov     eax, r8d
0x140001fae  mov     [rbp+70h+var_78], eax
0x140001fb1  mov     rax, [rbp+70h+arg_68]
0x140001fb8  mov     [rbp+70h+var_90], rax
0x140001fbc  mov     rax, [rbp+70h+arg_60]
0x140001fc3  mov     [rbp+70h+var_80], rcx
0x140001fc7  mov     [rbp+70h+var_74], edi
0x140001fca  mov     [rbp+70h+var_88], 4
0x140001fd2  mov     rcx, [rax]
0x140001fd5  test    rcx, rcx
0x140001fd8  jz      short loc_140001FEA
0x140001fda  mov     rax, rdx
0x140001fdd  inc     rax
0x140001fe0  cmp     [rcx+rax], dil
0x140001fe4  jnz     short loc_140001FDD
0x140001fe6  inc     eax
0x140001fe8  jmp     short loc_140001FF0
0x140001fea  mov     rcx, rsi
0x140001fed  mov     eax, r8d
0x140001ff0  mov     [rbp+70h+var_98], eax
0x140001ff3  mov     rax, [rbp+70h+arg_58]
0x140001ffa  mov     [rbp+70h+var_B0], rax
0x140001ffe  mov     rax, [rbp+70h+arg_50]
0x140002005  mov     [rbp+70h+var_A0], rcx
0x140002009  mov     [rbp+70h+var_94], edi
0x14000200c  mov     [rbp+70h+var_A8], 4
0x140002014  mov     rcx, [rax]
0x140002017  test    rcx, rcx
0x14000201a  jz      short loc_140002032
0x14000201c  mov     rax, rdx
0x14000201f  inc     rax
0x140002022  cmp     [rcx+rax*2], di
0x140002026  jnz     short loc_14000201F
0x140002028  lea     r9d, ds:2[rax*2]
0x140002030  jmp     short loc_140002039
0x140002032  lea     rcx, qword_140010DA8
0x140002039  mov     rax, [rbp+70h+arg_48]
0x140002040  mov     [rbp+70h+var_D0], rax
0x140002044  mov     rax, [rbp+70h+arg_40]
0x14000204b  mov     [rbp+70h+var_C0], rcx
0x14000204f  mov     [rbp+70h+var_B8], r9d
0x140002053  mov     [rbp+70h+var_B4], edi
0x140002056  mov     rcx, [rax]
0x140002059  mov     [rbp+70h+var_C8], 4
0x140002061  test    rcx, rcx
0x140002064  jz      short loc_140002076
0x140002066  mov     rax, rdx
0x140002069  inc     rax
0x14000206c  cmp     [rcx+rax], dil
0x140002070  jnz     short loc_140002069
0x140002072  inc     eax
0x140002074  jmp     short loc_14000207C
0x140002076  mov     rcx, rsi
0x140002079  mov     eax, r8d
0x14000207c  mov     [rbp+70h+var_D8], eax
0x14000207f  mov     rax, [rbp+70h+arg_38]
0x140002086  mov     [rbp+70h+var_F0], rax
0x14000208a  mov     rax, [rbp+70h+arg_30]
0x140002091  mov     [rbp+70h+var_E0], rcx
0x140002095  mov     [rbp+70h+var_D4], edi
0x140002098  mov     [rbp+70h+var_E8], 4
0x1400020a0  mov     rcx, [rax]
0x1400020a3  test    rcx, rcx
0x1400020a6  jz      short loc_1400020B7
0x1400020a8  inc     rdx
0x1400020ab  cmp     [rcx+rdx], dil
0x1400020af  jnz     short loc_1400020A8
0x1400020b1  lea     r8d, [rdx+1]
0x1400020b5  jmp     short loc_1400020BA
0x1400020b7  mov     rcx, rsi
0x1400020ba  mov     rax, [rbp+70h+arg_28]
0x1400020c1  xor     r9d, r9d
0x1400020c4  mov     [rsp+170h+var_110], rax
0x1400020c9  mov     rdx, r11
0x1400020cc  mov     rax, [rbp+70h+arg_20]
0x1400020d3  mov     [rsp+170h+var_120], rax
0x1400020d8  lea     rax, [rsp+170h+var_140]
0x1400020dd  mov     [rsp+170h+var_100], rcx
0x1400020e2  mov     rcx, r10
0x1400020e5  mov     [rsp+170h+var_F8], r8d
0x1400020ea  mov     r8, rbx
0x1400020ed  mov     [rsp+170h+var_148], rax
0x1400020f2  mov     [rsp+170h+var_150], 11h
0x1400020fa  mov     [rsp+170h+var_F4], edi
0x1400020fe  mov     [rsp+170h+var_108], 4
0x140002107  mov     [rsp+170h+var_118], 8
0x140002110  call    _tlgWriteTransfer_EventWriteTransfer
0x140002115  mov     rcx, [rbp+70h+var_30]
0x140002119  xor     rcx, rsp; StackCookie
0x14000211c  call    __security_check_cookie
0x140002121  add     rsp, 150h
0x140002128  pop     r14
0x14000212a  pop     rdi
0x14000212b  pop     rsi
0x14000212c  pop     rbx
0x14000212d  pop     rbp
0x14000212e  retn
```
