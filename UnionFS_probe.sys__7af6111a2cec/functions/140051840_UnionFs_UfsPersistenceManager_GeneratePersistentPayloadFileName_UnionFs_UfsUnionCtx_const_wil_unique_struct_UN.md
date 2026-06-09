# UnionFs::UfsPersistenceManager::GeneratePersistentPayloadFileName(UnionFs::UfsUnionCtx const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &,bool)

- ea: `0x140051840`
- end: `0x140051dec`
- name: `?GeneratePersistentPayloadFileName@UfsPersistenceManager@UnionFs@@IEBAJAEBVUfsUnionCtx@2@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@_N@Z`
- size: `1452`
- prototype: ``
- caller_count: `4`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x140050d78`
- `0x140051630`
- `0x140051df4`
- `0x140052fdc`

## callees

- `0x140001008`
- `0x14000f7fc`
- `0x140050378`
- `0x140051840`
- `0x140056a50`
- `0x140056afc`
- `0x140075254`
- `0x140078380`
- `0x14007843c`
- `0x140079a24`
- `0x140079c48`
- `0x140079d0c`
- `0x140079da0`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x140051b44`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140051b7b`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140051bc6`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140051b44`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140051b7b`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140051bc6`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051af1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051bff`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051c8f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051cc8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051cf7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051af1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051bff`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051c8f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051cc8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051cf7`
- `FLTMGR!FltCreateSystemVolumeInformationFolder` at `0x140051939`
- `FLTMGR!FltCreateSystemVolumeInformationFolder` at `0x140051939`

## string_xrefs

- `0x140051b60`: `API: Appending path separator`
- `0x140051b07`: `API: Appending scratch root path`
- `0x140051cda`: `API: Appending temp extension`
- `0x140051d09`: `API: Appending name extension`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPersistenceManager::GeneratePersistentPayloadFileName(
        __int64 a1,
        __int64 a2,
        struct _UNICODE_STRING *a3,
        __int64 a4,
        char a5)
{
  struct _UNICODE_STRING *v7; // r13
  unsigned __int64 *v9; // rdx
  __int64 *v10; // rax
  volatile signed __int32 *v11; // r14
  __int64 v12; // rbx
  NTSTATUS SystemVolumeInformationFolder; // ebx
  unsigned __int64 *v14; // rdx
  __int64 *v15; // rax
  volatile signed __int32 *v16; // r14
  __int64 v17; // rbx
  int v18; // ebx
  __int16 v19; // bx
  unsigned __int64 *v20; // rdx
  __int64 *v21; // rax
  volatile signed __int32 *v22; // r14
  __int64 v23; // r13
  __int16 v24; // bx
  __int16 v25; // bx
  unsigned __int64 *v26; // rdx
  const unsigned __int16 *v27; // r8
  __int64 *v28; // rax
  volatile signed __int32 *v29; // rbx
  __int64 v30; // r14
  const char *v31; // rax
  __int64 v32; // r8
  struct _UNICODE_STRING *v33; // rdx
  NTSTATUS appended; // eax
  __int64 v35; // r8
  USHORT Length; // cx
  __int64 v37; // r8
  PWSTR Buffer; // rdx
  __int128 v39; // xmm0
  unsigned __int64 *v40; // rdx
  __int64 *v41; // rax
  volatile signed __int32 *v42; // rbx
  __int64 v43; // rsi
  struct _UNICODE_STRING *v44; // rdx
  int v45; // esi
  struct _UNICODE_STRING *v46; // rdx
  struct _UNICODE_STRING v47; // xmm0
  char *v49; // [rsp+28h] [rbp-69h]
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-51h] BYREF
  struct _GUID v51; // [rsp+50h] [rbp-41h] BYREF
  int v52; // [rsp+60h] [rbp-31h] BYREF
  UNICODE_STRING Source; // [rsp+68h] [rbp-29h] BYREF
  __int128 v54; // [rsp+78h] [rbp-19h] BYREF
  UNICODE_STRING v55; // [rsp+88h] [rbp-9h] BYREF
  UNICODE_STRING v56; // [rsp+98h] [rbp+7h] BYREF
  _BYTE v57[8]; // [rsp+F8h] [rbp+67h] BYREF
  struct _UNICODE_STRING *v58; // [rsp+100h] [rbp+6Fh]

  v58 = a3;
  v7 = a3;
  if ( (unsigned int)dword_14009E178 > 5
    && (qword_14009E188 & 0x8000) != 0
    && (qword_14009E190 & 0x8000) == qword_14009E190 )
  {
    v52 = 1209;
    *(_QWORD *)&v54 = "onecore\\base\\fs\\unionfs\\sys\\persistencemanager.cpp";
    *(_QWORD *)&Source.Length = "UnionFs::UfsPersistenceManager::GeneratePersistentPayloadFileName";
    *(_QWORD *)&v51.Data1 = "ENTER";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"UnionFs::UfsPersistenceManager::GeneratePersistentPayloadFileName",
      (unsigned int)qword_1400981B8,
      0x8000,
      a4,
      (__int64)&v51,
      (__int64)&Source,
      (__int64)&v54,
      (__int64)&v52);
  }
  if ( (*(_DWORD *)(a2 + 24) & 0x20) == 0 )
  {
    FsFltWil::AcquirePushLockShared(&v51, a2 + 72);
    v10 = *(__int64 **)(a2 + 48);
    v11 = (volatile signed __int32 *)v10[1];
    v12 = *v10;
    if ( v11 )
      _InterlockedIncrement(v11 + 2);
    if ( *(_QWORD *)&v51.Data1 )
      FsFltWil::Details::ReleasePushLockShared(*(FsFltWil::Details **)&v51.Data1, v9);
    SystemVolumeInformationFolder = FltCreateSystemVolumeInformationFolder(**(PFLT_INSTANCE **)(v12 + 8));
    if ( v11 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v11);
    if ( SystemVolumeInformationFolder < 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)SystemVolumeInformationFolder,
        a4,
        (struct UnionFs::StackEventTracer *)0x336001704C7LL,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::GeneratePersistentPayloadFileName",
        "API: Verifying SVI folder",
        v49);
      goto LABEL_73;
    }
  }
  wcscpy((wchar_t *)v57, L"\\");
  FsFltWil::AcquirePushLockShared(&v51, a2 + 72);
  v15 = *(__int64 **)(a2 + 48);
  v16 = (volatile signed __int32 *)v15[1];
  v17 = *v15;
  if ( v16 )
    _InterlockedIncrement(v16 + 2);
  if ( *(_QWORD *)&v51.Data1 )
    FsFltWil::Details::ReleasePushLockShared(*(FsFltWil::Details **)&v51.Data1, v14);
  v18 = *(unsigned __int16 *)(*(_QWORD *)(v17 + 16) + 24LL);
  if ( v16 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v16);
  v19 = v18 + 2;
  if ( (*(_DWORD *)(a2 + 24) & 0x20) != 0 )
  {
    FsFltWil::AcquirePushLockShared(&v51, a2 + 72);
    v21 = *(__int64 **)(a2 + 48);
    v22 = (volatile signed __int32 *)v21[1];
    v23 = *v21;
    if ( v22 )
      _InterlockedIncrement(v22 + 2);
    if ( *(_QWORD *)&v51.Data1 )
      FsFltWil::Details::ReleasePushLockShared(*(FsFltWil::Details **)&v51.Data1, v20);
    v24 = *(_WORD *)(*(_QWORD *)(v23 + 16) + 40LL) + v19;
    if ( v22 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v22);
    v7 = v58;
  }
  else
  {
    v24 = v19 + 50;
  }
  v25 = v24 + 2;
  (*(void (__fastcall **)(__int64, UNICODE_STRING *))(*(_QWORD *)a1 + 80LL))(a1, &v55);
  (*(void (__fastcall **)(__int64, UNICODE_STRING *))(*(_QWORD *)a1 + 72LL))(a1, &v56);
  if ( (*(_DWORD *)(a2 + 24) & 0x20) != 0 )
    LOWORD(v18) = v55.Length + v25;
  else
    LOWORD(v18) = v56.Length + v25 + 78;
  FsFltWil::MakeUniqueUnicodeString(&Destination, (unsigned int)(v18 + 8), 1279685446);
  if ( (*(_DWORD *)(a2 + 24) & 0x20) != 0 )
  {
    Source = 0;
    FsFltWil::AcquirePushLockShared(&v51, a2 + 72);
    v28 = *(__int64 **)(a2 + 48);
    v29 = (volatile signed __int32 *)v28[1];
    v30 = *v28;
    if ( v29 )
      _InterlockedIncrement(v29 + 2);
    if ( *(_QWORD *)&v51.Data1 )
      FsFltWil::Details::ReleasePushLockShared(*(FsFltWil::Details **)&v51.Data1, v26);
    Source = *(UNICODE_STRING *)(*(_QWORD *)(v30 + 16) + 40LL);
    UnionFs::Utils::StripTrailingBackslashFromPath((UnionFs::Utils *)&Source, 0, v27);
    if ( v29 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v29);
    SystemVolumeInformationFolder = RtlAppendUnicodeStringToString(&Destination, &Source);
    if ( SystemVolumeInformationFolder < 0 )
    {
      v31 = "API: Appending scratch root path";
      v32 = 0x75001704FELL;
LABEL_41:
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)SystemVolumeInformationFolder,
        a4,
        (struct UnionFs::StackEventTracer *)v32,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::GeneratePersistentPayloadFileName",
        v31,
        v49);
LABEL_42:
      FsFltWil::Details::FreeUnicodeString(&Destination, v33);
      goto LABEL_73;
    }
  }
  else
  {
    appended = RtlAppendUnicodeToString(&Destination, (PCWSTR)v57);
    SystemVolumeInformationFolder = appended;
    if ( appended < 0 )
    {
      v35 = 0x2F100170507LL;
LABEL_45:
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)appended,
        a4,
        (struct UnionFs::StackEventTracer *)v35,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::GeneratePersistentPayloadFileName",
        "API: Appending path separator",
        v49);
      goto LABEL_42;
    }
    SystemVolumeInformationFolder = RtlAppendUnicodeToString(&Destination, L"System Volume Information");
    if ( SystemVolumeInformationFolder < 0 )
    {
      v31 = "API: Appending SVI";
      v32 = 0x2F20017050CLL;
      goto LABEL_41;
    }
  }
  Length = Destination.Length;
  v37 = 92;
  Buffer = Destination.Buffer;
  if ( Destination.Buffer[((unsigned __int64)Destination.Length >> 1) - 1] != 92 )
  {
    appended = RtlAppendUnicodeToString(&Destination, (PCWSTR)v57);
    SystemVolumeInformationFolder = appended;
    if ( appended < 0 )
    {
      v35 = 0x2F400170518LL;
      goto LABEL_45;
    }
    Buffer = Destination.Buffer;
    Length = Destination.Length;
  }
  if ( (*(_DWORD *)(a2 + 24) & 0x20) != 0 )
  {
    SystemVolumeInformationFolder = RtlAppendUnicodeStringToString(&Destination, &v55);
    if ( SystemVolumeInformationFolder < 0 )
    {
      v31 = "API: Appending self-contained name";
      v32 = 0x26900170522LL;
      goto LABEL_41;
    }
  }
  else
  {
    v39 = *(_OWORD *)(a2 + 8);
    v51.Data3 = 0;
    LOWORD(v51.Data1) = 0;
    *(unsigned int *)((char *)&v51.Data1 + 2) = (unsigned __int16)(Destination.MaximumLength - Length);
    *(_QWORD *)v51.Data4 = (char *)Buffer + Length;
    v54 = v39;
    SystemVolumeInformationFolder = UnionFs::Rtl::StringFromGUIDEx(
                                      (UnionFs::Rtl *)&v54,
                                      &v51,
                                      (struct _UNICODE_STRING *)v37);
    if ( SystemVolumeInformationFolder < 0 )
    {
      v31 = "API: Appending GUID string";
      v32 = 0x2E50017052FLL;
      goto LABEL_41;
    }
    Destination.Length += LOWORD(v51.Data1);
    SystemVolumeInformationFolder = RtlAppendUnicodeStringToString(&Destination, &v56);
    if ( SystemVolumeInformationFolder < 0 )
    {
      v31 = "API: Appending name suffix";
      v32 = 0x2E600170536LL;
      goto LABEL_41;
    }
  }
  if ( a5 )
  {
    SystemVolumeInformationFolder = RtlAppendUnicodeStringToString(&Destination, &stru_14007EE00);
    if ( SystemVolumeInformationFolder < 0 )
    {
      v31 = "API: Appending temp extension";
      v32 = 0x2E800170540LL;
      goto LABEL_41;
    }
  }
  else
  {
    SystemVolumeInformationFolder = RtlAppendUnicodeStringToString(&Destination, &stru_14007EDE0);
    if ( SystemVolumeInformationFolder < 0 )
    {
      v31 = "API: Appending name extension";
      v32 = 0x2E900170548LL;
      goto LABEL_41;
    }
  }
  FsFltWil::AcquirePushLockShared(&v51, a2 + 72);
  v41 = *(__int64 **)(a2 + 48);
  v42 = (volatile signed __int32 *)v41[1];
  v43 = *v41;
  if ( v42 )
    _InterlockedIncrement(v42 + 2);
  if ( *(_QWORD *)&v51.Data1 )
    FsFltWil::Details::ReleasePushLockShared(*(FsFltWil::Details **)&v51.Data1, v40);
  v45 = UnionFs::Utils::PrependVolumeNameFromInstance(**(_QWORD **)(v43 + 8), &Destination, a4, 0);
  if ( v42 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v42);
  if ( v45 >= 0 )
  {
    v47 = Destination;
    Destination = *v7;
    *v7 = v47;
    FsFltWil::Details::FreeUnicodeString(&Destination, v44);
    SystemVolumeInformationFolder = 0;
  }
  else
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v45,
      a4,
      (struct UnionFs::StackEventTracer *)0x2E700170551LL,
      (unsigned __int64)"UnionFs::UfsPersistenceManager::GeneratePersistentPayloadFileName",
      "PUSH: Prepending volume name",
      v49);
    FsFltWil::Details::FreeUnicodeString(&Destination, v46);
    SystemVolumeInformationFolder = v45;
  }
LABEL_73:
  lambda_925d2fa7f01dd4206570cbc3e3577b8e_::operator()();
  return (unsigned int)SystemVolumeInformationFolder;
}

```

## disassembly

```asm
0x140051840  mov     [rsp-8+arg_0], rbx
0x140051845  mov     [rsp-8+arg_10], r8
0x14005184a  push    rbp
0x14005184b  push    rsi
0x14005184c  push    rdi
0x14005184d  push    r12
0x14005184f  push    r13
0x140051851  push    r14
0x140051853  push    r15
0x140051855  lea     rbp, [rsp-1Fh]
0x14005185a  sub     rsp, 0B0h
0x140051861  mov     eax, cs:dword_14009E178
0x140051867  mov     r12, rcx
0x14005186a  lea     rcx, aUnionfsUfspers_18; "UnionFs::UfsPersistenceManager::Generat"...
0x140051871  mov     rdi, r9
0x140051874  mov     r13, r8
0x140051877  mov     rsi, rdx
0x14005187a  cmp     eax, 5
0x14005187d  jbe     short loc_1400518F4
0x14005187f  mov     rdx, cs:qword_14009E190
0x140051886  mov     r8d, 8000h
0x14005188c  mov     rax, cs:qword_14009E188
0x140051893  test    r8, rax
0x140051896  jz      short loc_1400518F4
0x140051898  mov     rax, rdx
0x14005189b  and     rax, r8
0x14005189e  cmp     rax, rdx
0x1400518a1  jnz     short loc_1400518F4
0x1400518a3  lea     rax, aOnecoreBaseFsU_1; "onecore\\base\\fs\\unionfs\\sys\\persis"...
0x1400518aa  mov     [rbp+4Fh+var_80], 4B9h
0x1400518b1  mov     qword ptr [rbp+4Fh+var_68], rax
0x1400518b5  lea     rdx, qword_1400981B8
0x1400518bc  lea     rax, aEnter; "ENTER"
0x1400518c3  mov     qword ptr [rbp+4Fh+Source.Length], rcx
0x1400518c7  mov     qword ptr [rbp+4Fh+var_90.Data1], rax
0x1400518cb  lea     rax, [rbp+4Fh+var_80]
0x1400518cf  mov     [rsp+0E0h+var_A8], rax
0x1400518d4  lea     rax, [rbp+4Fh+var_68]
0x1400518d8  mov     [rsp+0E0h+var_B0], rax
0x1400518dd  lea     rax, [rbp+4Fh+Source]
0x1400518e1  mov     [rsp+0E0h+var_B8], rax; char *
0x1400518e6  lea     rax, [rbp+4Fh+var_90]
0x1400518ea  mov     [rsp+0E0h+var_C0], rax
0x1400518ef  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400518f4  mov     eax, [rsi+18h]
0x1400518f7  lea     r15, [rsi+48h]
0x1400518fb  test    al, 20h
0x1400518fd  jnz     loc_140051984
0x140051903  mov     rdx, r15
0x140051906  lea     rcx, [rbp+4Fh+var_90]
0x14005190a  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x14005190f  mov     rax, [rsi+30h]
0x140051913  mov     r14, [rax+8]
0x140051917  mov     rbx, [rax]
0x14005191a  test    r14, r14
0x14005191d  jz      short loc_140051924
0x14005191f  lock inc dword ptr [r14+8]
0x140051924  mov     rcx, qword ptr [rbp+4Fh+var_90.Data1]; this
0x140051928  test    rcx, rcx
0x14005192b  jz      short loc_140051932
0x14005192d  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140051932  mov     rcx, [rbx+8]
0x140051936  mov     rcx, [rcx]; Instance
0x140051939  call    cs:__imp_FltCreateSystemVolumeInformationFolder
0x140051940  nop     dword ptr [rax+rax+00h]
0x140051945  mov     ebx, eax
0x140051947  test    r14, r14
0x14005194a  jz      short loc_140051954
0x14005194c  mov     rcx, r14; this
0x14005194f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140051954  test    ebx, ebx
0x140051956  jns     short loc_140051984
0x140051958  lea     rax, aApiVerifyingSv; "API: Verifying SVI folder"
0x14005195f  mov     r8, 336001704C7h; struct UnionFs::StackEventTracer *
0x140051969  lea     r9, aUnionfsUfspers_18; "UnionFs::UfsPersistenceManager::Generat"...
0x140051970  mov     [rsp+0E0h+var_C0], rax; char *
0x140051975  mov     rdx, rdi; int
0x140051978  mov     ecx, ebx; this
0x14005197a  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005197f  jmp     loc_140051DC9
0x140051984  mov     rdx, r15
0x140051987  mov     dword ptr [rbp+4Fh+arg_8], 5Ch ; '\'
0x14005198e  lea     rcx, [rbp+4Fh+var_90]
0x140051992  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140051997  mov     rax, [rsi+30h]
0x14005199b  mov     r14, [rax+8]
0x14005199f  mov     rbx, [rax]
0x1400519a2  test    r14, r14
0x1400519a5  jz      short loc_1400519AC
0x1400519a7  lock inc dword ptr [r14+8]
0x1400519ac  mov     rcx, qword ptr [rbp+4Fh+var_90.Data1]; this
0x1400519b0  test    rcx, rcx
0x1400519b3  jz      short loc_1400519BA
0x1400519b5  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x1400519ba  mov     rax, [rbx+10h]
0x1400519be  movzx   ebx, word ptr [rax+18h]
0x1400519c2  test    r14, r14
0x1400519c5  jz      short loc_1400519CF
0x1400519c7  mov     rcx, r14; this
0x1400519ca  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400519cf  mov     eax, [rsi+18h]
0x1400519d2  add     bx, 2
0x1400519d6  test    al, 20h
0x1400519d8  jz      loc_140051A63
0x1400519de  mov     rdx, r15
0x1400519e1  lea     rcx, [rbp+4Fh+var_90]
0x1400519e5  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x1400519ea  mov     rax, [rsi+30h]
0x1400519ee  mov     r14, [rax+8]
0x1400519f2  mov     r13, [rax]
0x1400519f5  test    r14, r14
0x1400519f8  jz      short loc_1400519FF
0x1400519fa  lock inc dword ptr [r14+8]
0x1400519ff  mov     rcx, qword ptr [rbp+4Fh+var_90.Data1]; this
0x140051a03  test    rcx, rcx
0x140051a06  jz      short loc_140051A0D
0x140051a08  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140051a0d  mov     rax, [r13+10h]
0x140051a11  add     bx, [rax+28h]
0x140051a15  test    r14, r14
0x140051a18  jz      short loc_140051A22
0x140051a1a  mov     rcx, r14; this
0x140051a1d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140051a22  mov     r13, [rbp+4Fh+arg_10]
0x140051a26  mov     rax, [r12]
0x140051a2a  lea     rdx, [rbp+4Fh+var_58]
0x140051a2e  mov     rcx, r12
0x140051a31  add     bx, 2
0x140051a35  mov     rax, [rax+50h]
0x140051a39  call    _guard_dispatch_icall
0x140051a3e  mov     rax, [r12]
0x140051a42  lea     rdx, [rbp+4Fh+var_48]
0x140051a46  mov     rcx, r12
0x140051a49  mov     rax, [rax+48h]
0x140051a4d  call    _guard_dispatch_icall
0x140051a52  mov     eax, [rsi+18h]
0x140051a55  mov     r12b, 20h ; ' '
0x140051a58  test    r12b, al
0x140051a5b  jz      short loc_140051A69
0x140051a5d  add     bx, [rbp+4Fh+var_58.Length]
0x140051a61  jmp     short loc_140051A71
0x140051a63  add     bx, 32h ; '2'
0x140051a67  jmp     short loc_140051A26
0x140051a69  add     bx, 4Eh ; 'N'
0x140051a6d  add     bx, [rbp+4Fh+var_48.Length]
0x140051a71  lea     edx, [rbx+8]
0x140051a74  mov     r8d, 4C467346h
0x140051a7a  lea     rcx, [rbp+4Fh+Destination]
0x140051a7e  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x140051a83  mov     eax, [rsi+18h]
0x140051a86  test    r12b, al
0x140051a89  jz      loc_140051B3C
0x140051a8f  xorps   xmm0, xmm0
0x140051a92  lea     rcx, [rbp+4Fh+var_90]
0x140051a96  mov     rdx, r15
0x140051a99  movups  xmmword ptr [rbp+4Fh+Source.Length], xmm0
0x140051a9d  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140051aa2  mov     rax, [rsi+30h]
0x140051aa6  mov     rbx, [rax+8]
0x140051aaa  mov     r14, [rax]
0x140051aad  test    rbx, rbx
0x140051ab0  jz      short loc_140051AB6
0x140051ab2  lock inc dword ptr [rbx+8]
0x140051ab6  mov     rcx, qword ptr [rbp+4Fh+var_90.Data1]; this
0x140051aba  test    rcx, rcx
0x140051abd  jz      short loc_140051AC4
0x140051abf  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140051ac4  mov     rax, [r14+10h]
0x140051ac8  lea     rcx, [rbp+4Fh+Source]; this
0x140051acc  xor     edx, edx; struct _UNICODE_STRING *
0x140051ace  movups  xmm0, xmmword ptr [rax+28h]
0x140051ad2  movdqu  xmmword ptr [rbp+4Fh+Source.Length], xmm0
0x140051ad7  call    ?StripTrailingBackslashFromPath@Utils@UnionFs@@YAXAEAU_UNICODE_STRING@@PEBG@Z; UnionFs::Utils::StripTrailingBackslashFromPath(_UNICODE_STRING &,ushort const *)
0x140051adc  test    rbx, rbx
0x140051adf  jz      short loc_140051AE9
0x140051ae1  mov     rcx, rbx; this
0x140051ae4  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140051ae9  lea     rdx, [rbp+4Fh+Source]; Source
0x140051aed  lea     rcx, [rbp+4Fh+Destination]; Destination
0x140051af1  call    cs:__imp_RtlAppendUnicodeStringToString
0x140051af8  nop     dword ptr [rax+rax+00h]
0x140051afd  mov     ebx, eax
0x140051aff  test    eax, eax
0x140051b01  jns     loc_140051BA3
0x140051b07  lea     rax, aApiAppendingSc; "API: Appending scratch root path"
0x140051b0e  mov     r8, 75001704FEh; struct UnionFs::StackEventTracer *
0x140051b18  mov     [rsp+0E0h+var_C0], rax; char *
0x140051b1d  mov     ecx, ebx; this
0x140051b1f  lea     r9, aUnionfsUfspers_18; "UnionFs::UfsPersistenceManager::Generat"...
0x140051b26  mov     rdx, rdi; int
0x140051b29  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140051b2e  lea     rcx, [rbp+4Fh+Destination]; UnicodeString
0x140051b32  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140051b37  jmp     loc_140051DC9
0x140051b3c  lea     rdx, [rbp+4Fh+arg_8]; Source
0x140051b40  lea     rcx, [rbp+4Fh+Destination]; Destination
0x140051b44  call    cs:__imp_RtlAppendUnicodeToString
0x140051b4b  nop     dword ptr [rax+rax+00h]
0x140051b50  mov     ebx, eax
0x140051b52  test    eax, eax
0x140051b54  jns     short loc_140051B70
0x140051b56  mov     r8, 2F100170507h
0x140051b60  lea     rcx, aApiAppendingPa_0; "API: Appending path separator"
0x140051b67  mov     [rsp+0E0h+var_C0], rcx
0x140051b6c  mov     ecx, eax
0x140051b6e  jmp     short loc_140051B1F
0x140051b70  lea     rdx, aSystemVolumeIn; "System Volume Information"
0x140051b77  lea     rcx, [rbp+4Fh+Destination]; Destination
0x140051b7b  call    cs:__imp_RtlAppendUnicodeToString
0x140051b82  nop     dword ptr [rax+rax+00h]
0x140051b87  mov     ebx, eax
0x140051b89  test    eax, eax
0x140051b8b  jns     short loc_140051BA3
0x140051b8d  lea     rax, aApiAppendingSv; "API: Appending SVI"
0x140051b94  mov     r8, 2F20017050Ch
0x140051b9e  jmp     loc_140051B18
0x140051ba3  movzx   ecx, [rbp+4Fh+Destination.Length]
0x140051ba7  mov     r8d, 5Ch ; '\'
0x140051bad  mov     rdx, [rbp+4Fh+Destination.Buffer]
0x140051bb1  mov     eax, ecx
0x140051bb3  shr     rax, 1
0x140051bb6  cmp     [rdx+rax*2-2], r8w
0x140051bbc  jz      short loc_140051BEF
0x140051bbe  lea     rdx, [rbp+4Fh+arg_8]; Source
0x140051bc2  lea     rcx, [rbp+4Fh+Destination]; Destination
0x140051bc6  call    cs:__imp_RtlAppendUnicodeToString
0x140051bcd  nop     dword ptr [rax+rax+00h]
0x140051bd2  mov     ebx, eax
0x140051bd4  test    eax, eax
0x140051bd6  jns     short loc_140051BE7
0x140051bd8  mov     r8, 2F400170518h
0x140051be2  jmp     loc_140051B60
0x140051be7  mov     rdx, [rbp+4Fh+Destination.Buffer]
0x140051beb  movzx   ecx, [rbp+4Fh+Destination.Length]
0x140051bef  mov     eax, [rsi+18h]
0x140051bf2  test    r12b, al
0x140051bf5  jz      short loc_140051C2B
0x140051bf7  lea     rdx, [rbp+4Fh+var_58]; Source
0x140051bfb  lea     rcx, [rbp+4Fh+Destination]; Destination
0x140051bff  call    cs:__imp_RtlAppendUnicodeStringToString
0x140051c06  nop     dword ptr [rax+rax+00h]
0x140051c0b  mov     ebx, eax
0x140051c0d  test    eax, eax
0x140051c0f  jns     loc_140051CB7
0x140051c15  lea     rax, aApiAppendingSe; "API: Appending self-contained name"
0x140051c1c  mov     r8, 26900170522h
0x140051c26  jmp     loc_140051B18
0x140051c2b  movups  xmm0, xmmword ptr [rsi+8]
0x140051c2f  xor     eax, eax
0x140051c31  mov     dword ptr [rbp+4Fh+var_90.Data2], 0
0x140051c38  mov     word ptr [rbp+4Fh+var_90.Data1], ax
0x140051c3c  movzx   eax, [rbp+4Fh+Destination.MaximumLength]
0x140051c40  sub     ax, cx
0x140051c43  mov     word ptr [rbp+4Fh+var_90.Data1+2], ax
0x140051c47  movzx   eax, cx
0x140051c4a  lea     rcx, [rbp+4Fh+var_68]; this
0x140051c4e  add     rax, rdx
0x140051c51  lea     rdx, [rbp+4Fh+var_90]; struct _GUID *
0x140051c55  mov     qword ptr [rbp+4Fh+var_90.Data4], rax
0x140051c59  movdqu  [rbp+4Fh+var_68], xmm0
0x140051c5e  call    ?StringFromGUIDEx@Rtl@UnionFs@@YAJAEBU_GUID@@AEAU_UNICODE_STRING@@@Z; UnionFs::Rtl::StringFromGUIDEx(_GUID const &,_UNICODE_STRING &)
0x140051c63  mov     ebx, eax
0x140051c65  test    eax, eax
0x140051c67  jns     short loc_140051C7F
0x140051c69  lea     rax, aApiAppendingGu; "API: Appending GUID string"
0x140051c70  mov     r8, 2E50017052Fh
0x140051c7a  jmp     loc_140051B18
0x140051c7f  movzx   eax, word ptr [rbp+4Fh+var_90.Data1]
0x140051c83  lea     rdx, [rbp+4Fh+var_48]; Source
0x140051c87  add     [rbp+4Fh+Destination.Length], ax
0x140051c8b  lea     rcx, [rbp+4Fh+Destination]; Destination
0x140051c8f  call    cs:__imp_RtlAppendUnicodeStringToString
0x140051c96  nop     dword ptr [rax+rax+00h]
0x140051c9b  mov     ebx, eax
0x140051c9d  test    eax, eax
0x140051c9f  jns     short loc_140051CB7
0x140051ca1  lea     rax, aApiAppendingNa; "API: Appending name suffix"
0x140051ca8  mov     r8, 2E600170536h
0x140051cb2  jmp     loc_140051B18
0x140051cb7  cmp     [rbp+4Fh+arg_20], 0
0x140051cbb  lea     rcx, [rbp+4Fh+Destination]; Destination
0x140051cbf  jz      short loc_140051CF0
0x140051cc1  lea     rdx, stru_14007EE00; Source
0x140051cc8  call    cs:__imp_RtlAppendUnicodeStringToString
0x140051ccf  nop     dword ptr [rax+rax+00h]
0x140051cd4  mov     ebx, eax
0x140051cd6  test    eax, eax
0x140051cd8  jns     short loc_140051D1F
0x140051cda  lea     rax, aApiAppendingTe; "API: Appending temp extension"
0x140051ce1  mov     r8, 2E800170540h
0x140051ceb  jmp     loc_140051B18
0x140051cf0  lea     rdx, stru_14007EDE0; Source
0x140051cf7  call    cs:__imp_RtlAppendUnicodeStringToString
0x140051cfe  nop     dword ptr [rax+rax+00h]
0x140051d03  mov     ebx, eax
0x140051d05  test    eax, eax
0x140051d07  jns     short loc_140051D1F
0x140051d09  lea     rax, aApiAppendingNa_0; "API: Appending name extension"
0x140051d10  mov     r8, 2E900170548h
0x140051d1a  jmp     loc_140051B18
  ... truncated ...
```
