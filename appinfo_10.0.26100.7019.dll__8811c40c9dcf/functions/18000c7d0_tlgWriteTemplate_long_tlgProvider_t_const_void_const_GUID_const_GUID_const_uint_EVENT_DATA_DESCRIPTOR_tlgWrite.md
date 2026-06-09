# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x18000c7d0`
- end: `0x18000cb22`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `850`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1800224a8`
- `0x180023a80`
- `0x1800371d0`
- `0x1800373f0`
- `0x180037610`
- `0x180037830`
- `0x180037a50`
- `0x180037c80`
- `0x18003f640`
- `0x18003f870`

## callees

- `0x18000c7d0`
- `0x180042950`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000cb00`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000cb00`

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
  __int64 v23; // rcx
  const wchar_t *v24; // r8
  __int64 v25; // rax
  bool v26; // zf
  int v27; // eax
  const unsigned __int16 *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  const wchar_t *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  const wchar_t *v40; // rdx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rdx
  __int64 v44; // rax
  int v45; // eax
  const unsigned __int16 *v46; // rdx
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
  const unsigned __int16 *v60; // [rsp+A0h] [rbp-60h]
  int v61; // [rsp+A8h] [rbp-58h]
  int v62; // [rsp+ACh] [rbp-54h]
  __int64 v63; // [rsp+B0h] [rbp-50h]
  __int64 v64; // [rsp+B8h] [rbp-48h]
  const unsigned __int16 *v65; // [rsp+C0h] [rbp-40h]
  int v66; // [rsp+C8h] [rbp-38h]
  int v67; // [rsp+CCh] [rbp-34h]
  __int64 v68; // [rsp+D0h] [rbp-30h]
  __int64 v69; // [rsp+D8h] [rbp-28h]
  const wchar_t *v70; // [rsp+E0h] [rbp-20h]
  int v71; // [rsp+E8h] [rbp-18h]
  int v72; // [rsp+ECh] [rbp-14h]
  __int64 v73; // [rsp+F0h] [rbp-10h]
  __int64 v74; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  __int64 v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v80; // [rsp+120h] [rbp+20h]
  int v81; // [rsp+128h] [rbp+28h]
  int v82; // [rsp+12Ch] [rbp+2Ch]
  const wchar_t *v83; // [rsp+130h] [rbp+30h]
  int v84; // [rsp+138h] [rbp+38h]
  int v85; // [rsp+13Ch] [rbp+3Ch]
  __int64 v86; // [rsp+140h] [rbp+40h]
  __int64 v87; // [rsp+148h] [rbp+48h]
  const unsigned __int16 *v88; // [rsp+150h] [rbp+50h]
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
    v24 = &String2;
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
    v28 = &word_180048468;
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
    v31 = &String2;
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
    v34 = &word_180048468;
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
    v37 = &word_180048468;
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
    v40 = &String2;
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
    v43 = &word_180048468;
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
    v46 = &word_180048468;
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
0x18000c7d0  push    rbp
0x18000c7d2  lea     rbp, [rsp-80h]
0x18000c7d7  sub     rsp, 180h
0x18000c7de  mov     rax, cs:__security_cookie
0x18000c7e5  xor     rax, rsp
0x18000c7e8  mov     [rbp+80h+var_10], rax
0x18000c7ec  mov     rax, [rbp+80h+arg_98]
0x18000c7f3  mov     r11, r8
0x18000c7f6  mov     r10, rcx
0x18000c7f9  mov     r9, rdx
0x18000c7fc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c803  mov     r8, [rax]
0x18000c806  test    r8, r8
0x18000c809  jz      short loc_18000C826
0x18000c80b  mov     rax, rcx
0x18000c80e  xchg    ax, ax
0x18000c810  cmp     word ptr [r8+rax*2+2], 0
0x18000c817  lea     rax, [rax+1]
0x18000c81b  jnz     short loc_18000C810
0x18000c81d  lea     eax, ds:2[rax*2]
0x18000c824  jmp     short loc_18000C832
0x18000c826  lea     r8, String2
0x18000c82d  mov     eax, 2
0x18000c832  mov     [rbp+80h+var_18], eax
0x18000c835  mov     rax, [rbp+80h+arg_90]
0x18000c83c  mov     [rbp+80h+var_20], r8
0x18000c840  xor     r8d, r8d
0x18000c843  mov     [rbp+80h+var_14], r8d
0x18000c847  mov     rdx, [rax]
0x18000c84a  test    rdx, rdx
0x18000c84d  jz      short loc_18000C85F
0x18000c84f  mov     rax, rcx
0x18000c852  inc     rax
0x18000c855  cmp     [rdx+rax], r8b
0x18000c859  jnz     short loc_18000C852
0x18000c85b  inc     eax
0x18000c85d  jmp     short loc_18000C86B
0x18000c85f  lea     rdx, word_180048468
0x18000c866  mov     eax, 1
0x18000c86b  mov     [rbp+80h+var_28], eax
0x18000c86e  mov     rax, [rbp+80h+arg_88]
0x18000c875  mov     [rbp+80h+var_40], rax
0x18000c879  mov     rax, [rbp+80h+arg_80]
0x18000c880  mov     [rbp+80h+var_30], rdx
0x18000c884  mov     [rbp+80h+var_24], r8d
0x18000c888  mov     [rbp+80h+var_38], 4
0x18000c890  mov     rdx, [rax]
0x18000c893  test    rdx, rdx
0x18000c896  jz      short loc_18000C8B5
0x18000c898  mov     rax, rcx
0x18000c89b  nop     dword ptr [rax+rax+00h]
0x18000c8a0  cmp     [rdx+rax*2+2], r8w
0x18000c8a6  lea     rax, [rax+1]
0x18000c8aa  jnz     short loc_18000C8A0
0x18000c8ac  lea     eax, ds:2[rax*2]
0x18000c8b3  jmp     short loc_18000C8C1
0x18000c8b5  lea     rdx, String2
0x18000c8bc  mov     eax, 2
0x18000c8c1  mov     [rbp+80h+var_48], eax
0x18000c8c4  mov     rax, [rbp+80h+arg_78]
0x18000c8cb  mov     [rbp+80h+var_50], rdx
0x18000c8cf  mov     [rbp+80h+var_44], r8d
0x18000c8d3  mov     rdx, [rax]
0x18000c8d6  test    rdx, rdx
0x18000c8d9  jz      short loc_18000C8ED
0x18000c8db  mov     rax, rcx
0x18000c8de  xchg    ax, ax
0x18000c8e0  inc     rax
0x18000c8e3  cmp     [rdx+rax], r8b
0x18000c8e7  jnz     short loc_18000C8E0
0x18000c8e9  inc     eax
0x18000c8eb  jmp     short loc_18000C8F9
0x18000c8ed  lea     rdx, word_180048468
0x18000c8f4  mov     eax, 1
0x18000c8f9  mov     [rbp+80h+var_58], eax
0x18000c8fc  mov     rax, [rbp+80h+arg_70]
0x18000c903  mov     [rbp+80h+var_70], rax
0x18000c907  mov     rax, [rbp+80h+arg_68]
0x18000c90e  mov     [rbp+80h+var_60], rdx
0x18000c912  mov     [rbp+80h+var_54], r8d
0x18000c916  mov     [rbp+80h+var_68], 4
0x18000c91e  mov     rdx, [rax]
0x18000c921  test    rdx, rdx
0x18000c924  jz      short loc_18000C93D
0x18000c926  mov     rax, rcx
0x18000c929  nop     dword ptr [rax+00000000h]
0x18000c930  inc     rax
0x18000c933  cmp     [rdx+rax], r8b
0x18000c937  jnz     short loc_18000C930
0x18000c939  inc     eax
0x18000c93b  jmp     short loc_18000C949
0x18000c93d  lea     rdx, word_180048468
0x18000c944  mov     eax, 1
0x18000c949  mov     [rbp+80h+var_78], eax
0x18000c94c  mov     rax, [rbp+80h+arg_60]
0x18000c953  mov     [rbp+80h+var_90], rax
0x18000c957  mov     rax, [rbp+80h+arg_58]
0x18000c95e  mov     [rbp+80h+var_80], rdx
0x18000c962  mov     [rbp+80h+var_74], r8d
0x18000c966  mov     [rbp+80h+var_88], 4
0x18000c96e  mov     rdx, [rax]
0x18000c971  test    rdx, rdx
0x18000c974  jz      short loc_18000C995
0x18000c976  mov     rax, rcx
0x18000c979  nop     dword ptr [rax+00000000h]
0x18000c980  cmp     [rdx+rax*2+2], r8w
0x18000c986  lea     rax, [rax+1]
0x18000c98a  jnz     short loc_18000C980
0x18000c98c  lea     eax, ds:2[rax*2]
0x18000c993  jmp     short loc_18000C9A1
0x18000c995  lea     rdx, String2
0x18000c99c  mov     eax, 2
0x18000c9a1  mov     [rbp+80h+var_98], eax
0x18000c9a4  mov     rax, [rbp+80h+arg_50]
0x18000c9ab  mov     [rbp+80h+var_B0], rax
0x18000c9af  mov     rax, [rbp+80h+arg_48]
0x18000c9b6  mov     [rbp+80h+var_A0], rdx
0x18000c9ba  mov     [rbp+80h+var_94], r8d
0x18000c9be  mov     [rbp+80h+var_A8], 4
0x18000c9c6  mov     rdx, [rax]
0x18000c9c9  test    rdx, rdx
0x18000c9cc  jz      short loc_18000C9DE
0x18000c9ce  mov     rax, rcx
0x18000c9d1  inc     rax
0x18000c9d4  cmp     [rdx+rax], r8b
0x18000c9d8  jnz     short loc_18000C9D1
0x18000c9da  inc     eax
0x18000c9dc  jmp     short loc_18000C9EA
0x18000c9de  lea     rdx, word_180048468
0x18000c9e5  mov     eax, 1
0x18000c9ea  mov     [rbp+80h+var_B8], eax
0x18000c9ed  mov     rax, [rbp+80h+arg_40]
0x18000c9f4  mov     [rbp+80h+var_D0], rax
0x18000c9f8  mov     rax, [rbp+80h+arg_38]
0x18000c9ff  mov     [rbp+80h+var_C0], rdx
0x18000ca03  mov     [rbp+80h+var_B4], r8d
0x18000ca07  mov     [rbp+80h+var_C8], 4
0x18000ca0f  mov     rdx, [rax]
0x18000ca12  test    rdx, rdx
0x18000ca15  jz      short loc_18000CA24
0x18000ca17  inc     rcx
0x18000ca1a  cmp     [rdx+rcx], r8b
0x18000ca1e  jnz     short loc_18000CA17
0x18000ca20  inc     ecx
0x18000ca22  jmp     short loc_18000CA30
0x18000ca24  lea     rdx, word_180048468
0x18000ca2b  mov     ecx, 1
0x18000ca30  mov     rax, [rbp+80h+arg_30]
0x18000ca37  mov     [rbp+80h+var_F0], rax
0x18000ca3b  mov     rax, [rbp+80h+arg_28]
0x18000ca42  mov     [rbp+80h+var_100], rax
0x18000ca46  mov     rax, [rbp+80h+arg_20]
0x18000ca4d  mov     [rsp+180h+var_110], rax
0x18000ca52  movzx   eax, byte ptr [r9]
0x18000ca56  shl     eax, 18h
0x18000ca59  mov     dword ptr [rsp+180h+EventDescriptor.Id], eax
0x18000ca5d  movzx   eax, word ptr [r9+1]
0x18000ca62  mov     dword ptr [rsp+180h+EventDescriptor.Level], eax
0x18000ca66  mov     rax, [r9+3]
0x18000ca6a  mov     [rsp+180h+EventDescriptor.Keyword], rax
0x18000ca6f  mov     rax, [r10+8]
0x18000ca73  mov     [rsp+180h+var_130.Ptr], rax
0x18000ca78  mov     [rbp+80h+var_D8], ecx
0x18000ca7b  lea     rcx, [r9+1]
0x18000ca7f  add     rcx, 0Ah
0x18000ca83  mov     [rbp+80h+var_E0], rdx
0x18000ca87  mov     [rbp+80h+var_D4], r8d
0x18000ca8b  lea     rdx, [rsp+180h+EventDescriptor]; EventDescriptor
0x18000ca90  mov     [rbp+80h+var_E8], 4
0x18000ca98  xor     r9d, r9d; RelatedActivityId
0x18000ca9b  mov     [rbp+80h+var_F8], 8
0x18000caa3  mov     r8, r11; ActivityId
0x18000caa6  mov     [rsp+180h+var_108], 8
0x18000caaf  movzx   eax, word ptr [rax]
0x18000cab2  mov     [rsp+180h+var_130.Size], eax
0x18000cab6  movzx   eax, word ptr [rcx]
0x18000cab9  mov     [rsp+180h+var_118], eax
0x18000cabd  lea     rax, _TraceLoggingMetadataEnd
0x18000cac4  mov     [rsp+180h+var_120], rcx
0x18000cac9  lea     rcx, _TraceLoggingMetadata
0x18000cad0  sub     eax, ecx
0x18000cad2  mov     dword ptr [rsp+180h+var_130.0Ch], 2
0x18000cada  mov     [rsp+180h+var_114], 1
0x18000cae2  mov     [rsp+180h+var_150], eax
0x18000cae6  mov     eax, [rsp+180h+var_150]
0x18000caea  mov     rcx, [r10+20h]; RegHandle
0x18000caee  lea     rax, [rsp+180h+var_130]
0x18000caf3  mov     [rsp+180h+UserData], rax; UserData
0x18000caf8  mov     [rsp+180h+UserDataCount], 12h; UserDataCount
0x18000cb00  call    cs:__imp_EventWriteTransfer
0x18000cb07  nop     dword ptr [rax+rax+00h]
0x18000cb0c  mov     rcx, [rbp+80h+var_10]
0x18000cb10  xor     rcx, rsp; StackCookie
0x18000cb13  call    __security_check_cookie
0x18000cb18  add     rsp, 180h
0x18000cb1f  pop     rbp
0x18000cb20  retn
```
