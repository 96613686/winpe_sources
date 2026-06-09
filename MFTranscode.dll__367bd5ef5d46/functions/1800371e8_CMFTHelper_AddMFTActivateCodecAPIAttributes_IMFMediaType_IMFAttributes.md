# CMFTHelper::AddMFTActivateCodecAPIAttributes(IMFMediaType *,IMFAttributes *)

- ea: `0x1800371e8`
- end: `0x180037738`
- name: `?AddMFTActivateCodecAPIAttributes@CMFTHelper@@CAJPEAUIMFMediaType@@PEAUIMFAttributes@@@Z`
- size: `1360`
- prototype: `__int64 __fastcall(struct IMFMediaType *, struct IMFAttributes *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009c5c`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x1800174c0`
- `0x180017dc0`
- `0x18001c280`
- `0x18002bb4c`
- `0x1800371e8`
- `0x180037740`
- `0x180037e2c`
- `0x18004f3c8`
- `0x18004f410`
- `0x1800594a4`
- `0x1800594b0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800376f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800376f7`

## pseudocode

```c
__int64 __fastcall CMFTHelper::AddMFTActivateCodecAPIAttributes(struct IMFMediaType *a1, struct IMFAttributes *a2)
{
  int v4; // edi
  CallStackTracing *v5; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v7; // rdx
  CallStackTracing *v8; // rcx
  struct CallStackContext *v9; // rax
  struct IMFAttributesVtbl *lpVtbl; // rax
  wchar_t *v11; // rbx
  int v12; // r8d
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
  struct IMFAttributesVtbl *v15; // rax
  unsigned int v16; // r8d
  int v17; // edi
  int v18; // ebx
  int v19; // eax
  __int64 v20; // r8
  unsigned int v21; // r15d
  unsigned int v22; // ebx
  int v23; // r12d
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  unsigned int v27; // [rsp+38h] [rbp-49h] BYREF
  int v28; // [rsp+3Ch] [rbp-45h] BYREF
  _BYTE v29[4]; // [rsp+40h] [rbp-41h] BYREF
  unsigned int v30; // [rsp+44h] [rbp-3Dh] BYREF
  int v31; // [rsp+48h] [rbp-39h] BYREF
  wchar_t *String1; // [rsp+50h] [rbp-31h] BYREF
  int v33; // [rsp+58h] [rbp-29h] BYREF
  unsigned int v34; // [rsp+5Ch] [rbp-25h] BYREF
  _QWORD v35[2]; // [rsp+60h] [rbp-21h] BYREF
  GUID Buf2; // [rsp+70h] [rbp-11h] BYREF
  GUID Buf1; // [rsp+80h] [rbp-1h] BYREF

  v28 = 0;
  v27 = 0;
  String1 = 0;
  Buf2 = GUID_00000000_0000_0000_0000_000000000000;
  Buf1 = GUID_00000000_0000_0000_0000_000000000000;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v29,
    "CMFTHelper::AddMFTActivateCodecAPIAttributes",
    585);
  v4 = ((__int64 (__fastcall *)(struct IMFMediaType *, GUID *))a1->lpVtbl->GetMajorType)(a1, &Buf2);
  if ( v4 < 0 )
  {
    v5 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v5 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v5);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v4 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFTHelper::AddMFTActivateCodecAPIAttributes", 585, v4);
    }
    if ( g_wppLevels )
    {
      v7 = 28;
LABEL_9:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_51ca0e26e9bc306247403b211e8b86d4_Traceguids, 0, v4);
      goto LABEL_65;
    }
    goto LABEL_65;
  }
  if ( memcmp_0(&MFMediaType_Video, &Buf2, 0x10u) )
    goto LABEL_65;
  v4 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, GUID *))a1->lpVtbl->GetGUID)(
         a1,
         &MF_MT_SUBTYPE,
         &Buf1);
  if ( v4 >= 0 )
  {
    if ( memcmp_0(&Buf1, &MEDIASUBTYPE_H264, 0x10u) )
      goto LABEL_65;
    if ( ((int (__fastcall *)(struct IMFMediaType *, const GUID *, int *))a1->lpVtbl->GetUINT32)(
           a1,
           &MF_MT_MPEG2_PROFILE,
           &v28) >= 0 )
      goto LABEL_37;
    lpVtbl = a2->lpVtbl;
    v30 = 0;
    v28 = 77;
    if ( ((int (__fastcall *)(struct IMFAttributes *, const IID *, wchar_t **, unsigned int *))lpVtbl->GetAllocatedString)(
           a2,
           &MF_TRANSCODE_ENCODINGPROFILE,
           &String1,
           &v30) >= 0 )
    {
      v11 = String1;
      if ( !wcsncmp_0(String1, L"CP", 2u) || !wcsncmp_0(v11, L"AP", 2u) )
      {
        v12 = 100;
      }
      else
      {
        if ( wcsncmp_0(v11, L"BP", 2u) && wcsncmp_0(v11, L"SP", 2u) )
          goto LABEL_28;
        v12 = 66;
      }
      v28 = v12;
    }
LABEL_28:
    v4 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *))a1->lpVtbl->SetUINT32)(a1, &MF_MT_MPEG2_PROFILE);
    if ( v4 < 0 )
    {
      v13 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v13 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v14 = CallStackTracing::GetThreadRelativeContext(v13);
        if ( *((_DWORD *)v14 + 499) != v4 )
          CallStackContext::TraceFailure(v14, "CMFTHelper::AddMFTActivateCodecAPIAttributes", 621, v4);
      }
      if ( g_wppLevels )
      {
        v7 = 30;
        goto LABEL_9;
      }
      goto LABEL_65;
    }
LABEL_37:
    if ( ((int (__fastcall *)(struct IMFMediaType *, const GUID *, unsigned int *))a1->lpVtbl->GetUINT32)(
           a1,
           &MF_MT_MPEG2_LEVEL,
           &v27) >= 0 )
      goto LABEL_63;
    v15 = a2->lpVtbl;
    v31 = 0;
    v27 = 0;
    if ( ((int (__fastcall *)(struct IMFAttributes *, const IID *, wchar_t **, int *))v15->GetAllocatedString)(
           a2,
           &MF_TRANSCODE_ENCODINGPROFILE,
           &String1,
           &v31) >= 0 )
    {
      if ( v31 == 4 )
      {
        if ( String1[2] == 64 )
        {
          v16 = 10 * o__wtol_0(String1 + 3);
          v27 = v16;
          goto LABEL_47;
        }
      }
      else
      {
        if ( v31 != 5 )
        {
          v16 = 0;
          v27 = 0;
          goto LABEL_47;
        }
        if ( String1[2] == 64 )
        {
          v16 = o__wtol_0(String1 + 3);
          v27 = v16;
          goto LABEL_47;
        }
      }
    }
    v16 = v27;
LABEL_47:
    v30 = 0;
    v34 = 0;
    v35[0] = 0;
    v33 = 0;
    if ( !v16 )
    {
      v17 = MFGetAttribute2UINT32asUINT64(a1, &MF_MT_FRAME_SIZE, &v30, &v34);
      v18 = MFGetAttribute2UINT32asUINT64(a1, &MF_MT_FRAME_RATE, v35, (char *)v35 + 4);
      v19 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, int *))a1->lpVtbl->GetUINT32)(
              a1,
              &MF_MT_AVG_BITRATE,
              &v33);
      v21 = v28;
      v4 = v18 | v19 | v17;
      if ( !v4 )
      {
        v22 = 1;
        v23 = v33;
        while ( !(unsigned __int8)CheckLevelLimitPreEncode(v30, v34, v20, v21, v23, v22) )
        {
          if ( (int)++v22 >= 21 )
          {
            v22 = 20;
            break;
          }
        }
        ConvertAvcLevelToMFLevel(v22, &v27);
      }
      if ( !v27 )
        goto LABEL_64;
    }
    v4 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *))a1->lpVtbl->SetUINT32)(a1, &MF_MT_MPEG2_LEVEL);
    if ( v4 < 0 )
    {
      v24 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v24 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v25 = CallStackTracing::GetThreadRelativeContext(v24);
        if ( *((_DWORD *)v25 + 499) != v4 )
          CallStackContext::TraceFailure(v25, "CMFTHelper::AddMFTActivateCodecAPIAttributes", 707, v4);
      }
      if ( g_wppLevels )
      {
        v7 = 31;
        goto LABEL_9;
      }
      goto LABEL_65;
    }
LABEL_63:
    v21 = v28;
LABEL_64:
    ((void (__fastcall *)(struct IMFAttributes *, GUID *, _QWORD))a2->lpVtbl->SetUINT32)(
      a2,
      &GUID_dabb534a_1d99_4284_975a_d90e2239baa1,
      v21);
    goto LABEL_65;
  }
  v8 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v8 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v8 + 8) )
  {
    v9 = CallStackTracing::GetThreadRelativeContext(v8);
    if ( *((_DWORD *)v9 + 499) != v4 )
      CallStackContext::TraceFailure(v9, "CMFTHelper::AddMFTActivateCodecAPIAttributes", 591, v4);
  }
  if ( g_wppLevels )
  {
    v7 = 29;
    goto LABEL_9;
  }
LABEL_65:
  if ( String1 )
  {
    CoTaskMemFree(String1);
    String1 = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v29);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800371e8  mov     rax, rsp
0x1800371eb  mov     [rax+18h], rbx
0x1800371ef  push    rbp
0x1800371f0  push    rsi
0x1800371f1  push    rdi
0x1800371f2  push    r12
0x1800371f4  push    r13
0x1800371f6  push    r14
0x1800371f8  push    r15
0x1800371fa  lea     rbp, [rax-5Fh]
0x1800371fe  sub     rsp, 0A0h
0x180037205  movaps  xmmword ptr [rax-48h], xmm6
0x180037209  mov     rax, cs:__security_cookie
0x180037210  xor     rax, rsp
0x180037213  mov     [rbp+57h+var_48], rax
0x180037217  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18003721e  xor     r13d, r13d
0x180037221  lea     r15, aCmfthelperAddm; "CMFTHelper::AddMFTActivateCodecAPIAttri"...
0x180037228  mov     r14, rdx
0x18003722b  mov     [rbp+57h+var_9C], r13d
0x18003722f  mov     rsi, rcx
0x180037232  mov     [rbp+57h+var_A0], r13d
0x180037236  mov     ebx, 249h
0x18003723b  mov     [rbp+57h+String1], r13
0x18003723f  mov     r8d, ebx; int
0x180037242  lea     rcx, [rbp+57h+var_98]; this
0x180037246  mov     rdx, r15; char *
0x180037249  movdqu  [rbp+57h+Buf2], xmm0
0x18003724e  movdqu  [rbp+57h+Buf1], xmm0
0x180037253  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180037258  mov     rax, [rsi]
0x18003725b  lea     rdx, [rbp+57h+Buf2]
0x18003725f  mov     rcx, rsi
0x180037262  mov     rax, [rax+108h]
0x180037269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003726e  mov     edi, eax
0x180037270  test    eax, eax
0x180037272  jns     short loc_1800372E5
0x180037274  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003727b  test    rcx, rcx
0x18003727e  jnz     short loc_18003728C
0x180037280  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180037285  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003728c  cmp     [rcx+8], r13b
0x180037290  jz      short loc_1800372B0
0x180037292  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037297  cmp     [rax+7CCh], edi
0x18003729d  jz      short loc_1800372B0
0x18003729f  mov     r9d, edi; int
0x1800372a2  mov     r8d, ebx; int
0x1800372a5  mov     rdx, r15; char *
0x1800372a8  mov     rcx, rax; this
0x1800372ab  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800372b0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800372b7  jb      loc_1800376EE
0x1800372bd  mov     edx, 1Ch
0x1800372c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800372c9  lea     r8, WPP_51ca0e26e9bc306247403b211e8b86d4_Traceguids
0x1800372d0  xor     r9d, r9d
0x1800372d3  mov     [rsp+0D0h+var_B0], edi
0x1800372d7  mov     rcx, [rcx+10h]
0x1800372db  call    WPP_SF_qd
0x1800372e0  jmp     loc_1800376EE
0x1800372e5  mov     ebx, 10h
0x1800372ea  lea     rdx, [rbp+57h+Buf2]; Buf2
0x1800372ee  mov     r8d, ebx; Size
0x1800372f1  lea     rcx, MFMediaType_Video; Buf1
0x1800372f8  call    memcmp_0
0x1800372fd  test    eax, eax
0x1800372ff  jnz     loc_1800376EE
0x180037305  mov     rax, [rsi]
0x180037308  lea     r8, [rbp+57h+Buf1]
0x18003730c  lea     rdx, MF_MT_SUBTYPE
0x180037313  mov     rcx, rsi
0x180037316  mov     rax, [rax+50h]
0x18003731a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003731f  mov     edi, eax
0x180037321  test    eax, eax
0x180037323  jns     short loc_18003737B
0x180037325  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003732c  test    rcx, rcx
0x18003732f  jnz     short loc_18003733D
0x180037331  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180037336  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003733d  cmp     [rcx+8], r13b
0x180037341  jz      short loc_180037364
0x180037343  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037348  cmp     [rax+7CCh], edi
0x18003734e  jz      short loc_180037364
0x180037350  mov     r9d, edi; int
0x180037353  mov     r8d, 24Fh; int
0x180037359  mov     rdx, r15; char *
0x18003735c  mov     rcx, rax; this
0x18003735f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180037364  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003736b  jb      loc_1800376EE
0x180037371  mov     edx, 1Dh
0x180037376  jmp     loc_1800372C2
0x18003737b  mov     r8, rbx; Size
0x18003737e  lea     rdx, MEDIASUBTYPE_H264; Buf2
0x180037385  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180037389  call    memcmp_0
0x18003738e  test    eax, eax
0x180037390  jnz     loc_1800376EE
0x180037396  mov     rax, [rsi]
0x180037399  lea     r8, [rbp+57h+var_9C]
0x18003739d  lea     rdx, MF_MT_MPEG2_PROFILE
0x1800373a4  mov     rcx, rsi
0x1800373a7  mov     rax, [rax+38h]
0x1800373ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373b0  test    eax, eax
0x1800373b2  jns     loc_1800374DE
0x1800373b8  mov     rax, [r14]
0x1800373bb  lea     r9, [rbp+57h+var_94]
0x1800373bf  lea     r8, [rbp+57h+String1]
0x1800373c3  mov     [rbp+57h+var_94], r13d
0x1800373c7  lea     rdx, MF_TRANSCODE_ENCODINGPROFILE
0x1800373ce  mov     [rbp+57h+var_9C], 4Dh ; 'M'
0x1800373d5  mov     rcx, r14
0x1800373d8  mov     rax, [rax+68h]
0x1800373dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373e1  test    eax, eax
0x1800373e3  js      short loc_18003745A
0x1800373e5  mov     rbx, [rbp+57h+String1]
0x1800373e9  lea     rdx, aCp; "CP"
0x1800373f0  mov     edi, 2
0x1800373f5  mov     rcx, rbx; String1
0x1800373f8  mov     r8d, edi; MaxCount
0x1800373fb  call    wcsncmp_0
0x180037400  test    eax, eax
0x180037402  jz      loc_1800374D3
0x180037408  mov     r8d, edi; MaxCount
0x18003740b  lea     rdx, aAp; "AP"
0x180037412  mov     rcx, rbx; String1
0x180037415  call    wcsncmp_0
0x18003741a  test    eax, eax
0x18003741c  jz      loc_1800374D3
0x180037422  mov     r8d, edi; MaxCount
0x180037425  lea     rdx, aBp; "BP"
0x18003742c  mov     rcx, rbx; String1
0x18003742f  call    wcsncmp_0
0x180037434  test    eax, eax
0x180037436  jnz     short loc_180037444
0x180037438  mov     r8d, 42h ; 'B'
0x18003743e  mov     [rbp+57h+var_9C], r8d
0x180037442  jmp     short loc_18003745E
0x180037444  mov     r8d, edi; MaxCount
0x180037447  lea     rdx, aSp; "SP"
0x18003744e  mov     rcx, rbx; String1
0x180037451  call    wcsncmp_0
0x180037456  test    eax, eax
0x180037458  jz      short loc_180037438
0x18003745a  mov     r8d, [rbp+57h+var_9C]
0x18003745e  mov     rax, [rsi]
0x180037461  lea     rdx, MF_MT_MPEG2_PROFILE
0x180037468  mov     rcx, rsi
0x18003746b  mov     rax, [rax+0A8h]
0x180037472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037477  mov     edi, eax
0x180037479  test    eax, eax
0x18003747b  jns     short loc_1800374DE
0x18003747d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037484  test    rcx, rcx
0x180037487  jnz     short loc_180037495
0x180037489  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003748e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180037495  cmp     [rcx+8], r13b
0x180037499  jz      short loc_1800374BC
0x18003749b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800374a0  cmp     [rax+7CCh], edi
0x1800374a6  jz      short loc_1800374BC
0x1800374a8  mov     r9d, edi; int
0x1800374ab  mov     r8d, 26Dh; int
0x1800374b1  mov     rdx, r15; char *
0x1800374b4  mov     rcx, rax; this
0x1800374b7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800374bc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800374c3  jb      loc_1800376EE
0x1800374c9  mov     edx, 1Eh
0x1800374ce  jmp     loc_1800372C2
0x1800374d3  mov     r8d, 64h ; 'd'
0x1800374d9  jmp     loc_18003743E
0x1800374de  mov     rax, [rsi]
0x1800374e1  lea     r8, [rbp+57h+var_A0]
0x1800374e5  lea     rdx, MF_MT_MPEG2_LEVEL
0x1800374ec  mov     rcx, rsi
0x1800374ef  mov     rax, [rax+38h]
0x1800374f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800374f8  test    eax, eax
0x1800374fa  jns     loc_1800376CE
0x180037500  mov     rax, [r14]
0x180037503  lea     r9, [rbp+57h+var_90]
0x180037507  lea     r8, [rbp+57h+String1]
0x18003750b  mov     [rbp+57h+var_90], r13d
0x18003750f  lea     rdx, MF_TRANSCODE_ENCODINGPROFILE
0x180037516  mov     [rbp+57h+var_A0], r13d
0x18003751a  mov     rcx, r14
0x18003751d  mov     rax, [rax+68h]
0x180037521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037526  test    eax, eax
0x180037528  js      short loc_180037584
0x18003752a  cmp     [rbp+57h+var_90], 4
0x18003752e  jnz     short loc_180037555
0x180037530  mov     rcx, [rbp+57h+String1]
0x180037534  mov     eax, 40h ; '@'
0x180037539  cmp     ax, [rcx+4]
0x18003753d  jnz     short loc_180037584
0x18003753f  add     rcx, 6
0x180037543  call    _o__wtol_0
0x180037548  lea     r8d, [rax+rax*4]
0x18003754c  add     r8d, r8d
0x18003754f  mov     [rbp+57h+var_A0], r8d
0x180037553  jmp     short loc_180037588
0x180037555  cmp     [rbp+57h+var_90], 5
0x180037559  jnz     short loc_18003757B
0x18003755b  mov     rcx, [rbp+57h+String1]
0x18003755f  mov     eax, 40h ; '@'
0x180037564  cmp     ax, [rcx+4]
0x180037568  jnz     short loc_180037584
0x18003756a  add     rcx, 6
0x18003756e  call    _o__wtol_0
0x180037573  mov     r8d, eax
0x180037576  mov     [rbp+57h+var_A0], eax
0x180037579  jmp     short loc_180037588
0x18003757b  mov     r8d, r13d
0x18003757e  mov     [rbp+57h+var_A0], r13d
0x180037582  jmp     short loc_180037588
0x180037584  mov     r8d, [rbp+57h+var_A0]
0x180037588  mov     [rbp+57h+var_94], r13d
0x18003758c  mov     [rbp+57h+var_7C], r13d
0x180037590  mov     [rbp+57h+var_78], r13
0x180037594  mov     [rbp+57h+var_80], r13d
0x180037598  test    r8d, r8d
0x18003759b  jnz     loc_18003765D
0x1800375a1  lea     r9, [rbp+57h+var_7C]
0x1800375a5  mov     rcx, rsi
0x1800375a8  lea     r8, [rbp+57h+var_94]
0x1800375ac  lea     rdx, MF_MT_FRAME_SIZE
0x1800375b3  call    MFGetAttribute2UINT32asUINT64
0x1800375b8  lea     r9, [rbp+57h+var_78+4]
0x1800375bc  mov     rcx, rsi
0x1800375bf  lea     r8, [rbp+57h+var_78]
0x1800375c3  mov     edi, eax
0x1800375c5  lea     rdx, MF_MT_FRAME_RATE
0x1800375cc  call    MFGetAttribute2UINT32asUINT64
0x1800375d1  mov     rcx, [rsi]
0x1800375d4  lea     r8, [rbp+57h+var_80]
0x1800375d8  mov     ebx, eax
0x1800375da  lea     rdx, MF_MT_AVG_BITRATE
0x1800375e1  mov     rax, [rcx+38h]
0x1800375e5  mov     rcx, rsi
0x1800375e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800375ed  mov     r15d, [rbp+57h+var_9C]
0x1800375f1  or      eax, ebx
0x1800375f3  or      edi, eax
0x1800375f5  jnz     short loc_18003764D
0x1800375f7  mov     eax, dword ptr [rbp+57h+var_78]
0x1800375fa  lea     ebx, [rdi+1]
0x1800375fd  mov     r12d, [rbp+57h+var_80]
0x180037601  xorps   xmm6, xmm6
0x180037604  xorps   xmm0, xmm0
0x180037607  cvtsi2sd xmm6, rax
0x18003760c  mov     eax, dword ptr [rbp+57h+var_78+4]
0x18003760f  cvtsi2sd xmm0, rax
0x180037614  divsd   xmm6, xmm0
0x180037618  mov     edx, [rbp+57h+var_7C]
0x18003761b  mov     r9d, r15d
0x18003761e  mov     ecx, [rbp+57h+var_94]
0x180037621  movaps  xmm2, xmm6
0x180037624  mov     [rsp+0D0h+var_A8], ebx
0x180037628  mov     [rsp+0D0h+var_B0], r12d
0x18003762d  call    ?CheckLevelLimitPreEncode@@YA_NIINW4eAVEncH264VProfile@@IW4tAvcLevel@@@Z; CheckLevelLimitPreEncode(uint,uint,double,eAVEncH264VProfile,uint,tAvcLevel)
0x180037632  test    al, al
0x180037634  jnz     short loc_180037642
0x180037636  inc     ebx
0x180037638  cmp     ebx, 15h
0x18003763b  jl      short loc_180037618
0x18003763d  mov     ebx, 14h
0x180037642  lea     rdx, [rbp+57h+var_A0]; unsigned int *
0x180037646  mov     ecx, ebx; unsigned int
0x180037648  call    ?ConvertAvcLevelToMFLevel@@YAJKPEAI@Z; ConvertAvcLevelToMFLevel(ulong,uint *)
0x18003764d  mov     r8d, [rbp+57h+var_A0]
0x180037651  test    r8d, r8d
0x180037654  jz      short loc_1800376D2
0x180037656  lea     r15, aCmfthelperAddm; "CMFTHelper::AddMFTActivateCodecAPIAttri"...
0x18003765d  mov     rax, [rsi]
0x180037660  lea     rdx, MF_MT_MPEG2_LEVEL
0x180037667  mov     rcx, rsi
0x18003766a  mov     rax, [rax+0A8h]
0x180037671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037676  mov     edi, eax
0x180037678  test    eax, eax
0x18003767a  jns     short loc_1800376CE
0x18003767c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037683  test    rcx, rcx
0x180037686  jnz     short loc_180037694
0x180037688  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003768d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180037694  cmp     [rcx+8], r13b
0x180037698  jz      short loc_1800376BB
  ... truncated ...
```
