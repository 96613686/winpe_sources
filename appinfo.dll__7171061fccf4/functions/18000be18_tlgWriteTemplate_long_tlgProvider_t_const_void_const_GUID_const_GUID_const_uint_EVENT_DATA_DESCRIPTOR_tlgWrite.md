# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x18000be18`
- end: `0x18000c123`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `779`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const wchar_t **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const wchar_t **, __int64, const unsigned __int16 **, const wchar_t **)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180024bb8`
- `0x180025db0`
- `0x18003a590`
- `0x18003a7c0`
- `0x18003a9f0`
- `0x18003ac20`
- `0x18003ae50`
- `0x18003b080`
- `0x180043da0`
- `0x180043fd0`

## callees

- `0x18000be18`
- `0x180046e50`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c0fe`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c0fe`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
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
        const wchar_t **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        const wchar_t **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        const wchar_t **a20)
{
  __int64 v22; // rcx
  const wchar_t *v24; // r8
  __int64 v25; // rax
  int v26; // eax
  const unsigned __int16 *v27; // rdx
  __int64 v28; // rax
  int v29; // eax
  const wchar_t *v30; // rdx
  __int64 v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // rdx
  __int64 v34; // rax
  int v35; // eax
  const unsigned __int16 *v36; // rdx
  __int64 v37; // rax
  int v38; // eax
  const wchar_t *v39; // rdx
  __int64 v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // rdx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rdx
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
  const unsigned __int16 *v59; // [rsp+A0h] [rbp-60h]
  int v60; // [rsp+A8h] [rbp-58h]
  int v61; // [rsp+ACh] [rbp-54h]
  __int64 v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+B8h] [rbp-48h]
  const unsigned __int16 *v64; // [rsp+C0h] [rbp-40h]
  int v65; // [rsp+C8h] [rbp-38h]
  int v66; // [rsp+CCh] [rbp-34h]
  __int64 v67; // [rsp+D0h] [rbp-30h]
  __int64 v68; // [rsp+D8h] [rbp-28h]
  const wchar_t *v69; // [rsp+E0h] [rbp-20h]
  int v70; // [rsp+E8h] [rbp-18h]
  int v71; // [rsp+ECh] [rbp-14h]
  __int64 v72; // [rsp+F0h] [rbp-10h]
  __int64 v73; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v74; // [rsp+100h] [rbp+0h]
  int v75; // [rsp+108h] [rbp+8h]
  int v76; // [rsp+10Ch] [rbp+Ch]
  __int64 v77; // [rsp+110h] [rbp+10h]
  __int64 v78; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v79; // [rsp+120h] [rbp+20h]
  int v80; // [rsp+128h] [rbp+28h]
  int v81; // [rsp+12Ch] [rbp+2Ch]
  const wchar_t *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  __int64 v85; // [rsp+140h] [rbp+40h]
  __int64 v86; // [rsp+148h] [rbp+48h]
  const unsigned __int16 *v87; // [rsp+150h] [rbp+50h]
  int v88; // [rsp+158h] [rbp+58h]
  int v89; // [rsp+15Ch] [rbp+5Ch]
  const wchar_t *v90; // [rsp+160h] [rbp+60h]
  int v91; // [rsp+168h] [rbp+68h]
  int v92; // [rsp+16Ch] [rbp+6Ch]

  v22 = -1;
  v24 = *a20;
  if ( *a20 )
  {
    v25 = -1;
    do
      ++v25;
    while ( v24[v25] );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &String2;
    v26 = 2;
  }
  v91 = v26;
  v90 = v24;
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
    v27 = &dword_18004D4B4;
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
      ++v31;
    while ( v30[v31] );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &String2;
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
    v33 = &dword_18004D4B4;
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
    v36 = &dword_18004D4B4;
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
      ++v40;
    while ( v39[v40] );
    v41 = 2 * v40 + 2;
  }
  else
  {
    v39 = &String2;
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
    v42 = &dword_18004D4B4;
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
    v45 = &dword_18004D4B4;
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
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, 0, 0x12u, &UserData);
}

```

## disassembly

```asm
0x18000be18  mov     [rsp-8+arg_8], rbx
0x18000be1d  push    rbp
0x18000be1e  push    rsi
0x18000be1f  push    rdi
0x18000be20  lea     rbp, [rsp-80h]
0x18000be25  sub     rsp, 180h
0x18000be2c  mov     rax, cs:__security_cookie
0x18000be33  xor     rax, rsp
0x18000be36  mov     [rbp+90h+var_20], rax
0x18000be3a  mov     rax, [rbp+90h+arg_98]
0x18000be41  mov     r11, r8
0x18000be44  mov     r10, rcx
0x18000be47  xor     ebx, ebx
0x18000be49  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000be4d  mov     r9, rdx
0x18000be50  mov     r8, [rax]
0x18000be53  test    r8, r8
0x18000be56  jz      short loc_18000BE6E
0x18000be58  mov     rax, rcx
0x18000be5b  inc     rax
0x18000be5e  cmp     [r8+rax*2], bx
0x18000be63  jnz     short loc_18000BE5B
0x18000be65  lea     eax, ds:2[rax*2]
0x18000be6c  jmp     short loc_18000BE7A
0x18000be6e  lea     r8, String2
0x18000be75  mov     eax, 2
0x18000be7a  mov     [rbp+90h+var_28], eax
0x18000be7d  mov     edi, 1
0x18000be82  mov     rax, [rbp+90h+arg_90]
0x18000be89  mov     [rbp+90h+var_30], r8
0x18000be8d  lea     r8, dword_18004D4B4
0x18000be94  mov     [rbp+90h+var_24], ebx
0x18000be97  mov     rdx, [rax]
0x18000be9a  test    rdx, rdx
0x18000be9d  jz      short loc_18000BEAE
0x18000be9f  mov     rax, rcx
0x18000bea2  inc     rax
0x18000bea5  cmp     [rdx+rax], bl
0x18000bea8  jnz     short loc_18000BEA2
0x18000beaa  inc     eax
0x18000beac  jmp     short loc_18000BEB3
0x18000beae  mov     rdx, r8
0x18000beb1  mov     eax, edi
0x18000beb3  mov     [rbp+90h+var_38], eax
0x18000beb6  mov     rax, [rbp+90h+arg_88]
0x18000bebd  mov     [rbp+90h+var_50], rax
0x18000bec1  mov     rax, [rbp+90h+arg_80]
0x18000bec8  mov     [rbp+90h+var_40], rdx
0x18000becc  mov     [rbp+90h+var_34], ebx
0x18000becf  mov     [rbp+90h+var_48], 4
0x18000bed7  mov     rdx, [rax]
0x18000beda  test    rdx, rdx
0x18000bedd  jz      short loc_18000BEF4
0x18000bedf  mov     rax, rcx
0x18000bee2  inc     rax
0x18000bee5  cmp     [rdx+rax*2], bx
0x18000bee9  jnz     short loc_18000BEE2
0x18000beeb  lea     eax, ds:2[rax*2]
0x18000bef2  jmp     short loc_18000BF00
0x18000bef4  lea     rdx, String2
0x18000befb  mov     eax, 2
0x18000bf00  mov     [rbp+90h+var_58], eax
0x18000bf03  mov     rax, [rbp+90h+arg_78]
0x18000bf0a  mov     [rbp+90h+var_60], rdx
0x18000bf0e  mov     [rbp+90h+var_54], ebx
0x18000bf11  mov     rdx, [rax]
0x18000bf14  test    rdx, rdx
0x18000bf17  jz      short loc_18000BF28
0x18000bf19  mov     rax, rcx
0x18000bf1c  inc     rax
0x18000bf1f  cmp     [rdx+rax], bl
0x18000bf22  jnz     short loc_18000BF1C
0x18000bf24  inc     eax
0x18000bf26  jmp     short loc_18000BF2D
0x18000bf28  mov     rdx, r8
0x18000bf2b  mov     eax, edi
0x18000bf2d  mov     [rbp+90h+var_68], eax
0x18000bf30  mov     rax, [rbp+90h+arg_70]
0x18000bf37  mov     [rbp+90h+var_80], rax
0x18000bf3b  mov     rax, [rbp+90h+arg_68]
0x18000bf42  mov     [rbp+90h+var_70], rdx
0x18000bf46  mov     [rbp+90h+var_64], ebx
0x18000bf49  mov     [rbp+90h+var_78], 4
0x18000bf51  mov     rdx, [rax]
0x18000bf54  test    rdx, rdx
0x18000bf57  jz      short loc_18000BF68
0x18000bf59  mov     rax, rcx
0x18000bf5c  inc     rax
0x18000bf5f  cmp     [rdx+rax], bl
0x18000bf62  jnz     short loc_18000BF5C
0x18000bf64  inc     eax
0x18000bf66  jmp     short loc_18000BF6D
0x18000bf68  mov     rdx, r8
0x18000bf6b  mov     eax, edi
0x18000bf6d  mov     [rbp+90h+var_88], eax
0x18000bf70  mov     rax, [rbp+90h+arg_60]
0x18000bf77  mov     [rbp+90h+var_A0], rax
0x18000bf7b  mov     rax, [rbp+90h+arg_58]
0x18000bf82  mov     [rbp+90h+var_90], rdx
0x18000bf86  mov     [rbp+90h+var_84], ebx
0x18000bf89  mov     [rbp+90h+var_98], 4
0x18000bf91  mov     rdx, [rax]
0x18000bf94  test    rdx, rdx
0x18000bf97  jz      short loc_18000BFAE
0x18000bf99  mov     rax, rcx
0x18000bf9c  inc     rax
0x18000bf9f  cmp     [rdx+rax*2], bx
0x18000bfa3  jnz     short loc_18000BF9C
0x18000bfa5  lea     eax, ds:2[rax*2]
0x18000bfac  jmp     short loc_18000BFBA
0x18000bfae  lea     rdx, String2
0x18000bfb5  mov     eax, 2
0x18000bfba  mov     [rbp+90h+var_A8], eax
0x18000bfbd  mov     rax, [rbp+90h+arg_50]
0x18000bfc4  mov     [rbp+90h+var_C0], rax
0x18000bfc8  mov     rax, [rbp+90h+arg_48]
0x18000bfcf  mov     [rbp+90h+var_B0], rdx
0x18000bfd3  mov     [rbp+90h+var_A4], ebx
0x18000bfd6  mov     [rbp+90h+var_B8], 4
0x18000bfde  mov     rdx, [rax]
0x18000bfe1  test    rdx, rdx
0x18000bfe4  jz      short loc_18000BFF5
0x18000bfe6  mov     rax, rcx
0x18000bfe9  inc     rax
0x18000bfec  cmp     [rdx+rax], bl
0x18000bfef  jnz     short loc_18000BFE9
0x18000bff1  inc     eax
0x18000bff3  jmp     short loc_18000BFFA
0x18000bff5  mov     rdx, r8
0x18000bff8  mov     eax, edi
0x18000bffa  mov     [rbp+90h+var_C8], eax
0x18000bffd  mov     rax, [rbp+90h+arg_40]
0x18000c004  mov     [rbp+90h+var_E0], rax
0x18000c008  mov     rax, [rbp+90h+arg_38]
0x18000c00f  mov     [rbp+90h+var_D0], rdx
0x18000c013  mov     [rbp+90h+var_C4], ebx
0x18000c016  mov     [rbp+90h+var_D8], 4
0x18000c01e  mov     rdx, [rax]
0x18000c021  test    rdx, rdx
0x18000c024  jz      short loc_18000C032
0x18000c026  inc     rcx
0x18000c029  cmp     [rdx+rcx], bl
0x18000c02c  jnz     short loc_18000C026
0x18000c02e  inc     ecx
0x18000c030  jmp     short loc_18000C037
0x18000c032  mov     rdx, r8
0x18000c035  mov     ecx, edi
0x18000c037  mov     rax, [rbp+90h+arg_30]
0x18000c03e  mov     r8, r11; ActivityId
0x18000c041  mov     [rbp+90h+var_100], rax
0x18000c045  mov     rax, [rbp+90h+arg_28]
0x18000c04c  mov     [rbp+90h+var_110], rax
0x18000c050  mov     rax, [rbp+90h+arg_20]
0x18000c057  mov     [rsp+190h+var_120], rax
0x18000c05c  movzx   eax, byte ptr [r9]
0x18000c060  shl     eax, 18h
0x18000c063  mov     dword ptr [rsp+190h+EventDescriptor.Id], eax
0x18000c067  movzx   eax, word ptr [r9+1]
0x18000c06c  mov     dword ptr [rsp+190h+EventDescriptor.Level], eax
0x18000c070  mov     rax, [r9+3]
0x18000c074  mov     [rsp+190h+EventDescriptor.Keyword], rax
0x18000c079  mov     rax, [r10+8]
0x18000c07d  mov     [rsp+190h+var_140.Ptr], rax
0x18000c082  mov     [rbp+90h+var_E8], ecx
0x18000c085  lea     rcx, [r9+0Bh]
0x18000c089  mov     [rbp+90h+var_F0], rdx
0x18000c08d  xor     r9d, r9d; RelatedActivityId
0x18000c090  mov     [rbp+90h+var_E4], ebx
0x18000c093  lea     rdx, [rsp+190h+EventDescriptor]; EventDescriptor
0x18000c098  mov     [rbp+90h+var_F8], 4
0x18000c0a0  mov     [rbp+90h+var_108], 8
0x18000c0a8  mov     [rsp+190h+var_118], 8
0x18000c0b1  movzx   eax, word ptr [rax]
0x18000c0b4  mov     [rsp+190h+var_140.Size], eax
0x18000c0b8  movzx   eax, word ptr [rcx]
0x18000c0bb  mov     [rsp+190h+var_128], eax
0x18000c0bf  lea     rax, _TraceLoggingMetadataEnd
0x18000c0c6  mov     [rsp+190h+var_130], rcx
0x18000c0cb  lea     rcx, _TraceLoggingMetadata
0x18000c0d2  sub     eax, ecx
0x18000c0d4  mov     dword ptr [rsp+190h+var_140.0Ch], 2
0x18000c0dc  mov     [rsp+190h+var_124], edi
0x18000c0e0  mov     [rsp+190h+var_160], eax
0x18000c0e4  mov     eax, [rsp+190h+var_160]
0x18000c0e8  mov     rcx, [r10+20h]; RegHandle
0x18000c0ec  lea     rax, [rsp+190h+var_140]
0x18000c0f1  mov     [rsp+190h+UserData], rax; UserData
0x18000c0f6  mov     [rsp+190h+UserDataCount], 12h; UserDataCount
0x18000c0fe  call    cs:__imp_EventWriteTransfer
0x18000c104  mov     rcx, [rbp+90h+var_20]
0x18000c108  xor     rcx, rsp; StackCookie
0x18000c10b  call    __security_check_cookie
0x18000c110  mov     rbx, [rsp+190h+arg_8]
0x18000c118  add     rsp, 180h
0x18000c11f  pop     rdi
0x18000c120  pop     rsi
0x18000c121  pop     rbp
0x18000c122  retn
```
