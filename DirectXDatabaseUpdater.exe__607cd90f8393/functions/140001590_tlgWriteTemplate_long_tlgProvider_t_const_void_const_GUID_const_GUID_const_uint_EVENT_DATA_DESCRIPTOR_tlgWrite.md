# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001590`
- end: `0x140001875`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564566@Z`
- size: `741`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b6e4`
- `0x14000b93c`

## callees

- `0x140001590`
- `0x140002318`
- `0x140002f40`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
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
        __int64 **a20,
        __int64 **a21)
{
  __int64 v23; // rdx
  int v25; // r9d
  __int64 *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  __int64 *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  int v32; // r8d
  const unsigned __int16 *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  __int64 *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  __int64 *v45; // rcx
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
  __int64 v57; // [rsp+70h] [rbp-90h]
  __int64 v58; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v59; // [rsp+80h] [rbp-80h]
  int v60; // [rsp+88h] [rbp-78h]
  int v61; // [rsp+8Ch] [rbp-74h]
  __int64 v62; // [rsp+90h] [rbp-70h]
  __int64 v63; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v64; // [rsp+A0h] [rbp-60h]
  int v65; // [rsp+A8h] [rbp-58h]
  int v66; // [rsp+ACh] [rbp-54h]
  __int64 v67; // [rsp+B0h] [rbp-50h]
  __int64 v68; // [rsp+B8h] [rbp-48h]
  __int64 *v69; // [rsp+C0h] [rbp-40h]
  int v70; // [rsp+C8h] [rbp-38h]
  int v71; // [rsp+CCh] [rbp-34h]
  __int64 v72; // [rsp+D0h] [rbp-30h]
  __int64 v73; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v74; // [rsp+E0h] [rbp-20h]
  int v75; // [rsp+E8h] [rbp-18h]
  int v76; // [rsp+ECh] [rbp-14h]
  __int64 v77; // [rsp+F0h] [rbp-10h]
  __int64 v78; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v79; // [rsp+100h] [rbp+0h]
  int v80; // [rsp+108h] [rbp+8h]
  int v81; // [rsp+10Ch] [rbp+Ch]
  __int64 *v82; // [rsp+110h] [rbp+10h]
  int v83; // [rsp+118h] [rbp+18h]
  int v84; // [rsp+11Ch] [rbp+1Ch]
  __int64 v85; // [rsp+120h] [rbp+20h]
  __int64 v86; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v87; // [rsp+130h] [rbp+30h]
  int v88; // [rsp+138h] [rbp+38h]
  int v89; // [rsp+13Ch] [rbp+3Ch]
  __int64 *v90; // [rsp+140h] [rbp+40h]
  int v91; // [rsp+148h] [rbp+48h]
  int v92; // [rsp+14Ch] [rbp+4Ch]
  __int64 *v93; // [rsp+150h] [rbp+50h]
  int v94; // [rsp+158h] [rbp+58h]
  int v95; // [rsp+15Ch] [rbp+5Ch]

  v23 = -1;
  v25 = 2;
  v26 = *a21;
  if ( *a21 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *((_WORD *)v26 + v27) );
    v28 = 2 * v27 + 2;
  }
  else
  {
    v26 = &qword_14001C2F8;
    v28 = 2;
  }
  v94 = v28;
  v93 = v26;
  v95 = 0;
  v29 = *a20;
  if ( *a20 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *((_WORD *)v29 + v30) );
    v31 = 2 * v30 + 2;
  }
  else
  {
    v29 = &qword_14001C2F8;
    v31 = 2;
  }
  v91 = v31;
  v32 = 1;
  v90 = v29;
  v92 = 0;
  v33 = *a19;
  if ( *a19 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_BYTE *)v33 + v34) );
    v35 = v34 + 1;
  }
  else
  {
    v33 = &byte_14001C2F5;
    v35 = 1;
  }
  v88 = v35;
  v85 = a18;
  v87 = v33;
  v89 = 0;
  v86 = 4;
  v36 = *a17;
  if ( *a17 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_WORD *)v36 + v37) );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v36 = &qword_14001C2F8;
    v38 = 2;
  }
  v83 = v38;
  v82 = v36;
  v84 = 0;
  v39 = *a16;
  if ( *a16 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_BYTE *)v39 + v40) );
    v41 = v40 + 1;
  }
  else
  {
    v39 = &byte_14001C2F5;
    v41 = 1;
  }
  v80 = v41;
  v77 = a15;
  v79 = v39;
  v81 = 0;
  v78 = 4;
  v42 = *a14;
  if ( *a14 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &byte_14001C2F5;
    v44 = 1;
  }
  v75 = v44;
  v72 = a13;
  v74 = v42;
  v76 = 0;
  v73 = 4;
  v45 = *a12;
  if ( *a12 )
  {
    v46 = -1;
    do
      ++v46;
    while ( *((_WORD *)v45 + v46) );
    v25 = 2 * v46 + 2;
  }
  else
  {
    v45 = &qword_14001C2F8;
  }
  v67 = a11;
  v69 = v45;
  v70 = v25;
  v71 = 0;
  v47 = *a10;
  v68 = 4;
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
    v47 = &byte_14001C2F5;
    v49 = 1;
  }
  v65 = v49;
  v62 = a9;
  v64 = v47;
  v66 = 0;
  v63 = 4;
  v50 = *a8;
  if ( *a8 )
  {
    do
      ++v23;
    while ( *((_BYTE *)v50 + v23) );
    v32 = v23 + 1;
  }
  else
  {
    v50 = &byte_14001C2F5;
  }
  v57 = a7;
  v55 = a6;
  v53 = a5;
  v59 = v50;
  v60 = v32;
  v61 = 0;
  v58 = 4;
  v56 = 8;
  v54 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x13u, &v52);
}

```

## disassembly

```asm
0x140001590  push    rbp
0x140001592  push    rbx
0x140001593  push    rsi
0x140001594  push    rdi
0x140001595  push    r14
0x140001597  lea     rbp, [rsp-70h]
0x14000159c  sub     rsp, 170h
0x1400015a3  mov     rax, cs:__security_cookie
0x1400015aa  xor     rax, rsp
0x1400015ad  mov     [rbp+90h+var_30], rax
0x1400015b1  mov     rax, [rbp+90h+arg_A0]
0x1400015b8  mov     r11, rdx
0x1400015bb  mov     r10, rcx
0x1400015be  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400015c2  xor     edi, edi
0x1400015c4  mov     rbx, r8
0x1400015c7  mov     r9d, 2
0x1400015cd  mov     rcx, [rax]
0x1400015d0  test    rcx, rcx
0x1400015d3  jz      short loc_1400015EA
0x1400015d5  mov     rax, rdx
0x1400015d8  inc     rax
0x1400015db  cmp     [rcx+rax*2], di
0x1400015df  jnz     short loc_1400015D8
0x1400015e1  lea     eax, ds:2[rax*2]
0x1400015e8  jmp     short loc_1400015F4
0x1400015ea  lea     rcx, qword_14001C2F8
0x1400015f1  mov     eax, r9d
0x1400015f4  mov     [rbp+90h+var_38], eax
0x1400015f7  mov     rax, [rbp+90h+arg_98]
0x1400015fe  mov     [rbp+90h+var_40], rcx
0x140001602  mov     [rbp+90h+var_34], edi
0x140001605  mov     rcx, [rax]
0x140001608  test    rcx, rcx
0x14000160b  jz      short loc_140001622
0x14000160d  mov     rax, rdx
0x140001610  inc     rax
0x140001613  cmp     [rcx+rax*2], di
0x140001617  jnz     short loc_140001610
0x140001619  lea     eax, ds:2[rax*2]
0x140001620  jmp     short loc_14000162C
0x140001622  lea     rcx, qword_14001C2F8
0x140001629  mov     eax, r9d
0x14000162c  mov     [rbp+90h+var_48], eax
0x14000162f  lea     rsi, byte_14001C2F5
0x140001636  mov     rax, [rbp+90h+arg_90]
0x14000163d  mov     r8d, 1
0x140001643  mov     [rbp+90h+var_50], rcx
0x140001647  mov     [rbp+90h+var_44], edi
0x14000164a  mov     rcx, [rax]
0x14000164d  test    rcx, rcx
0x140001650  jz      short loc_140001662
0x140001652  mov     rax, rdx
0x140001655  inc     rax
0x140001658  cmp     [rcx+rax], dil
0x14000165c  jnz     short loc_140001655
0x14000165e  inc     eax
0x140001660  jmp     short loc_140001668
0x140001662  mov     rcx, rsi
0x140001665  mov     eax, r8d
0x140001668  mov     [rbp+90h+var_58], eax
0x14000166b  mov     rax, [rbp+90h+arg_88]
0x140001672  mov     [rbp+90h+var_70], rax
0x140001676  mov     rax, [rbp+90h+arg_80]
0x14000167d  mov     [rbp+90h+var_60], rcx
0x140001681  mov     [rbp+90h+var_54], edi
0x140001684  mov     [rbp+90h+var_68], 4
0x14000168c  mov     rcx, [rax]
0x14000168f  test    rcx, rcx
0x140001692  jz      short loc_1400016A9
0x140001694  mov     rax, rdx
0x140001697  inc     rax
0x14000169a  cmp     [rcx+rax*2], di
0x14000169e  jnz     short loc_140001697
0x1400016a0  lea     eax, ds:2[rax*2]
0x1400016a7  jmp     short loc_1400016B3
0x1400016a9  lea     rcx, qword_14001C2F8
0x1400016b0  mov     eax, r9d
0x1400016b3  mov     [rbp+90h+var_78], eax
0x1400016b6  mov     rax, [rbp+90h+arg_78]
0x1400016bd  mov     [rbp+90h+var_80], rcx
0x1400016c1  mov     [rbp+90h+var_74], edi
0x1400016c4  mov     rcx, [rax]
0x1400016c7  test    rcx, rcx
0x1400016ca  jz      short loc_1400016DC
0x1400016cc  mov     rax, rdx
0x1400016cf  inc     rax
0x1400016d2  cmp     [rcx+rax], dil
0x1400016d6  jnz     short loc_1400016CF
0x1400016d8  inc     eax
0x1400016da  jmp     short loc_1400016E2
0x1400016dc  mov     rcx, rsi
0x1400016df  mov     eax, r8d
0x1400016e2  mov     [rbp+90h+var_88], eax
0x1400016e5  mov     rax, [rbp+90h+arg_70]
0x1400016ec  mov     [rbp+90h+var_A0], rax
0x1400016f0  mov     rax, [rbp+90h+arg_68]
0x1400016f7  mov     [rbp+90h+var_90], rcx
0x1400016fb  mov     [rbp+90h+var_84], edi
0x1400016fe  mov     [rbp+90h+var_98], 4
0x140001706  mov     rcx, [rax]
0x140001709  test    rcx, rcx
0x14000170c  jz      short loc_14000171E
0x14000170e  mov     rax, rdx
0x140001711  inc     rax
0x140001714  cmp     [rcx+rax], dil
0x140001718  jnz     short loc_140001711
0x14000171a  inc     eax
0x14000171c  jmp     short loc_140001724
0x14000171e  mov     rcx, rsi
0x140001721  mov     eax, r8d
0x140001724  mov     [rbp+90h+var_A8], eax
0x140001727  mov     rax, [rbp+90h+arg_60]
0x14000172e  mov     [rbp+90h+var_C0], rax
0x140001732  mov     rax, [rbp+90h+arg_58]
0x140001739  mov     [rbp+90h+var_B0], rcx
0x14000173d  mov     [rbp+90h+var_A4], edi
0x140001740  mov     [rbp+90h+var_B8], 4
0x140001748  mov     rcx, [rax]
0x14000174b  test    rcx, rcx
0x14000174e  jz      short loc_140001766
0x140001750  mov     rax, rdx
0x140001753  inc     rax
0x140001756  cmp     [rcx+rax*2], di
0x14000175a  jnz     short loc_140001753
0x14000175c  lea     r9d, ds:2[rax*2]
0x140001764  jmp     short loc_14000176D
0x140001766  lea     rcx, qword_14001C2F8
0x14000176d  mov     rax, [rbp+90h+arg_50]
0x140001774  mov     [rbp+90h+var_E0], rax
0x140001778  mov     rax, [rbp+90h+arg_48]
0x14000177f  mov     [rbp+90h+var_D0], rcx
0x140001783  mov     [rbp+90h+var_C8], r9d
0x140001787  mov     [rbp+90h+var_C4], edi
0x14000178a  mov     rcx, [rax]
0x14000178d  mov     [rbp+90h+var_D8], 4
0x140001795  test    rcx, rcx
0x140001798  jz      short loc_1400017AA
0x14000179a  mov     rax, rdx
0x14000179d  inc     rax
0x1400017a0  cmp     [rcx+rax], dil
0x1400017a4  jnz     short loc_14000179D
0x1400017a6  inc     eax
0x1400017a8  jmp     short loc_1400017B0
0x1400017aa  mov     rcx, rsi
0x1400017ad  mov     eax, r8d
0x1400017b0  mov     [rbp+90h+var_E8], eax
0x1400017b3  mov     rax, [rbp+90h+arg_40]
0x1400017ba  mov     [rbp+90h+var_100], rax
0x1400017be  mov     rax, [rbp+90h+arg_38]
0x1400017c5  mov     [rbp+90h+var_F0], rcx
0x1400017c9  mov     [rbp+90h+var_E4], edi
0x1400017cc  mov     [rbp+90h+var_F8], 4
0x1400017d4  mov     rcx, [rax]
0x1400017d7  test    rcx, rcx
0x1400017da  jz      short loc_1400017EB
0x1400017dc  inc     rdx
0x1400017df  cmp     [rcx+rdx], dil
0x1400017e3  jnz     short loc_1400017DC
0x1400017e5  lea     r8d, [rdx+1]
0x1400017e9  jmp     short loc_1400017EE
0x1400017eb  mov     rcx, rsi
0x1400017ee  mov     rax, [rbp+90h+arg_30]
0x1400017f5  xor     r9d, r9d
0x1400017f8  mov     [rsp+190h+var_120], rax
0x1400017fd  mov     rdx, r11
0x140001800  mov     rax, [rbp+90h+arg_28]
0x140001807  mov     [rsp+190h+var_130], rax
0x14000180c  mov     rax, [rbp+90h+arg_20]
0x140001813  mov     [rsp+190h+var_140], rax
0x140001818  lea     rax, [rsp+190h+var_160]
0x14000181d  mov     [rbp+90h+var_110], rcx
0x140001821  mov     rcx, r10
0x140001824  mov     [rbp+90h+var_108], r8d
0x140001828  mov     r8, rbx
0x14000182b  mov     [rsp+190h+var_168], rax
0x140001830  mov     [rsp+190h+var_170], 13h
0x140001838  mov     [rbp+90h+var_104], edi
0x14000183b  mov     [rsp+190h+var_118], 4
0x140001844  mov     [rsp+190h+var_128], 8
0x14000184d  mov     [rsp+190h+var_138], 8
0x140001856  call    _tlgWriteTransfer_EventWriteTransfer
0x14000185b  mov     rcx, [rbp+90h+var_30]
0x14000185f  xor     rcx, rsp; StackCookie
0x140001862  call    __security_check_cookie
0x140001867  add     rsp, 170h
0x14000186e  pop     r14
0x140001870  pop     rdi
0x140001871  pop     rsi
0x140001872  pop     rbx
0x140001873  pop     rbp
0x140001874  retn
```
