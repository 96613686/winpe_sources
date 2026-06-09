# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)

- ea: `0x1800011f0`
- end: `0x180001534`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z`
- size: `836`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64, __int64, __int64, const wchar_t **, __int64, const wchar_t **, __int64, const wchar_t **, __int64, const wchar_t **, __int64, const wchar_t **, const wchar_t **, __int64, const wchar_t **, const wchar_t **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011600`

## callees

- `0x1800011f0`
- `0x180034ef0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180001519`
- `ADVAPI32!EventWriteTransfer` at `0x180001519`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const wchar_t **a8,
        __int64 a9,
        const wchar_t **a10,
        __int64 a11,
        const wchar_t **a12,
        __int64 a13,
        const wchar_t **a14,
        __int64 a15,
        const wchar_t **a16,
        const wchar_t **a17,
        __int64 a18,
        const wchar_t **a19,
        const wchar_t **a20)
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
  __int64 v57; // [rsp+90h] [rbp-70h]
  __int64 v58; // [rsp+98h] [rbp-68h]
  const wchar_t *v59; // [rsp+A0h] [rbp-60h]
  int v60; // [rsp+A8h] [rbp-58h]
  int v61; // [rsp+ACh] [rbp-54h]
  __int64 v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+B8h] [rbp-48h]
  const wchar_t *v64; // [rsp+C0h] [rbp-40h]
  int v65; // [rsp+C8h] [rbp-38h]
  int v66; // [rsp+CCh] [rbp-34h]
  __int64 v67; // [rsp+D0h] [rbp-30h]
  __int64 v68; // [rsp+D8h] [rbp-28h]
  const wchar_t *v69; // [rsp+E0h] [rbp-20h]
  int v70; // [rsp+E8h] [rbp-18h]
  int v71; // [rsp+ECh] [rbp-14h]
  __int64 v72; // [rsp+F0h] [rbp-10h]
  __int64 v73; // [rsp+F8h] [rbp-8h]
  const wchar_t *v74; // [rsp+100h] [rbp+0h]
  int v75; // [rsp+108h] [rbp+8h]
  int v76; // [rsp+10Ch] [rbp+Ch]
  __int64 v77; // [rsp+110h] [rbp+10h]
  __int64 v78; // [rsp+118h] [rbp+18h]
  const wchar_t *v79; // [rsp+120h] [rbp+20h]
  int v80; // [rsp+128h] [rbp+28h]
  int v81; // [rsp+12Ch] [rbp+2Ch]
  const wchar_t *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  __int64 v85; // [rsp+140h] [rbp+40h]
  __int64 v86; // [rsp+148h] [rbp+48h]
  const wchar_t *v87; // [rsp+150h] [rbp+50h]
  int v88; // [rsp+158h] [rbp+58h]
  int v89; // [rsp+15Ch] [rbp+5Ch]
  const wchar_t *v90; // [rsp+160h] [rbp+60h]
  int v91; // [rsp+168h] [rbp+68h]
  int v92; // [rsp+16Ch] [rbp+6Ch]

  v22 = -1;
  v23 = *a20;
  if ( *a20 )
  {
    v24 = -1;
    do
      v25 = v23[++v24] == 0;
    while ( !v25 );
    v26 = 2 * v24 + 2;
  }
  else
  {
    v23 = &Src;
    v26 = 2;
  }
  v91 = v26;
  v90 = v23;
  v92 = 0;
  v27 = *a19;
  if ( *a19 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *((_BYTE *)v27 + v28) );
    v29 = v28 + 1;
  }
  else
  {
    v27 = &qword_180047B28;
    v29 = 1;
  }
  v88 = v29;
  v85 = a18;
  v87 = v27;
  v89 = 0;
  v86 = 4;
  v30 = *a17;
  if ( *a17 )
  {
    v31 = -1;
    do
      v25 = v30[++v31] == 0;
    while ( !v25 );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &Src;
    v32 = 2;
  }
  v83 = v32;
  v82 = v30;
  v84 = 0;
  v33 = *a16;
  if ( *a16 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_BYTE *)v33 + v34) );
    v35 = v34 + 1;
  }
  else
  {
    v33 = &qword_180047B28;
    v35 = 1;
  }
  v80 = v35;
  v77 = a15;
  v79 = v33;
  v81 = 0;
  v78 = 4;
  v36 = *a14;
  if ( *a14 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_BYTE *)v36 + v37) );
    v38 = v37 + 1;
  }
  else
  {
    v36 = &qword_180047B28;
    v38 = 1;
  }
  v75 = v38;
  v72 = a13;
  v74 = v36;
  v76 = 0;
  v73 = 4;
  v39 = *a12;
  if ( *a12 )
  {
    v40 = -1;
    do
      v25 = v39[++v40] == 0;
    while ( !v25 );
    v41 = 2 * v40 + 2;
  }
  else
  {
    v39 = &Src;
    v41 = 2;
  }
  v70 = v41;
  v67 = a11;
  v69 = v39;
  v71 = 0;
  v68 = 4;
  v42 = *a10;
  if ( *a10 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &qword_180047B28;
    v44 = 1;
  }
  v65 = v44;
  v62 = a9;
  v64 = v42;
  v66 = 0;
  v63 = 4;
  v45 = *a8;
  if ( *a8 )
  {
    do
      ++v22;
    while ( *((_BYTE *)v45 + v22) );
    v46 = v22 + 1;
  }
  else
  {
    v45 = &qword_180047B28;
    v46 = 1;
  }
  v57 = a7;
  v55 = a6;
  v53 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v60 = v46;
  v59 = v45;
  v61 = 0;
  v58 = 4;
  v56 = 8;
  v54 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v51 = *(unsigned __int16 *)(a2 + 11);
  v50 = a2 + 11;
  UserData.Reserved = 2;
  v52 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, 0x12u, &UserData);
}

```

## disassembly

```asm
0x1800011f0  push    rbp
0x1800011f2  lea     rbp, [rsp-80h]
0x1800011f7  sub     rsp, 180h
0x1800011fe  mov     rax, cs:__security_cookie
0x180001205  xor     rax, rsp
0x180001208  mov     [rbp+80h+var_10], rax
0x18000120c  mov     rax, [rbp+80h+arg_98]
0x180001213  mov     r10, rcx
0x180001216  mov     r9, rdx
0x180001219  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180001220  mov     r8, [rax]
0x180001223  test    r8, r8
0x180001226  jz      short loc_180001246
0x180001228  mov     rax, rcx
0x18000122b  nop     dword ptr [rax+rax+00h]
0x180001230  cmp     word ptr [r8+rax*2+2], 0
0x180001237  lea     rax, [rax+1]
0x18000123b  jnz     short loc_180001230
0x18000123d  lea     eax, ds:2[rax*2]
0x180001244  jmp     short loc_180001252
0x180001246  lea     r8, Src
0x18000124d  mov     eax, 2
0x180001252  mov     [rbp+80h+var_18], eax
0x180001255  mov     rax, [rbp+80h+arg_90]
0x18000125c  mov     [rbp+80h+var_20], r8
0x180001260  xor     r8d, r8d; ActivityId
0x180001263  mov     [rbp+80h+var_14], r8d
0x180001267  mov     rdx, [rax]
0x18000126a  test    rdx, rdx
0x18000126d  jz      short loc_18000127F
0x18000126f  mov     rax, rcx
0x180001272  inc     rax
0x180001275  cmp     [rdx+rax], r8b
0x180001279  jnz     short loc_180001272
0x18000127b  inc     eax
0x18000127d  jmp     short loc_18000128B
0x18000127f  lea     rdx, qword_180047B28
0x180001286  mov     eax, 1
0x18000128b  mov     [rbp+80h+var_28], eax
0x18000128e  mov     rax, [rbp+80h+arg_88]
0x180001295  mov     [rbp+80h+var_40], rax
0x180001299  mov     rax, [rbp+80h+arg_80]
0x1800012a0  mov     [rbp+80h+var_30], rdx
0x1800012a4  mov     [rbp+80h+var_24], r8d
0x1800012a8  mov     [rbp+80h+var_38], 4
0x1800012b0  mov     rdx, [rax]
0x1800012b3  test    rdx, rdx
0x1800012b6  jz      short loc_1800012D5
0x1800012b8  mov     rax, rcx
0x1800012bb  nop     dword ptr [rax+rax+00h]
0x1800012c0  cmp     [rdx+rax*2+2], r8w
0x1800012c6  lea     rax, [rax+1]
0x1800012ca  jnz     short loc_1800012C0
0x1800012cc  lea     eax, ds:2[rax*2]
0x1800012d3  jmp     short loc_1800012E1
0x1800012d5  lea     rdx, Src
0x1800012dc  mov     eax, 2
0x1800012e1  mov     [rbp+80h+var_48], eax
0x1800012e4  mov     rax, [rbp+80h+arg_78]
0x1800012eb  mov     [rbp+80h+var_50], rdx
0x1800012ef  mov     [rbp+80h+var_44], r8d
0x1800012f3  mov     rdx, [rax]
0x1800012f6  test    rdx, rdx
0x1800012f9  jz      short loc_18000130D
0x1800012fb  mov     rax, rcx
0x1800012fe  xchg    ax, ax
0x180001300  inc     rax
0x180001303  cmp     [rdx+rax], r8b
0x180001307  jnz     short loc_180001300
0x180001309  inc     eax
0x18000130b  jmp     short loc_180001319
0x18000130d  lea     rdx, qword_180047B28
0x180001314  mov     eax, 1
0x180001319  mov     [rbp+80h+var_58], eax
0x18000131c  mov     rax, [rbp+80h+arg_70]
0x180001323  mov     [rbp+80h+var_70], rax
0x180001327  mov     rax, [rbp+80h+arg_68]
0x18000132e  mov     [rbp+80h+var_60], rdx
0x180001332  mov     [rbp+80h+var_54], r8d
0x180001336  mov     [rbp+80h+var_68], 4
0x18000133e  mov     rdx, [rax]
0x180001341  test    rdx, rdx
0x180001344  jz      short loc_18000135D
0x180001346  mov     rax, rcx
0x180001349  nop     dword ptr [rax+00000000h]
0x180001350  inc     rax
0x180001353  cmp     [rdx+rax], r8b
0x180001357  jnz     short loc_180001350
0x180001359  inc     eax
0x18000135b  jmp     short loc_180001369
0x18000135d  lea     rdx, qword_180047B28
0x180001364  mov     eax, 1
0x180001369  mov     [rbp+80h+var_78], eax
0x18000136c  mov     rax, [rbp+80h+arg_60]
0x180001373  mov     [rbp+80h+var_90], rax
0x180001377  mov     rax, [rbp+80h+arg_58]
0x18000137e  mov     [rbp+80h+var_80], rdx
0x180001382  mov     [rbp+80h+var_74], r8d
0x180001386  mov     [rbp+80h+var_88], 4
0x18000138e  mov     rdx, [rax]
0x180001391  test    rdx, rdx
0x180001394  jz      short loc_1800013B5
0x180001396  mov     rax, rcx
0x180001399  nop     dword ptr [rax+00000000h]
0x1800013a0  cmp     [rdx+rax*2+2], r8w
0x1800013a6  lea     rax, [rax+1]
0x1800013aa  jnz     short loc_1800013A0
0x1800013ac  lea     eax, ds:2[rax*2]
0x1800013b3  jmp     short loc_1800013C1
0x1800013b5  lea     rdx, Src
0x1800013bc  mov     eax, 2
0x1800013c1  mov     [rbp+80h+var_98], eax
0x1800013c4  mov     rax, [rbp+80h+arg_50]
0x1800013cb  mov     [rbp+80h+var_B0], rax
0x1800013cf  mov     rax, [rbp+80h+arg_48]
0x1800013d6  mov     [rbp+80h+var_A0], rdx
0x1800013da  mov     [rbp+80h+var_94], r8d
0x1800013de  mov     [rbp+80h+var_A8], 4
0x1800013e6  mov     rdx, [rax]
0x1800013e9  test    rdx, rdx
0x1800013ec  jz      short loc_1800013FE
0x1800013ee  mov     rax, rcx
0x1800013f1  inc     rax
0x1800013f4  cmp     [rdx+rax], r8b
0x1800013f8  jnz     short loc_1800013F1
0x1800013fa  inc     eax
0x1800013fc  jmp     short loc_18000140A
0x1800013fe  lea     rdx, qword_180047B28
0x180001405  mov     eax, 1
0x18000140a  mov     [rbp+80h+var_B8], eax
0x18000140d  mov     rax, [rbp+80h+arg_40]
0x180001414  mov     [rbp+80h+var_D0], rax
0x180001418  mov     rax, [rbp+80h+arg_38]
0x18000141f  mov     [rbp+80h+var_C0], rdx
0x180001423  mov     [rbp+80h+var_B4], r8d
0x180001427  mov     [rbp+80h+var_C8], 4
0x18000142f  mov     rdx, [rax]
0x180001432  test    rdx, rdx
0x180001435  jz      short loc_180001444
0x180001437  inc     rcx
0x18000143a  cmp     [rdx+rcx], r8b
0x18000143e  jnz     short loc_180001437
0x180001440  inc     ecx
0x180001442  jmp     short loc_180001450
0x180001444  lea     rdx, qword_180047B28
0x18000144b  mov     ecx, 1
0x180001450  mov     rax, [rbp+80h+arg_30]
0x180001457  mov     [rbp+80h+var_F0], rax
0x18000145b  mov     rax, [rbp+80h+arg_28]
0x180001462  mov     [rbp+80h+var_100], rax
0x180001466  mov     rax, [rbp+80h+arg_20]
0x18000146d  mov     [rsp+180h+var_110], rax
0x180001472  movzx   eax, byte ptr [r9]
0x180001476  shl     eax, 18h
0x180001479  mov     dword ptr [rsp+180h+EventDescriptor.Id], eax
0x18000147d  movzx   eax, word ptr [r9+1]
0x180001482  mov     dword ptr [rsp+180h+EventDescriptor.Level], eax
0x180001486  mov     rax, [r9+3]
0x18000148a  mov     [rsp+180h+EventDescriptor.Keyword], rax
0x18000148f  mov     rax, [r10+8]
0x180001493  mov     [rsp+180h+var_130.Ptr], rax
0x180001498  mov     [rbp+80h+var_D8], ecx
0x18000149b  lea     rcx, [r9+0Bh]
0x18000149f  mov     [rbp+80h+var_E0], rdx
0x1800014a3  xor     r9d, r9d; RelatedActivityId
0x1800014a6  mov     [rbp+80h+var_D4], r8d
0x1800014aa  lea     rdx, [rsp+180h+EventDescriptor]; EventDescriptor
0x1800014af  mov     [rbp+80h+var_E8], 4
0x1800014b7  mov     [rbp+80h+var_F8], 8
0x1800014bf  mov     [rsp+180h+var_108], 8
0x1800014c8  movzx   eax, word ptr [rax]
0x1800014cb  mov     [rsp+180h+var_130.Size], eax
0x1800014cf  movzx   eax, word ptr [rcx]
0x1800014d2  mov     [rsp+180h+var_118], eax
0x1800014d6  lea     rax, _TraceLoggingMetadataEnd
0x1800014dd  mov     [rsp+180h+var_120], rcx
0x1800014e2  lea     rcx, _TraceLoggingMetadata
0x1800014e9  sub     eax, ecx
0x1800014eb  mov     dword ptr [rsp+180h+var_130.0Ch], 2
0x1800014f3  mov     [rsp+180h+var_114], 1
0x1800014fb  mov     [rsp+180h+var_150], eax
0x1800014ff  mov     eax, [rsp+180h+var_150]
0x180001503  mov     rcx, [r10+20h]; RegHandle
0x180001507  lea     rax, [rsp+180h+var_130]
0x18000150c  mov     [rsp+180h+UserData], rax; UserData
0x180001511  mov     [rsp+180h+UserDataCount], 12h; UserDataCount
0x180001519  call    cs:__imp_EventWriteTransfer
0x18000151f  mov     rcx, [rbp+80h+var_10]
0x180001523  xor     rcx, rsp; StackCookie
0x180001526  call    __security_check_cookie
0x18000152b  add     rsp, 180h
0x180001532  pop     rbp
0x180001533  retn
```
