# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)

- ea: `0x1800011b0`
- end: `0x1800014f4`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z`
- size: `836`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64, __int64, __int64, const wchar_t **, __int64, const wchar_t **, __int64, __int64 **, __int64, const wchar_t **, __int64, const wchar_t **, __int64 **, __int64, const wchar_t **, __int64 **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800156c0`

## callees

- `0x1800011b0`
- `0x18004c070`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800014d9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800014d9`

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
        __int64 **a12,
        __int64 a13,
        const wchar_t **a14,
        __int64 a15,
        const wchar_t **a16,
        __int64 **a17,
        __int64 a18,
        const wchar_t **a19,
        __int64 **a20)
{
  __int64 v22; // rcx
  __int64 *v23; // r8
  __int64 v24; // rax
  bool v25; // zf
  int v26; // eax
  const wchar_t *v27; // rdx
  __int64 v28; // rax
  int v29; // eax
  __int64 *v30; // rdx
  __int64 v31; // rax
  int v32; // eax
  const wchar_t *v33; // rdx
  __int64 v34; // rax
  int v35; // eax
  const wchar_t *v36; // rdx
  __int64 v37; // rax
  int v38; // eax
  __int64 *v39; // rdx
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
  __int64 *v69; // [rsp+E0h] [rbp-20h]
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
  __int64 *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  __int64 v85; // [rsp+140h] [rbp+40h]
  __int64 v86; // [rsp+148h] [rbp+48h]
  const wchar_t *v87; // [rsp+150h] [rbp+50h]
  int v88; // [rsp+158h] [rbp+58h]
  int v89; // [rsp+15Ch] [rbp+5Ch]
  __int64 *v90; // [rsp+160h] [rbp+60h]
  int v91; // [rsp+168h] [rbp+68h]
  int v92; // [rsp+16Ch] [rbp+6Ch]

  v22 = -1;
  v23 = *a20;
  if ( *a20 )
  {
    v24 = -1;
    do
      v25 = *((_WORD *)v23 + ++v24) == 0;
    while ( !v25 );
    v26 = 2 * v24 + 2;
  }
  else
  {
    v23 = &qword_18006D0D8;
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
    v27 = &qword_18006F810;
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
      v25 = *((_WORD *)v30 + ++v31) == 0;
    while ( !v25 );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &qword_18006D0D8;
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
    v33 = &qword_18006F810;
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
    v36 = &qword_18006F810;
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
      v25 = *((_WORD *)v39 + ++v40) == 0;
    while ( !v25 );
    v41 = 2 * v40 + 2;
  }
  else
  {
    v39 = &qword_18006D0D8;
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
    v42 = &qword_18006F810;
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
    v45 = &qword_18006F810;
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
0x1800011b0  push    rbp
0x1800011b2  lea     rbp, [rsp-80h]
0x1800011b7  sub     rsp, 180h
0x1800011be  mov     rax, cs:__security_cookie
0x1800011c5  xor     rax, rsp
0x1800011c8  mov     [rbp+80h+var_10], rax
0x1800011cc  mov     rax, [rbp+80h+arg_98]
0x1800011d3  mov     r10, rcx
0x1800011d6  mov     r9, rdx
0x1800011d9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800011e0  mov     r8, [rax]
0x1800011e3  test    r8, r8
0x1800011e6  jz      short loc_180001206
0x1800011e8  mov     rax, rcx
0x1800011eb  nop     dword ptr [rax+rax+00h]
0x1800011f0  cmp     word ptr [r8+rax*2+2], 0
0x1800011f7  lea     rax, [rax+1]
0x1800011fb  jnz     short loc_1800011F0
0x1800011fd  lea     eax, ds:2[rax*2]
0x180001204  jmp     short loc_180001212
0x180001206  lea     r8, qword_18006D0D8
0x18000120d  mov     eax, 2
0x180001212  mov     [rbp+80h+var_18], eax
0x180001215  mov     rax, [rbp+80h+arg_90]
0x18000121c  mov     [rbp+80h+var_20], r8
0x180001220  xor     r8d, r8d; ActivityId
0x180001223  mov     [rbp+80h+var_14], r8d
0x180001227  mov     rdx, [rax]
0x18000122a  test    rdx, rdx
0x18000122d  jz      short loc_18000123F
0x18000122f  mov     rax, rcx
0x180001232  inc     rax
0x180001235  cmp     [rdx+rax], r8b
0x180001239  jnz     short loc_180001232
0x18000123b  inc     eax
0x18000123d  jmp     short loc_18000124B
0x18000123f  lea     rdx, qword_18006F810
0x180001246  mov     eax, 1
0x18000124b  mov     [rbp+80h+var_28], eax
0x18000124e  mov     rax, [rbp+80h+arg_88]
0x180001255  mov     [rbp+80h+var_40], rax
0x180001259  mov     rax, [rbp+80h+arg_80]
0x180001260  mov     [rbp+80h+var_30], rdx
0x180001264  mov     [rbp+80h+var_24], r8d
0x180001268  mov     [rbp+80h+var_38], 4
0x180001270  mov     rdx, [rax]
0x180001273  test    rdx, rdx
0x180001276  jz      short loc_180001295
0x180001278  mov     rax, rcx
0x18000127b  nop     dword ptr [rax+rax+00h]
0x180001280  cmp     [rdx+rax*2+2], r8w
0x180001286  lea     rax, [rax+1]
0x18000128a  jnz     short loc_180001280
0x18000128c  lea     eax, ds:2[rax*2]
0x180001293  jmp     short loc_1800012A1
0x180001295  lea     rdx, qword_18006D0D8
0x18000129c  mov     eax, 2
0x1800012a1  mov     [rbp+80h+var_48], eax
0x1800012a4  mov     rax, [rbp+80h+arg_78]
0x1800012ab  mov     [rbp+80h+var_50], rdx
0x1800012af  mov     [rbp+80h+var_44], r8d
0x1800012b3  mov     rdx, [rax]
0x1800012b6  test    rdx, rdx
0x1800012b9  jz      short loc_1800012CD
0x1800012bb  mov     rax, rcx
0x1800012be  xchg    ax, ax
0x1800012c0  inc     rax
0x1800012c3  cmp     [rdx+rax], r8b
0x1800012c7  jnz     short loc_1800012C0
0x1800012c9  inc     eax
0x1800012cb  jmp     short loc_1800012D9
0x1800012cd  lea     rdx, qword_18006F810
0x1800012d4  mov     eax, 1
0x1800012d9  mov     [rbp+80h+var_58], eax
0x1800012dc  mov     rax, [rbp+80h+arg_70]
0x1800012e3  mov     [rbp+80h+var_70], rax
0x1800012e7  mov     rax, [rbp+80h+arg_68]
0x1800012ee  mov     [rbp+80h+var_60], rdx
0x1800012f2  mov     [rbp+80h+var_54], r8d
0x1800012f6  mov     [rbp+80h+var_68], 4
0x1800012fe  mov     rdx, [rax]
0x180001301  test    rdx, rdx
0x180001304  jz      short loc_18000131D
0x180001306  mov     rax, rcx
0x180001309  nop     dword ptr [rax+00000000h]
0x180001310  inc     rax
0x180001313  cmp     [rdx+rax], r8b
0x180001317  jnz     short loc_180001310
0x180001319  inc     eax
0x18000131b  jmp     short loc_180001329
0x18000131d  lea     rdx, qword_18006F810
0x180001324  mov     eax, 1
0x180001329  mov     [rbp+80h+var_78], eax
0x18000132c  mov     rax, [rbp+80h+arg_60]
0x180001333  mov     [rbp+80h+var_90], rax
0x180001337  mov     rax, [rbp+80h+arg_58]
0x18000133e  mov     [rbp+80h+var_80], rdx
0x180001342  mov     [rbp+80h+var_74], r8d
0x180001346  mov     [rbp+80h+var_88], 4
0x18000134e  mov     rdx, [rax]
0x180001351  test    rdx, rdx
0x180001354  jz      short loc_180001375
0x180001356  mov     rax, rcx
0x180001359  nop     dword ptr [rax+00000000h]
0x180001360  cmp     [rdx+rax*2+2], r8w
0x180001366  lea     rax, [rax+1]
0x18000136a  jnz     short loc_180001360
0x18000136c  lea     eax, ds:2[rax*2]
0x180001373  jmp     short loc_180001381
0x180001375  lea     rdx, qword_18006D0D8
0x18000137c  mov     eax, 2
0x180001381  mov     [rbp+80h+var_98], eax
0x180001384  mov     rax, [rbp+80h+arg_50]
0x18000138b  mov     [rbp+80h+var_B0], rax
0x18000138f  mov     rax, [rbp+80h+arg_48]
0x180001396  mov     [rbp+80h+var_A0], rdx
0x18000139a  mov     [rbp+80h+var_94], r8d
0x18000139e  mov     [rbp+80h+var_A8], 4
0x1800013a6  mov     rdx, [rax]
0x1800013a9  test    rdx, rdx
0x1800013ac  jz      short loc_1800013BE
0x1800013ae  mov     rax, rcx
0x1800013b1  inc     rax
0x1800013b4  cmp     [rdx+rax], r8b
0x1800013b8  jnz     short loc_1800013B1
0x1800013ba  inc     eax
0x1800013bc  jmp     short loc_1800013CA
0x1800013be  lea     rdx, qword_18006F810
0x1800013c5  mov     eax, 1
0x1800013ca  mov     [rbp+80h+var_B8], eax
0x1800013cd  mov     rax, [rbp+80h+arg_40]
0x1800013d4  mov     [rbp+80h+var_D0], rax
0x1800013d8  mov     rax, [rbp+80h+arg_38]
0x1800013df  mov     [rbp+80h+var_C0], rdx
0x1800013e3  mov     [rbp+80h+var_B4], r8d
0x1800013e7  mov     [rbp+80h+var_C8], 4
0x1800013ef  mov     rdx, [rax]
0x1800013f2  test    rdx, rdx
0x1800013f5  jz      short loc_180001404
0x1800013f7  inc     rcx
0x1800013fa  cmp     [rdx+rcx], r8b
0x1800013fe  jnz     short loc_1800013F7
0x180001400  inc     ecx
0x180001402  jmp     short loc_180001410
0x180001404  lea     rdx, qword_18006F810
0x18000140b  mov     ecx, 1
0x180001410  mov     rax, [rbp+80h+arg_30]
0x180001417  mov     [rbp+80h+var_F0], rax
0x18000141b  mov     rax, [rbp+80h+arg_28]
0x180001422  mov     [rbp+80h+var_100], rax
0x180001426  mov     rax, [rbp+80h+arg_20]
0x18000142d  mov     [rsp+180h+var_110], rax
0x180001432  movzx   eax, byte ptr [r9]
0x180001436  shl     eax, 18h
0x180001439  mov     dword ptr [rsp+180h+EventDescriptor.Id], eax
0x18000143d  movzx   eax, word ptr [r9+1]
0x180001442  mov     dword ptr [rsp+180h+EventDescriptor.Level], eax
0x180001446  mov     rax, [r9+3]
0x18000144a  mov     [rsp+180h+EventDescriptor.Keyword], rax
0x18000144f  mov     rax, [r10+8]
0x180001453  mov     [rsp+180h+var_130.Ptr], rax
0x180001458  mov     [rbp+80h+var_D8], ecx
0x18000145b  lea     rcx, [r9+0Bh]
0x18000145f  mov     [rbp+80h+var_E0], rdx
0x180001463  xor     r9d, r9d; RelatedActivityId
0x180001466  mov     [rbp+80h+var_D4], r8d
0x18000146a  lea     rdx, [rsp+180h+EventDescriptor]; EventDescriptor
0x18000146f  mov     [rbp+80h+var_E8], 4
0x180001477  mov     [rbp+80h+var_F8], 8
0x18000147f  mov     [rsp+180h+var_108], 8
0x180001488  movzx   eax, word ptr [rax]
0x18000148b  mov     [rsp+180h+var_130.Size], eax
0x18000148f  movzx   eax, word ptr [rcx]
0x180001492  mov     [rsp+180h+var_118], eax
0x180001496  lea     rax, _TraceLoggingMetadataEnd
0x18000149d  mov     [rsp+180h+var_120], rcx
0x1800014a2  lea     rcx, _TraceLoggingMetadata
0x1800014a9  sub     eax, ecx
0x1800014ab  mov     dword ptr [rsp+180h+var_130.0Ch], 2
0x1800014b3  mov     [rsp+180h+var_114], 1
0x1800014bb  mov     [rsp+180h+var_150], eax
0x1800014bf  mov     eax, [rsp+180h+var_150]
0x1800014c3  mov     rcx, [r10+20h]; RegHandle
0x1800014c7  lea     rax, [rsp+180h+var_130]
0x1800014cc  mov     [rsp+180h+UserData], rax; UserData
0x1800014d1  mov     [rsp+180h+UserDataCount], 12h; UserDataCount
0x1800014d9  call    cs:__imp_EventWriteTransfer
0x1800014df  mov     rcx, [rbp+80h+var_10]
0x1800014e3  xor     rcx, rsp; StackCookie
0x1800014e6  call    __security_check_cookie
0x1800014eb  add     rsp, 180h
0x1800014f2  pop     rbp
0x1800014f3  retn
```
