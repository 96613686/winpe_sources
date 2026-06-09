# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)

- ea: `0x180001490`
- end: `0x1800017c4`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z`
- size: `820`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, __int64, __int64, __int64, const wchar_t **, __int64, const wchar_t **, __int64, const wchar_t **, __int64, const wchar_t **, __int64, const wchar_t **, const wchar_t **, __int64, const wchar_t **, const wchar_t **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010480`

## callees

- `0x180001490`
- `0x1800181b0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800017a9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800017a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
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
        const wchar_t **a19)
{
  __int64 v22; // rcx
  const wchar_t *v23; // r8
  __int64 v24; // rax
  bool v25; // zf
  int v26; // eax
  const wchar_t *v27; // rdx
  __int64 v28; // rax
  int v29; // eax
  const wchar_t *v30; // rdx
  __int64 v31; // rax
  int v32; // eax
  const wchar_t *v33; // rdx
  __int64 v34; // rax
  int v35; // eax
  const wchar_t *v36; // rdx
  __int64 v37; // rax
  int v38; // eax
  const wchar_t *v39; // rdx
  __int64 v40; // rax
  int v41; // eax
  const wchar_t *v42; // rdx
  __int64 v43; // rax
  int v44; // eax
  const wchar_t *v45; // rdx
  int v46; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v50; // [rsp+60h] [rbp-A0h]
  int v51; // [rsp+68h] [rbp-98h]
  int v52; // [rsp+6Ch] [rbp-94h]
  __int64 v53; // [rsp+70h] [rbp-90h]
  __int64 v54; // [rsp+78h] [rbp-88h]
  __int64 v55; // [rsp+80h] [rbp-80h]
  __int64 v56; // [rsp+88h] [rbp-78h]
  const wchar_t *v57; // [rsp+90h] [rbp-70h]
  int v58; // [rsp+98h] [rbp-68h]
  int v59; // [rsp+9Ch] [rbp-64h]
  __int64 v60; // [rsp+A0h] [rbp-60h]
  __int64 v61; // [rsp+A8h] [rbp-58h]
  const wchar_t *v62; // [rsp+B0h] [rbp-50h]
  int v63; // [rsp+B8h] [rbp-48h]
  int v64; // [rsp+BCh] [rbp-44h]
  __int64 v65; // [rsp+C0h] [rbp-40h]
  __int64 v66; // [rsp+C8h] [rbp-38h]
  const wchar_t *v67; // [rsp+D0h] [rbp-30h]
  int v68; // [rsp+D8h] [rbp-28h]
  int v69; // [rsp+DCh] [rbp-24h]
  __int64 v70; // [rsp+E0h] [rbp-20h]
  __int64 v71; // [rsp+E8h] [rbp-18h]
  const wchar_t *v72; // [rsp+F0h] [rbp-10h]
  int v73; // [rsp+F8h] [rbp-8h]
  int v74; // [rsp+FCh] [rbp-4h]
  __int64 v75; // [rsp+100h] [rbp+0h]
  __int64 v76; // [rsp+108h] [rbp+8h]
  const wchar_t *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  const wchar_t *v80; // [rsp+120h] [rbp+20h]
  int v81; // [rsp+128h] [rbp+28h]
  int v82; // [rsp+12Ch] [rbp+2Ch]
  __int64 v83; // [rsp+130h] [rbp+30h]
  __int64 v84; // [rsp+138h] [rbp+38h]
  const wchar_t *v85; // [rsp+140h] [rbp+40h]
  int v86; // [rsp+148h] [rbp+48h]
  int v87; // [rsp+14Ch] [rbp+4Ch]
  const wchar_t *v88; // [rsp+150h] [rbp+50h]
  int v89; // [rsp+158h] [rbp+58h]
  int v90; // [rsp+15Ch] [rbp+5Ch]

  v22 = -1;
  v23 = *a19;
  if ( *a19 )
  {
    v24 = -1;
    do
      v25 = v23[++v24] == 0;
    while ( !v25 );
    v26 = 2 * v24 + 2;
  }
  else
  {
    v23 = &S2;
    v26 = 2;
  }
  v89 = v26;
  v88 = v23;
  v90 = 0;
  v27 = *a18;
  if ( *a18 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *((_BYTE *)v27 + v28) );
    v29 = v28 + 1;
  }
  else
  {
    v27 = &qword_1800250A8;
    v29 = 1;
  }
  v86 = v29;
  v83 = a17;
  v85 = v27;
  v87 = 0;
  v84 = 4;
  v30 = *a16;
  if ( *a16 )
  {
    v31 = -1;
    do
      v25 = v30[++v31] == 0;
    while ( !v25 );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &S2;
    v32 = 2;
  }
  v81 = v32;
  v80 = v30;
  v82 = 0;
  v33 = *a15;
  if ( *a15 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_BYTE *)v33 + v34) );
    v35 = v34 + 1;
  }
  else
  {
    v33 = &qword_1800250A8;
    v35 = 1;
  }
  v78 = v35;
  v75 = a14;
  v77 = v33;
  v79 = 0;
  v76 = 4;
  v36 = *a13;
  if ( *a13 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_BYTE *)v36 + v37) );
    v38 = v37 + 1;
  }
  else
  {
    v36 = &qword_1800250A8;
    v38 = 1;
  }
  v73 = v38;
  v70 = a12;
  v72 = v36;
  v74 = 0;
  v71 = 4;
  v39 = *a11;
  if ( *a11 )
  {
    v40 = -1;
    do
      v25 = v39[++v40] == 0;
    while ( !v25 );
    v41 = 2 * v40 + 2;
  }
  else
  {
    v39 = &S2;
    v41 = 2;
  }
  v68 = v41;
  v65 = a10;
  v67 = v39;
  v69 = 0;
  v66 = 4;
  v42 = *a9;
  if ( *a9 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &qword_1800250A8;
    v44 = 1;
  }
  v63 = v44;
  v60 = a8;
  v62 = v42;
  v64 = 0;
  v61 = 4;
  v45 = *a7;
  if ( *a7 )
  {
    do
      ++v22;
    while ( *((_BYTE *)v45 + v22) );
    v46 = v22 + 1;
  }
  else
  {
    v45 = &qword_1800250A8;
    v46 = 1;
  }
  v55 = a6;
  v53 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v58 = v46;
  v57 = v45;
  v59 = 0;
  v56 = 4;
  v54 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v51 = *(unsigned __int16 *)(a2 + 11);
  v50 = a2 + 11;
  UserData.Reserved = 2;
  v52 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, 0, 0x11u, &UserData);
}

```

## disassembly

```asm
0x180001490  push    rbp
0x180001492  lea     rbp, [rsp-70h]
0x180001497  sub     rsp, 170h
0x18000149e  mov     rax, cs:__security_cookie
0x1800014a5  xor     rax, rsp
0x1800014a8  mov     [rbp+70h+var_10], rax
0x1800014ac  mov     rax, [rbp+70h+arg_90]
0x1800014b3  mov     r11, r8
0x1800014b6  mov     r10, rcx
0x1800014b9  mov     r9, rdx
0x1800014bc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800014c3  mov     r8, [rax]
0x1800014c6  test    r8, r8
0x1800014c9  jz      short loc_1800014E6
0x1800014cb  mov     rax, rcx
0x1800014ce  xchg    ax, ax
0x1800014d0  cmp     word ptr [r8+rax*2+2], 0
0x1800014d7  lea     rax, [rax+1]
0x1800014db  jnz     short loc_1800014D0
0x1800014dd  lea     eax, ds:2[rax*2]
0x1800014e4  jmp     short loc_1800014F2
0x1800014e6  lea     r8, S2
0x1800014ed  mov     eax, 2
0x1800014f2  mov     [rbp+70h+var_18], eax
0x1800014f5  mov     rax, [rbp+70h+arg_88]
0x1800014fc  mov     [rbp+70h+var_20], r8
0x180001500  xor     r8d, r8d
0x180001503  mov     [rbp+70h+var_14], r8d
0x180001507  mov     rdx, [rax]
0x18000150a  test    rdx, rdx
0x18000150d  jz      short loc_18000151F
0x18000150f  mov     rax, rcx
0x180001512  inc     rax
0x180001515  cmp     [rdx+rax], r8b
0x180001519  jnz     short loc_180001512
0x18000151b  inc     eax
0x18000151d  jmp     short loc_18000152B
0x18000151f  lea     rdx, qword_1800250A8
0x180001526  mov     eax, 1
0x18000152b  mov     [rbp+70h+var_28], eax
0x18000152e  mov     rax, [rbp+70h+arg_80]
0x180001535  mov     [rbp+70h+var_40], rax
0x180001539  mov     rax, [rbp+70h+arg_78]
0x180001540  mov     [rbp+70h+var_30], rdx
0x180001544  mov     [rbp+70h+var_24], r8d
0x180001548  mov     [rbp+70h+var_38], 4
0x180001550  mov     rdx, [rax]
0x180001553  test    rdx, rdx
0x180001556  jz      short loc_180001575
0x180001558  mov     rax, rcx
0x18000155b  nop     dword ptr [rax+rax+00h]
0x180001560  cmp     [rdx+rax*2+2], r8w
0x180001566  lea     rax, [rax+1]
0x18000156a  jnz     short loc_180001560
0x18000156c  lea     eax, ds:2[rax*2]
0x180001573  jmp     short loc_180001581
0x180001575  lea     rdx, S2
0x18000157c  mov     eax, 2
0x180001581  mov     [rbp+70h+var_48], eax
0x180001584  mov     rax, [rbp+70h+arg_70]
0x18000158b  mov     [rbp+70h+var_50], rdx
0x18000158f  mov     [rbp+70h+var_44], r8d
0x180001593  mov     rdx, [rax]
0x180001596  test    rdx, rdx
0x180001599  jz      short loc_1800015AD
0x18000159b  mov     rax, rcx
0x18000159e  xchg    ax, ax
0x1800015a0  inc     rax
0x1800015a3  cmp     [rdx+rax], r8b
0x1800015a7  jnz     short loc_1800015A0
0x1800015a9  inc     eax
0x1800015ab  jmp     short loc_1800015B9
0x1800015ad  lea     rdx, qword_1800250A8
0x1800015b4  mov     eax, 1
0x1800015b9  mov     [rbp+70h+var_58], eax
0x1800015bc  mov     rax, [rbp+70h+arg_68]
0x1800015c3  mov     [rbp+70h+var_70], rax
0x1800015c7  mov     rax, [rbp+70h+arg_60]
0x1800015ce  mov     [rbp+70h+var_60], rdx
0x1800015d2  mov     [rbp+70h+var_54], r8d
0x1800015d6  mov     [rbp+70h+var_68], 4
0x1800015de  mov     rdx, [rax]
0x1800015e1  test    rdx, rdx
0x1800015e4  jz      short loc_1800015FD
0x1800015e6  mov     rax, rcx
0x1800015e9  nop     dword ptr [rax+00000000h]
0x1800015f0  inc     rax
0x1800015f3  cmp     [rdx+rax], r8b
0x1800015f7  jnz     short loc_1800015F0
0x1800015f9  inc     eax
0x1800015fb  jmp     short loc_180001609
0x1800015fd  lea     rdx, qword_1800250A8
0x180001604  mov     eax, 1
0x180001609  mov     [rbp+70h+var_78], eax
0x18000160c  mov     rax, [rbp+70h+arg_58]
0x180001613  mov     [rbp+70h+var_90], rax
0x180001617  mov     rax, [rbp+70h+arg_50]
0x18000161e  mov     [rbp+70h+var_80], rdx
0x180001622  mov     [rbp+70h+var_74], r8d
0x180001626  mov     [rbp+70h+var_88], 4
0x18000162e  mov     rdx, [rax]
0x180001631  test    rdx, rdx
0x180001634  jz      short loc_180001655
0x180001636  mov     rax, rcx
0x180001639  nop     dword ptr [rax+00000000h]
0x180001640  cmp     [rdx+rax*2+2], r8w
0x180001646  lea     rax, [rax+1]
0x18000164a  jnz     short loc_180001640
0x18000164c  lea     eax, ds:2[rax*2]
0x180001653  jmp     short loc_180001661
0x180001655  lea     rdx, S2
0x18000165c  mov     eax, 2
0x180001661  mov     [rbp+70h+var_98], eax
0x180001664  mov     rax, [rbp+70h+arg_48]
0x18000166b  mov     [rbp+70h+var_B0], rax
0x18000166f  mov     rax, [rbp+70h+arg_40]
0x180001676  mov     [rbp+70h+var_A0], rdx
0x18000167a  mov     [rbp+70h+var_94], r8d
0x18000167e  mov     [rbp+70h+var_A8], 4
0x180001686  mov     rdx, [rax]
0x180001689  test    rdx, rdx
0x18000168c  jz      short loc_18000169E
0x18000168e  mov     rax, rcx
0x180001691  inc     rax
0x180001694  cmp     [rdx+rax], r8b
0x180001698  jnz     short loc_180001691
0x18000169a  inc     eax
0x18000169c  jmp     short loc_1800016AA
0x18000169e  lea     rdx, qword_1800250A8
0x1800016a5  mov     eax, 1
0x1800016aa  mov     [rbp+70h+var_B8], eax
0x1800016ad  mov     rax, [rbp+70h+arg_38]
0x1800016b4  mov     [rbp+70h+var_D0], rax
0x1800016b8  mov     rax, [rbp+70h+arg_30]
0x1800016bf  mov     [rbp+70h+var_C0], rdx
0x1800016c3  mov     [rbp+70h+var_B4], r8d
0x1800016c7  mov     [rbp+70h+var_C8], 4
0x1800016cf  mov     rdx, [rax]
0x1800016d2  test    rdx, rdx
0x1800016d5  jz      short loc_1800016E4
0x1800016d7  inc     rcx
0x1800016da  cmp     [rdx+rcx], r8b
0x1800016de  jnz     short loc_1800016D7
0x1800016e0  inc     ecx
0x1800016e2  jmp     short loc_1800016F0
0x1800016e4  lea     rdx, qword_1800250A8
0x1800016eb  mov     ecx, 1
0x1800016f0  mov     rax, [rbp+70h+arg_28]
0x1800016f7  mov     [rbp+70h+var_F0], rax
0x1800016fb  mov     rax, [rbp+70h+arg_20]
0x180001702  mov     [rsp+170h+var_100], rax
0x180001707  movzx   eax, byte ptr [r9]
0x18000170b  shl     eax, 18h
0x18000170e  mov     dword ptr [rsp+170h+EventDescriptor.Id], eax
0x180001712  movzx   eax, word ptr [r9+1]
0x180001717  mov     dword ptr [rsp+170h+EventDescriptor.Level], eax
0x18000171b  mov     rax, [r9+3]
0x18000171f  mov     [rsp+170h+EventDescriptor.Keyword], rax
0x180001724  mov     rax, [r10+8]
0x180001728  mov     [rsp+170h+var_120.Ptr], rax
0x18000172d  mov     [rbp+70h+var_D8], ecx
0x180001730  lea     rcx, [r9+0Bh]
0x180001734  mov     [rbp+70h+var_E0], rdx
0x180001738  xor     r9d, r9d; RelatedActivityId
0x18000173b  mov     [rbp+70h+var_D4], r8d
0x18000173f  lea     rdx, [rsp+170h+EventDescriptor]; EventDescriptor
0x180001744  mov     [rbp+70h+var_E8], 4
0x18000174c  mov     r8, r11; ActivityId
0x18000174f  mov     [rsp+170h+var_F8], 8
0x180001758  movzx   eax, word ptr [rax]
0x18000175b  mov     [rsp+170h+var_120.Size], eax
0x18000175f  movzx   eax, word ptr [rcx]
0x180001762  mov     [rsp+170h+var_108], eax
0x180001766  lea     rax, _TraceLoggingMetadataEnd
0x18000176d  mov     [rsp+170h+var_110], rcx
0x180001772  lea     rcx, _TraceLoggingMetadata
0x180001779  sub     eax, ecx
0x18000177b  mov     dword ptr [rsp+170h+var_120.0Ch], 2
0x180001783  mov     [rsp+170h+var_104], 1
0x18000178b  mov     [rsp+170h+var_140], eax
0x18000178f  mov     eax, [rsp+170h+var_140]
0x180001793  mov     rcx, [r10+20h]; RegHandle
0x180001797  lea     rax, [rsp+170h+var_120]
0x18000179c  mov     [rsp+170h+UserData], rax; UserData
0x1800017a1  mov     [rsp+170h+UserDataCount], 11h; UserDataCount
0x1800017a9  call    cs:__imp_EventWriteTransfer
0x1800017af  mov     rcx, [rbp+70h+var_10]
0x1800017b3  xor     rcx, rsp; StackCookie
0x1800017b6  call    __security_check_cookie
0x1800017bb  add     rsp, 170h
0x1800017c2  pop     rbp
0x1800017c3  retn
```
