# CUMTSCommandPlugin::InitializeInstance(IRDPCoreVirtualChannel *,IRDPCollection *)

- ea: `0x180063340`
- end: `0x180063700`
- name: `?InitializeInstance@CUMTSCommandPlugin@@UEAAJPEAUIRDPCoreVirtualChannel@@PEAUIRDPCollection@@@Z`
- size: `960`
- prototype: `__int64 __fastcall(CUMTSCommandPlugin *__hidden this, struct IRDPCoreVirtualChannel *, struct IRDPCollection *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002170`
- `0x18000d550`
- `0x18000e4ec`
- `0x18000f660`
- `0x180063340`
- `0x180076090`
- `0x180079770`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063638`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180063622`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180063622`

## string_xrefs

- `0x1800634ee`: `ReplaceCustomRdpScheduler`
- `0x180063660`: `onecore\termsrv\rdpplatform\rdpenc\enccore\umtscommandplugin.cpp`
- `0x180063454`: `Failed to open channel in UMTS Command Plugin`
- `0x18006352b`: `Failed to get the replace custom scheduler property, falling back to legacy scheduler.`
- `0x180063672`: `Failed to create the Cancel wait event.  GetLastError[0x%x]`

## pseudocode

```c
__int64 __fastcall CUMTSCommandPlugin::InitializeInstance(
        CUMTSCommandPlugin *this,
        struct IRDPCoreVirtualChannel *a2,
        struct IRDPCollection *a3)
{
  int v5; // r12d
  signed int LastError; // eax
  signed int v7; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v9; // eax
  int v10; // edx
  const char *v11; // rcx
  _QWORD *v12; // r14
  int v13; // eax
  char v14; // bl
  unsigned int v15; // eax
  HANDLE EventW; // rax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  bool v20; // sf
  int v22; // [rsp+50h] [rbp-20h] BYREF
  int v23; // [rsp+54h] [rbp-1Ch] BYREF
  const char *v24; // [rsp+58h] [rbp-18h] BYREF
  const char *v25; // [rsp+60h] [rbp-10h] BYREF
  const char *v26; // [rsp+68h] [rbp-8h] BYREF
  int v27; // [rsp+A0h] [rbp+30h] BYREF
  signed int v28; // [rsp+B8h] [rbp+48h] BYREF

  v27 = 0;
  v5 = CTSCriticalSection::Initialize((CUMTSCommandPlugin *)((char *)this + 120));
  if ( !v5 )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)WPP_5b7f50767cde39cd9426574acc398437_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"Failed m_Lock.Initialize",
          v7);
      }
      return (unsigned int)v7;
    }
  }
  TCntPtr<IRDPCoreVirtualChannel>::operator=((char *)this + 88, a2);
  v7 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)this + 11) + 40LL))(
         *((_QWORD *)this + 11),
         (char *)this - 8,
         0);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 12;
      v11 = "Failed to open channel in UMTS Command Plugin";
LABEL_14:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        (unsigned int)WPP_5b7f50767cde39cd9426574acc398437_Traceguids,
        v9,
        (__int64)v11,
        v7);
      goto LABEL_42;
    }
    goto LABEL_42;
  }
  v12 = (_QWORD *)((char *)this + 96);
  v7 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, char *))this + 10))(
         *((_QWORD *)this + 10),
         &IID_IRDPENCPlatformContext,
         (char *)this + 96);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 13;
      v11 = "Failed to get the platform context";
      goto LABEL_14;
    }
LABEL_42:
    if ( v5 )
      CUMTSCommandPlugin::TerminateInstance(this);
    return (unsigned int)v7;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, int *))(*(_QWORD *)*v12 + 32LL))(
          *v12,
          L"ReplaceCustomRdpScheduler",
          &v27);
  v14 = v13;
  if ( v13 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)WPP_5b7f50767cde39cd9426574acc398437_Traceguids,
      v15,
      (__int64)"Failed to get the replace custom scheduler property, falling back to legacy scheduler.",
      v14);
  }
  if ( !v27 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v12 + 112LL))(*v12, (char *)this + 104);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 15;
        v11 = "Failed to get scheduler";
        goto LABEL_14;
      }
      goto LABEL_42;
    }
    v7 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, char *))(**((_QWORD **)this + 13) + 40LL))(
           *((_QWORD *)this + 13),
           ((unsigned __int64)this + 16) & -(__int64)(this != (CUMTSCommandPlugin *)8),
           (char *)this + 112);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 16;
        v11 = "Failed to register VCMgr with Scheduler";
        goto LABEL_14;
      }
      goto LABEL_42;
    }
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 18) = EventW;
  if ( EventW )
  {
    *((_DWORD *)this + 13) |= 2u;
    return 0;
  }
  v7 = GetLastError();
  if ( (unsigned int)CallbackContext > 2 )
  {
    v28 = v7;
    v24 = "InitializeInstance";
    v22 = 116;
    v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\umtscommandplugin.cpp";
    v26 = "Failed to create the Cancel wait event.  GetLastError[0x%x]";
    v23 = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v17,
      (unsigned int)word_1802863D2,
      v18,
      v19,
      (__int64)&v26,
      (__int64)&v23,
      (__int64)&v25,
      (__int64)&v22,
      (__int64)&v24,
      (__int64)&v28);
  }
  v20 = v7 < 0;
  if ( v7 > 0 )
  {
    v7 = (unsigned __int16)v7 | 0x80070000;
    v20 = v7 < 0;
  }
  if ( v20 )
    goto LABEL_42;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180063340  mov     [rsp-28h+arg_8], rbx
0x180063345  mov     [rsp-28h+arg_10], rsi
0x18006334a  push    rbp
0x18006334b  push    rdi
0x18006334c  push    r12
0x18006334e  push    r14
0x180063350  push    r15
0x180063352  mov     rbp, rsp
0x180063355  sub     rsp, 70h
0x180063359  mov     rsi, rcx
0x18006335c  mov     [rbp+arg_0], 0
0x180063363  add     rcx, 78h ; 'x'; this
0x180063367  mov     rdi, rdx
0x18006336a  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x18006336f  mov     r12d, eax
0x180063372  test    eax, eax
0x180063374  jnz     short loc_1800633F3
0x180063376  call    cs:__imp_GetLastError
0x18006337c  mov     ebx, eax
0x18006337e  test    eax, eax
0x180063380  jle     short loc_18006338B
0x180063382  movzx   ebx, ax
0x180063385  or      ebx, 80070000h
0x18006338b  test    ebx, ebx
0x18006338d  jns     short loc_1800633F3
0x18006338f  mov     rax, cs:WPP_GLOBAL_Control
0x180063396  lea     rdi, WPP_GLOBAL_Control
0x18006339d  cmp     rax, rdi
0x1800633a0  jz      loc_1800636E5
0x1800633a6  test    byte ptr [rax+1Ch], 8
0x1800633aa  jz      loc_1800636E5
0x1800633b0  cmp     byte ptr [rax+19h], 2
0x1800633b4  jb      loc_1800636E5
0x1800633ba  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800633bf  lea     rcx, aFailedMLockIni; "Failed m_Lock.Initialize"
0x1800633c6  mov     dword ptr [rsp+70h+var_48], ebx
0x1800633ca  mov     [rsp+70h+var_50], rcx
0x1800633cf  lea     r8, WPP_5b7f50767cde39cd9426574acc398437_Traceguids
0x1800633d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800633dd  mov     edx, 0Bh
0x1800633e2  mov     r9d, eax
0x1800633e5  mov     rcx, [rcx+10h]
0x1800633e9  call    WPP_SF_DsD
0x1800633ee  jmp     loc_1800636E5
0x1800633f3  lea     rcx, [rsi+58h]
0x1800633f7  mov     rdx, rdi
0x1800633fa  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x1800633ff  lea     r15, [rsi-8]
0x180063403  xor     r8d, r8d
0x180063406  mov     rcx, [r15+60h]
0x18006340a  mov     rdx, r15
0x18006340d  mov     rax, [rcx]
0x180063410  mov     rax, [rax+28h]
0x180063414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063419  mov     ebx, eax
0x18006341b  test    eax, eax
0x18006341d  jns     short loc_180063483
0x18006341f  mov     rax, cs:WPP_GLOBAL_Control
0x180063426  lea     rdi, WPP_GLOBAL_Control
0x18006342d  cmp     rax, rdi
0x180063430  jz      loc_1800636D0
0x180063436  test    byte ptr [rax+1Ch], 8
0x18006343a  jz      loc_1800636D0
0x180063440  cmp     byte ptr [rax+19h], 2
0x180063444  jb      loc_1800636D0
0x18006344a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006344f  mov     edx, 0Ch
0x180063454  lea     rcx, aFailedToOpenCh_5; "Failed to open channel in UMTS Command "...
0x18006345b  mov     dword ptr [rsp+70h+var_48], ebx
0x18006345f  lea     r8, WPP_5b7f50767cde39cd9426574acc398437_Traceguids
0x180063466  mov     [rsp+70h+var_50], rcx
0x18006346b  mov     r9d, eax
0x18006346e  mov     rcx, cs:WPP_GLOBAL_Control
0x180063475  mov     rcx, [rcx+10h]
0x180063479  call    WPP_SF_DsD
0x18006347e  jmp     loc_1800636D0
0x180063483  mov     rcx, [rsi+50h]
0x180063487  lea     r14, [rsi+60h]
0x18006348b  mov     r8, r14
0x18006348e  lea     rdx, IID_IRDPENCPlatformContext
0x180063495  mov     rax, [rcx]
0x180063498  mov     rax, [rax]
0x18006349b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800634a0  mov     ebx, eax
0x1800634a2  test    eax, eax
0x1800634a4  jns     short loc_1800634E7
0x1800634a6  mov     rax, cs:WPP_GLOBAL_Control
0x1800634ad  lea     rdi, WPP_GLOBAL_Control
0x1800634b4  cmp     rax, rdi
0x1800634b7  jz      loc_1800636D0
0x1800634bd  test    byte ptr [rax+1Ch], 8
0x1800634c1  jz      loc_1800636D0
0x1800634c7  cmp     byte ptr [rax+19h], 2
0x1800634cb  jb      loc_1800636D0
0x1800634d1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800634d6  mov     edx, 0Dh
0x1800634db  lea     rcx, aFailedToGetThe_12; "Failed to get the platform context"
0x1800634e2  jmp     loc_18006345B
0x1800634e7  mov     rcx, [r14]
0x1800634ea  lea     r8, [rbp+arg_0]
0x1800634ee  lea     rdx, aReplacecustomr; "ReplaceCustomRdpScheduler"
0x1800634f5  mov     rax, [rcx]
0x1800634f8  mov     rax, [rax+20h]
0x1800634fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063501  lea     rdi, WPP_GLOBAL_Control
0x180063508  mov     ebx, eax
0x18006350a  test    eax, eax
0x18006350c  jns     short loc_18006355A
0x18006350e  mov     rcx, cs:WPP_GLOBAL_Control
0x180063515  cmp     rcx, rdi
0x180063518  jz      short loc_18006355A
0x18006351a  test    byte ptr [rcx+1Ch], 8
0x18006351e  jz      short loc_18006355A
0x180063520  cmp     byte ptr [rcx+19h], 2
0x180063524  jb      short loc_18006355A
0x180063526  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006352b  lea     rcx, aFailedToGetThe_6; "Failed to get the replace custom schedu"...
0x180063532  mov     dword ptr [rsp+70h+var_48], ebx
0x180063536  mov     [rsp+70h+var_50], rcx
0x18006353b  lea     r8, WPP_5b7f50767cde39cd9426574acc398437_Traceguids
0x180063542  mov     rcx, cs:WPP_GLOBAL_Control
0x180063549  mov     edx, 0Eh
0x18006354e  mov     r9d, eax
0x180063551  mov     rcx, [rcx+10h]
0x180063555  call    WPP_SF_DsD
0x18006355a  cmp     [rbp+arg_0], 0
0x18006355e  jnz     loc_180063618
0x180063564  mov     rcx, [r14]
0x180063567  lea     rdx, [rsi+68h]
0x18006356b  mov     rax, [rcx]
0x18006356e  mov     rax, [rax+70h]
0x180063572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063577  mov     ebx, eax
0x180063579  test    eax, eax
0x18006357b  jns     short loc_1800635B7
0x18006357d  mov     rax, cs:WPP_GLOBAL_Control
0x180063584  cmp     rax, rdi
0x180063587  jz      loc_1800636D0
0x18006358d  test    byte ptr [rax+1Ch], 8
0x180063591  jz      loc_1800636D0
0x180063597  cmp     byte ptr [rax+19h], 2
0x18006359b  jb      loc_1800636D0
0x1800635a1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800635a6  mov     edx, 0Fh
0x1800635ab  lea     rcx, aFailedToGetSch_0; "Failed to get scheduler"
0x1800635b2  jmp     loc_18006345B
0x1800635b7  mov     rcx, [rsi+68h]
0x1800635bb  lea     rax, [rsi+10h]
0x1800635bf  neg     r15
0x1800635c2  lea     r8, [rsi+70h]
0x1800635c6  sbb     rdx, rdx
0x1800635c9  mov     r9, [rcx]
0x1800635cc  and     rdx, rax
0x1800635cf  mov     rax, [r9+28h]
0x1800635d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800635d8  mov     ebx, eax
0x1800635da  test    eax, eax
0x1800635dc  jns     short loc_180063618
0x1800635de  mov     rax, cs:WPP_GLOBAL_Control
0x1800635e5  cmp     rax, rdi
0x1800635e8  jz      loc_1800636D0
0x1800635ee  test    byte ptr [rax+1Ch], 8
0x1800635f2  jz      loc_1800636D0
0x1800635f8  cmp     byte ptr [rax+19h], 2
0x1800635fc  jb      loc_1800636D0
0x180063602  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180063607  mov     edx, 10h
0x18006360c  lea     rcx, aFailedToRegist; "Failed to register VCMgr with Scheduler"
0x180063613  jmp     loc_18006345B
0x180063618  xor     r9d, r9d; lpName
0x18006361b  xor     r8d, r8d; bInitialState
0x18006361e  xor     edx, edx; bManualReset
0x180063620  xor     ecx, ecx; lpEventAttributes
0x180063622  call    cs:__imp_CreateEventW
0x180063628  mov     [rsi+90h], rax
0x18006362f  test    rax, rax
0x180063632  jnz     loc_1800636DF
0x180063638  call    cs:__imp_GetLastError
0x18006363e  mov     ebx, eax
0x180063640  mov     eax, cs:CallbackContext
0x180063646  cmp     eax, 2
0x180063649  jbe     short loc_1800636BF
0x18006364b  lea     rax, aInitializeinst_0; "InitializeInstance"
0x180063652  mov     [rbp+arg_18], ebx
0x180063655  mov     [rbp+var_18], rax
0x180063659  lea     rdx, word_1802863D2
0x180063660  lea     rax, aOnecoreTermsrv_70; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180063667  mov     [rbp+var_20], 74h ; 't'
0x18006366e  mov     [rbp+var_10], rax
0x180063672  lea     rax, aFailedToCreate_42; "Failed to create the Cancel wait event."...
0x180063679  mov     [rbp+var_8], rax
0x18006367d  lea     rax, [rbp+arg_18]
0x180063681  mov     [rsp+70h+var_28], rax
0x180063686  lea     rax, [rbp+var_18]
0x18006368a  mov     [rsp+70h+var_30], rax
0x18006368f  lea     rax, [rbp+var_20]
0x180063693  mov     [rsp+70h+var_38], rax
0x180063698  lea     rax, [rbp+var_10]
0x18006369c  mov     [rsp+70h+var_40], rax
0x1800636a1  lea     rax, [rbp+var_1C]
0x1800636a5  mov     [rsp+70h+var_48], rax
0x1800636aa  lea     rax, [rbp+var_8]
0x1800636ae  mov     [rsp+70h+var_50], rax
0x1800636b3  mov     [rbp+var_1C], 80004005h
0x1800636ba  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800636bf  test    ebx, ebx
0x1800636c1  jle     short loc_1800636CE
0x1800636c3  movzx   ebx, bx
0x1800636c6  or      ebx, 80070000h
0x1800636cc  test    ebx, ebx
0x1800636ce  jns     short loc_1800636E5
0x1800636d0  test    r12d, r12d
0x1800636d3  jz      short loc_1800636E5
0x1800636d5  mov     rcx, rsi; this
0x1800636d8  call    ?TerminateInstance@CUMTSCommandPlugin@@UEAAJXZ; CUMTSCommandPlugin::TerminateInstance(void)
0x1800636dd  jmp     short loc_1800636E5
0x1800636df  or      dword ptr [rsi+34h], 2
0x1800636e3  xor     ebx, ebx
0x1800636e5  lea     r11, [rsp+70h+var_s0]
0x1800636ea  mov     eax, ebx
0x1800636ec  mov     rbx, [r11+38h]
0x1800636f0  mov     rsi, [r11+40h]
0x1800636f4  mov     rsp, r11
0x1800636f7  pop     r15
0x1800636f9  pop     r14
0x1800636fb  pop     r12
0x1800636fd  pop     rdi
0x1800636fe  pop     rbp
0x1800636ff  retn
```
