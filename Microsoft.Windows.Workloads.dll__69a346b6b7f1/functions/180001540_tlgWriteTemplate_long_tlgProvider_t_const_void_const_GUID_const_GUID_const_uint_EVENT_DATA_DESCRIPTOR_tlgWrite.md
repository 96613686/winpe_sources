# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001540`
- end: `0x1800018e4`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z`
- size: `932`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64, __int64, const wchar_t **, __int64, const wchar_t **, __int64, const wchar_t **, __int64, const wchar_t **, __int64, const wchar_t **, const wchar_t **, __int64, const wchar_t **, const wchar_t **, __int64, __int64, const wchar_t **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011760`

## callees

- `0x180001540`
- `0x180034ef0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x1800018c6`
- `ADVAPI32!EventWriteTransfer` at `0x1800018c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const wchar_t **a7,
        __int64 a8,
        const wchar_t **a9,
        __int64 a10,
        const wchar_t **a11,
        __int64 a12,
        const wchar_t **a13,
        __int64 a14,
        const wchar_t **a15,
        const wchar_t **a16,
        __int64 a17,
        const wchar_t **a18,
        const wchar_t **a19,
        __int64 a20,
        __int64 a21,
        const wchar_t **a22)
{
  __int64 v24; // rcx
  const wchar_t *v25; // r8
  __int64 v26; // rax
  int v27; // eax
  const wchar_t *v28; // rdx
  __int64 v29; // rax
  bool v30; // zf
  int v31; // eax
  const wchar_t *v32; // rdx
  __int64 v33; // rax
  int v34; // eax
  const wchar_t *v35; // rdx
  __int64 v36; // rax
  int v37; // eax
  const wchar_t *v38; // rdx
  __int64 v39; // rax
  int v40; // eax
  const wchar_t *v41; // rdx
  __int64 v42; // rax
  int v43; // eax
  const wchar_t *v44; // rdx
  __int64 v45; // rax
  int v46; // eax
  const wchar_t *v47; // rdx
  __int64 v48; // rax
  int v49; // eax
  const wchar_t *v50; // rdx
  int v51; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v55; // [rsp+60h] [rbp-A0h]
  int v56; // [rsp+68h] [rbp-98h]
  int v57; // [rsp+6Ch] [rbp-94h]
  __int64 v58; // [rsp+70h] [rbp-90h]
  __int64 v59; // [rsp+78h] [rbp-88h]
  __int64 v60; // [rsp+80h] [rbp-80h]
  __int64 v61; // [rsp+88h] [rbp-78h]
  const wchar_t *v62; // [rsp+90h] [rbp-70h]
  int v63; // [rsp+98h] [rbp-68h]
  int v64; // [rsp+9Ch] [rbp-64h]
  __int64 v65; // [rsp+A0h] [rbp-60h]
  __int64 v66; // [rsp+A8h] [rbp-58h]
  const wchar_t *v67; // [rsp+B0h] [rbp-50h]
  int v68; // [rsp+B8h] [rbp-48h]
  int v69; // [rsp+BCh] [rbp-44h]
  __int64 v70; // [rsp+C0h] [rbp-40h]
  __int64 v71; // [rsp+C8h] [rbp-38h]
  const wchar_t *v72; // [rsp+D0h] [rbp-30h]
  int v73; // [rsp+D8h] [rbp-28h]
  int v74; // [rsp+DCh] [rbp-24h]
  __int64 v75; // [rsp+E0h] [rbp-20h]
  __int64 v76; // [rsp+E8h] [rbp-18h]
  const wchar_t *v77; // [rsp+F0h] [rbp-10h]
  int v78; // [rsp+F8h] [rbp-8h]
  int v79; // [rsp+FCh] [rbp-4h]
  __int64 v80; // [rsp+100h] [rbp+0h]
  __int64 v81; // [rsp+108h] [rbp+8h]
  const wchar_t *v82; // [rsp+110h] [rbp+10h]
  int v83; // [rsp+118h] [rbp+18h]
  int v84; // [rsp+11Ch] [rbp+1Ch]
  const wchar_t *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  __int64 v88; // [rsp+130h] [rbp+30h]
  __int64 v89; // [rsp+138h] [rbp+38h]
  const wchar_t *v90; // [rsp+140h] [rbp+40h]
  int v91; // [rsp+148h] [rbp+48h]
  int v92; // [rsp+14Ch] [rbp+4Ch]
  const wchar_t *v93; // [rsp+150h] [rbp+50h]
  int v94; // [rsp+158h] [rbp+58h]
  int v95; // [rsp+15Ch] [rbp+5Ch]
  __int64 v96; // [rsp+160h] [rbp+60h]
  __int64 v97; // [rsp+168h] [rbp+68h]
  __int64 v98; // [rsp+170h] [rbp+70h]
  __int64 v99; // [rsp+178h] [rbp+78h]
  const wchar_t *v100; // [rsp+180h] [rbp+80h]
  int v101; // [rsp+188h] [rbp+88h]
  int v102; // [rsp+18Ch] [rbp+8Ch]

  v24 = -1;
  v25 = *a22;
  if ( *a22 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *((_BYTE *)v25 + v26) );
    v27 = v26 + 1;
  }
  else
  {
    v25 = &qword_180047B28;
    v27 = 1;
  }
  v101 = v27;
  v98 = a21;
  v96 = a20;
  v100 = v25;
  v102 = 0;
  v99 = 4;
  v28 = *a19;
  v97 = 4;
  if ( v28 )
  {
    v29 = -1;
    do
      v30 = v28[++v29] == 0;
    while ( !v30 );
    v31 = 2 * v29 + 2;
  }
  else
  {
    v28 = &Src;
    v31 = 2;
  }
  v94 = v31;
  v93 = v28;
  v95 = 0;
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
    v32 = &qword_180047B28;
    v34 = 1;
  }
  v91 = v34;
  v88 = a17;
  v90 = v32;
  v92 = 0;
  v89 = 4;
  v35 = *a16;
  if ( *a16 )
  {
    v36 = -1;
    do
      v30 = v35[++v36] == 0;
    while ( !v30 );
    v37 = 2 * v36 + 2;
  }
  else
  {
    v35 = &Src;
    v37 = 2;
  }
  v86 = v37;
  v85 = v35;
  v87 = 0;
  v38 = *a15;
  if ( *a15 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *((_BYTE *)v38 + v39) );
    v40 = v39 + 1;
  }
  else
  {
    v38 = &qword_180047B28;
    v40 = 1;
  }
  v83 = v40;
  v80 = a14;
  v82 = v38;
  v84 = 0;
  v81 = 4;
  v41 = *a13;
  if ( *a13 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *((_BYTE *)v41 + v42) );
    v43 = v42 + 1;
  }
  else
  {
    v41 = &qword_180047B28;
    v43 = 1;
  }
  v78 = v43;
  v75 = a12;
  v77 = v41;
  v79 = 0;
  v76 = 4;
  v44 = *a11;
  if ( *a11 )
  {
    v45 = -1;
    do
      v30 = v44[++v45] == 0;
    while ( !v30 );
    v46 = 2 * v45 + 2;
  }
  else
  {
    v44 = &Src;
    v46 = 2;
  }
  v73 = v46;
  v70 = a10;
  v72 = v44;
  v74 = 0;
  v71 = 4;
  v47 = *a9;
  if ( *a9 )
  {
    v48 = -1;
    do
      ++v48;
    while ( *((_BYTE *)v47 + v48) );
    v49 = v48 + 1;
  }
  else
  {
    v47 = &qword_180047B28;
    v49 = 1;
  }
  v68 = v49;
  v65 = a8;
  v67 = v47;
  v69 = 0;
  v66 = 4;
  v50 = *a7;
  if ( *a7 )
  {
    do
      ++v24;
    while ( *((_BYTE *)v50 + v24) );
    v51 = v24 + 1;
  }
  else
  {
    v50 = &qword_180047B28;
    v51 = 1;
  }
  v60 = a6;
  v58 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v63 = v51;
  v62 = v50;
  v64 = 0;
  v61 = 4;
  v59 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v56 = *(unsigned __int16 *)(a2 + 11);
  v55 = a2 + 11;
  UserData.Reserved = 2;
  v57 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, 0x14u, &UserData);
}

```

## disassembly

```asm
0x180001540  push    rbp
0x180001542  lea     rbp, [rsp-0A0h]
0x18000154a  sub     rsp, 1A0h
0x180001551  mov     rax, cs:__security_cookie
0x180001558  xor     rax, rsp
0x18000155b  mov     [rbp+0A0h+var_10], rax
0x180001562  mov     rax, [rbp+0A0h+arg_A8]
0x180001569  mov     r10, rcx
0x18000156c  mov     r9, rdx
0x18000156f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180001576  mov     r8, [rax]
0x180001579  test    r8, r8
0x18000157c  jz      short loc_18000158F
0x18000157e  mov     rax, rcx
0x180001581  inc     rax
0x180001584  cmp     byte ptr [r8+rax], 0
0x180001589  jnz     short loc_180001581
0x18000158b  inc     eax
0x18000158d  jmp     short loc_18000159B
0x18000158f  lea     r8, qword_180047B28
0x180001596  mov     eax, 1
0x18000159b  mov     [rbp+0A0h+var_18], eax
0x1800015a1  mov     rax, [rbp+0A0h+arg_A0]
0x1800015a8  mov     [rbp+0A0h+var_30], rax
0x1800015ac  mov     rax, [rbp+0A0h+arg_98]
0x1800015b3  mov     [rbp+0A0h+var_40], rax
0x1800015b7  mov     rax, [rbp+0A0h+arg_90]
0x1800015be  mov     [rbp+0A0h+var_20], r8
0x1800015c5  xor     r8d, r8d; ActivityId
0x1800015c8  mov     [rbp+0A0h+var_14], r8d
0x1800015cf  mov     [rbp+0A0h+var_28], 4
0x1800015d7  mov     rdx, [rax]
0x1800015da  mov     [rbp+0A0h+var_38], 4
0x1800015e2  test    rdx, rdx
0x1800015e5  jz      short loc_180001605
0x1800015e7  mov     rax, rcx
0x1800015ea  nop     word ptr [rax+rax+00h]
0x1800015f0  cmp     [rdx+rax*2+2], r8w
0x1800015f6  lea     rax, [rax+1]
0x1800015fa  jnz     short loc_1800015F0
0x1800015fc  lea     eax, ds:2[rax*2]
0x180001603  jmp     short loc_180001611
0x180001605  lea     rdx, Src
0x18000160c  mov     eax, 2
0x180001611  mov     [rbp+0A0h+var_48], eax
0x180001614  mov     rax, [rbp+0A0h+arg_88]
0x18000161b  mov     [rbp+0A0h+var_50], rdx
0x18000161f  mov     [rbp+0A0h+var_44], r8d
0x180001623  mov     rdx, [rax]
0x180001626  test    rdx, rdx
0x180001629  jz      short loc_18000163D
0x18000162b  mov     rax, rcx
0x18000162e  xchg    ax, ax
0x180001630  inc     rax
0x180001633  cmp     [rdx+rax], r8b
0x180001637  jnz     short loc_180001630
0x180001639  inc     eax
0x18000163b  jmp     short loc_180001649
0x18000163d  lea     rdx, qword_180047B28
0x180001644  mov     eax, 1
0x180001649  mov     [rbp+0A0h+var_58], eax
0x18000164c  mov     rax, [rbp+0A0h+arg_80]
0x180001653  mov     [rbp+0A0h+var_70], rax
0x180001657  mov     rax, [rbp+0A0h+arg_78]
0x18000165e  mov     [rbp+0A0h+var_60], rdx
0x180001662  mov     [rbp+0A0h+var_54], r8d
0x180001666  mov     [rbp+0A0h+var_68], 4
0x18000166e  mov     rdx, [rax]
0x180001671  test    rdx, rdx
0x180001674  jz      short loc_180001695
0x180001676  mov     rax, rcx
0x180001679  nop     dword ptr [rax+00000000h]
0x180001680  cmp     [rdx+rax*2+2], r8w
0x180001686  lea     rax, [rax+1]
0x18000168a  jnz     short loc_180001680
0x18000168c  lea     eax, ds:2[rax*2]
0x180001693  jmp     short loc_1800016A1
0x180001695  lea     rdx, Src
0x18000169c  mov     eax, 2
0x1800016a1  mov     [rbp+0A0h+var_78], eax
0x1800016a4  mov     rax, [rbp+0A0h+arg_70]
0x1800016ab  mov     [rbp+0A0h+var_80], rdx
0x1800016af  mov     [rbp+0A0h+var_74], r8d
0x1800016b3  mov     rdx, [rax]
0x1800016b6  test    rdx, rdx
0x1800016b9  jz      short loc_1800016CD
0x1800016bb  mov     rax, rcx
0x1800016be  xchg    ax, ax
0x1800016c0  inc     rax
0x1800016c3  cmp     [rdx+rax], r8b
0x1800016c7  jnz     short loc_1800016C0
0x1800016c9  inc     eax
0x1800016cb  jmp     short loc_1800016D9
0x1800016cd  lea     rdx, qword_180047B28
0x1800016d4  mov     eax, 1
0x1800016d9  mov     [rbp+0A0h+var_88], eax
0x1800016dc  mov     rax, [rbp+0A0h+arg_68]
0x1800016e3  mov     [rbp+0A0h+var_A0], rax
0x1800016e7  mov     rax, [rbp+0A0h+arg_60]
0x1800016ee  mov     [rbp+0A0h+var_90], rdx
0x1800016f2  mov     [rbp+0A0h+var_84], r8d
0x1800016f6  mov     [rbp+0A0h+var_98], 4
0x1800016fe  mov     rdx, [rax]
0x180001701  test    rdx, rdx
0x180001704  jz      short loc_18000171D
0x180001706  mov     rax, rcx
0x180001709  nop     dword ptr [rax+00000000h]
0x180001710  inc     rax
0x180001713  cmp     [rdx+rax], r8b
0x180001717  jnz     short loc_180001710
0x180001719  inc     eax
0x18000171b  jmp     short loc_180001729
0x18000171d  lea     rdx, qword_180047B28
0x180001724  mov     eax, 1
0x180001729  mov     [rbp+0A0h+var_A8], eax
0x18000172c  mov     rax, [rbp+0A0h+arg_58]
0x180001733  mov     [rbp+0A0h+var_C0], rax
0x180001737  mov     rax, [rbp+0A0h+arg_50]
0x18000173e  mov     [rbp+0A0h+var_B0], rdx
0x180001742  mov     [rbp+0A0h+var_A4], r8d
0x180001746  mov     [rbp+0A0h+var_B8], 4
0x18000174e  mov     rdx, [rax]
0x180001751  test    rdx, rdx
0x180001754  jz      short loc_180001775
0x180001756  mov     rax, rcx
0x180001759  nop     dword ptr [rax+00000000h]
0x180001760  cmp     [rdx+rax*2+2], r8w
0x180001766  lea     rax, [rax+1]
0x18000176a  jnz     short loc_180001760
0x18000176c  lea     eax, ds:2[rax*2]
0x180001773  jmp     short loc_180001781
0x180001775  lea     rdx, Src
0x18000177c  mov     eax, 2
0x180001781  mov     [rbp+0A0h+var_C8], eax
0x180001784  mov     rax, [rbp+0A0h+arg_48]
0x18000178b  mov     [rbp+0A0h+var_E0], rax
0x18000178f  mov     rax, [rbp+0A0h+arg_40]
0x180001796  mov     [rbp+0A0h+var_D0], rdx
0x18000179a  mov     [rbp+0A0h+var_C4], r8d
0x18000179e  mov     [rbp+0A0h+var_D8], 4
0x1800017a6  mov     rdx, [rax]
0x1800017a9  test    rdx, rdx
0x1800017ac  jz      short loc_1800017BE
0x1800017ae  mov     rax, rcx
0x1800017b1  inc     rax
0x1800017b4  cmp     [rdx+rax], r8b
0x1800017b8  jnz     short loc_1800017B1
0x1800017ba  inc     eax
0x1800017bc  jmp     short loc_1800017CA
0x1800017be  lea     rdx, qword_180047B28
0x1800017c5  mov     eax, 1
0x1800017ca  mov     [rbp+0A0h+var_E8], eax
0x1800017cd  mov     rax, [rbp+0A0h+arg_38]
0x1800017d4  mov     [rbp+0A0h+var_100], rax
0x1800017d8  mov     rax, [rbp+0A0h+arg_30]
0x1800017df  mov     [rbp+0A0h+var_F0], rdx
0x1800017e3  mov     [rbp+0A0h+var_E4], r8d
0x1800017e7  mov     [rbp+0A0h+var_F8], 4
0x1800017ef  mov     rdx, [rax]
0x1800017f2  test    rdx, rdx
0x1800017f5  jz      short loc_180001804
0x1800017f7  inc     rcx
0x1800017fa  cmp     [rdx+rcx], r8b
0x1800017fe  jnz     short loc_1800017F7
0x180001800  inc     ecx
0x180001802  jmp     short loc_180001810
0x180001804  lea     rdx, qword_180047B28
0x18000180b  mov     ecx, 1
0x180001810  mov     rax, [rbp+0A0h+arg_28]
0x180001817  mov     [rbp+0A0h+var_120], rax
0x18000181b  mov     rax, [rbp+0A0h+arg_20]
0x180001822  mov     [rsp+1A0h+var_130], rax
0x180001827  movzx   eax, byte ptr [r9]
0x18000182b  shl     eax, 18h
0x18000182e  mov     dword ptr [rsp+1A0h+EventDescriptor.Id], eax
0x180001832  movzx   eax, word ptr [r9+1]
0x180001837  mov     dword ptr [rsp+1A0h+EventDescriptor.Level], eax
0x18000183b  mov     rax, [r9+3]
0x18000183f  mov     [rsp+1A0h+EventDescriptor.Keyword], rax
0x180001844  mov     rax, [r10+8]
0x180001848  mov     [rsp+1A0h+var_150.Ptr], rax
0x18000184d  mov     [rbp+0A0h+var_108], ecx
0x180001850  lea     rcx, [r9+0Bh]
0x180001854  mov     [rbp+0A0h+var_110], rdx
0x180001858  xor     r9d, r9d; RelatedActivityId
0x18000185b  mov     [rbp+0A0h+var_104], r8d
0x18000185f  lea     rdx, [rsp+1A0h+EventDescriptor]; EventDescriptor
0x180001864  mov     [rbp+0A0h+var_118], 4
0x18000186c  mov     [rsp+1A0h+var_128], 8
0x180001875  movzx   eax, word ptr [rax]
0x180001878  mov     [rsp+1A0h+var_150.Size], eax
0x18000187c  movzx   eax, word ptr [rcx]
0x18000187f  mov     [rsp+1A0h+var_138], eax
0x180001883  lea     rax, _TraceLoggingMetadataEnd
0x18000188a  mov     [rsp+1A0h+var_140], rcx
0x18000188f  lea     rcx, _TraceLoggingMetadata
0x180001896  sub     eax, ecx
0x180001898  mov     dword ptr [rsp+1A0h+var_150.0Ch], 2
0x1800018a0  mov     [rsp+1A0h+var_134], 1
0x1800018a8  mov     [rsp+1A0h+var_170], eax
0x1800018ac  mov     eax, [rsp+1A0h+var_170]
0x1800018b0  mov     rcx, [r10+20h]; RegHandle
0x1800018b4  lea     rax, [rsp+1A0h+var_150]
0x1800018b9  mov     [rsp+1A0h+UserData], rax; UserData
0x1800018be  mov     [rsp+1A0h+UserDataCount], 14h; UserDataCount
0x1800018c6  call    cs:__imp_EventWriteTransfer
0x1800018cc  mov     rcx, [rbp+0A0h+var_10]
0x1800018d3  xor     rcx, rsp; StackCookie
0x1800018d6  call    __security_check_cookie
0x1800018db  add     rsp, 1A0h
0x1800018e2  pop     rbp
0x1800018e3  retn
```
