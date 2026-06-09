# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1800013e0`
- end: `0x180001784`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z`
- size: `932`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011ff0`

## callees

- `0x1800013e0`
- `0x1801f7110`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001766`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001766`

## pseudocode

```c
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
    v25 = &byte_1802990D8;
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
    v28 = &String;
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
    v32 = &byte_1802990D8;
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
    v35 = &String;
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
    v38 = &byte_1802990D8;
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
    v41 = &byte_1802990D8;
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
    v44 = &String;
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
    v47 = &byte_1802990D8;
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
    v50 = &byte_1802990D8;
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
0x1800013e0  push    rbp
0x1800013e2  lea     rbp, [rsp-0A0h]
0x1800013ea  sub     rsp, 1A0h
0x1800013f1  mov     rax, cs:__security_cookie
0x1800013f8  xor     rax, rsp
0x1800013fb  mov     [rbp+0A0h+var_10], rax
0x180001402  mov     rax, [rbp+0A0h+arg_A8]
0x180001409  mov     r10, rcx
0x18000140c  mov     r9, rdx
0x18000140f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180001416  mov     r8, [rax]
0x180001419  test    r8, r8
0x18000141c  jz      short loc_18000142F
0x18000141e  mov     rax, rcx
0x180001421  inc     rax
0x180001424  cmp     byte ptr [r8+rax], 0
0x180001429  jnz     short loc_180001421
0x18000142b  inc     eax
0x18000142d  jmp     short loc_18000143B
0x18000142f  lea     r8, byte_1802990D8
0x180001436  mov     eax, 1
0x18000143b  mov     [rbp+0A0h+var_18], eax
0x180001441  mov     rax, [rbp+0A0h+arg_A0]
0x180001448  mov     [rbp+0A0h+var_30], rax
0x18000144c  mov     rax, [rbp+0A0h+arg_98]
0x180001453  mov     [rbp+0A0h+var_40], rax
0x180001457  mov     rax, [rbp+0A0h+arg_90]
0x18000145e  mov     [rbp+0A0h+var_20], r8
0x180001465  xor     r8d, r8d; ActivityId
0x180001468  mov     [rbp+0A0h+var_14], r8d
0x18000146f  mov     [rbp+0A0h+var_28], 4
0x180001477  mov     rdx, [rax]
0x18000147a  mov     [rbp+0A0h+var_38], 4
0x180001482  test    rdx, rdx
0x180001485  jz      short loc_1800014A5
0x180001487  mov     rax, rcx
0x18000148a  nop     word ptr [rax+rax+00h]
0x180001490  cmp     [rdx+rax*2+2], r8w
0x180001496  lea     rax, [rax+1]
0x18000149a  jnz     short loc_180001490
0x18000149c  lea     eax, ds:2[rax*2]
0x1800014a3  jmp     short loc_1800014B1
0x1800014a5  lea     rdx, String
0x1800014ac  mov     eax, 2
0x1800014b1  mov     [rbp+0A0h+var_48], eax
0x1800014b4  mov     rax, [rbp+0A0h+arg_88]
0x1800014bb  mov     [rbp+0A0h+var_50], rdx
0x1800014bf  mov     [rbp+0A0h+var_44], r8d
0x1800014c3  mov     rdx, [rax]
0x1800014c6  test    rdx, rdx
0x1800014c9  jz      short loc_1800014DD
0x1800014cb  mov     rax, rcx
0x1800014ce  xchg    ax, ax
0x1800014d0  inc     rax
0x1800014d3  cmp     [rdx+rax], r8b
0x1800014d7  jnz     short loc_1800014D0
0x1800014d9  inc     eax
0x1800014db  jmp     short loc_1800014E9
0x1800014dd  lea     rdx, byte_1802990D8
0x1800014e4  mov     eax, 1
0x1800014e9  mov     [rbp+0A0h+var_58], eax
0x1800014ec  mov     rax, [rbp+0A0h+arg_80]
0x1800014f3  mov     [rbp+0A0h+var_70], rax
0x1800014f7  mov     rax, [rbp+0A0h+arg_78]
0x1800014fe  mov     [rbp+0A0h+var_60], rdx
0x180001502  mov     [rbp+0A0h+var_54], r8d
0x180001506  mov     [rbp+0A0h+var_68], 4
0x18000150e  mov     rdx, [rax]
0x180001511  test    rdx, rdx
0x180001514  jz      short loc_180001535
0x180001516  mov     rax, rcx
0x180001519  nop     dword ptr [rax+00000000h]
0x180001520  cmp     [rdx+rax*2+2], r8w
0x180001526  lea     rax, [rax+1]
0x18000152a  jnz     short loc_180001520
0x18000152c  lea     eax, ds:2[rax*2]
0x180001533  jmp     short loc_180001541
0x180001535  lea     rdx, String
0x18000153c  mov     eax, 2
0x180001541  mov     [rbp+0A0h+var_78], eax
0x180001544  mov     rax, [rbp+0A0h+arg_70]
0x18000154b  mov     [rbp+0A0h+var_80], rdx
0x18000154f  mov     [rbp+0A0h+var_74], r8d
0x180001553  mov     rdx, [rax]
0x180001556  test    rdx, rdx
0x180001559  jz      short loc_18000156D
0x18000155b  mov     rax, rcx
0x18000155e  xchg    ax, ax
0x180001560  inc     rax
0x180001563  cmp     [rdx+rax], r8b
0x180001567  jnz     short loc_180001560
0x180001569  inc     eax
0x18000156b  jmp     short loc_180001579
0x18000156d  lea     rdx, byte_1802990D8
0x180001574  mov     eax, 1
0x180001579  mov     [rbp+0A0h+var_88], eax
0x18000157c  mov     rax, [rbp+0A0h+arg_68]
0x180001583  mov     [rbp+0A0h+var_A0], rax
0x180001587  mov     rax, [rbp+0A0h+arg_60]
0x18000158e  mov     [rbp+0A0h+var_90], rdx
0x180001592  mov     [rbp+0A0h+var_84], r8d
0x180001596  mov     [rbp+0A0h+var_98], 4
0x18000159e  mov     rdx, [rax]
0x1800015a1  test    rdx, rdx
0x1800015a4  jz      short loc_1800015BD
0x1800015a6  mov     rax, rcx
0x1800015a9  nop     dword ptr [rax+00000000h]
0x1800015b0  inc     rax
0x1800015b3  cmp     [rdx+rax], r8b
0x1800015b7  jnz     short loc_1800015B0
0x1800015b9  inc     eax
0x1800015bb  jmp     short loc_1800015C9
0x1800015bd  lea     rdx, byte_1802990D8
0x1800015c4  mov     eax, 1
0x1800015c9  mov     [rbp+0A0h+var_A8], eax
0x1800015cc  mov     rax, [rbp+0A0h+arg_58]
0x1800015d3  mov     [rbp+0A0h+var_C0], rax
0x1800015d7  mov     rax, [rbp+0A0h+arg_50]
0x1800015de  mov     [rbp+0A0h+var_B0], rdx
0x1800015e2  mov     [rbp+0A0h+var_A4], r8d
0x1800015e6  mov     [rbp+0A0h+var_B8], 4
0x1800015ee  mov     rdx, [rax]
0x1800015f1  test    rdx, rdx
0x1800015f4  jz      short loc_180001615
0x1800015f6  mov     rax, rcx
0x1800015f9  nop     dword ptr [rax+00000000h]
0x180001600  cmp     [rdx+rax*2+2], r8w
0x180001606  lea     rax, [rax+1]
0x18000160a  jnz     short loc_180001600
0x18000160c  lea     eax, ds:2[rax*2]
0x180001613  jmp     short loc_180001621
0x180001615  lea     rdx, String
0x18000161c  mov     eax, 2
0x180001621  mov     [rbp+0A0h+var_C8], eax
0x180001624  mov     rax, [rbp+0A0h+arg_48]
0x18000162b  mov     [rbp+0A0h+var_E0], rax
0x18000162f  mov     rax, [rbp+0A0h+arg_40]
0x180001636  mov     [rbp+0A0h+var_D0], rdx
0x18000163a  mov     [rbp+0A0h+var_C4], r8d
0x18000163e  mov     [rbp+0A0h+var_D8], 4
0x180001646  mov     rdx, [rax]
0x180001649  test    rdx, rdx
0x18000164c  jz      short loc_18000165E
0x18000164e  mov     rax, rcx
0x180001651  inc     rax
0x180001654  cmp     [rdx+rax], r8b
0x180001658  jnz     short loc_180001651
0x18000165a  inc     eax
0x18000165c  jmp     short loc_18000166A
0x18000165e  lea     rdx, byte_1802990D8
0x180001665  mov     eax, 1
0x18000166a  mov     [rbp+0A0h+var_E8], eax
0x18000166d  mov     rax, [rbp+0A0h+arg_38]
0x180001674  mov     [rbp+0A0h+var_100], rax
0x180001678  mov     rax, [rbp+0A0h+arg_30]
0x18000167f  mov     [rbp+0A0h+var_F0], rdx
0x180001683  mov     [rbp+0A0h+var_E4], r8d
0x180001687  mov     [rbp+0A0h+var_F8], 4
0x18000168f  mov     rdx, [rax]
0x180001692  test    rdx, rdx
0x180001695  jz      short loc_1800016A4
0x180001697  inc     rcx
0x18000169a  cmp     [rdx+rcx], r8b
0x18000169e  jnz     short loc_180001697
0x1800016a0  inc     ecx
0x1800016a2  jmp     short loc_1800016B0
0x1800016a4  lea     rdx, byte_1802990D8
0x1800016ab  mov     ecx, 1
0x1800016b0  mov     rax, [rbp+0A0h+arg_28]
0x1800016b7  mov     [rbp+0A0h+var_120], rax
0x1800016bb  mov     rax, [rbp+0A0h+arg_20]
0x1800016c2  mov     [rsp+1A0h+var_130], rax
0x1800016c7  movzx   eax, byte ptr [r9]
0x1800016cb  shl     eax, 18h
0x1800016ce  mov     dword ptr [rsp+1A0h+EventDescriptor.Id], eax
0x1800016d2  movzx   eax, word ptr [r9+1]
0x1800016d7  mov     dword ptr [rsp+1A0h+EventDescriptor.Level], eax
0x1800016db  mov     rax, [r9+3]
0x1800016df  mov     [rsp+1A0h+EventDescriptor.Keyword], rax
0x1800016e4  mov     rax, [r10+8]
0x1800016e8  mov     [rsp+1A0h+var_150.Ptr], rax
0x1800016ed  mov     [rbp+0A0h+var_108], ecx
0x1800016f0  lea     rcx, [r9+0Bh]
0x1800016f4  mov     [rbp+0A0h+var_110], rdx
0x1800016f8  xor     r9d, r9d; RelatedActivityId
0x1800016fb  mov     [rbp+0A0h+var_104], r8d
0x1800016ff  lea     rdx, [rsp+1A0h+EventDescriptor]; EventDescriptor
0x180001704  mov     [rbp+0A0h+var_118], 4
0x18000170c  mov     [rsp+1A0h+var_128], 8
0x180001715  movzx   eax, word ptr [rax]
0x180001718  mov     [rsp+1A0h+var_150.Size], eax
0x18000171c  movzx   eax, word ptr [rcx]
0x18000171f  mov     [rsp+1A0h+var_138], eax
0x180001723  lea     rax, _TraceLoggingMetadataEnd
0x18000172a  mov     [rsp+1A0h+var_140], rcx
0x18000172f  lea     rcx, _TraceLoggingMetadata
0x180001736  sub     eax, ecx
0x180001738  mov     dword ptr [rsp+1A0h+var_150.0Ch], 2
0x180001740  mov     [rsp+1A0h+var_134], 1
0x180001748  mov     [rsp+1A0h+var_170], eax
0x18000174c  mov     eax, [rsp+1A0h+var_170]
0x180001750  mov     rcx, [r10+20h]; RegHandle
0x180001754  lea     rax, [rsp+1A0h+var_150]
0x180001759  mov     [rsp+1A0h+UserData], rax; UserData
0x18000175e  mov     [rsp+1A0h+UserDataCount], 14h; UserDataCount
0x180001766  call    cs:__imp_EventWriteTransfer
0x18000176c  mov     rcx, [rbp+0A0h+var_10]
0x180001773  xor     rcx, rsp; StackCookie
0x180001776  call    __security_check_cookie
0x18000177b  add     rsp, 1A0h
0x180001782  pop     rbp
0x180001783  retn
```
