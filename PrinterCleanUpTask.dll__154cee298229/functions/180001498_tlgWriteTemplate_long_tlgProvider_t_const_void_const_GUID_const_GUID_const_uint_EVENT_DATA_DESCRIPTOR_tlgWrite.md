# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001498`
- end: `0x180001787`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `751`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const WCHAR **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const WCHAR **, __int64, const unsigned __int16 **, const WCHAR **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e5a0`

## callees

- `0x180001498`
- `0x180001918`
- `0x180002020`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
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
        const WCHAR **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        const WCHAR **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        const WCHAR **a19,
        __int64 a20,
        __int64 a21,
        const unsigned __int16 **a22)
{
  __int64 v24; // rdx
  int v25; // r8d
  const unsigned __int16 *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int v29; // r9d
  const WCHAR *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  const WCHAR *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  const WCHAR *v45; // rcx
  __int64 v46; // rax
  const unsigned __int16 *v47; // rcx
  __int64 v48; // rax
  int v49; // eax
  const unsigned __int16 *v50; // rcx
  _BYTE v52[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B0h]
  __int64 v54; // [rsp+58h] [rbp-A8h]
  __int64 v55; // [rsp+60h] [rbp-A0h]
  __int64 v56; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v57; // [rsp+70h] [rbp-90h]
  int v58; // [rsp+78h] [rbp-88h]
  int v59; // [rsp+7Ch] [rbp-84h]
  __int64 v60; // [rsp+80h] [rbp-80h]
  __int64 v61; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v62; // [rsp+90h] [rbp-70h]
  int v63; // [rsp+98h] [rbp-68h]
  int v64; // [rsp+9Ch] [rbp-64h]
  __int64 v65; // [rsp+A0h] [rbp-60h]
  __int64 v66; // [rsp+A8h] [rbp-58h]
  const WCHAR *v67; // [rsp+B0h] [rbp-50h]
  int v68; // [rsp+B8h] [rbp-48h]
  int v69; // [rsp+BCh] [rbp-44h]
  __int64 v70; // [rsp+C0h] [rbp-40h]
  __int64 v71; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v72; // [rsp+D0h] [rbp-30h]
  int v73; // [rsp+D8h] [rbp-28h]
  int v74; // [rsp+DCh] [rbp-24h]
  __int64 v75; // [rsp+E0h] [rbp-20h]
  __int64 v76; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v77; // [rsp+F0h] [rbp-10h]
  int v78; // [rsp+F8h] [rbp-8h]
  int v79; // [rsp+FCh] [rbp-4h]
  const WCHAR *v80; // [rsp+100h] [rbp+0h]
  int v81; // [rsp+108h] [rbp+8h]
  int v82; // [rsp+10Ch] [rbp+Ch]
  __int64 v83; // [rsp+110h] [rbp+10h]
  __int64 v84; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  const WCHAR *v88; // [rsp+130h] [rbp+30h]
  int v89; // [rsp+138h] [rbp+38h]
  int v90; // [rsp+13Ch] [rbp+3Ch]
  __int64 v91; // [rsp+140h] [rbp+40h]
  __int64 v92; // [rsp+148h] [rbp+48h]
  __int64 v93; // [rsp+150h] [rbp+50h]
  __int64 v94; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v95; // [rsp+160h] [rbp+60h]
  int v96; // [rsp+168h] [rbp+68h]
  int v97; // [rsp+16Ch] [rbp+6Ch]

  v24 = -1;
  v25 = 1;
  v26 = *a22;
  if ( *a22 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *((_BYTE *)v26 + v27) );
    v28 = v27 + 1;
  }
  else
  {
    v26 = &dword_18001A274;
    v28 = 1;
  }
  v96 = v28;
  v29 = 2;
  v93 = a21;
  v91 = a20;
  v95 = v26;
  v97 = 0;
  v94 = 4;
  v30 = *a19;
  v92 = 4;
  if ( v30 )
  {
    v31 = -1;
    do
      ++v31;
    while ( v30[v31] );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &LocaleName;
    v32 = 2;
  }
  v89 = v32;
  v88 = v30;
  v90 = 0;
  v33 = *a18;
  if ( *a18 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_BYTE *)v33 + v34) );
    v35 = v34 + 1;
  }
  else
  {
    v33 = &dword_18001A274;
    v35 = 1;
  }
  v86 = v35;
  v83 = a17;
  v85 = v33;
  v87 = 0;
  v84 = 4;
  v36 = *a16;
  if ( *a16 )
  {
    v37 = -1;
    do
      ++v37;
    while ( v36[v37] );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v36 = &LocaleName;
    v38 = 2;
  }
  v81 = v38;
  v80 = v36;
  v82 = 0;
  v39 = *a15;
  if ( *a15 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_BYTE *)v39 + v40) );
    v41 = v40 + 1;
  }
  else
  {
    v39 = &dword_18001A274;
    v41 = 1;
  }
  v78 = v41;
  v75 = a14;
  v77 = v39;
  v79 = 0;
  v76 = 4;
  v42 = *a13;
  if ( *a13 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &dword_18001A274;
    v44 = 1;
  }
  v73 = v44;
  v70 = a12;
  v72 = v42;
  v74 = 0;
  v71 = 4;
  v45 = *a11;
  if ( *a11 )
  {
    v46 = -1;
    do
      ++v46;
    while ( v45[v46] );
    v29 = 2 * v46 + 2;
  }
  else
  {
    v45 = &LocaleName;
  }
  v65 = a10;
  v67 = v45;
  v68 = v29;
  v69 = 0;
  v47 = *a9;
  v66 = 4;
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
    v47 = &dword_18001A274;
    v49 = 1;
  }
  v63 = v49;
  v60 = a8;
  v62 = v47;
  v64 = 0;
  v61 = 4;
  v50 = *a7;
  if ( *a7 )
  {
    do
      ++v24;
    while ( *((_BYTE *)v50 + v24) );
    v25 = v24 + 1;
  }
  else
  {
    v50 = &dword_18001A274;
  }
  v55 = a6;
  v53 = a5;
  v57 = v50;
  v58 = v25;
  v59 = 0;
  v56 = 4;
  v54 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 20, v52);
}

```

## disassembly

```asm
0x180001498  mov     [rsp-8+arg_10], rbx
0x18000149d  push    rbp
0x18000149e  push    rdi
0x18000149f  push    r14
0x1800014a1  lea     rbp, [rsp-80h]
0x1800014a6  sub     rsp, 180h
0x1800014ad  mov     rax, cs:__security_cookie
0x1800014b4  xor     rax, rsp
0x1800014b7  mov     [rbp+90h+var_20], rax
0x1800014bb  mov     rax, [rbp+90h+arg_A8]
0x1800014c2  lea     rdi, dword_18001A274
0x1800014c9  mov     r11, rdx
0x1800014cc  mov     r10, rcx
0x1800014cf  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800014d3  xor     ebx, ebx
0x1800014d5  mov     r8d, 1
0x1800014db  mov     rcx, [rax]
0x1800014de  test    rcx, rcx
0x1800014e1  jz      short loc_1800014F2
0x1800014e3  mov     rax, rdx
0x1800014e6  inc     rax
0x1800014e9  cmp     [rcx+rax], bl
0x1800014ec  jnz     short loc_1800014E6
0x1800014ee  inc     eax
0x1800014f0  jmp     short loc_1800014F8
0x1800014f2  mov     rcx, rdi
0x1800014f5  mov     eax, r8d
0x1800014f8  mov     [rbp+90h+var_28], eax
0x1800014fb  mov     r9d, 2
0x180001501  mov     rax, [rbp+90h+arg_A0]
0x180001508  mov     [rbp+90h+var_40], rax
0x18000150c  mov     rax, [rbp+90h+arg_98]
0x180001513  mov     [rbp+90h+var_50], rax
0x180001517  mov     rax, [rbp+90h+arg_90]
0x18000151e  mov     [rbp+90h+var_30], rcx
0x180001522  mov     [rbp+90h+var_24], ebx
0x180001525  mov     [rbp+90h+var_38], 4
0x18000152d  mov     rcx, [rax]
0x180001530  mov     [rbp+90h+var_48], 4
0x180001538  test    rcx, rcx
0x18000153b  jz      short loc_180001552
0x18000153d  mov     rax, rdx
0x180001540  inc     rax
0x180001543  cmp     [rcx+rax*2], bx
0x180001547  jnz     short loc_180001540
0x180001549  lea     eax, ds:2[rax*2]
0x180001550  jmp     short loc_18000155C
0x180001552  lea     rcx, LocaleName
0x180001559  mov     eax, r9d
0x18000155c  mov     [rbp+90h+var_58], eax
0x18000155f  mov     rax, [rbp+90h+arg_88]
0x180001566  mov     [rbp+90h+var_60], rcx
0x18000156a  mov     [rbp+90h+var_54], ebx
0x18000156d  mov     rcx, [rax]
0x180001570  test    rcx, rcx
0x180001573  jz      short loc_180001584
0x180001575  mov     rax, rdx
0x180001578  inc     rax
0x18000157b  cmp     [rcx+rax], bl
0x18000157e  jnz     short loc_180001578
0x180001580  inc     eax
0x180001582  jmp     short loc_18000158A
0x180001584  mov     rcx, rdi
0x180001587  mov     eax, r8d
0x18000158a  mov     [rbp+90h+var_68], eax
0x18000158d  mov     rax, [rbp+90h+arg_80]
0x180001594  mov     [rbp+90h+var_80], rax
0x180001598  mov     rax, [rbp+90h+arg_78]
0x18000159f  mov     [rbp+90h+var_70], rcx
0x1800015a3  mov     [rbp+90h+var_64], ebx
0x1800015a6  mov     [rbp+90h+var_78], 4
0x1800015ae  mov     rcx, [rax]
0x1800015b1  test    rcx, rcx
0x1800015b4  jz      short loc_1800015CB
0x1800015b6  mov     rax, rdx
0x1800015b9  inc     rax
0x1800015bc  cmp     [rcx+rax*2], bx
0x1800015c0  jnz     short loc_1800015B9
0x1800015c2  lea     eax, ds:2[rax*2]
0x1800015c9  jmp     short loc_1800015D5
0x1800015cb  lea     rcx, LocaleName
0x1800015d2  mov     eax, r9d
0x1800015d5  mov     [rbp+90h+var_88], eax
0x1800015d8  mov     rax, [rbp+90h+arg_70]
0x1800015df  mov     [rbp+90h+var_90], rcx
0x1800015e3  mov     [rbp+90h+var_84], ebx
0x1800015e6  mov     rcx, [rax]
0x1800015e9  test    rcx, rcx
0x1800015ec  jz      short loc_1800015FD
0x1800015ee  mov     rax, rdx
0x1800015f1  inc     rax
0x1800015f4  cmp     [rcx+rax], bl
0x1800015f7  jnz     short loc_1800015F1
0x1800015f9  inc     eax
0x1800015fb  jmp     short loc_180001603
0x1800015fd  mov     rcx, rdi
0x180001600  mov     eax, r8d
0x180001603  mov     [rbp+90h+var_98], eax
0x180001606  mov     rax, [rbp+90h+arg_68]
0x18000160d  mov     [rbp+90h+var_B0], rax
0x180001611  mov     rax, [rbp+90h+arg_60]
0x180001618  mov     [rbp+90h+var_A0], rcx
0x18000161c  mov     [rbp+90h+var_94], ebx
0x18000161f  mov     [rbp+90h+var_A8], 4
0x180001627  mov     rcx, [rax]
0x18000162a  test    rcx, rcx
0x18000162d  jz      short loc_18000163E
0x18000162f  mov     rax, rdx
0x180001632  inc     rax
0x180001635  cmp     [rcx+rax], bl
0x180001638  jnz     short loc_180001632
0x18000163a  inc     eax
0x18000163c  jmp     short loc_180001644
0x18000163e  mov     rcx, rdi
0x180001641  mov     eax, r8d
0x180001644  mov     [rbp+90h+var_B8], eax
0x180001647  mov     rax, [rbp+90h+arg_58]
0x18000164e  mov     [rbp+90h+var_D0], rax
0x180001652  mov     rax, [rbp+90h+arg_50]
0x180001659  mov     [rbp+90h+var_C0], rcx
0x18000165d  mov     [rbp+90h+var_B4], ebx
0x180001660  mov     [rbp+90h+var_C8], 4
0x180001668  mov     rcx, [rax]
0x18000166b  test    rcx, rcx
0x18000166e  jz      short loc_180001686
0x180001670  mov     rax, rdx
0x180001673  inc     rax
0x180001676  cmp     [rcx+rax*2], bx
0x18000167a  jnz     short loc_180001673
0x18000167c  lea     r9d, ds:2[rax*2]
0x180001684  jmp     short loc_18000168D
0x180001686  lea     rcx, LocaleName
0x18000168d  mov     rax, [rbp+90h+arg_48]
0x180001694  mov     [rbp+90h+var_F0], rax
0x180001698  mov     rax, [rbp+90h+arg_40]
0x18000169f  mov     [rbp+90h+var_E0], rcx
0x1800016a3  mov     [rbp+90h+var_D8], r9d
0x1800016a7  mov     [rbp+90h+var_D4], ebx
0x1800016aa  mov     rcx, [rax]
0x1800016ad  mov     [rbp+90h+var_E8], 4
0x1800016b5  test    rcx, rcx
0x1800016b8  jz      short loc_1800016C9
0x1800016ba  mov     rax, rdx
0x1800016bd  inc     rax
0x1800016c0  cmp     [rcx+rax], bl
0x1800016c3  jnz     short loc_1800016BD
0x1800016c5  inc     eax
0x1800016c7  jmp     short loc_1800016CF
0x1800016c9  mov     rcx, rdi
0x1800016cc  mov     eax, r8d
0x1800016cf  mov     [rbp+90h+var_F8], eax
0x1800016d2  mov     rax, [rbp+90h+arg_38]
0x1800016d9  mov     [rbp+90h+var_110], rax
0x1800016dd  mov     rax, [rbp+90h+arg_30]
0x1800016e4  mov     [rbp+90h+var_100], rcx
0x1800016e8  mov     [rbp+90h+var_F4], ebx
0x1800016eb  mov     [rbp+90h+var_108], 4
0x1800016f3  mov     rcx, [rax]
0x1800016f6  test    rcx, rcx
0x1800016f9  jz      short loc_180001709
0x1800016fb  inc     rdx
0x1800016fe  cmp     [rcx+rdx], bl
0x180001701  jnz     short loc_1800016FB
0x180001703  lea     r8d, [rdx+1]
0x180001707  jmp     short loc_18000170C
0x180001709  mov     rcx, rdi
0x18000170c  mov     rax, [rbp+90h+arg_28]
0x180001713  xor     r9d, r9d
0x180001716  mov     [rsp+190h+var_130], rax
0x18000171b  mov     rdx, r11
0x18000171e  mov     rax, [rbp+90h+arg_20]
0x180001725  mov     [rsp+190h+var_140], rax
0x18000172a  lea     rax, [rsp+190h+var_160]
0x18000172f  mov     [rsp+190h+var_120], rcx
0x180001734  mov     rcx, r10
0x180001737  mov     [rsp+190h+var_118], r8d
0x18000173c  xor     r8d, r8d
0x18000173f  mov     [rsp+190h+var_168], rax
0x180001744  mov     [rsp+190h+var_170], 14h
0x18000174c  mov     [rsp+190h+var_114], ebx
0x180001750  mov     [rsp+190h+var_128], 4
0x180001759  mov     [rsp+190h+var_138], 8
0x180001762  call    _tlgWriteTransfer_EventWriteTransfer
0x180001767  mov     rcx, [rbp+90h+var_20]
0x18000176b  xor     rcx, rsp; StackCookie
0x18000176e  call    __security_check_cookie
0x180001773  mov     rbx, [rsp+190h+arg_10]
0x18000177b  add     rsp, 180h
0x180001782  pop     r14
0x180001784  pop     rdi
0x180001785  pop     rbp
0x180001786  retn
```
