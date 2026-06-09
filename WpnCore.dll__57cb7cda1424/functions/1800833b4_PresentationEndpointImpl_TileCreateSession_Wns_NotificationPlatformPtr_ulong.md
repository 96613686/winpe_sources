# PresentationEndpointImpl::TileCreateSession(Wns::NotificationPlatformPtr &,ulong *)

- ea: `0x1800833b4`
- end: `0x180083888`
- name: `?TileCreateSession@PresentationEndpointImpl@@QEAAJAEAVNotificationPlatformPtr@Wns@@PEAK@Z`
- size: `1236`
- prototype: `__int64 __fastcall(PresentationEndpointImpl *__hidden this, struct Wns::NotificationPlatformPtr *, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x180083330`

## callees

- `0x180001d24`
- `0x180011618`
- `0x18001bf30`
- `0x18002ee38`
- `0x18003a184`
- `0x1800724b0`
- `0x180072764`
- `0x18007302c`
- `0x1800833b4`
- `0x1800841e4`
- `0x180089f50`
- `0x18008a97c`
- `0x18009f488`
- `0x1800af0a4`
- `0x1800b99f0`
- `0x180118010`

## import_xrefs

- `ntdll!NtRaiseHardError` at `0x18008384f`
- `ntdll!NtRaiseHardError` at `0x18008384f`
- `ntdll!RtlAdjustPrivilege` at `0x1800837f0`
- `ntdll!RtlAdjustPrivilege` at `0x1800837f0`
- `ntdll!RtlInitUnicodeString` at `0x1800837ff`
- `ntdll!RtlInitUnicodeString` at `0x1800837ff`
- `ntdll!RtlGetSuiteMask` at `0x180083744`
- `ntdll!RtlGetSuiteMask` at `0x180083744`

## string_xrefs

- `0x18008375c`: `Windows must now restart because the Notification service ran out of session handles`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PresentationEndpointImpl::TileCreateSession(
        PresentationEndpointImpl *this,
        struct Wns::NotificationPlatformPtr *a2,
        unsigned int *a3)
{
  unsigned __int16 **v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // ebx
  int v9; // edx
  __int64 v10; // r8
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned int *v14; // rdx
  int CallingProcessId; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  int v19; // ebx
  int v20; // eax
  unsigned int v21; // edi
  __int64 v22; // rcx
  __int64 (__fastcall ***v23)(_QWORD, PresentationEndpointImpl *, _QWORD, _QWORD); // rcx
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  int ValidResponseOptions; // [rsp+20h] [rbp-E0h]
  int ValidResponseOptionsa; // [rsp+20h] [rbp-E0h]
  unsigned __int8 OldValue[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v32; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v33; // [rsp+48h] [rbp-B8h]
  ULONG Response; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned __int16 *v35; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwSize[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 Parameters[4]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SourceString[88]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR ExeName[264]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+288h]

  v33 = 0;
  v35 = 0;
  dwSize[0] = 260;
  CallerIdentity::GetCallerProcessImageName(ExeName, dwSize, a3);
  if ( (byte_18015DE47 & 4) != 0 )
    McTemplateU0pz_EventWriteTransfer(v7, WPNUI_TILE_CREATE_SESSION_ENTRY, 0, ExeName);
  if ( !a3 )
  {
    v8 = -2147467261;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\presentationendpointimpl.cpp",
      (const char *)0x80004003LL,
      ValidResponseOptions);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_30;
    v12 = 14;
    v13 = 2147500035LL;
    goto LABEL_7;
  }
  if ( (unsigned int)UserAwareCallerIdentity::GetCallingProcessAppId((UserAwareCallerIdentity *)&v35, v6) == -2147024891 )
  {
    v32 = 0;
    CallingProcessId = UserAwareCallerIdentity::GetCallingProcessId((UserAwareCallerIdentity *)&v32, v14);
    v8 = CallingProcessId;
    if ( CallingProcessId < 0 )
    {
      v18 = 163;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\presentationendpointimpl.cpp",
        (const char *)(unsigned int)CallingProcessId,
        ValidResponseOptions);
      goto LABEL_38;
    }
    CallingProcessId = _AllocStringWorker<CTCoAllocPolicy>(v17, v16, 0, 11);
    v8 = CallingProcessId;
    if ( CallingProcessId < 0 )
    {
      v18 = 166;
      goto LABEL_13;
    }
    v19 = (int)v35;
    v20 = StringCchPrintfW(v35, 0xBu, L"%d", v32);
    v21 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA8,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\presentationendpointimpl.cpp",
        (const char *)(unsigned int)v20,
        ValidResponseOptions);
      v8 = v21;
      goto LABEL_38;
    }
  }
  else
  {
    v19 = (int)v35;
  }
  if ( *((_DWORD *)this + 4) )
  {
    v22 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 184LL) + 128LL);
    v23 = (__int64 (__fastcall ***)(_QWORD, PresentationEndpointImpl *, _QWORD, _QWORD))((v22 + 8) & -(__int64)(v22 != 0));
    if ( v23 )
    {
      ValidResponseOptionsa = v19;
      v24 = (**v23)(v23, this, *((unsigned int *)this + 4), *((_QWORD *)this + 1));
      v8 = v24;
      if ( v24 >= 0 )
      {
        *a3 = v33;
        goto LABEL_30;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC6,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\presentationendpointimpl.cpp",
        (const char *)(unsigned int)v24,
        ValidResponseOptionsa);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_30;
      v12 = 19;
      v13 = v8;
    }
    else
    {
      v8 = -2143420155;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBA,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\presentationendpointimpl.cpp",
        (const char *)0x803E0105LL,
        ValidResponseOptions);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_30;
      v12 = 18;
      v13 = 2151547141LL;
    }
  }
  else
  {
    v8 = -2147467259;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\presentationendpointimpl.cpp",
      (const char *)0x80004005LL,
      ValidResponseOptions);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_30;
    v12 = 17;
    v13 = 2147500037LL;
  }
LABEL_7:
  WPP_SF_d(v11[2], v12, WPP_e6d612fff5b730372a2b7ad6302a0a9f_Traceguids, v13);
LABEL_30:
  if ( (byte_18015DE47 & 4) != 0 )
    McTemplateU0pqdzdd_EventWriteTransfer((_DWORD)v11, v9, 0, v33, v8, (__int64)ExeName);
  if ( v8 == -2143419904 )
  {
    if ( (unsigned int)dword_18015C038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18015C038, 0x200000000000LL, v10) )
    {
      v32 = g_nQueuedTileCleanups;
      dwSize[1] = g_nQueuedTileCloses;
      *(_QWORD *)&DestinationString.Length = ExeName;
      Response = -2143419904;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v25,
        (__int64)byte_180137399,
        v26,
        v27,
        (__int64)&Response,
        &DestinationString);
    }
    if ( (RtlGetSuiteMask() & 0x10000) != 0 )
    {
      Response = 0;
      wcscpy(SourceString, L"Windows must now restart because the Notification service ran out of sessihandles");
      DestinationString = 0;
      OldValue[0] = 0;
      RtlAdjustPrivilege(0x13u, 1u, 0, OldValue);
      RtlInitUnicodeString(&DestinationString, SourceString);
      Parameters[0] = (unsigned __int64)&DestinationString;
      Parameters[1] = -2143419904;
      Parameters[2] = g_nQueuedTileCloses;
      Parameters[3] = g_nQueuedTileCleanups;
      NtRaiseHardError(-1073741286, 4u, 1u, Parameters, 6u, &Response);
    }
  }
LABEL_38:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v35);
  return v8;
}

```

## disassembly

```asm
0x1800833b4  mov     [rsp-8+arg_18], rbx
0x1800833b9  push    rbp
0x1800833ba  push    rsi
0x1800833bb  push    rdi
0x1800833bc  push    r14
0x1800833be  push    r15
0x1800833c0  lea     rbp, [rsp-260h]
0x1800833c8  sub     rsp, 360h
0x1800833cf  mov     rax, cs:__security_cookie
0x1800833d6  xor     rax, rsp
0x1800833d9  mov     [rbp+280h+var_30], rax
0x1800833e0  mov     r14, r8
0x1800833e3  mov     r15, rdx
0x1800833e6  mov     rsi, rcx
0x1800833e9  mov     [rsp+380h+var_338], 0
0x1800833f1  mov     [rsp+380h+var_330], 0
0x1800833fa  mov     [rsp+380h+dwSize], 104h
0x180083402  lea     rdx, [rsp+380h+dwSize]; lpdwSize
0x180083407  lea     rcx, [rbp+280h+ExeName]; lpExeName
0x18008340b  call    ?GetCallerProcessImageName@CallerIdentity@@YAJPEAGPEAK@Z; CallerIdentity::GetCallerProcessImageName(ushort *,ulong *)
0x180083410  test    cs:byte_18015DE47, 4
0x180083417  jz      short loc_18008342C
0x180083419  lea     r9, [rbp+280h+ExeName]
0x18008341d  xor     r8d, r8d
0x180083420  lea     rdx, WPNUI_TILE_CREATE_SESSION_ENTRY
0x180083427  call    McTemplateU0pz_EventWriteTransfer
0x18008342c  test    r14, r14
0x18008342f  jnz     short loc_180083491
0x180083431  mov     ebx, 80004003h
0x180083436  mov     rcx, [rbp+288h]; this
0x18008343d  mov     r9d, ebx; char *
0x180083440  lea     r8, aOnecoreuapBase_103; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180083447  mov     edx, 96h; void *
0x18008344c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180083451  lea     rax, WPP_GLOBAL_Control
0x180083458  mov     rcx, cs:WPP_GLOBAL_Control
0x18008345f  cmp     rcx, rax
0x180083462  jz      loc_180083694
0x180083468  test    byte ptr [rcx+1Ch], 80h
0x18008346c  jz      loc_180083694
0x180083472  lea     edx, [r14+0Eh]
0x180083476  mov     r9d, 80004003h
0x18008347c  lea     r8, WPP_e6d612fff5b730372a2b7ad6302a0a9f_Traceguids
0x180083483  mov     rcx, [rcx+10h]
0x180083487  call    WPP_SF_d
0x18008348c  jmp     loc_180083694
0x180083491  lea     rcx, [rsp+380h+var_330]; this
0x180083496  call    ?GetCallingProcessAppId@UserAwareCallerIdentity@@YAJPEAPEAG@Z; UserAwareCallerIdentity::GetCallingProcessAppId(ushort * *)
0x18008349b  cmp     eax, 80070005h
0x1800834a0  jnz     loc_180083549
0x1800834a6  mov     [rsp+380h+var_33C], 0
0x1800834ae  lea     rcx, [rsp+380h+var_33C]; this
0x1800834b3  call    ?GetCallingProcessId@UserAwareCallerIdentity@@YAJPEAK@Z; UserAwareCallerIdentity::GetCallingProcessId(ulong *)
0x1800834b8  mov     ebx, eax
0x1800834ba  test    eax, eax
0x1800834bc  jns     short loc_1800834C5
0x1800834be  mov     edx, 0A3h
0x1800834c3  jmp     short loc_1800834EA
0x1800834c5  lea     rax, [rsp+380h+var_330]
0x1800834ca  mov     [rsp+380h+Response], rax
0x1800834cf  mov     edi, 0Bh
0x1800834d4  mov     r9d, edi
0x1800834d7  xor     r8d, r8d
0x1800834da  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800834df  mov     ebx, eax
0x1800834e1  test    eax, eax
0x1800834e3  jns     short loc_180083505
0x1800834e5  mov     edx, 0A6h; void *
0x1800834ea  lea     r8, aOnecoreuapBase_103; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800834f1  mov     r9d, eax; char *
0x1800834f4  mov     rcx, [rbp+288h]; this
0x1800834fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083500  jmp     loc_180083856
0x180083505  mov     r9d, [rsp+380h+var_33C]
0x18008350a  lea     r8, aD; "%d"
0x180083511  mov     rdx, rdi; unsigned __int64
0x180083514  mov     rbx, [rsp+380h+var_330]
0x180083519  mov     rcx, rbx; unsigned __int16 *
0x18008351c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180083521  mov     edi, eax
0x180083523  test    eax, eax
0x180083525  jns     short loc_18008354E
0x180083527  mov     rcx, [rbp+288h]; this
0x18008352e  mov     r9d, eax; char *
0x180083531  lea     r8, aOnecoreuapBase_103; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180083538  mov     edx, 0A8h; void *
0x18008353d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083542  mov     ebx, edi
0x180083544  jmp     loc_180083856
0x180083549  mov     rbx, [rsp+380h+var_330]
0x18008354e  mov     eax, [rsi+10h]
0x180083551  test    eax, eax
0x180083553  jnz     short loc_1800835A6
0x180083555  mov     ebx, 80004005h
0x18008355a  mov     rcx, [rbp+288h]; this
0x180083561  mov     r9d, ebx; char *
0x180083564  lea     r8, aOnecoreuapBase_103; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008356b  mov     edx, 0B6h; void *
0x180083570  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180083575  lea     rax, WPP_GLOBAL_Control
0x18008357c  mov     rcx, cs:WPP_GLOBAL_Control
0x180083583  cmp     rcx, rax
0x180083586  jz      loc_180083694
0x18008358c  test    byte ptr [rcx+1Ch], 80h
0x180083590  jz      loc_180083694
0x180083596  mov     edx, 11h
0x18008359b  mov     r9d, 80004005h
0x1800835a1  jmp     loc_18008347C
0x1800835a6  mov     rax, [r15]
0x1800835a9  nop
0x1800835aa  mov     rax, [rax+0B8h]
0x1800835b1  mov     rcx, [rax+80h]
0x1800835b8  lea     rax, [rcx+8]
0x1800835bc  neg     rcx
0x1800835bf  sbb     rcx, rcx
0x1800835c2  and     rcx, rax
0x1800835c5  jnz     short loc_180083618
0x1800835c7  mov     ebx, 803E0105h
0x1800835cc  mov     rcx, [rbp+288h]; this
0x1800835d3  mov     r9d, ebx; char *
0x1800835d6  lea     r8, aOnecoreuapBase_103; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800835dd  mov     edx, 0BAh; void *
0x1800835e2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800835e7  lea     rax, WPP_GLOBAL_Control
0x1800835ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800835f5  cmp     rcx, rax
0x1800835f8  jz      loc_180083694
0x1800835fe  test    byte ptr [rcx+1Ch], 80h
0x180083602  jz      loc_180083694
0x180083608  mov     edx, 12h
0x18008360d  mov     r9d, 803E0105h
0x180083613  jmp     loc_18008347C
0x180083618  mov     rax, [rcx]
0x18008361b  lea     rdx, [rsp+380h+var_338]
0x180083620  mov     [rsp+380h+var_350], rdx
0x180083625  lea     rdx, [rbp+280h+ExeName]
0x180083629  mov     [rsp+380h+Response], rdx
0x18008362e  mov     qword ptr [rsp+380h+ValidResponseOptions], rbx; int
0x180083633  mov     r9, [rsi+8]
0x180083637  mov     r8d, [rsi+10h]
0x18008363b  mov     rdx, rsi
0x18008363e  mov     rax, [rax]
0x180083641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083646  mov     ebx, eax
0x180083648  test    eax, eax
0x18008364a  jns     short loc_18008368D
0x18008364c  mov     rcx, [rbp+288h]; this
0x180083653  mov     r9d, eax; char *
0x180083656  lea     r8, aOnecoreuapBase_103; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008365d  mov     edx, 0C6h; void *
0x180083662  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180083667  lea     rax, WPP_GLOBAL_Control
0x18008366e  mov     rcx, cs:WPP_GLOBAL_Control
0x180083675  cmp     rcx, rax
0x180083678  jz      short loc_180083694
0x18008367a  test    byte ptr [rcx+1Ch], 80h
0x18008367e  jz      short loc_180083694
0x180083680  mov     edx, 13h
0x180083685  mov     r9d, ebx
0x180083688  jmp     loc_18008347C
0x18008368d  mov     eax, [rsp+380h+var_338]
0x180083691  mov     [r14], eax
0x180083694  test    cs:byte_18015DE47, 4
0x18008369b  jz      short loc_1800836B7
0x18008369d  lea     rax, [rbp+280h+ExeName]
0x1800836a1  mov     [rsp+380h+Response], rax
0x1800836a6  mov     [rsp+380h+ValidResponseOptions], ebx
0x1800836aa  mov     r9d, [rsp+380h+var_338]
0x1800836af  xor     r8d, r8d
0x1800836b2  call    McTemplateU0pqdzdd_EventWriteTransfer
0x1800836b7  mov     rdi, 0FFFFFFFF803E0200h
0x1800836be  cmp     ebx, edi
0x1800836c0  jnz     loc_180083856
0x1800836c6  mov     eax, cs:dword_18015C038
0x1800836cc  cmp     eax, 5
0x1800836cf  jbe     short loc_180083744
0x1800836d1  mov     rdx, 200000000000h
0x1800836db  lea     rcx, dword_18015C038
0x1800836e2  call    _tlgKeywordOn
0x1800836e7  test    al, al
0x1800836e9  jz      short loc_180083744
0x1800836eb  mov     eax, cs:?g_nQueuedTileCleanups@@3JA; long g_nQueuedTileCleanups
0x1800836f1  mov     [rsp+380h+var_33C], eax
0x1800836f5  mov     eax, cs:?g_nQueuedTileCloses@@3JA; long g_nQueuedTileCloses
0x1800836fb  mov     [rsp+380h+var_324], eax
0x1800836ff  lea     rax, [rbp+280h+ExeName]
0x180083703  mov     qword ptr [rsp+380h+DestinationString.Length], rax
0x180083708  mov     [rsp+380h+var_334], 803E0200h
0x180083710  lea     rax, [rsp+380h+var_33C]
0x180083715  mov     [rsp+380h+var_348], rax
0x18008371a  lea     rax, [rsp+380h+var_324]
0x18008371f  mov     [rsp+380h+var_350], rax
0x180083724  lea     rax, [rsp+380h+DestinationString]
0x180083729  mov     [rsp+380h+Response], rax
0x18008372e  lea     rax, [rsp+380h+var_334]
0x180083733  mov     qword ptr [rsp+380h+ValidResponseOptions], rax
0x180083738  lea     rdx, byte_180137399
0x18008373f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180083744  call    cs:__imp_RtlGetSuiteMask
0x18008374a  bt      eax, 10h
0x18008374e  jnb     loc_180083856
0x180083754  mov     [rsp+380h+var_334], 0
0x18008375c  movaps  xmm0, xmmword ptr cs:aWindowsMustNow; "Windows must now restart because the No"...
0x180083763  movups  xmmword ptr [rbp+280h+SourceString], xmm0
0x180083767  movaps  xmm1, xmmword ptr cs:aWindowsMustNow+10h; "must now restart because the Notificati"...
0x18008376e  movups  [rbp+280h+var_2E0], xmm1
0x180083772  movaps  xmm0, xmmword ptr cs:aWindowsMustNow+20h; " restart because the Notification servi"...
0x180083779  movups  [rbp+280h+var_2D0], xmm0
0x18008377d  movaps  xmm1, xmmword ptr cs:aWindowsMustNow+30h; " because the Notification service ran o"...
0x180083784  movups  [rbp+280h+var_2C0], xmm1
0x180083788  movaps  xmm0, xmmword ptr cs:aWindowsMustNow+40h; " the Notification service ran out of se"...
0x18008378f  movups  [rbp+280h+var_2B0], xmm0
0x180083793  movaps  xmm1, xmmword ptr cs:aWindowsMustNow+50h; "ification service ran out of session ha"...
0x18008379a  movups  [rbp+280h+var_2A0], xmm1
0x18008379e  movaps  xmm0, xmmword ptr cs:aWindowsMustNow+60h; "n service ran out of session handles"
0x1800837a5  movups  [rbp+280h+var_290], xmm0
0x1800837a9  movaps  xmm1, xmmword ptr cs:aWindowsMustNow+70h; "e ran out of session handles"
0x1800837b0  movups  [rbp+280h+var_280], xmm1
0x1800837b4  movaps  xmm0, xmmword ptr cs:aWindowsMustNow+80h; "t of session handles"
0x1800837bb  movups  [rbp+280h+var_270], xmm0
0x1800837bf  movaps  xmm1, xmmword ptr cs:aWindowsMustNow+90h; "sion handles"
0x1800837c6  movups  [rbp+280h+var_260], xmm1
0x1800837ca  movups  xmm0, xmmword ptr cs:aWindowsMustNow+9Ah; "handles"
0x1800837d1  movups  [rbp+280h+var_260+0Ah], xmm0
0x1800837d5  xorps   xmm0, xmm0
0x1800837d8  movups  xmmword ptr [rsp+380h+DestinationString.Length], xmm0
0x1800837dd  mov     [rsp+380h+OldValue], 0
0x1800837e2  lea     r9, [rsp+380h+OldValue]; OldValue
0x1800837e7  xor     r8d, r8d; ForThread
0x1800837ea  mov     dl, 1; NewValue
0x1800837ec  lea     ecx, [r8+13h]; Privilege
0x1800837f0  call    cs:__imp_RtlAdjustPrivilege
0x1800837f6  lea     rdx, [rbp+280h+SourceString]; SourceString
0x1800837fa  lea     rcx, [rsp+380h+DestinationString]; DestinationString
0x1800837ff  call    cs:__imp_RtlInitUnicodeString
0x180083805  lea     rax, [rsp+380h+DestinationString]
0x18008380a  mov     [rsp+380h+Parameters], rax
0x18008380f  mov     [rsp+380h+var_308], rdi
0x180083814  movsxd  rax, cs:?g_nQueuedTileCloses@@3JA; long g_nQueuedTileCloses
0x18008381b  mov     [rbp+280h+var_300], rax
0x18008381f  movsxd  rax, cs:?g_nQueuedTileCleanups@@3JA; long g_nQueuedTileCleanups
0x180083826  mov     [rbp+280h+var_2F8], rax
0x18008382a  lea     rax, [rsp+380h+var_334]
0x18008382f  mov     [rsp+380h+Response], rax; Response
0x180083834  mov     [rsp+380h+ValidResponseOptions], 6; ValidResponseOptions
0x18008383c  lea     r9, [rsp+380h+Parameters]; Parameters
0x180083841  mov     edx, 4; NumberOfParameters
0x180083846  mov     ecx, 0C000021Ah; ErrorStatus
0x18008384b  lea     r8d, [rdx-3]; UnicodeStringParameterMask
0x18008384f  call    cs:__imp_NtRaiseHardError
0x180083855  nop
0x180083856  lea     rcx, [rsp+380h+var_330]
0x18008385b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180083860  mov     eax, ebx
0x180083862  mov     rcx, [rbp+280h+var_30]
0x180083869  xor     rcx, rsp; StackCookie
0x18008386c  call    __security_check_cookie
0x180083871  mov     rbx, [rsp+380h+arg_18]
0x180083879  add     rsp, 360h
0x180083880  pop     r15
0x180083882  pop     r14
0x180083884  pop     rdi
0x180083885  pop     rsi
0x180083886  pop     rbp
0x180083887  retn
```
