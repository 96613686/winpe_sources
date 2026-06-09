# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001440`
- end: `0x140001721`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@_W@@U2@U2@U2@U2@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U3@U3@U3@U3@U2@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@_W@@44444AEBU?$_tlgWrapperByVal@$03@@55555555455@Z`
- size: `737`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001e9dc`

## callees

- `0x140001440`
- `0x140001ad4`
- `0x140005c20`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int **a6,
        int **a7,
        int **a8,
        int **a9,
        int **a10,
        int **a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        int **a21,
        __int64 a22,
        __int64 a23)
{
  __int64 v24; // rcx
  int v26; // edx
  int *v27; // r8
  __int64 v28; // rax
  int v29; // eax
  int *v30; // r8
  __int64 v31; // rax
  int v32; // eax
  int *v33; // r8
  __int64 v34; // rax
  int v35; // eax
  int *v36; // r8
  __int64 v37; // rax
  int v38; // eax
  int *v39; // r8
  __int64 v40; // rax
  int v41; // eax
  int *v42; // r8
  __int64 v43; // rax
  int v44; // eax
  int *v45; // r8
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  int *v50; // [rsp+60h] [rbp-A0h]
  int v51; // [rsp+68h] [rbp-98h]
  int v52; // [rsp+6Ch] [rbp-94h]
  int *v53; // [rsp+70h] [rbp-90h]
  int v54; // [rsp+78h] [rbp-88h]
  int v55; // [rsp+7Ch] [rbp-84h]
  int *v56; // [rsp+80h] [rbp-80h]
  int v57; // [rsp+88h] [rbp-78h]
  int v58; // [rsp+8Ch] [rbp-74h]
  int *v59; // [rsp+90h] [rbp-70h]
  int v60; // [rsp+98h] [rbp-68h]
  int v61; // [rsp+9Ch] [rbp-64h]
  int *v62; // [rsp+A0h] [rbp-60h]
  int v63; // [rsp+A8h] [rbp-58h]
  int v64; // [rsp+ACh] [rbp-54h]
  int *v65; // [rsp+B0h] [rbp-50h]
  int v66; // [rsp+B8h] [rbp-48h]
  int v67; // [rsp+BCh] [rbp-44h]
  __int64 v68; // [rsp+C0h] [rbp-40h]
  __int64 v69; // [rsp+C8h] [rbp-38h]
  __int64 v70; // [rsp+D0h] [rbp-30h]
  __int64 v71; // [rsp+D8h] [rbp-28h]
  __int64 v72; // [rsp+E0h] [rbp-20h]
  __int64 v73; // [rsp+E8h] [rbp-18h]
  __int64 v74; // [rsp+F0h] [rbp-10h]
  __int64 v75; // [rsp+F8h] [rbp-8h]
  __int64 v76; // [rsp+100h] [rbp+0h]
  __int64 v77; // [rsp+108h] [rbp+8h]
  __int64 v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  __int64 v82; // [rsp+130h] [rbp+30h]
  __int64 v83; // [rsp+138h] [rbp+38h]
  __int64 v84; // [rsp+140h] [rbp+40h]
  __int64 v85; // [rsp+148h] [rbp+48h]
  int *v86; // [rsp+150h] [rbp+50h]
  int v87; // [rsp+158h] [rbp+58h]
  int v88; // [rsp+15Ch] [rbp+5Ch]
  __int64 v89; // [rsp+160h] [rbp+60h]
  __int64 v90; // [rsp+168h] [rbp+68h]
  __int64 v91; // [rsp+170h] [rbp+70h]
  __int64 v92; // [rsp+178h] [rbp+78h]

  v91 = a23;
  v89 = a22;
  v24 = -1;
  v92 = 4;
  v26 = 2;
  v90 = 4;
  v27 = *a21;
  if ( *a21 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *((_WORD *)v27 + v28) );
    v29 = 2 * v28 + 2;
  }
  else
  {
    v27 = &dword_140033A5C;
    v29 = 2;
  }
  v87 = v29;
  v84 = a20;
  v82 = a19;
  v80 = a18;
  v78 = a17;
  v76 = a16;
  v74 = a15;
  v72 = a14;
  v70 = a13;
  v68 = a12;
  v86 = v27;
  v88 = 0;
  v85 = 4;
  v30 = *a11;
  v83 = 4;
  v81 = 4;
  v79 = 4;
  v77 = 4;
  v75 = 4;
  v73 = 4;
  v71 = 4;
  v69 = 4;
  if ( v30 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *((_WORD *)v30 + v31) );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &dword_140033A5C;
    v32 = 2;
  }
  v66 = v32;
  v65 = v30;
  v67 = 0;
  v33 = *a10;
  if ( *a10 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_WORD *)v33 + v34) );
    v35 = 2 * v34 + 2;
  }
  else
  {
    v33 = &dword_140033A5C;
    v35 = 2;
  }
  v63 = v35;
  v62 = v33;
  v64 = 0;
  v36 = *a9;
  if ( *a9 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_WORD *)v36 + v37) );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v36 = &dword_140033A5C;
    v38 = 2;
  }
  v60 = v38;
  v59 = v36;
  v61 = 0;
  v39 = *a8;
  if ( *a8 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_WORD *)v39 + v40) );
    v41 = 2 * v40 + 2;
  }
  else
  {
    v39 = &dword_140033A5C;
    v41 = 2;
  }
  v57 = v41;
  v56 = v39;
  v58 = 0;
  v42 = *a7;
  if ( *a7 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_WORD *)v42 + v43) );
    v44 = 2 * v43 + 2;
  }
  else
  {
    v42 = &dword_140033A5C;
    v44 = 2;
  }
  v54 = v44;
  v53 = v42;
  v55 = 0;
  v45 = *a6;
  if ( *a6 )
  {
    do
      ++v24;
    while ( *((_WORD *)v45 + v24) );
    v26 = 2 * v24 + 2;
  }
  else
  {
    v45 = &dword_140033A5C;
  }
  v48 = a5;
  v50 = v45;
  v51 = v26;
  v52 = 0;
  v49 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0x15u, &v47);
}

```

## disassembly

```asm
0x140001440  mov     [rsp-8+arg_10], rbx
0x140001445  mov     [rsp-8+arg_18], rdi
0x14000144a  push    rbp
0x14000144b  lea     rbp, [rsp-90h]
0x140001453  sub     rsp, 190h
0x14000145a  mov     rax, cs:__security_cookie
0x140001461  xor     rax, rsp
0x140001464  mov     [rbp+90h+var_10], rax
0x14000146b  mov     rax, [rbp+90h+arg_B0]
0x140001472  lea     rbx, dword_140033A5C
0x140001479  mov     [rbp+90h+var_20], rax
0x14000147d  xor     r9d, r9d; int
0x140001480  mov     rax, [rbp+90h+arg_A8]
0x140001487  mov     r10, rcx
0x14000148a  mov     [rbp+90h+var_30], rax
0x14000148e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001492  mov     rax, [rbp+90h+arg_A0]
0x140001499  mov     r11, rdx
0x14000149c  mov     [rbp+90h+var_18], 4
0x1400014a4  lea     edx, [r9+2]
0x1400014a8  mov     [rbp+90h+var_28], 4
0x1400014b0  mov     r8, [rax]
0x1400014b3  test    r8, r8
0x1400014b6  jz      short loc_1400014CE
0x1400014b8  mov     rax, rcx
0x1400014bb  inc     rax
0x1400014be  cmp     [r8+rax*2], r9w
0x1400014c3  jnz     short loc_1400014BB
0x1400014c5  lea     eax, ds:2[rax*2]
0x1400014cc  jmp     short loc_1400014D3
0x1400014ce  mov     r8, rbx
0x1400014d1  mov     eax, edx
0x1400014d3  mov     [rbp+90h+var_38], eax
0x1400014d6  mov     rax, [rbp+90h+arg_98]
0x1400014dd  mov     [rbp+90h+var_50], rax
0x1400014e1  mov     rax, [rbp+90h+arg_90]
0x1400014e8  mov     [rbp+90h+var_60], rax
0x1400014ec  mov     rax, [rbp+90h+arg_88]
0x1400014f3  mov     [rbp+90h+var_70], rax
0x1400014f7  mov     rax, [rbp+90h+arg_80]
0x1400014fe  mov     [rbp+90h+var_80], rax
0x140001502  mov     rax, [rbp+90h+arg_78]
0x140001509  mov     [rbp+90h+var_90], rax
0x14000150d  mov     rax, [rbp+90h+arg_70]
0x140001514  mov     [rbp+90h+var_A0], rax
0x140001518  mov     rax, [rbp+90h+arg_68]
0x14000151f  mov     [rbp+90h+var_B0], rax
0x140001523  mov     rax, [rbp+90h+arg_60]
0x14000152a  mov     [rbp+90h+var_C0], rax
0x14000152e  mov     rax, [rbp+90h+arg_58]
0x140001535  mov     [rbp+90h+var_D0], rax
0x140001539  mov     rax, [rbp+90h+arg_50]
0x140001540  mov     [rbp+90h+var_40], r8
0x140001544  mov     [rbp+90h+var_34], r9d
0x140001548  mov     [rbp+90h+var_48], 4
0x140001550  mov     r8, [rax]
0x140001553  mov     [rbp+90h+var_58], 4
0x14000155b  mov     [rbp+90h+var_68], 4
0x140001563  mov     [rbp+90h+var_78], 4
0x14000156b  mov     [rbp+90h+var_88], 4
0x140001573  mov     [rbp+90h+var_98], 4
0x14000157b  mov     [rbp+90h+var_A8], 4
0x140001583  mov     [rbp+90h+var_B8], 4
0x14000158b  mov     [rbp+90h+var_C8], 4
0x140001593  test    r8, r8
0x140001596  jz      short loc_1400015AE
0x140001598  mov     rax, rcx
0x14000159b  inc     rax
0x14000159e  cmp     [r8+rax*2], r9w
0x1400015a3  jnz     short loc_14000159B
0x1400015a5  lea     eax, ds:2[rax*2]
0x1400015ac  jmp     short loc_1400015B3
0x1400015ae  mov     r8, rbx
0x1400015b1  mov     eax, edx
0x1400015b3  mov     [rbp+90h+var_D8], eax
0x1400015b6  mov     rax, [rbp+90h+arg_48]
0x1400015bd  mov     [rbp+90h+var_E0], r8
0x1400015c1  mov     [rbp+90h+var_D4], r9d
0x1400015c5  mov     r8, [rax]
0x1400015c8  test    r8, r8
0x1400015cb  jz      short loc_1400015E3
0x1400015cd  mov     rax, rcx
0x1400015d0  inc     rax
0x1400015d3  cmp     [r8+rax*2], r9w
0x1400015d8  jnz     short loc_1400015D0
0x1400015da  lea     eax, ds:2[rax*2]
0x1400015e1  jmp     short loc_1400015E8
0x1400015e3  mov     r8, rbx
0x1400015e6  mov     eax, edx
0x1400015e8  mov     [rbp+90h+var_E8], eax
0x1400015eb  mov     rax, [rbp+90h+arg_40]
0x1400015f2  mov     [rbp+90h+var_F0], r8
0x1400015f6  mov     [rbp+90h+var_E4], r9d
0x1400015fa  mov     r8, [rax]
0x1400015fd  test    r8, r8
0x140001600  jz      short loc_140001618
0x140001602  mov     rax, rcx
0x140001605  inc     rax
0x140001608  cmp     [r8+rax*2], r9w
0x14000160d  jnz     short loc_140001605
0x14000160f  lea     eax, ds:2[rax*2]
0x140001616  jmp     short loc_14000161D
0x140001618  mov     r8, rbx
0x14000161b  mov     eax, edx
0x14000161d  mov     [rbp+90h+var_F8], eax
0x140001620  mov     rax, [rbp+90h+arg_38]
0x140001627  mov     [rbp+90h+var_100], r8
0x14000162b  mov     [rbp+90h+var_F4], r9d
0x14000162f  mov     r8, [rax]
0x140001632  test    r8, r8
0x140001635  jz      short loc_14000164D
0x140001637  mov     rax, rcx
0x14000163a  inc     rax
0x14000163d  cmp     [r8+rax*2], r9w
0x140001642  jnz     short loc_14000163A
0x140001644  lea     eax, ds:2[rax*2]
0x14000164b  jmp     short loc_140001652
0x14000164d  mov     r8, rbx
0x140001650  mov     eax, edx
0x140001652  mov     [rbp+90h+var_108], eax
0x140001655  mov     rax, [rbp+90h+arg_30]
0x14000165c  mov     [rbp+90h+var_110], r8
0x140001660  mov     [rbp+90h+var_104], r9d
0x140001664  mov     r8, [rax]
0x140001667  test    r8, r8
0x14000166a  jz      short loc_140001682
0x14000166c  mov     rax, rcx
0x14000166f  inc     rax
0x140001672  cmp     [r8+rax*2], r9w
0x140001677  jnz     short loc_14000166F
0x140001679  lea     eax, ds:2[rax*2]
0x140001680  jmp     short loc_140001687
0x140001682  mov     r8, rbx
0x140001685  mov     eax, edx
0x140001687  mov     [rsp+190h+var_118], eax
0x14000168b  mov     rax, [rbp+90h+arg_28]
0x140001692  mov     [rsp+190h+var_120], r8
0x140001697  mov     [rsp+190h+var_114], r9d
0x14000169c  mov     r8, [rax]
0x14000169f  test    r8, r8
0x1400016a2  jz      short loc_1400016B7
0x1400016a4  inc     rcx
0x1400016a7  cmp     [r8+rcx*2], r9w
0x1400016ac  jnz     short loc_1400016A4
0x1400016ae  lea     edx, ds:2[rcx*2]
0x1400016b5  jmp     short loc_1400016BA
0x1400016b7  mov     r8, rbx
0x1400016ba  mov     rax, [rbp+90h+arg_20]
0x1400016c1  mov     rcx, r10; int
0x1400016c4  mov     [rsp+190h+var_140], rax
0x1400016c9  lea     rax, [rsp+190h+var_160]
0x1400016ce  mov     [rsp+190h+var_130], r8
0x1400016d3  xor     r8d, r8d; int
0x1400016d6  mov     [rsp+190h+var_128], edx
0x1400016da  mov     rdx, r11; int
0x1400016dd  mov     [rsp+190h+var_168], rax; PEVENT_DATA_DESCRIPTOR
0x1400016e2  mov     [rsp+190h+var_170], 15h; ULONG
0x1400016ea  mov     [rsp+190h+var_124], r9d
0x1400016ef  mov     [rsp+190h+var_138], 8
0x1400016f8  call    _tlgWriteTransfer_EventWriteTransfer
0x1400016fd  mov     rcx, [rbp+90h+var_10]
0x140001704  xor     rcx, rsp; StackCookie
0x140001707  call    __security_check_cookie
0x14000170c  lea     r11, [rsp+190h+var_s0]
0x140001714  mov     rbx, [r11+20h]
0x140001718  mov     rdi, [r11+28h]
0x14000171c  mov     rsp, r11
0x14000171f  pop     rbp
0x140001720  retn
```
