# UnionFs::UfsPersistenceManager::GeneratePersistentPayloadFileName(UnionFs::UfsUnionCtx const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &,bool)

- ea: `0x1400519c0`
- end: `0x140051f6c`
- name: `?GeneratePersistentPayloadFileName@UfsPersistenceManager@UnionFs@@IEBAJAEBVUfsUnionCtx@2@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@_N@Z`
- size: `1452`
- prototype: ``
- caller_count: `4`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x140050ef8`
- `0x1400517b0`
- `0x140051f74`
- `0x14005315c`

## callees

- `0x140001008`
- `0x14000f81c`
- `0x1400504f8`
- `0x1400519c0`
- `0x140056bd0`
- `0x140056c7c`
- `0x140075454`
- `0x1400786a8`
- `0x140078764`
- `0x140079d44`
- `0x140079f68`
- `0x14007a02c`
- `0x14007a0c0`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x140051cc4`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140051cfb`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140051d46`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140051cc4`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140051cfb`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140051d46`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051c71`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051d7f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051e0f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051e48`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051e77`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051c71`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051d7f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051e0f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051e48`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051e77`
- `FLTMGR!FltCreateSystemVolumeInformationFolder` at `0x140051ab9`
- `FLTMGR!FltCreateSystemVolumeInformationFolder` at `0x140051ab9`

## string_xrefs

- `0x140051ce0`: `API: Appending path separator`
- `0x140051c87`: `API: Appending scratch root path`
- `0x140051e5a`: `API: Appending temp extension`
- `0x140051e89`: `API: Appending name extension`

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
      (unsigned int)qword_140098238,
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
    SystemVolumeInformationFolder = RtlAppendUnicodeStringToString(&Destination, &stru_14007EE08);
    if ( SystemVolumeInformationFolder < 0 )
    {
      v31 = "API: Appending temp extension";
      v32 = 0x2E800170540LL;
      goto LABEL_41;
    }
  }
  else
  {
    SystemVolumeInformationFolder = RtlAppendUnicodeStringToString(&Destination, &stru_14007EDE8);
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
0x1400519c0  mov     [rsp-8+arg_0], rbx
0x1400519c5  mov     [rsp-8+arg_10], r8
0x1400519ca  push    rbp
0x1400519cb  push    rsi
0x1400519cc  push    rdi
0x1400519cd  push    r12
0x1400519cf  push    r13
0x1400519d1  push    r14
0x1400519d3  push    r15
0x1400519d5  lea     rbp, [rsp-1Fh]
0x1400519da  sub     rsp, 0B0h
0x1400519e1  mov     eax, cs:dword_14009E178
0x1400519e7  mov     r12, rcx
0x1400519ea  lea     rcx, aUnionfsUfspers_18; "UnionFs::UfsPersistenceManager::Generat"...
0x1400519f1  mov     rdi, r9
0x1400519f4  mov     r13, r8
0x1400519f7  mov     rsi, rdx
0x1400519fa  cmp     eax, 5
0x1400519fd  jbe     short loc_140051A74
0x1400519ff  mov     rdx, cs:qword_14009E190
0x140051a06  mov     r8d, 8000h
0x140051a0c  mov     rax, cs:qword_14009E188
0x140051a13  test    r8, rax
0x140051a16  jz      short loc_140051A74
0x140051a18  mov     rax, rdx
0x140051a1b  and     rax, r8
0x140051a1e  cmp     rax, rdx
0x140051a21  jnz     short loc_140051A74
0x140051a23  lea     rax, aOnecoreBaseFsU_1; "onecore\\base\\fs\\unionfs\\sys\\persis"...
0x140051a2a  mov     [rbp+4Fh+var_80], 4B9h
0x140051a31  mov     qword ptr [rbp+4Fh+var_68], rax
0x140051a35  lea     rdx, qword_140098238
0x140051a3c  lea     rax, aEnter; "ENTER"
0x140051a43  mov     qword ptr [rbp+4Fh+Source.Length], rcx
0x140051a47  mov     qword ptr [rbp+4Fh+var_90.Data1], rax
0x140051a4b  lea     rax, [rbp+4Fh+var_80]
0x140051a4f  mov     [rsp+0E0h+var_A8], rax
0x140051a54  lea     rax, [rbp+4Fh+var_68]
0x140051a58  mov     [rsp+0E0h+var_B0], rax
0x140051a5d  lea     rax, [rbp+4Fh+Source]
0x140051a61  mov     [rsp+0E0h+var_B8], rax; char *
0x140051a66  lea     rax, [rbp+4Fh+var_90]
0x140051a6a  mov     [rsp+0E0h+var_C0], rax
0x140051a6f  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140051a74  mov     eax, [rsi+18h]
0x140051a77  lea     r15, [rsi+48h]
0x140051a7b  test    al, 20h
0x140051a7d  jnz     loc_140051B04
0x140051a83  mov     rdx, r15
0x140051a86  lea     rcx, [rbp+4Fh+var_90]
0x140051a8a  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140051a8f  mov     rax, [rsi+30h]
0x140051a93  mov     r14, [rax+8]
0x140051a97  mov     rbx, [rax]
0x140051a9a  test    r14, r14
0x140051a9d  jz      short loc_140051AA4
0x140051a9f  lock inc dword ptr [r14+8]
0x140051aa4  mov     rcx, qword ptr [rbp+4Fh+var_90.Data1]; this
0x140051aa8  test    rcx, rcx
0x140051aab  jz      short loc_140051AB2
0x140051aad  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140051ab2  mov     rcx, [rbx+8]
0x140051ab6  mov     rcx, [rcx]; Instance
0x140051ab9  call    cs:__imp_FltCreateSystemVolumeInformationFolder
0x140051ac0  nop     dword ptr [rax+rax+00h]
0x140051ac5  mov     ebx, eax
0x140051ac7  test    r14, r14
0x140051aca  jz      short loc_140051AD4
0x140051acc  mov     rcx, r14; this
0x140051acf  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140051ad4  test    ebx, ebx
0x140051ad6  jns     short loc_140051B04
0x140051ad8  lea     rax, aApiVerifyingSv; "API: Verifying SVI folder"
0x140051adf  mov     r8, 336001704C7h; struct UnionFs::StackEventTracer *
0x140051ae9  lea     r9, aUnionfsUfspers_18; "UnionFs::UfsPersistenceManager::Generat"...
0x140051af0  mov     [rsp+0E0h+var_C0], rax; char *
0x140051af5  mov     rdx, rdi; int
0x140051af8  mov     ecx, ebx; this
0x140051afa  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140051aff  jmp     loc_140051F49
0x140051b04  mov     rdx, r15
0x140051b07  mov     dword ptr [rbp+4Fh+arg_8], 5Ch ; '\'
0x140051b0e  lea     rcx, [rbp+4Fh+var_90]
0x140051b12  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140051b17  mov     rax, [rsi+30h]
0x140051b1b  mov     r14, [rax+8]
0x140051b1f  mov     rbx, [rax]
0x140051b22  test    r14, r14
0x140051b25  jz      short loc_140051B2C
0x140051b27  lock inc dword ptr [r14+8]
0x140051b2c  mov     rcx, qword ptr [rbp+4Fh+var_90.Data1]; this
0x140051b30  test    rcx, rcx
0x140051b33  jz      short loc_140051B3A
0x140051b35  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140051b3a  mov     rax, [rbx+10h]
0x140051b3e  movzx   ebx, word ptr [rax+18h]
0x140051b42  test    r14, r14
0x140051b45  jz      short loc_140051B4F
0x140051b47  mov     rcx, r14; this
0x140051b4a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140051b4f  mov     eax, [rsi+18h]
0x140051b52  add     bx, 2
0x140051b56  test    al, 20h
0x140051b58  jz      loc_140051BE3
0x140051b5e  mov     rdx, r15
0x140051b61  lea     rcx, [rbp+4Fh+var_90]
0x140051b65  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140051b6a  mov     rax, [rsi+30h]
0x140051b6e  mov     r14, [rax+8]
0x140051b72  mov     r13, [rax]
0x140051b75  test    r14, r14
0x140051b78  jz      short loc_140051B7F
0x140051b7a  lock inc dword ptr [r14+8]
0x140051b7f  mov     rcx, qword ptr [rbp+4Fh+var_90.Data1]; this
0x140051b83  test    rcx, rcx
0x140051b86  jz      short loc_140051B8D
0x140051b88  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140051b8d  mov     rax, [r13+10h]
0x140051b91  add     bx, [rax+28h]
0x140051b95  test    r14, r14
0x140051b98  jz      short loc_140051BA2
0x140051b9a  mov     rcx, r14; this
0x140051b9d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140051ba2  mov     r13, [rbp+4Fh+arg_10]
0x140051ba6  mov     rax, [r12]
0x140051baa  lea     rdx, [rbp+4Fh+var_58]
0x140051bae  mov     rcx, r12
0x140051bb1  add     bx, 2
0x140051bb5  mov     rax, [rax+50h]
0x140051bb9  call    _guard_dispatch_icall
0x140051bbe  mov     rax, [r12]
0x140051bc2  lea     rdx, [rbp+4Fh+var_48]
0x140051bc6  mov     rcx, r12
0x140051bc9  mov     rax, [rax+48h]
0x140051bcd  call    _guard_dispatch_icall
0x140051bd2  mov     eax, [rsi+18h]
0x140051bd5  mov     r12b, 20h ; ' '
0x140051bd8  test    r12b, al
0x140051bdb  jz      short loc_140051BE9
0x140051bdd  add     bx, [rbp+4Fh+var_58.Length]
0x140051be1  jmp     short loc_140051BF1
0x140051be3  add     bx, 32h ; '2'
0x140051be7  jmp     short loc_140051BA6
0x140051be9  add     bx, 4Eh ; 'N'
0x140051bed  add     bx, [rbp+4Fh+var_48.Length]
0x140051bf1  lea     edx, [rbx+8]
0x140051bf4  mov     r8d, 4C467346h
0x140051bfa  lea     rcx, [rbp+4Fh+Destination]
0x140051bfe  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x140051c03  mov     eax, [rsi+18h]
0x140051c06  test    r12b, al
0x140051c09  jz      loc_140051CBC
0x140051c0f  xorps   xmm0, xmm0
0x140051c12  lea     rcx, [rbp+4Fh+var_90]
0x140051c16  mov     rdx, r15
0x140051c19  movups  xmmword ptr [rbp+4Fh+Source.Length], xmm0
0x140051c1d  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140051c22  mov     rax, [rsi+30h]
0x140051c26  mov     rbx, [rax+8]
0x140051c2a  mov     r14, [rax]
0x140051c2d  test    rbx, rbx
0x140051c30  jz      short loc_140051C36
0x140051c32  lock inc dword ptr [rbx+8]
0x140051c36  mov     rcx, qword ptr [rbp+4Fh+var_90.Data1]; this
0x140051c3a  test    rcx, rcx
0x140051c3d  jz      short loc_140051C44
0x140051c3f  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140051c44  mov     rax, [r14+10h]
0x140051c48  lea     rcx, [rbp+4Fh+Source]; this
0x140051c4c  xor     edx, edx; struct _UNICODE_STRING *
0x140051c4e  movups  xmm0, xmmword ptr [rax+28h]
0x140051c52  movdqu  xmmword ptr [rbp+4Fh+Source.Length], xmm0
0x140051c57  call    ?StripTrailingBackslashFromPath@Utils@UnionFs@@YAXAEAU_UNICODE_STRING@@PEBG@Z; UnionFs::Utils::StripTrailingBackslashFromPath(_UNICODE_STRING &,ushort const *)
0x140051c5c  test    rbx, rbx
0x140051c5f  jz      short loc_140051C69
0x140051c61  mov     rcx, rbx; this
0x140051c64  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140051c69  lea     rdx, [rbp+4Fh+Source]; Source
0x140051c6d  lea     rcx, [rbp+4Fh+Destination]; Destination
0x140051c71  call    cs:__imp_RtlAppendUnicodeStringToString
0x140051c78  nop     dword ptr [rax+rax+00h]
0x140051c7d  mov     ebx, eax
0x140051c7f  test    eax, eax
0x140051c81  jns     loc_140051D23
0x140051c87  lea     rax, aApiAppendingSc; "API: Appending scratch root path"
0x140051c8e  mov     r8, 75001704FEh; struct UnionFs::StackEventTracer *
0x140051c98  mov     [rsp+0E0h+var_C0], rax; char *
0x140051c9d  mov     ecx, ebx; this
0x140051c9f  lea     r9, aUnionfsUfspers_18; "UnionFs::UfsPersistenceManager::Generat"...
0x140051ca6  mov     rdx, rdi; int
0x140051ca9  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140051cae  lea     rcx, [rbp+4Fh+Destination]; UnicodeString
0x140051cb2  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140051cb7  jmp     loc_140051F49
0x140051cbc  lea     rdx, [rbp+4Fh+arg_8]; Source
0x140051cc0  lea     rcx, [rbp+4Fh+Destination]; Destination
0x140051cc4  call    cs:__imp_RtlAppendUnicodeToString
0x140051ccb  nop     dword ptr [rax+rax+00h]
0x140051cd0  mov     ebx, eax
0x140051cd2  test    eax, eax
0x140051cd4  jns     short loc_140051CF0
0x140051cd6  mov     r8, 2F100170507h
0x140051ce0  lea     rcx, aApiAppendingPa_0; "API: Appending path separator"
0x140051ce7  mov     [rsp+0E0h+var_C0], rcx
0x140051cec  mov     ecx, eax
0x140051cee  jmp     short loc_140051C9F
0x140051cf0  lea     rdx, aSystemVolumeIn; "System Volume Information"
0x140051cf7  lea     rcx, [rbp+4Fh+Destination]; Destination
0x140051cfb  call    cs:__imp_RtlAppendUnicodeToString
0x140051d02  nop     dword ptr [rax+rax+00h]
0x140051d07  mov     ebx, eax
0x140051d09  test    eax, eax
0x140051d0b  jns     short loc_140051D23
0x140051d0d  lea     rax, aApiAppendingSv; "API: Appending SVI"
0x140051d14  mov     r8, 2F20017050Ch
0x140051d1e  jmp     loc_140051C98
0x140051d23  movzx   ecx, [rbp+4Fh+Destination.Length]
0x140051d27  mov     r8d, 5Ch ; '\'
0x140051d2d  mov     rdx, [rbp+4Fh+Destination.Buffer]
0x140051d31  mov     eax, ecx
0x140051d33  shr     rax, 1
0x140051d36  cmp     [rdx+rax*2-2], r8w
0x140051d3c  jz      short loc_140051D6F
0x140051d3e  lea     rdx, [rbp+4Fh+arg_8]; Source
0x140051d42  lea     rcx, [rbp+4Fh+Destination]; Destination
0x140051d46  call    cs:__imp_RtlAppendUnicodeToString
0x140051d4d  nop     dword ptr [rax+rax+00h]
0x140051d52  mov     ebx, eax
0x140051d54  test    eax, eax
0x140051d56  jns     short loc_140051D67
0x140051d58  mov     r8, 2F400170518h
0x140051d62  jmp     loc_140051CE0
0x140051d67  mov     rdx, [rbp+4Fh+Destination.Buffer]
0x140051d6b  movzx   ecx, [rbp+4Fh+Destination.Length]
0x140051d6f  mov     eax, [rsi+18h]
0x140051d72  test    r12b, al
0x140051d75  jz      short loc_140051DAB
0x140051d77  lea     rdx, [rbp+4Fh+var_58]; Source
0x140051d7b  lea     rcx, [rbp+4Fh+Destination]; Destination
0x140051d7f  call    cs:__imp_RtlAppendUnicodeStringToString
0x140051d86  nop     dword ptr [rax+rax+00h]
0x140051d8b  mov     ebx, eax
0x140051d8d  test    eax, eax
0x140051d8f  jns     loc_140051E37
0x140051d95  lea     rax, aApiAppendingSe; "API: Appending self-contained name"
0x140051d9c  mov     r8, 26900170522h
0x140051da6  jmp     loc_140051C98
0x140051dab  movups  xmm0, xmmword ptr [rsi+8]
0x140051daf  xor     eax, eax
0x140051db1  mov     dword ptr [rbp+4Fh+var_90.Data2], 0
0x140051db8  mov     word ptr [rbp+4Fh+var_90.Data1], ax
0x140051dbc  movzx   eax, [rbp+4Fh+Destination.MaximumLength]
0x140051dc0  sub     ax, cx
0x140051dc3  mov     word ptr [rbp+4Fh+var_90.Data1+2], ax
0x140051dc7  movzx   eax, cx
0x140051dca  lea     rcx, [rbp+4Fh+var_68]; this
0x140051dce  add     rax, rdx
0x140051dd1  lea     rdx, [rbp+4Fh+var_90]; struct _GUID *
0x140051dd5  mov     qword ptr [rbp+4Fh+var_90.Data4], rax
0x140051dd9  movdqu  [rbp+4Fh+var_68], xmm0
0x140051dde  call    ?StringFromGUIDEx@Rtl@UnionFs@@YAJAEBU_GUID@@AEAU_UNICODE_STRING@@@Z; UnionFs::Rtl::StringFromGUIDEx(_GUID const &,_UNICODE_STRING &)
0x140051de3  mov     ebx, eax
0x140051de5  test    eax, eax
0x140051de7  jns     short loc_140051DFF
0x140051de9  lea     rax, aApiAppendingGu; "API: Appending GUID string"
0x140051df0  mov     r8, 2E50017052Fh
0x140051dfa  jmp     loc_140051C98
0x140051dff  movzx   eax, word ptr [rbp+4Fh+var_90.Data1]
0x140051e03  lea     rdx, [rbp+4Fh+var_48]; Source
0x140051e07  add     [rbp+4Fh+Destination.Length], ax
0x140051e0b  lea     rcx, [rbp+4Fh+Destination]; Destination
0x140051e0f  call    cs:__imp_RtlAppendUnicodeStringToString
0x140051e16  nop     dword ptr [rax+rax+00h]
0x140051e1b  mov     ebx, eax
0x140051e1d  test    eax, eax
0x140051e1f  jns     short loc_140051E37
0x140051e21  lea     rax, aApiAppendingNa; "API: Appending name suffix"
0x140051e28  mov     r8, 2E600170536h
0x140051e32  jmp     loc_140051C98
0x140051e37  cmp     [rbp+4Fh+arg_20], 0
0x140051e3b  lea     rcx, [rbp+4Fh+Destination]; Destination
0x140051e3f  jz      short loc_140051E70
0x140051e41  lea     rdx, stru_14007EE08; Source
0x140051e48  call    cs:__imp_RtlAppendUnicodeStringToString
0x140051e4f  nop     dword ptr [rax+rax+00h]
0x140051e54  mov     ebx, eax
0x140051e56  test    eax, eax
0x140051e58  jns     short loc_140051E9F
0x140051e5a  lea     rax, aApiAppendingTe; "API: Appending temp extension"
0x140051e61  mov     r8, 2E800170540h
0x140051e6b  jmp     loc_140051C98
0x140051e70  lea     rdx, stru_14007EDE8; Source
0x140051e77  call    cs:__imp_RtlAppendUnicodeStringToString
0x140051e7e  nop     dword ptr [rax+rax+00h]
0x140051e83  mov     ebx, eax
0x140051e85  test    eax, eax
0x140051e87  jns     short loc_140051E9F
0x140051e89  lea     rax, aApiAppendingNa_0; "API: Appending name extension"
0x140051e90  mov     r8, 2E900170548h
0x140051e9a  jmp     loc_140051C98
  ... truncated ...
```
