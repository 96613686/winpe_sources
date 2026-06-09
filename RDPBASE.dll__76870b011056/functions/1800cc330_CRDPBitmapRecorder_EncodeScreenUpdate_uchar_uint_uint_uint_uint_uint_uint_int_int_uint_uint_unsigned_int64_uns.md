# CRDPBitmapRecorder::EncodeScreenUpdate(uchar *,uint,uint,uint,uint,uint,uint,int,int,uint,uint,unsigned __int64,unsigned __int64,int)

- ea: `0x1800cc330`
- end: `0x1800cc66e`
- name: `?EncodeScreenUpdate@CRDPBitmapRecorder@@UEAAJPEAEIIIIIIHHII_K1H@Z`
- size: `830`
- prototype: `__int64 __fastcall(CRDPBitmapRecorder *__hidden this, unsigned __int8 *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, int, int, unsigned int, unsigned int, unsigned __int64, unsigned __int64, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update`

## callers

- `0x1800cc250`

## callees

- `0x180002550`
- `0x180016ad0`
- `0x180019a80`
- `0x180019ab0`
- `0x180046a84`
- `0x1800506ac`
- `0x1800711c8`
- `0x180078c20`
- `0x18007f094`
- `0x1800cc330`
- `0x1800cc798`
- `0x1800cc9e8`
- `0x180162010`

## import_xrefs

- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!SetRect` at `0x1800cc45e`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!SetRect` at `0x1800cc45e`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x1800cc46f`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x1800cc56a`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x1800cc46f`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x1800cc56a`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x1800cc549`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x1800cc549`

## pseudocode

```c
__int64 __fastcall CRDPBitmapRecorder::EncodeScreenUpdate(
        CRDPBitmapRecorder *this,
        unsigned __int8 *a2,
        __int64 a3,
        int a4,
        unsigned int a5,
        LONG a6,
        LONG a7)
{
  __int64 v7; // rbx
  int v11; // edi
  CRDPBitmapRecorder *v12; // rsi
  int v13; // r9d
  int v14; // r15d
  int v15; // r9d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v17; // edx
  const char *v18; // rcx
  int v19; // eax
  int v20; // r14d
  int v21; // r15d
  char *v23; // [rsp+40h] [rbp-49h] BYREF
  __int64 v24; // [rsp+48h] [rbp-41h] BYREF
  struct tagRECT rcDst; // [rsp+50h] [rbp-39h] BYREF
  RECT rcSrc2; // [rsp+60h] [rbp-29h] BYREF
  tagRECT rc; // [rsp+70h] [rbp-19h] BYREF

  v7 = 0;
  v24 = 0;
  rc = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_e67005ee347b3de4dcefe371ffb2ec11_Traceguids);
    }
    v11 = -2147024809;
    v12 = (CRDPBitmapRecorder *)((char *)this - 48);
    goto LABEL_34;
  }
  v11 = 0;
  v23 = (char *)this + 48;
  CTSCriticalSection::Lock((CRDPBitmapRecorder *)((char *)this + 48));
  v12 = (CRDPBitmapRecorder *)((char *)this - 48);
  if ( !*((_DWORD *)this + 16) )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      *(_QWORD *)&rcDst.left = "CRDPBitmapEncoder::StopRecording() called even when it is not recording";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&CallbackContext,
        (unsigned int)&dword_1801B911C,
        0,
        v13,
        (__int64)&rcDst);
    }
LABEL_10:
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v23);
    goto LABEL_35;
  }
  if ( *((_QWORD *)this + 4) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease(&v24);
    v7 = *((_QWORD *)this + 4);
    v24 = v7;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(&v24);
  }
  v14 = *((_DWORD *)this + 17);
  if ( *((_DWORD *)this + 18) )
    rc = *(tagRECT *)((char *)this + 88);
  else
    SetRect(&rc, 0, 0, *((_DWORD *)this + 19), *((_DWORD *)this + 20));
  if ( IsRectEmpty((const RECT *)((char *)this + 88)) )
  {
    if ( (unsigned int)CallbackContext > 5 )
    {
      *(_QWORD *)&rcDst.left = "Recording cropping rectangle is empty whenencoding";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&CallbackContext,
        (unsigned int)byte_1801B90FB,
        0,
        v15,
        (__int64)&rcDst);
    }
    v11 = 1;
    goto LABEL_10;
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v23);
  if ( v14 )
  {
    v11 = CRDPBitmapRecorder::ResetRecording((CRDPBitmapRecorder *)((char *)this - 48));
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_34;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v17 = 15;
      v18 = "Failed to reset recording params";
LABEL_33:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        (unsigned int)WPP_e67005ee347b3de4dcefe371ffb2ec11_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v18,
        v11);
LABEL_34:
      CRDPBitmapRecorder::OnRecordingFailure(v12, v11);
      v11 = 0;
      goto LABEL_35;
    }
  }
  if ( v7 )
  {
    rcSrc2.top = a7;
    rcSrc2.left = a6;
    rcSrc2.bottom = a5 + a7;
    rcSrc2.right = a4 + a6;
    rcDst = 0;
    IntersectRect(&rcDst, &rc, &rcSrc2);
    v19 = *((_DWORD *)this + 21);
    v20 = rcSrc2.bottom - rcDst.bottom;
    v21 = rcDst.left - rcSrc2.left;
    LODWORD(v23) = v19;
    if ( !IsRectEmpty(&rcDst) )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int, int, unsigned __int8 *))(*(_QWORD *)v7 + 40LL))(
              v7,
              (unsigned int)(rcDst.left - rc.left),
              (unsigned int)(rcDst.top - rc.top),
              (unsigned int)(rcDst.right - rcDst.left),
              rcDst.bottom - rcDst.top,
              a4,
              &a2[4 * v20 * ((a4 * (((_DWORD)v23 + 3) & 0xFFFFFFFC) + 31) >> 5)
                + v21 * ((unsigned int)((_DWORD)v23 + 7) >> 3)]);
      if ( v11 < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_34;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v17 = 16;
        v18 = "Failed to EncodeScreenData";
        goto LABEL_33;
      }
    }
  }
LABEL_35:
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v24);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800cc330  mov     [rsp-8+arg_10], rbx
0x1800cc335  push    rbp
0x1800cc336  push    rsi
0x1800cc337  push    rdi
0x1800cc338  push    r12
0x1800cc33a  push    r13
0x1800cc33c  push    r14
0x1800cc33e  push    r15
0x1800cc340  lea     rbp, [rsp-7]
0x1800cc345  sub     rsp, 90h
0x1800cc34c  mov     rax, cs:__security_cookie
0x1800cc353  xor     rax, rsp
0x1800cc356  mov     [rbp+37h+var_40], rax
0x1800cc35a  xor     ebx, ebx
0x1800cc35c  xorps   xmm0, xmm0
0x1800cc35f  mov     [rbp+37h+var_78], rbx
0x1800cc363  mov     r13d, r9d
0x1800cc366  mov     r12, rdx
0x1800cc369  mov     r14, rcx
0x1800cc36c  movups  xmmword ptr [rbp+37h+rc.left], xmm0
0x1800cc370  test    rdx, rdx
0x1800cc373  jnz     short loc_1800CC3B8
0x1800cc375  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc37c  lea     rax, WPP_GLOBAL_Control
0x1800cc383  cmp     rcx, rax
0x1800cc386  jz      short loc_1800CC3AA
0x1800cc388  lea     edi, [rdx+1]
0x1800cc38b  test    [rcx+1Ch], dil
0x1800cc38f  jz      short loc_1800CC3AA
0x1800cc391  cmp     [rcx+19h], dil
0x1800cc395  jb      short loc_1800CC3AA
0x1800cc397  mov     rcx, [rcx+10h]
0x1800cc39b  lea     edx, [rbx+0Eh]
0x1800cc39e  lea     r8, WPP_e67005ee347b3de4dcefe371ffb2ec11_Traceguids
0x1800cc3a5  call    WPP_SF_
0x1800cc3aa  mov     edi, 80070057h
0x1800cc3af  lea     rsi, [r14-30h]
0x1800cc3b3  jmp     loc_1800CC630
0x1800cc3b8  add     rcx, 30h ; '0'; this
0x1800cc3bc  xor     edi, edi
0x1800cc3be  mov     [rbp+37h+var_80], rcx
0x1800cc3c2  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1800cc3c7  lea     rsi, [r14-30h]
0x1800cc3cb  cmp     [rsi+70h], ebx
0x1800cc3ce  jnz     short loc_1800CC413
0x1800cc3d0  mov     eax, cs:CallbackContext
0x1800cc3d6  cmp     eax, 4
0x1800cc3d9  jbe     short loc_1800CC405
0x1800cc3db  lea     rax, aCrdpbitmapenco; "CRDPBitmapEncoder::StopRecording() call"...
0x1800cc3e2  xor     r8d, r8d
0x1800cc3e5  mov     qword ptr [rbp+37h+rcDst.left], rax
0x1800cc3e9  lea     rdx, dword_1801B911C
0x1800cc3f0  lea     rax, [rbp+37h+rcDst]
0x1800cc3f4  lea     rcx, CallbackContext
0x1800cc3fb  mov     qword ptr [rsp+0C0h+yBottom], rax
0x1800cc400  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800cc405  lea     rcx, [rbp+37h+var_80]; this
0x1800cc409  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800cc40e  jmp     loc_1800CC63C
0x1800cc413  cmp     [r14+20h], rbx
0x1800cc417  jz      short loc_1800CC433
0x1800cc419  lea     rcx, [rbp+37h+var_78]; void *
0x1800cc41d  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800cc422  mov     rbx, [r14+20h]
0x1800cc426  lea     rcx, [rbp+37h+var_78]
0x1800cc42a  mov     [rbp+37h+var_78], rbx
0x1800cc42e  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800cc433  mov     r15d, [r14+44h]
0x1800cc437  cmp     [r14+48h], edi
0x1800cc43b  jz      short loc_1800CC449
0x1800cc43d  movups  xmm0, xmmword ptr [r14+58h]
0x1800cc442  movdqu  xmmword ptr [rbp+37h+rc.left], xmm0
0x1800cc447  jmp     short loc_1800CC464
0x1800cc449  mov     eax, [r14+50h]
0x1800cc44d  lea     rcx, [rbp+37h+rc]; lprc
0x1800cc451  mov     r9d, [r14+4Ch]; xRight
0x1800cc455  xor     r8d, r8d; yTop
0x1800cc458  xor     edx, edx; xLeft
0x1800cc45a  mov     [rsp+0C0h+yBottom], eax; yBottom
0x1800cc45e  call    cs:__imp_SetRect
0x1800cc464  mov     eax, 58h ; 'X'
0x1800cc469  mov     rcx, r14
0x1800cc46c  add     rcx, rax; lprc
0x1800cc46f  call    cs:__imp_IsRectEmpty
0x1800cc475  test    eax, eax
0x1800cc477  jz      short loc_1800CC4B8
0x1800cc479  mov     eax, cs:CallbackContext
0x1800cc47f  cmp     eax, 5
0x1800cc482  jbe     short loc_1800CC4AE
0x1800cc484  lea     rax, aRecordingCropp; "Recording cropping rectangle is empty w"...
0x1800cc48b  xor     r8d, r8d
0x1800cc48e  mov     qword ptr [rbp+37h+rcDst.left], rax
0x1800cc492  lea     rdx, byte_1801B90FB
0x1800cc499  lea     rax, [rbp+37h+rcDst]
0x1800cc49d  lea     rcx, CallbackContext
0x1800cc4a4  mov     qword ptr [rsp+0C0h+yBottom], rax
0x1800cc4a9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800cc4ae  mov     edi, 1
0x1800cc4b3  jmp     loc_1800CC405
0x1800cc4b8  lea     rcx, [rbp+37h+var_80]; this
0x1800cc4bc  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800cc4c1  test    r15d, r15d
0x1800cc4c4  jz      short loc_1800CC515
0x1800cc4c6  mov     rcx, rsi; this
0x1800cc4c9  call    ?ResetRecording@CRDPBitmapRecorder@@IEAAJXZ; CRDPBitmapRecorder::ResetRecording(void)
0x1800cc4ce  mov     edi, eax
0x1800cc4d0  test    eax, eax
0x1800cc4d2  jns     short loc_1800CC515
0x1800cc4d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc4db  lea     rax, WPP_GLOBAL_Control
0x1800cc4e2  cmp     rcx, rax
0x1800cc4e5  jz      loc_1800CC630
0x1800cc4eb  test    byte ptr [rcx+1Ch], 8
0x1800cc4ef  jz      loc_1800CC630
0x1800cc4f5  cmp     byte ptr [rcx+19h], 2
0x1800cc4f9  jb      loc_1800CC630
0x1800cc4ff  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800cc504  mov     edx, 0Fh
0x1800cc509  lea     rcx, aFailedToResetR; "Failed to reset recording params"
0x1800cc510  jmp     loc_1800CC60D
0x1800cc515  test    rbx, rbx
0x1800cc518  jz      loc_1800CC63C
0x1800cc51e  mov     ecx, [rbp+37h+arg_30]
0x1800cc521  lea     r8, [rbp+37h+rcSrc2]; lprcSrc2
0x1800cc525  mov     eax, [rbp+37h+arg_28]
0x1800cc528  lea     rdx, [rbp+37h+rc]; lprcSrc1
0x1800cc52c  mov     [rbp+37h+rcSrc2.top], ecx
0x1800cc52f  xorps   xmm0, xmm0
0x1800cc532  add     ecx, [rbp+37h+arg_20]
0x1800cc535  mov     [rbp+37h+rcSrc2.left], eax
0x1800cc538  add     eax, r13d
0x1800cc53b  mov     [rbp+37h+rcSrc2.bottom], ecx
0x1800cc53e  lea     rcx, [rbp+37h+rcDst]; lprcDst
0x1800cc542  mov     [rbp+37h+rcSrc2.right], eax
0x1800cc545  movups  xmmword ptr [rbp+37h+rcDst.left], xmm0
0x1800cc549  call    cs:__imp_IntersectRect
0x1800cc54f  mov     eax, [r14+54h]
0x1800cc553  lea     rcx, [rbp+37h+rcDst]; lprc
0x1800cc557  mov     r14d, [rbp+37h+rcSrc2.bottom]
0x1800cc55b  mov     r15d, [rbp+37h+rcDst.left]
0x1800cc55f  sub     r14d, [rbp+37h+rcDst.bottom]
0x1800cc563  sub     r15d, [rbp+37h+rcSrc2.left]
0x1800cc567  mov     dword ptr [rbp+37h+var_80], eax
0x1800cc56a  call    cs:__imp_IsRectEmpty
0x1800cc570  test    eax, eax
0x1800cc572  jnz     loc_1800CC63C
0x1800cc578  mov     eax, dword ptr [rbp+37h+var_80]
0x1800cc57b  mov     r8d, [rbp+37h+rcDst.top]
0x1800cc57f  mov     edx, [rbp+37h+rcDst.left]
0x1800cc582  mov     r10, [rbx]
0x1800cc585  mov     r9d, [rbp+37h+rcDst.right]
0x1800cc589  lea     ecx, [rax+3]
0x1800cc58c  and     ecx, 0FFFFFFFCh
0x1800cc58f  add     eax, 7
0x1800cc592  imul    ecx, r13d
0x1800cc596  sub     r9d, edx
0x1800cc599  sub     edx, [rbp+37h+rc.left]
0x1800cc59c  shr     eax, 3
0x1800cc59f  imul    eax, r15d
0x1800cc5a3  add     ecx, 1Fh
0x1800cc5a6  shr     ecx, 5
0x1800cc5a9  imul    ecx, r14d
0x1800cc5ad  lea     ecx, [rax+rcx*4]
0x1800cc5b0  mov     eax, [rbp+37h+rcDst.bottom]
0x1800cc5b3  sub     eax, r8d
0x1800cc5b6  add     rcx, r12
0x1800cc5b9  sub     r8d, [rbp+37h+rc.top]
0x1800cc5bd  mov     [rsp+0C0h+var_90], rcx
0x1800cc5c2  mov     rcx, rbx
0x1800cc5c5  mov     [rsp+0C0h+var_98], r13d
0x1800cc5ca  mov     [rsp+0C0h+yBottom], eax
0x1800cc5ce  mov     rax, [r10+28h]
0x1800cc5d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc5d7  mov     edi, eax
0x1800cc5d9  test    eax, eax
0x1800cc5db  jns     short loc_1800CC63C
0x1800cc5dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc5e4  lea     rax, WPP_GLOBAL_Control
0x1800cc5eb  cmp     rcx, rax
0x1800cc5ee  jz      short loc_1800CC630
0x1800cc5f0  test    byte ptr [rcx+1Ch], 8
0x1800cc5f4  jz      short loc_1800CC630
0x1800cc5f6  cmp     byte ptr [rcx+19h], 2
0x1800cc5fa  jb      short loc_1800CC630
0x1800cc5fc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800cc601  mov     edx, 10h
0x1800cc606  lea     rcx, aFailedToEncode_2; "Failed to EncodeScreenData"
0x1800cc60d  mov     [rsp+0C0h+var_98], edi
0x1800cc611  lea     r8, WPP_e67005ee347b3de4dcefe371ffb2ec11_Traceguids
0x1800cc618  mov     qword ptr [rsp+0C0h+yBottom], rcx
0x1800cc61d  mov     r9d, eax
0x1800cc620  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc627  mov     rcx, [rcx+10h]
0x1800cc62b  call    WPP_SF_DsD
0x1800cc630  mov     edx, edi; int
0x1800cc632  mov     rcx, rsi; this
0x1800cc635  call    ?OnRecordingFailure@CRDPBitmapRecorder@@IEAAJJ@Z; CRDPBitmapRecorder::OnRecordingFailure(long)
0x1800cc63a  xor     edi, edi
0x1800cc63c  lea     rcx, [rbp+37h+var_78]; void *
0x1800cc640  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800cc645  mov     eax, edi
0x1800cc647  mov     rcx, [rbp+37h+var_40]
0x1800cc64b  xor     rcx, rsp; StackCookie
0x1800cc64e  call    __security_check_cookie
0x1800cc653  mov     rbx, [rsp+0C0h+arg_10]
0x1800cc65b  add     rsp, 90h
0x1800cc662  pop     r15
0x1800cc664  pop     r14
0x1800cc666  pop     r13
0x1800cc668  pop     r12
0x1800cc66a  pop     rdi
0x1800cc66b  pop     rsi
0x1800cc66c  pop     rbp
0x1800cc66d  retn
```
