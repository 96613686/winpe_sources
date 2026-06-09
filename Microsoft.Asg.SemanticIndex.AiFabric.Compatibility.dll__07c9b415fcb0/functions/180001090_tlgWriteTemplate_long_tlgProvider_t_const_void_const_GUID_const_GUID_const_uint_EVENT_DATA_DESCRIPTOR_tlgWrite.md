# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)

- ea: `0x180001090`
- end: `0x1800013d4`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z`
- size: `836`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011e90`

## callees

- `0x180001090`
- `0x1801f7110`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800013b9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800013b9`

## pseudocode

```c
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
    v23 = &String;
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
    v27 = &byte_1802990D8;
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
    v30 = &String;
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
    v33 = &byte_1802990D8;
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
    v36 = &byte_1802990D8;
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
    v39 = &String;
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
    v42 = &byte_1802990D8;
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
    v45 = &byte_1802990D8;
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
0x180001090  push    rbp
0x180001092  lea     rbp, [rsp-80h]
0x180001097  sub     rsp, 180h
0x18000109e  mov     rax, cs:__security_cookie
0x1800010a5  xor     rax, rsp
0x1800010a8  mov     [rbp+80h+var_10], rax
0x1800010ac  mov     rax, [rbp+80h+arg_98]
0x1800010b3  mov     r10, rcx
0x1800010b6  mov     r9, rdx
0x1800010b9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800010c0  mov     r8, [rax]
0x1800010c3  test    r8, r8
0x1800010c6  jz      short loc_1800010E6
0x1800010c8  mov     rax, rcx
0x1800010cb  nop     dword ptr [rax+rax+00h]
0x1800010d0  cmp     word ptr [r8+rax*2+2], 0
0x1800010d7  lea     rax, [rax+1]
0x1800010db  jnz     short loc_1800010D0
0x1800010dd  lea     eax, ds:2[rax*2]
0x1800010e4  jmp     short loc_1800010F2
0x1800010e6  lea     r8, String
0x1800010ed  mov     eax, 2
0x1800010f2  mov     [rbp+80h+var_18], eax
0x1800010f5  mov     rax, [rbp+80h+arg_90]
0x1800010fc  mov     [rbp+80h+var_20], r8
0x180001100  xor     r8d, r8d; ActivityId
0x180001103  mov     [rbp+80h+var_14], r8d
0x180001107  mov     rdx, [rax]
0x18000110a  test    rdx, rdx
0x18000110d  jz      short loc_18000111F
0x18000110f  mov     rax, rcx
0x180001112  inc     rax
0x180001115  cmp     [rdx+rax], r8b
0x180001119  jnz     short loc_180001112
0x18000111b  inc     eax
0x18000111d  jmp     short loc_18000112B
0x18000111f  lea     rdx, byte_1802990D8
0x180001126  mov     eax, 1
0x18000112b  mov     [rbp+80h+var_28], eax
0x18000112e  mov     rax, [rbp+80h+arg_88]
0x180001135  mov     [rbp+80h+var_40], rax
0x180001139  mov     rax, [rbp+80h+arg_80]
0x180001140  mov     [rbp+80h+var_30], rdx
0x180001144  mov     [rbp+80h+var_24], r8d
0x180001148  mov     [rbp+80h+var_38], 4
0x180001150  mov     rdx, [rax]
0x180001153  test    rdx, rdx
0x180001156  jz      short loc_180001175
0x180001158  mov     rax, rcx
0x18000115b  nop     dword ptr [rax+rax+00h]
0x180001160  cmp     [rdx+rax*2+2], r8w
0x180001166  lea     rax, [rax+1]
0x18000116a  jnz     short loc_180001160
0x18000116c  lea     eax, ds:2[rax*2]
0x180001173  jmp     short loc_180001181
0x180001175  lea     rdx, String
0x18000117c  mov     eax, 2
0x180001181  mov     [rbp+80h+var_48], eax
0x180001184  mov     rax, [rbp+80h+arg_78]
0x18000118b  mov     [rbp+80h+var_50], rdx
0x18000118f  mov     [rbp+80h+var_44], r8d
0x180001193  mov     rdx, [rax]
0x180001196  test    rdx, rdx
0x180001199  jz      short loc_1800011AD
0x18000119b  mov     rax, rcx
0x18000119e  xchg    ax, ax
0x1800011a0  inc     rax
0x1800011a3  cmp     [rdx+rax], r8b
0x1800011a7  jnz     short loc_1800011A0
0x1800011a9  inc     eax
0x1800011ab  jmp     short loc_1800011B9
0x1800011ad  lea     rdx, byte_1802990D8
0x1800011b4  mov     eax, 1
0x1800011b9  mov     [rbp+80h+var_58], eax
0x1800011bc  mov     rax, [rbp+80h+arg_70]
0x1800011c3  mov     [rbp+80h+var_70], rax
0x1800011c7  mov     rax, [rbp+80h+arg_68]
0x1800011ce  mov     [rbp+80h+var_60], rdx
0x1800011d2  mov     [rbp+80h+var_54], r8d
0x1800011d6  mov     [rbp+80h+var_68], 4
0x1800011de  mov     rdx, [rax]
0x1800011e1  test    rdx, rdx
0x1800011e4  jz      short loc_1800011FD
0x1800011e6  mov     rax, rcx
0x1800011e9  nop     dword ptr [rax+00000000h]
0x1800011f0  inc     rax
0x1800011f3  cmp     [rdx+rax], r8b
0x1800011f7  jnz     short loc_1800011F0
0x1800011f9  inc     eax
0x1800011fb  jmp     short loc_180001209
0x1800011fd  lea     rdx, byte_1802990D8
0x180001204  mov     eax, 1
0x180001209  mov     [rbp+80h+var_78], eax
0x18000120c  mov     rax, [rbp+80h+arg_60]
0x180001213  mov     [rbp+80h+var_90], rax
0x180001217  mov     rax, [rbp+80h+arg_58]
0x18000121e  mov     [rbp+80h+var_80], rdx
0x180001222  mov     [rbp+80h+var_74], r8d
0x180001226  mov     [rbp+80h+var_88], 4
0x18000122e  mov     rdx, [rax]
0x180001231  test    rdx, rdx
0x180001234  jz      short loc_180001255
0x180001236  mov     rax, rcx
0x180001239  nop     dword ptr [rax+00000000h]
0x180001240  cmp     [rdx+rax*2+2], r8w
0x180001246  lea     rax, [rax+1]
0x18000124a  jnz     short loc_180001240
0x18000124c  lea     eax, ds:2[rax*2]
0x180001253  jmp     short loc_180001261
0x180001255  lea     rdx, String
0x18000125c  mov     eax, 2
0x180001261  mov     [rbp+80h+var_98], eax
0x180001264  mov     rax, [rbp+80h+arg_50]
0x18000126b  mov     [rbp+80h+var_B0], rax
0x18000126f  mov     rax, [rbp+80h+arg_48]
0x180001276  mov     [rbp+80h+var_A0], rdx
0x18000127a  mov     [rbp+80h+var_94], r8d
0x18000127e  mov     [rbp+80h+var_A8], 4
0x180001286  mov     rdx, [rax]
0x180001289  test    rdx, rdx
0x18000128c  jz      short loc_18000129E
0x18000128e  mov     rax, rcx
0x180001291  inc     rax
0x180001294  cmp     [rdx+rax], r8b
0x180001298  jnz     short loc_180001291
0x18000129a  inc     eax
0x18000129c  jmp     short loc_1800012AA
0x18000129e  lea     rdx, byte_1802990D8
0x1800012a5  mov     eax, 1
0x1800012aa  mov     [rbp+80h+var_B8], eax
0x1800012ad  mov     rax, [rbp+80h+arg_40]
0x1800012b4  mov     [rbp+80h+var_D0], rax
0x1800012b8  mov     rax, [rbp+80h+arg_38]
0x1800012bf  mov     [rbp+80h+var_C0], rdx
0x1800012c3  mov     [rbp+80h+var_B4], r8d
0x1800012c7  mov     [rbp+80h+var_C8], 4
0x1800012cf  mov     rdx, [rax]
0x1800012d2  test    rdx, rdx
0x1800012d5  jz      short loc_1800012E4
0x1800012d7  inc     rcx
0x1800012da  cmp     [rdx+rcx], r8b
0x1800012de  jnz     short loc_1800012D7
0x1800012e0  inc     ecx
0x1800012e2  jmp     short loc_1800012F0
0x1800012e4  lea     rdx, byte_1802990D8
0x1800012eb  mov     ecx, 1
0x1800012f0  mov     rax, [rbp+80h+arg_30]
0x1800012f7  mov     [rbp+80h+var_F0], rax
0x1800012fb  mov     rax, [rbp+80h+arg_28]
0x180001302  mov     [rbp+80h+var_100], rax
0x180001306  mov     rax, [rbp+80h+arg_20]
0x18000130d  mov     [rsp+180h+var_110], rax
0x180001312  movzx   eax, byte ptr [r9]
0x180001316  shl     eax, 18h
0x180001319  mov     dword ptr [rsp+180h+EventDescriptor.Id], eax
0x18000131d  movzx   eax, word ptr [r9+1]
0x180001322  mov     dword ptr [rsp+180h+EventDescriptor.Level], eax
0x180001326  mov     rax, [r9+3]
0x18000132a  mov     [rsp+180h+EventDescriptor.Keyword], rax
0x18000132f  mov     rax, [r10+8]
0x180001333  mov     [rsp+180h+var_130.Ptr], rax
0x180001338  mov     [rbp+80h+var_D8], ecx
0x18000133b  lea     rcx, [r9+0Bh]
0x18000133f  mov     [rbp+80h+var_E0], rdx
0x180001343  xor     r9d, r9d; RelatedActivityId
0x180001346  mov     [rbp+80h+var_D4], r8d
0x18000134a  lea     rdx, [rsp+180h+EventDescriptor]; EventDescriptor
0x18000134f  mov     [rbp+80h+var_E8], 4
0x180001357  mov     [rbp+80h+var_F8], 8
0x18000135f  mov     [rsp+180h+var_108], 8
0x180001368  movzx   eax, word ptr [rax]
0x18000136b  mov     [rsp+180h+var_130.Size], eax
0x18000136f  movzx   eax, word ptr [rcx]
0x180001372  mov     [rsp+180h+var_118], eax
0x180001376  lea     rax, _TraceLoggingMetadataEnd
0x18000137d  mov     [rsp+180h+var_120], rcx
0x180001382  lea     rcx, _TraceLoggingMetadata
0x180001389  sub     eax, ecx
0x18000138b  mov     dword ptr [rsp+180h+var_130.0Ch], 2
0x180001393  mov     [rsp+180h+var_114], 1
0x18000139b  mov     [rsp+180h+var_150], eax
0x18000139f  mov     eax, [rsp+180h+var_150]
0x1800013a3  mov     rcx, [r10+20h]; RegHandle
0x1800013a7  lea     rax, [rsp+180h+var_130]
0x1800013ac  mov     [rsp+180h+UserData], rax; UserData
0x1800013b1  mov     [rsp+180h+UserDataCount], 12h; UserDataCount
0x1800013b9  call    cs:__imp_EventWriteTransfer
0x1800013bf  mov     rcx, [rbp+80h+var_10]
0x1800013c3  xor     rcx, rsp; StackCookie
0x1800013c6  call    __security_check_cookie
0x1800013cb  add     rsp, 180h
0x1800013d2  pop     rbp
0x1800013d3  retn
```
