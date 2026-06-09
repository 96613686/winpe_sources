# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)

- ea: `0x180001970`
- end: `0x180001cb7`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z`
- size: `839`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, __int64, __int64, __int64, __int64, const wchar_t **, __int64, const wchar_t **, __int64, const wchar_t **, __int64, const wchar_t **, __int64, const wchar_t **, const wchar_t **, __int64, const wchar_t **, const wchar_t **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180010950`
- `0x180012330`

## callees

- `0x180001970`
- `0x1800181b0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001c9c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001c9c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
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
  __int64 v23; // rcx
  const wchar_t *v24; // r8
  __int64 v25; // rax
  bool v26; // zf
  int v27; // eax
  const wchar_t *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  const wchar_t *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const wchar_t *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const wchar_t *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  const wchar_t *v40; // rdx
  __int64 v41; // rax
  int v42; // eax
  const wchar_t *v43; // rdx
  __int64 v44; // rax
  int v45; // eax
  const wchar_t *v46; // rdx
  int v47; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v51; // [rsp+60h] [rbp-A0h]
  int v52; // [rsp+68h] [rbp-98h]
  int v53; // [rsp+6Ch] [rbp-94h]
  __int64 v54; // [rsp+70h] [rbp-90h]
  __int64 v55; // [rsp+78h] [rbp-88h]
  __int64 v56; // [rsp+80h] [rbp-80h]
  __int64 v57; // [rsp+88h] [rbp-78h]
  __int64 v58; // [rsp+90h] [rbp-70h]
  __int64 v59; // [rsp+98h] [rbp-68h]
  const wchar_t *v60; // [rsp+A0h] [rbp-60h]
  int v61; // [rsp+A8h] [rbp-58h]
  int v62; // [rsp+ACh] [rbp-54h]
  __int64 v63; // [rsp+B0h] [rbp-50h]
  __int64 v64; // [rsp+B8h] [rbp-48h]
  const wchar_t *v65; // [rsp+C0h] [rbp-40h]
  int v66; // [rsp+C8h] [rbp-38h]
  int v67; // [rsp+CCh] [rbp-34h]
  __int64 v68; // [rsp+D0h] [rbp-30h]
  __int64 v69; // [rsp+D8h] [rbp-28h]
  const wchar_t *v70; // [rsp+E0h] [rbp-20h]
  int v71; // [rsp+E8h] [rbp-18h]
  int v72; // [rsp+ECh] [rbp-14h]
  __int64 v73; // [rsp+F0h] [rbp-10h]
  __int64 v74; // [rsp+F8h] [rbp-8h]
  const wchar_t *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  __int64 v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  const wchar_t *v80; // [rsp+120h] [rbp+20h]
  int v81; // [rsp+128h] [rbp+28h]
  int v82; // [rsp+12Ch] [rbp+2Ch]
  const wchar_t *v83; // [rsp+130h] [rbp+30h]
  int v84; // [rsp+138h] [rbp+38h]
  int v85; // [rsp+13Ch] [rbp+3Ch]
  __int64 v86; // [rsp+140h] [rbp+40h]
  __int64 v87; // [rsp+148h] [rbp+48h]
  const wchar_t *v88; // [rsp+150h] [rbp+50h]
  int v89; // [rsp+158h] [rbp+58h]
  int v90; // [rsp+15Ch] [rbp+5Ch]
  const wchar_t *v91; // [rsp+160h] [rbp+60h]
  int v92; // [rsp+168h] [rbp+68h]
  int v93; // [rsp+16Ch] [rbp+6Ch]

  v23 = -1;
  v24 = *a20;
  if ( *a20 )
  {
    v25 = -1;
    do
      v26 = v24[++v25] == 0;
    while ( !v26 );
    v27 = 2 * v25 + 2;
  }
  else
  {
    v24 = &S2;
    v27 = 2;
  }
  v92 = v27;
  v91 = v24;
  v93 = 0;
  v28 = *a19;
  if ( *a19 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_BYTE *)v28 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &qword_1800250A8;
    v30 = 1;
  }
  v89 = v30;
  v86 = a18;
  v88 = v28;
  v90 = 0;
  v87 = 4;
  v31 = *a17;
  if ( *a17 )
  {
    v32 = -1;
    do
      v26 = v31[++v32] == 0;
    while ( !v26 );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &S2;
    v33 = 2;
  }
  v84 = v33;
  v83 = v31;
  v85 = 0;
  v34 = *a16;
  if ( *a16 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &qword_1800250A8;
    v36 = 1;
  }
  v81 = v36;
  v78 = a15;
  v80 = v34;
  v82 = 0;
  v79 = 4;
  v37 = *a14;
  if ( *a14 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_BYTE *)v37 + v38) );
    v39 = v38 + 1;
  }
  else
  {
    v37 = &qword_1800250A8;
    v39 = 1;
  }
  v76 = v39;
  v73 = a13;
  v75 = v37;
  v77 = 0;
  v74 = 4;
  v40 = *a12;
  if ( *a12 )
  {
    v41 = -1;
    do
      v26 = v40[++v41] == 0;
    while ( !v26 );
    v42 = 2 * v41 + 2;
  }
  else
  {
    v40 = &S2;
    v42 = 2;
  }
  v71 = v42;
  v68 = a11;
  v70 = v40;
  v72 = 0;
  v69 = 4;
  v43 = *a10;
  if ( *a10 )
  {
    v44 = -1;
    do
      ++v44;
    while ( *((_BYTE *)v43 + v44) );
    v45 = v44 + 1;
  }
  else
  {
    v43 = &qword_1800250A8;
    v45 = 1;
  }
  v66 = v45;
  v63 = a9;
  v65 = v43;
  v67 = 0;
  v64 = 4;
  v46 = *a8;
  if ( *a8 )
  {
    do
      ++v23;
    while ( *((_BYTE *)v46 + v23) );
    v47 = v23 + 1;
  }
  else
  {
    v46 = &qword_1800250A8;
    v47 = 1;
  }
  v58 = a7;
  v56 = a6;
  v54 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v61 = v47;
  v60 = v46;
  v62 = 0;
  v59 = 4;
  v57 = 8;
  v55 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v52 = *(unsigned __int16 *)(a2 + 11);
  v51 = a2 + 11;
  UserData.Reserved = 2;
  v53 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, 0, 0x12u, &UserData);
}

```

## disassembly

```asm
0x180001970  push    rbp
0x180001972  lea     rbp, [rsp-80h]
0x180001977  sub     rsp, 180h
0x18000197e  mov     rax, cs:__security_cookie
0x180001985  xor     rax, rsp
0x180001988  mov     [rbp+80h+var_10], rax
0x18000198c  mov     rax, [rbp+80h+arg_98]
0x180001993  mov     r11, r8
0x180001996  mov     r10, rcx
0x180001999  mov     r9, rdx
0x18000199c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800019a3  mov     r8, [rax]
0x1800019a6  test    r8, r8
0x1800019a9  jz      short loc_1800019C6
0x1800019ab  mov     rax, rcx
0x1800019ae  xchg    ax, ax
0x1800019b0  cmp     word ptr [r8+rax*2+2], 0
0x1800019b7  lea     rax, [rax+1]
0x1800019bb  jnz     short loc_1800019B0
0x1800019bd  lea     eax, ds:2[rax*2]
0x1800019c4  jmp     short loc_1800019D2
0x1800019c6  lea     r8, S2
0x1800019cd  mov     eax, 2
0x1800019d2  mov     [rbp+80h+var_18], eax
0x1800019d5  mov     rax, [rbp+80h+arg_90]
0x1800019dc  mov     [rbp+80h+var_20], r8
0x1800019e0  xor     r8d, r8d
0x1800019e3  mov     [rbp+80h+var_14], r8d
0x1800019e7  mov     rdx, [rax]
0x1800019ea  test    rdx, rdx
0x1800019ed  jz      short loc_1800019FF
0x1800019ef  mov     rax, rcx
0x1800019f2  inc     rax
0x1800019f5  cmp     [rdx+rax], r8b
0x1800019f9  jnz     short loc_1800019F2
0x1800019fb  inc     eax
0x1800019fd  jmp     short loc_180001A0B
0x1800019ff  lea     rdx, qword_1800250A8
0x180001a06  mov     eax, 1
0x180001a0b  mov     [rbp+80h+var_28], eax
0x180001a0e  mov     rax, [rbp+80h+arg_88]
0x180001a15  mov     [rbp+80h+var_40], rax
0x180001a19  mov     rax, [rbp+80h+arg_80]
0x180001a20  mov     [rbp+80h+var_30], rdx
0x180001a24  mov     [rbp+80h+var_24], r8d
0x180001a28  mov     [rbp+80h+var_38], 4
0x180001a30  mov     rdx, [rax]
0x180001a33  test    rdx, rdx
0x180001a36  jz      short loc_180001A55
0x180001a38  mov     rax, rcx
0x180001a3b  nop     dword ptr [rax+rax+00h]
0x180001a40  cmp     [rdx+rax*2+2], r8w
0x180001a46  lea     rax, [rax+1]
0x180001a4a  jnz     short loc_180001A40
0x180001a4c  lea     eax, ds:2[rax*2]
0x180001a53  jmp     short loc_180001A61
0x180001a55  lea     rdx, S2
0x180001a5c  mov     eax, 2
0x180001a61  mov     [rbp+80h+var_48], eax
0x180001a64  mov     rax, [rbp+80h+arg_78]
0x180001a6b  mov     [rbp+80h+var_50], rdx
0x180001a6f  mov     [rbp+80h+var_44], r8d
0x180001a73  mov     rdx, [rax]
0x180001a76  test    rdx, rdx
0x180001a79  jz      short loc_180001A8D
0x180001a7b  mov     rax, rcx
0x180001a7e  xchg    ax, ax
0x180001a80  inc     rax
0x180001a83  cmp     [rdx+rax], r8b
0x180001a87  jnz     short loc_180001A80
0x180001a89  inc     eax
0x180001a8b  jmp     short loc_180001A99
0x180001a8d  lea     rdx, qword_1800250A8
0x180001a94  mov     eax, 1
0x180001a99  mov     [rbp+80h+var_58], eax
0x180001a9c  mov     rax, [rbp+80h+arg_70]
0x180001aa3  mov     [rbp+80h+var_70], rax
0x180001aa7  mov     rax, [rbp+80h+arg_68]
0x180001aae  mov     [rbp+80h+var_60], rdx
0x180001ab2  mov     [rbp+80h+var_54], r8d
0x180001ab6  mov     [rbp+80h+var_68], 4
0x180001abe  mov     rdx, [rax]
0x180001ac1  test    rdx, rdx
0x180001ac4  jz      short loc_180001ADD
0x180001ac6  mov     rax, rcx
0x180001ac9  nop     dword ptr [rax+00000000h]
0x180001ad0  inc     rax
0x180001ad3  cmp     [rdx+rax], r8b
0x180001ad7  jnz     short loc_180001AD0
0x180001ad9  inc     eax
0x180001adb  jmp     short loc_180001AE9
0x180001add  lea     rdx, qword_1800250A8
0x180001ae4  mov     eax, 1
0x180001ae9  mov     [rbp+80h+var_78], eax
0x180001aec  mov     rax, [rbp+80h+arg_60]
0x180001af3  mov     [rbp+80h+var_90], rax
0x180001af7  mov     rax, [rbp+80h+arg_58]
0x180001afe  mov     [rbp+80h+var_80], rdx
0x180001b02  mov     [rbp+80h+var_74], r8d
0x180001b06  mov     [rbp+80h+var_88], 4
0x180001b0e  mov     rdx, [rax]
0x180001b11  test    rdx, rdx
0x180001b14  jz      short loc_180001B35
0x180001b16  mov     rax, rcx
0x180001b19  nop     dword ptr [rax+00000000h]
0x180001b20  cmp     [rdx+rax*2+2], r8w
0x180001b26  lea     rax, [rax+1]
0x180001b2a  jnz     short loc_180001B20
0x180001b2c  lea     eax, ds:2[rax*2]
0x180001b33  jmp     short loc_180001B41
0x180001b35  lea     rdx, S2
0x180001b3c  mov     eax, 2
0x180001b41  mov     [rbp+80h+var_98], eax
0x180001b44  mov     rax, [rbp+80h+arg_50]
0x180001b4b  mov     [rbp+80h+var_B0], rax
0x180001b4f  mov     rax, [rbp+80h+arg_48]
0x180001b56  mov     [rbp+80h+var_A0], rdx
0x180001b5a  mov     [rbp+80h+var_94], r8d
0x180001b5e  mov     [rbp+80h+var_A8], 4
0x180001b66  mov     rdx, [rax]
0x180001b69  test    rdx, rdx
0x180001b6c  jz      short loc_180001B7E
0x180001b6e  mov     rax, rcx
0x180001b71  inc     rax
0x180001b74  cmp     [rdx+rax], r8b
0x180001b78  jnz     short loc_180001B71
0x180001b7a  inc     eax
0x180001b7c  jmp     short loc_180001B8A
0x180001b7e  lea     rdx, qword_1800250A8
0x180001b85  mov     eax, 1
0x180001b8a  mov     [rbp+80h+var_B8], eax
0x180001b8d  mov     rax, [rbp+80h+arg_40]
0x180001b94  mov     [rbp+80h+var_D0], rax
0x180001b98  mov     rax, [rbp+80h+arg_38]
0x180001b9f  mov     [rbp+80h+var_C0], rdx
0x180001ba3  mov     [rbp+80h+var_B4], r8d
0x180001ba7  mov     [rbp+80h+var_C8], 4
0x180001baf  mov     rdx, [rax]
0x180001bb2  test    rdx, rdx
0x180001bb5  jz      short loc_180001BC4
0x180001bb7  inc     rcx
0x180001bba  cmp     [rdx+rcx], r8b
0x180001bbe  jnz     short loc_180001BB7
0x180001bc0  inc     ecx
0x180001bc2  jmp     short loc_180001BD0
0x180001bc4  lea     rdx, qword_1800250A8
0x180001bcb  mov     ecx, 1
0x180001bd0  mov     rax, [rbp+80h+arg_30]
0x180001bd7  mov     [rbp+80h+var_F0], rax
0x180001bdb  mov     rax, [rbp+80h+arg_28]
0x180001be2  mov     [rbp+80h+var_100], rax
0x180001be6  mov     rax, [rbp+80h+arg_20]
0x180001bed  mov     [rsp+180h+var_110], rax
0x180001bf2  movzx   eax, byte ptr [r9]
0x180001bf6  shl     eax, 18h
0x180001bf9  mov     dword ptr [rsp+180h+EventDescriptor.Id], eax
0x180001bfd  movzx   eax, word ptr [r9+1]
0x180001c02  mov     dword ptr [rsp+180h+EventDescriptor.Level], eax
0x180001c06  mov     rax, [r9+3]
0x180001c0a  mov     [rsp+180h+EventDescriptor.Keyword], rax
0x180001c0f  mov     rax, [r10+8]
0x180001c13  mov     [rsp+180h+var_130.Ptr], rax
0x180001c18  mov     [rbp+80h+var_D8], ecx
0x180001c1b  lea     rcx, [r9+0Bh]
0x180001c1f  mov     [rbp+80h+var_E0], rdx
0x180001c23  xor     r9d, r9d; RelatedActivityId
0x180001c26  mov     [rbp+80h+var_D4], r8d
0x180001c2a  lea     rdx, [rsp+180h+EventDescriptor]; EventDescriptor
0x180001c2f  mov     [rbp+80h+var_E8], 4
0x180001c37  mov     r8, r11; ActivityId
0x180001c3a  mov     [rbp+80h+var_F8], 8
0x180001c42  mov     [rsp+180h+var_108], 8
0x180001c4b  movzx   eax, word ptr [rax]
0x180001c4e  mov     [rsp+180h+var_130.Size], eax
0x180001c52  movzx   eax, word ptr [rcx]
0x180001c55  mov     [rsp+180h+var_118], eax
0x180001c59  lea     rax, _TraceLoggingMetadataEnd
0x180001c60  mov     [rsp+180h+var_120], rcx
0x180001c65  lea     rcx, _TraceLoggingMetadata
0x180001c6c  sub     eax, ecx
0x180001c6e  mov     dword ptr [rsp+180h+var_130.0Ch], 2
0x180001c76  mov     [rsp+180h+var_114], 1
0x180001c7e  mov     [rsp+180h+var_150], eax
0x180001c82  mov     eax, [rsp+180h+var_150]
0x180001c86  mov     rcx, [r10+20h]; RegHandle
0x180001c8a  lea     rax, [rsp+180h+var_130]
0x180001c8f  mov     [rsp+180h+UserData], rax; UserData
0x180001c94  mov     [rsp+180h+UserDataCount], 12h; UserDataCount
0x180001c9c  call    cs:__imp_EventWriteTransfer
0x180001ca2  mov     rcx, [rbp+80h+var_10]
0x180001ca6  xor     rcx, rsp; StackCookie
0x180001ca9  call    __security_check_cookie
0x180001cae  add     rsp, 180h
0x180001cb5  pop     rbp
0x180001cb6  retn
```
