# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001120`
- end: `0x180001487`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@454564563@Z`
- size: `871`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, __int64, __int64, __int64, __int64, const wchar_t **, __int64, const wchar_t **, __int64, const wchar_t **, __int64, const wchar_t **, __int64, const wchar_t **, const wchar_t **, __int64, const wchar_t **, const wchar_t **, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f840`

## callees

- `0x180001120`
- `0x1800181b0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001469`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001469`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(
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
        const wchar_t **a20,
        __int64 a21)
{
  __int64 v24; // rcx
  const wchar_t *v25; // rdx
  __int64 v26; // rax
  bool v27; // zf
  int v28; // eax
  const wchar_t *v29; // rdx
  __int64 v30; // rax
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
  int v48; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v52; // [rsp+60h] [rbp-A0h]
  int v53; // [rsp+68h] [rbp-98h]
  int v54; // [rsp+6Ch] [rbp-94h]
  __int64 v55; // [rsp+70h] [rbp-90h]
  __int64 v56; // [rsp+78h] [rbp-88h]
  __int64 v57; // [rsp+80h] [rbp-80h]
  __int64 v58; // [rsp+88h] [rbp-78h]
  __int64 v59; // [rsp+90h] [rbp-70h]
  __int64 v60; // [rsp+98h] [rbp-68h]
  const wchar_t *v61; // [rsp+A0h] [rbp-60h]
  int v62; // [rsp+A8h] [rbp-58h]
  int v63; // [rsp+ACh] [rbp-54h]
  __int64 v64; // [rsp+B0h] [rbp-50h]
  __int64 v65; // [rsp+B8h] [rbp-48h]
  const wchar_t *v66; // [rsp+C0h] [rbp-40h]
  int v67; // [rsp+C8h] [rbp-38h]
  int v68; // [rsp+CCh] [rbp-34h]
  __int64 v69; // [rsp+D0h] [rbp-30h]
  __int64 v70; // [rsp+D8h] [rbp-28h]
  const wchar_t *v71; // [rsp+E0h] [rbp-20h]
  int v72; // [rsp+E8h] [rbp-18h]
  int v73; // [rsp+ECh] [rbp-14h]
  __int64 v74; // [rsp+F0h] [rbp-10h]
  __int64 v75; // [rsp+F8h] [rbp-8h]
  const wchar_t *v76; // [rsp+100h] [rbp+0h]
  int v77; // [rsp+108h] [rbp+8h]
  int v78; // [rsp+10Ch] [rbp+Ch]
  __int64 v79; // [rsp+110h] [rbp+10h]
  __int64 v80; // [rsp+118h] [rbp+18h]
  const wchar_t *v81; // [rsp+120h] [rbp+20h]
  int v82; // [rsp+128h] [rbp+28h]
  int v83; // [rsp+12Ch] [rbp+2Ch]
  const wchar_t *v84; // [rsp+130h] [rbp+30h]
  int v85; // [rsp+138h] [rbp+38h]
  int v86; // [rsp+13Ch] [rbp+3Ch]
  __int64 v87; // [rsp+140h] [rbp+40h]
  __int64 v88; // [rsp+148h] [rbp+48h]
  const wchar_t *v89; // [rsp+150h] [rbp+50h]
  int v90; // [rsp+158h] [rbp+58h]
  int v91; // [rsp+15Ch] [rbp+5Ch]
  const wchar_t *v92; // [rsp+160h] [rbp+60h]
  int v93; // [rsp+168h] [rbp+68h]
  int v94; // [rsp+16Ch] [rbp+6Ch]
  __int64 v95; // [rsp+170h] [rbp+70h]
  __int64 v96; // [rsp+178h] [rbp+78h]

  v95 = a21;
  v96 = 8;
  v24 = -1;
  v25 = *a20;
  if ( *a20 )
  {
    v26 = -1;
    do
      v27 = v25[++v26] == 0;
    while ( !v27 );
    v28 = 2 * v26 + 2;
  }
  else
  {
    v25 = &S2;
    v28 = 2;
  }
  v93 = v28;
  v92 = v25;
  v94 = 0;
  v29 = *a19;
  if ( *a19 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *((_BYTE *)v29 + v30) );
    v31 = v30 + 1;
  }
  else
  {
    v29 = &qword_1800250A8;
    v31 = 1;
  }
  v90 = v31;
  v87 = a18;
  v89 = v29;
  v91 = 0;
  v88 = 4;
  v32 = *a17;
  if ( *a17 )
  {
    v33 = -1;
    do
      v27 = v32[++v33] == 0;
    while ( !v27 );
    v34 = 2 * v33 + 2;
  }
  else
  {
    v32 = &S2;
    v34 = 2;
  }
  v85 = v34;
  v84 = v32;
  v86 = 0;
  v35 = *a16;
  if ( *a16 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_BYTE *)v35 + v36) );
    v37 = v36 + 1;
  }
  else
  {
    v35 = &qword_1800250A8;
    v37 = 1;
  }
  v82 = v37;
  v79 = a15;
  v81 = v35;
  v83 = 0;
  v80 = 4;
  v38 = *a14;
  if ( *a14 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *((_BYTE *)v38 + v39) );
    v40 = v39 + 1;
  }
  else
  {
    v38 = &qword_1800250A8;
    v40 = 1;
  }
  v77 = v40;
  v74 = a13;
  v76 = v38;
  v78 = 0;
  v75 = 4;
  v41 = *a12;
  if ( *a12 )
  {
    v42 = -1;
    do
      v27 = v41[++v42] == 0;
    while ( !v27 );
    v43 = 2 * v42 + 2;
  }
  else
  {
    v41 = &S2;
    v43 = 2;
  }
  v72 = v43;
  v69 = a11;
  v71 = v41;
  v73 = 0;
  v70 = 4;
  v44 = *a10;
  if ( *a10 )
  {
    v45 = -1;
    do
      ++v45;
    while ( *((_BYTE *)v44 + v45) );
    v46 = v45 + 1;
  }
  else
  {
    v44 = &qword_1800250A8;
    v46 = 1;
  }
  v67 = v46;
  v64 = a9;
  v66 = v44;
  v68 = 0;
  v65 = 4;
  v47 = *a8;
  if ( *a8 )
  {
    do
      ++v24;
    while ( *((_BYTE *)v47 + v24) );
    v48 = v24 + 1;
  }
  else
  {
    v47 = &qword_1800250A8;
    v48 = 1;
  }
  v59 = a7;
  v57 = a6;
  v55 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v62 = v48;
  v61 = v47;
  v63 = 0;
  v60 = 4;
  v58 = 8;
  v56 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v53 = *(unsigned __int16 *)(a2 + 11);
  v52 = a2 + 11;
  UserData.Reserved = 2;
  v54 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, 0, 0x13u, &UserData);
}

```

## disassembly

```asm
0x180001120  push    rbp
0x180001122  lea     rbp, [rsp-90h]
0x18000112a  sub     rsp, 190h
0x180001131  mov     rax, cs:__security_cookie
0x180001138  xor     rax, rsp
0x18000113b  mov     [rbp+90h+var_10], rax
0x180001142  mov     rax, [rbp+90h+arg_A0]
0x180001149  mov     r11, r8
0x18000114c  mov     [rbp+90h+var_20], rax
0x180001150  mov     r8, rdx
0x180001153  mov     rax, [rbp+90h+arg_98]
0x18000115a  xor     r9d, r9d; RelatedActivityId
0x18000115d  mov     r10, rcx
0x180001160  mov     [rbp+90h+var_18], 8
0x180001168  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000116f  mov     rdx, [rax]
0x180001172  test    rdx, rdx
0x180001175  jz      short loc_180001195
0x180001177  mov     rax, rcx
0x18000117a  nop     word ptr [rax+rax+00h]
0x180001180  cmp     [rdx+rax*2+2], r9w
0x180001186  lea     rax, [rax+1]
0x18000118a  jnz     short loc_180001180
0x18000118c  lea     eax, ds:2[rax*2]
0x180001193  jmp     short loc_1800011A1
0x180001195  lea     rdx, S2
0x18000119c  mov     eax, 2
0x1800011a1  mov     [rbp+90h+var_28], eax
0x1800011a4  mov     rax, [rbp+90h+arg_90]
0x1800011ab  mov     [rbp+90h+var_30], rdx
0x1800011af  mov     [rbp+90h+var_24], r9d
0x1800011b3  mov     rdx, [rax]
0x1800011b6  test    rdx, rdx
0x1800011b9  jz      short loc_1800011CD
0x1800011bb  mov     rax, rcx
0x1800011be  xchg    ax, ax
0x1800011c0  inc     rax
0x1800011c3  cmp     [rdx+rax], r9b
0x1800011c7  jnz     short loc_1800011C0
0x1800011c9  inc     eax
0x1800011cb  jmp     short loc_1800011D9
0x1800011cd  lea     rdx, qword_1800250A8
0x1800011d4  mov     eax, 1
0x1800011d9  mov     [rbp+90h+var_38], eax
0x1800011dc  mov     rax, [rbp+90h+arg_88]
0x1800011e3  mov     [rbp+90h+var_50], rax
0x1800011e7  mov     rax, [rbp+90h+arg_80]
0x1800011ee  mov     [rbp+90h+var_40], rdx
0x1800011f2  mov     [rbp+90h+var_34], r9d
0x1800011f6  mov     [rbp+90h+var_48], 4
0x1800011fe  mov     rdx, [rax]
0x180001201  test    rdx, rdx
0x180001204  jz      short loc_180001225
0x180001206  mov     rax, rcx
0x180001209  nop     dword ptr [rax+00000000h]
0x180001210  cmp     [rdx+rax*2+2], r9w
0x180001216  lea     rax, [rax+1]
0x18000121a  jnz     short loc_180001210
0x18000121c  lea     eax, ds:2[rax*2]
0x180001223  jmp     short loc_180001231
0x180001225  lea     rdx, S2
0x18000122c  mov     eax, 2
0x180001231  mov     [rbp+90h+var_58], eax
0x180001234  mov     rax, [rbp+90h+arg_78]
0x18000123b  mov     [rbp+90h+var_60], rdx
0x18000123f  mov     [rbp+90h+var_54], r9d
0x180001243  mov     rdx, [rax]
0x180001246  test    rdx, rdx
0x180001249  jz      short loc_18000125D
0x18000124b  mov     rax, rcx
0x18000124e  xchg    ax, ax
0x180001250  inc     rax
0x180001253  cmp     [rdx+rax], r9b
0x180001257  jnz     short loc_180001250
0x180001259  inc     eax
0x18000125b  jmp     short loc_180001269
0x18000125d  lea     rdx, qword_1800250A8
0x180001264  mov     eax, 1
0x180001269  mov     [rbp+90h+var_68], eax
0x18000126c  mov     rax, [rbp+90h+arg_70]
0x180001273  mov     [rbp+90h+var_80], rax
0x180001277  mov     rax, [rbp+90h+arg_68]
0x18000127e  mov     [rbp+90h+var_70], rdx
0x180001282  mov     [rbp+90h+var_64], r9d
0x180001286  mov     [rbp+90h+var_78], 4
0x18000128e  mov     rdx, [rax]
0x180001291  test    rdx, rdx
0x180001294  jz      short loc_1800012AD
0x180001296  mov     rax, rcx
0x180001299  nop     dword ptr [rax+00000000h]
0x1800012a0  inc     rax
0x1800012a3  cmp     [rdx+rax], r9b
0x1800012a7  jnz     short loc_1800012A0
0x1800012a9  inc     eax
0x1800012ab  jmp     short loc_1800012B9
0x1800012ad  lea     rdx, qword_1800250A8
0x1800012b4  mov     eax, 1
0x1800012b9  mov     [rbp+90h+var_88], eax
0x1800012bc  mov     rax, [rbp+90h+arg_60]
0x1800012c3  mov     [rbp+90h+var_A0], rax
0x1800012c7  mov     rax, [rbp+90h+arg_58]
0x1800012ce  mov     [rbp+90h+var_90], rdx
0x1800012d2  mov     [rbp+90h+var_84], r9d
0x1800012d6  mov     [rbp+90h+var_98], 4
0x1800012de  mov     rdx, [rax]
0x1800012e1  test    rdx, rdx
0x1800012e4  jz      short loc_180001305
0x1800012e6  mov     rax, rcx
0x1800012e9  nop     dword ptr [rax+00000000h]
0x1800012f0  cmp     [rdx+rax*2+2], r9w
0x1800012f6  lea     rax, [rax+1]
0x1800012fa  jnz     short loc_1800012F0
0x1800012fc  lea     eax, ds:2[rax*2]
0x180001303  jmp     short loc_180001311
0x180001305  lea     rdx, S2
0x18000130c  mov     eax, 2
0x180001311  mov     [rbp+90h+var_A8], eax
0x180001314  mov     rax, [rbp+90h+arg_50]
0x18000131b  mov     [rbp+90h+var_C0], rax
0x18000131f  mov     rax, [rbp+90h+arg_48]
0x180001326  mov     [rbp+90h+var_B0], rdx
0x18000132a  mov     [rbp+90h+var_A4], r9d
0x18000132e  mov     [rbp+90h+var_B8], 4
0x180001336  mov     rdx, [rax]
0x180001339  test    rdx, rdx
0x18000133c  jz      short loc_18000134E
0x18000133e  mov     rax, rcx
0x180001341  inc     rax
0x180001344  cmp     [rdx+rax], r9b
0x180001348  jnz     short loc_180001341
0x18000134a  inc     eax
0x18000134c  jmp     short loc_18000135A
0x18000134e  lea     rdx, qword_1800250A8
0x180001355  mov     eax, 1
0x18000135a  mov     [rbp+90h+var_C8], eax
0x18000135d  mov     rax, [rbp+90h+arg_40]
0x180001364  mov     [rbp+90h+var_E0], rax
0x180001368  mov     rax, [rbp+90h+arg_38]
0x18000136f  mov     [rbp+90h+var_D0], rdx
0x180001373  mov     [rbp+90h+var_C4], r9d
0x180001377  mov     [rbp+90h+var_D8], 4
0x18000137f  mov     rdx, [rax]
0x180001382  test    rdx, rdx
0x180001385  jz      short loc_180001394
0x180001387  inc     rcx
0x18000138a  cmp     [rdx+rcx], r9b
0x18000138e  jnz     short loc_180001387
0x180001390  inc     ecx
0x180001392  jmp     short loc_1800013A0
0x180001394  lea     rdx, qword_1800250A8
0x18000139b  mov     ecx, 1
0x1800013a0  mov     rax, [rbp+90h+arg_30]
0x1800013a7  mov     [rbp+90h+var_100], rax
0x1800013ab  mov     rax, [rbp+90h+arg_28]
0x1800013b2  mov     [rbp+90h+var_110], rax
0x1800013b6  mov     rax, [rbp+90h+arg_20]
0x1800013bd  mov     [rsp+190h+var_120], rax
0x1800013c2  movzx   eax, byte ptr [r8]
0x1800013c6  shl     eax, 18h
0x1800013c9  mov     dword ptr [rsp+190h+EventDescriptor.Id], eax
0x1800013cd  movzx   eax, word ptr [r8+1]
0x1800013d2  mov     dword ptr [rsp+190h+EventDescriptor.Level], eax
0x1800013d6  mov     rax, [r8+3]
0x1800013da  mov     [rsp+190h+EventDescriptor.Keyword], rax
0x1800013df  mov     rax, [r10+8]
0x1800013e3  mov     [rsp+190h+var_140.Ptr], rax
0x1800013e8  mov     [rbp+90h+var_E8], ecx
0x1800013eb  lea     rcx, [r8+0Bh]
0x1800013ef  mov     [rbp+90h+var_F0], rdx
0x1800013f3  mov     r8, r11; ActivityId
0x1800013f6  mov     [rbp+90h+var_E4], r9d
0x1800013fa  lea     rdx, [rsp+190h+EventDescriptor]; EventDescriptor
0x1800013ff  mov     [rbp+90h+var_F8], 4
0x180001407  mov     [rbp+90h+var_108], 8
0x18000140f  mov     [rsp+190h+var_118], 8
0x180001418  movzx   eax, word ptr [rax]
0x18000141b  mov     [rsp+190h+var_140.Size], eax
0x18000141f  movzx   eax, word ptr [rcx]
0x180001422  mov     [rsp+190h+var_128], eax
0x180001426  lea     rax, _TraceLoggingMetadataEnd
0x18000142d  mov     [rsp+190h+var_130], rcx
0x180001432  lea     rcx, _TraceLoggingMetadata
0x180001439  sub     eax, ecx
0x18000143b  mov     dword ptr [rsp+190h+var_140.0Ch], 2
0x180001443  mov     [rsp+190h+var_124], 1
0x18000144b  mov     [rsp+190h+var_160], eax
0x18000144f  mov     eax, [rsp+190h+var_160]
0x180001453  mov     rcx, [r10+20h]; RegHandle
0x180001457  lea     rax, [rsp+190h+var_140]
0x18000145c  mov     [rsp+190h+UserData], rax; UserData
0x180001461  mov     [rsp+190h+UserDataCount], 13h; UserDataCount
0x180001469  call    cs:__imp_EventWriteTransfer
0x18000146f  mov     rcx, [rbp+90h+var_10]
0x180001476  xor     rcx, rsp; StackCookie
0x180001479  call    __security_check_cookie
0x18000147e  add     rsp, 190h
0x180001485  pop     rbp
0x180001486  retn
```
