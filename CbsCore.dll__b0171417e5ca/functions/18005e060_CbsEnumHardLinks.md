# CbsEnumHardLinks

- ea: `0x18005e060`
- end: `0x18005e645`
- name: `CbsEnumHardLinks`
- size: `1509`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b53dc`

## callees

- `0x180010cc0`
- `0x180013250`
- `0x18004f454`
- `0x180055b4c`
- `0x18005aa38`
- `0x18005caf4`
- `0x18005e060`
- `0x180060a20`
- `0x180095924`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800c731c`
- `0x1800d0588`
- `0x1800eb920`
- `0x1800fe364`
- `0x1801026fc`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x18005e324`
- `ntdll!NtQueryInformationFile` at `0x18005e324`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18005e19e`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18005e19e`
- `ntdll!RtlFreeHeap` at `0x18005e390`
- `ntdll!RtlFreeHeap` at `0x18005e46e`
- `ntdll!RtlFreeHeap` at `0x18005e60e`
- `ntdll!RtlFreeHeap` at `0x18005e390`
- `ntdll!RtlFreeHeap` at `0x18005e46e`
- `ntdll!RtlFreeHeap` at `0x18005e60e`
- `ntdll!NtCreateFile` at `0x18005e275`
- `ntdll!NtCreateFile` at `0x18005e275`

## string_xrefs

- `0x18005e2a7`: `Failed opening {}`
- `0x18005e40f`: `Failed querying hard link information for {}`
- `0x18005e158`: `No hard links specified`
- `0x18005e1c7`: `Failed converting pathname`

## pseudocode

```c
__int64 __fastcall CbsEnumHardLinks(const WCHAR *a1, __int64 a2)
{
  int Parent; // ebx
  __int64 v4; // rdx
  __int64 v5; // rdx
  void **v6; // rax
  NTSTATUS v7; // eax
  NTSTATUS v8; // ebx
  int v9; // edx
  __int64 v10; // rdx
  signed int v11; // ebx
  __int64 i; // rdx
  signed int *v13; // rsi
  unsigned __int64 v14; // r9
  int v16; // edx
  unsigned int *v17; // rdi
  int v18; // r14d
  struct _FILE_NAME_INFORMATION **InitPointer; // rax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  __int64 v24; // rbx
  int AllocationSize; // [rsp+20h] [rbp-A9h]
  int v26[4]; // [rsp+60h] [rbp-69h] BYREF
  __int64 v27; // [rsp+70h] [rbp-59h] BYREF
  PVOID FileInformation; // [rsp+78h] [rbp-51h] BYREF
  const WCHAR *v29; // [rsp+80h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-41h] BYREF
  int v31; // [rsp+B8h] [rbp-11h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+C0h] [rbp-9h] BYREF
  _WORD *v33; // [rsp+D0h] [rbp+7h] BYREF
  HANDLE FileHandle; // [rsp+D8h] [rbp+Fh] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v29 = a1;
  FileHandle = (HANDLE)-1LL;
  FileInformation = 0;
  v33 = 0;
  v27 = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  NtPathName = 0;
  if ( !a1 )
  {
    Parent = -2147024809;
    v31 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No filename specified");
      *(_QWORD *)v26 = &v31;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v26);
    }
    v4 = 290;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile2.cpp",
      (const char *)0x80070057LL,
      AllocationSize);
LABEL_28:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v27);
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v33);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileHandle);
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&FileInformation);
    return (unsigned int)Parent;
  }
  if ( !a2 )
  {
    Parent = -2147024809;
    v31 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No hard links specified");
      *(_QWORD *)v26 = &v31;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v26);
    }
    v4 = 291;
    goto LABEL_5;
  }
  if ( !RtlDosPathNameToNtPathName_U(a1, &NtPathName, 0, 0) )
  {
    Parent = -2147024809;
    v31 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed converting pathname");
      *(_QWORD *)v26 = &v31;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v26);
    }
    v5 = 302;
LABEL_24:
    v14 = (unsigned int)Parent;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile2.cpp",
      (const char *)v14,
      AllocationSize);
    goto LABEL_26;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &NtPathName;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.Attributes = 64;
  v6 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&FileHandle);
  v7 = NtCreateFile(v6, 0x100080u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x200020u, 0, 0);
  v8 = v7;
  if ( v7 < 0 )
  {
    v31 = v7;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed opening {}",
        (__int64)&v29);
      *(_QWORD *)v26 = &v31;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v9,
        3,
        (unsigned int)": {}",
        (__int64)v26);
    }
    v10 = 319;
LABEL_18:
    Parent = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v10,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsfile2.cpp",
               (const char *)(unsigned int)v8,
               AllocationSize);
LABEL_26:
    if ( NtPathName.Length )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
    goto LABEL_28;
  }
  v11 = 96;
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&FileInformation);
  for ( i = 96; ; i = v11 )
  {
    if ( !Windows::AutoNewWithUnsizedArrayPtr<_BACKING_REGION_OUTPUT>::AllocateWithTotalSize(&FileInformation, i) )
    {
      Parent = -2147024882;
      v5 = 324;
      goto LABEL_24;
    }
    v13 = (signed int *)FileInformation;
    v8 = NtQueryInformationFile(FileHandle, &IoStatusBlock, FileInformation, v11, FileHardLinkInformation);
    if ( v8 != -2147483643 )
      break;
    v11 = *v13;
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&FileInformation);
  }
  if ( v8 < 0 )
  {
    v31 = v8;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed querying hard link information for {}",
        (__int64)&v29);
      *(_QWORD *)v26 = &v31;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v16,
        3,
        (unsigned int)": {}",
        (__int64)v26);
    }
    v10 = 330;
    goto LABEL_18;
  }
  if ( !IoStatusBlock.Information )
  {
    if ( NtPathName.Length )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
    Parent = -2147024894;
    goto LABEL_28;
  }
  v17 = (unsigned int *)(v13 + 2);
  v18 = 0;
  if ( v13[1] )
  {
    while ( 1 )
    {
      *(_OWORD *)v26 = 0;
      InitPointer = (struct _FILE_NAME_INFORMATION **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v33);
      Parent = FindParent(FileHandle, *((_QWORD *)v17 + 1), InitPointer);
      if ( Parent < 0 )
        break;
      *(_QWORD *)&v26[2] = v33 + 2;
      HIWORD(v26[0]) = *v33;
      LOWORD(v26[0]) = HIWORD(v26[0]);
      v20 = SczAllocConcatUnicodeString(&v27, v26);
      Parent = v20;
      if ( v20 < 0 )
      {
        v14 = (unsigned int)v20;
        v5 = 360;
        goto LABEL_25;
      }
      v21 = SczEnsureBackslashTerminated(&v27);
      Parent = v21;
      if ( v21 < 0 )
      {
        v14 = (unsigned int)v21;
        v5 = 361;
        goto LABEL_25;
      }
      *(_QWORD *)&v26[2] = v17 + 5;
      HIWORD(v26[0]) = 2 * *((_WORD *)v17 + 8);
      LOWORD(v26[0]) = HIWORD(v26[0]);
      v22 = SczAllocConcatUnicodeString(&v27, v26);
      Parent = v22;
      if ( v22 < 0 )
      {
        v14 = (unsigned int)v22;
        v5 = 367;
        goto LABEL_25;
      }
      *(_QWORD *)v26 = v27;
      v23 = CCbsArrayBase<wchar_t *,CCbsStringArray>::Add(a2, v26);
      Parent = v23;
      if ( v23 < 0 )
      {
        v14 = (unsigned int)v23;
        v5 = 368;
        goto LABEL_25;
      }
      v24 = *v17;
      v27 = 0;
      Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v33);
      if ( ++v18 >= (unsigned int)v13[1] )
        goto LABEL_52;
      v17 = (unsigned int *)((char *)v17 + v24);
    }
    v31 = Parent;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting parent name");
      *(_QWORD *)v26 = &v31;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v26);
    }
    v5 = 353;
    goto LABEL_24;
  }
LABEL_52:
  if ( NtPathName.Length )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v27);
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v33);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileHandle);
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&FileInformation);
  return 0;
}

```

## disassembly

```asm
0x18005e060  mov     [rsp-8+arg_10], rbx
0x18005e065  mov     [rsp-8+arg_18], rsi
0x18005e06a  push    rbp
0x18005e06b  push    rdi
0x18005e06c  push    r12
0x18005e06e  push    r14
0x18005e070  push    r15
0x18005e072  lea     rbp, [rsp-37h]
0x18005e077  sub     rsp, 100h
0x18005e07e  mov     rax, cs:__security_cookie
0x18005e085  xor     rax, rsp
0x18005e088  mov     [rbp+57h+var_30], rax
0x18005e08c  xorps   xmm0, xmm0
0x18005e08f  mov     [rbp+57h+var_A0], rcx
0x18005e093  xor     r12d, r12d
0x18005e096  mov     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x18005e09e  mov     [rbp+57h+FileInformation], r12
0x18005e0a2  mov     r15, rdx
0x18005e0a5  mov     [rbp+57h+var_50], r12
0x18005e0a9  mov     [rbp+57h+var_B0], r12
0x18005e0ad  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18005e0b1  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18005e0b5  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18005e0b9  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005e0bd  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x18005e0c1  test    rcx, rcx
0x18005e0c4  jnz     short loc_18005E136
0x18005e0c6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005e0cd  mov     ebx, 80070057h
0x18005e0d2  mov     [rbp+57h+var_68], ebx
0x18005e0d5  test    rcx, rcx
0x18005e0d8  jz      short loc_18005E119
0x18005e0da  lea     edi, [r12+3]
0x18005e0df  xor     edx, edx
0x18005e0e1  mov     r8d, edi
0x18005e0e4  lea     r9, aNoFilenameSpec; "No filename specified"
0x18005e0eb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005e0f0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005e0f7  lea     rax, [rbp+57h+var_68]
0x18005e0fb  mov     qword ptr [rbp+57h+var_C0], rax
0x18005e0ff  lea     r9, asc_1802EE7AC; ": {}"
0x18005e106  lea     rax, [rbp+57h+var_C0]
0x18005e10a  mov     r8d, edi
0x18005e10d  mov     dl, 1
0x18005e10f  mov     [rsp+120h+AllocationSize], rax; int
0x18005e114  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005e119  mov     edx, 122h; void *
0x18005e11e  mov     rcx, [rbp+5Fh]; this
0x18005e122  lea     r8, aOnecoreBaseCbs_48; "onecore\\base\\cbs\\util\\cbsfile2.cpp"
0x18005e129  mov     r9d, ebx; char *
0x18005e12c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e131  jmp     loc_18005E39C
0x18005e136  test    r15, r15
0x18005e139  jnz     short loc_18005E194
0x18005e13b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005e142  mov     ebx, 80070057h
0x18005e147  mov     [rbp+57h+var_68], ebx
0x18005e14a  test    rcx, rcx
0x18005e14d  jz      short loc_18005E18D
0x18005e14f  lea     edi, [r15+3]
0x18005e153  xor     edx, edx
0x18005e155  mov     r8d, edi
0x18005e158  lea     r9, aNoHardLinksSpe; "No hard links specified"
0x18005e15f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005e164  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005e16b  lea     rax, [rbp+57h+var_68]
0x18005e16f  mov     qword ptr [rbp+57h+var_C0], rax
0x18005e173  lea     r9, asc_1802EE7AC; ": {}"
0x18005e17a  lea     rax, [rbp+57h+var_C0]
0x18005e17e  mov     r8d, edi
0x18005e181  mov     dl, 1
0x18005e183  mov     [rsp+120h+AllocationSize], rax
0x18005e188  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005e18d  mov     edx, 123h
0x18005e192  jmp     short loc_18005E11E
0x18005e194  xor     r9d, r9d; DirectoryInfo
0x18005e197  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x18005e19b  xor     r8d, r8d; NtFileNamePart
0x18005e19e  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18005e1a5  nop     dword ptr [rax+rax+00h]
0x18005e1aa  test    al, al
0x18005e1ac  jnz     short loc_18005E20B
0x18005e1ae  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005e1b5  mov     ebx, 80070057h
0x18005e1ba  mov     [rbp+57h+var_68], ebx
0x18005e1bd  test    rcx, rcx
0x18005e1c0  jz      short loc_18005E201
0x18005e1c2  mov     edi, 3
0x18005e1c7  lea     r9, aFailedConverti_1; "Failed converting pathname"
0x18005e1ce  mov     r8d, edi
0x18005e1d1  xor     edx, edx
0x18005e1d3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005e1d8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005e1df  lea     rax, [rbp+57h+var_68]
0x18005e1e3  mov     qword ptr [rbp+57h+var_C0], rax
0x18005e1e7  lea     r9, asc_1802EE7AC; ": {}"
0x18005e1ee  lea     rax, [rbp+57h+var_C0]
0x18005e1f2  mov     r8d, edi
0x18005e1f5  mov     dl, 1
0x18005e1f7  mov     [rsp+120h+AllocationSize], rax
0x18005e1fc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005e201  mov     edx, 12Eh
0x18005e206  jmp     loc_18005E363
0x18005e20b  lea     rax, [rbp+57h+NtPathName]
0x18005e20f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18005e216  xorps   xmm0, xmm0
0x18005e219  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18005e21d  lea     rcx, [rbp+57h+FileHandle]
0x18005e221  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x18005e225  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005e22a  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18005e231  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18005e236  mov     [rsp+120h+EaLength], r12d; EaLength
0x18005e23b  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18005e23f  mov     [rsp+120h+EaBuffer], r12; EaBuffer
0x18005e244  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18005e248  mov     [rsp+120h+CreateOptions], 200020h; CreateOptions
0x18005e250  mov     rcx, rax; FileHandle
0x18005e253  mov     [rsp+120h+CreateDisposition], 1; CreateDisposition
0x18005e25b  mov     edx, 100080h; DesiredAccess
0x18005e260  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x18005e268  mov     [rsp+120h+FileAttributes], 80h; FileAttributes
0x18005e270  mov     [rsp+120h+AllocationSize], r12; AllocationSize
0x18005e275  call    cs:__imp_NtCreateFile
0x18005e27c  nop     dword ptr [rax+rax+00h]
0x18005e281  mov     ebx, eax
0x18005e283  test    eax, eax
0x18005e285  jns     short loc_18005E2F8
0x18005e287  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005e28e  mov     [rbp+57h+var_68], eax
0x18005e291  test    rcx, rcx
0x18005e294  jz      short loc_18005E2DC
0x18005e296  lea     rax, [rbp+57h+var_A0]
0x18005e29a  mov     edi, 3
0x18005e29f  mov     r8d, edi
0x18005e2a2  mov     [rsp+120h+AllocationSize], rax
0x18005e2a7  lea     r9, aFailedOpening; "Failed opening {}"
0x18005e2ae  xor     edx, edx
0x18005e2b0  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18005e2b5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005e2bc  lea     rax, [rbp+57h+var_68]
0x18005e2c0  mov     qword ptr [rbp+57h+var_C0], rax
0x18005e2c4  lea     r9, asc_1802EE7AC; ": {}"
0x18005e2cb  lea     rax, [rbp+57h+var_C0]
0x18005e2cf  mov     r8d, edi
0x18005e2d2  mov     [rsp+120h+AllocationSize], rax; int
0x18005e2d7  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18005e2dc  mov     edx, 13Fh; void *
0x18005e2e1  mov     rcx, [rbp+5Fh]; this
0x18005e2e5  lea     r8, aOnecoreBaseCbs_48; "onecore\\base\\cbs\\util\\cbsfile2.cpp"
0x18005e2ec  mov     r9d, ebx; char *
0x18005e2ef  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18005e2f4  mov     ebx, eax
0x18005e2f6  jmp     short loc_18005E376
0x18005e2f8  lea     rcx, [rbp+57h+FileInformation]
0x18005e2fc  mov     ebx, 60h ; '`'
0x18005e301  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x18005e306  mov     edx, ebx
0x18005e308  jmp     short loc_18005E34B
0x18005e30a  mov     rsi, [rbp+57h+FileInformation]
0x18005e30e  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18005e312  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18005e316  mov     r8, rsi; FileInformation
0x18005e319  mov     r9d, ebx; Length
0x18005e31c  mov     dword ptr [rsp+120h+AllocationSize], 2Eh ; '.'; int
0x18005e324  call    cs:__imp_NtQueryInformationFile
0x18005e32b  nop     dword ptr [rax+rax+00h]
0x18005e330  mov     ebx, eax
0x18005e332  cmp     eax, 80000005h
0x18005e337  jnz     loc_18005E3EB
0x18005e33d  mov     ebx, [rsi]
0x18005e33f  lea     rcx, [rbp+57h+FileInformation]
0x18005e343  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x18005e348  movsxd  rdx, ebx
0x18005e34b  lea     rcx, [rbp+57h+FileInformation]
0x18005e34f  call    ?AllocateWithTotalSize@?$AutoNewWithUnsizedArrayPtr@U_BACKING_REGION_OUTPUT@@@Windows@@QEAAPEAU_BACKING_REGION_OUTPUT@@_K@Z; Windows::AutoNewWithUnsizedArrayPtr<_BACKING_REGION_OUTPUT>::AllocateWithTotalSize(unsigned __int64)
0x18005e354  test    rax, rax
0x18005e357  jnz     short loc_18005E30A
0x18005e359  mov     ebx, 8007000Eh
0x18005e35e  mov     edx, 144h; void *
0x18005e363  mov     r9d, ebx; char *
0x18005e366  mov     rcx, [rbp+5Fh]; this
0x18005e36a  lea     r8, aOnecoreBaseCbs_48; "onecore\\base\\cbs\\util\\cbsfile2.cpp"
0x18005e371  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e376  cmp     [rbp+57h+NtPathName.Length], r12w
0x18005e37b  jz      short loc_18005E39C
0x18005e37d  mov     rcx, gs:60h
0x18005e386  xor     edx, edx; Flags
0x18005e388  mov     r8, [rbp+57h+NtPathName.Buffer]; P
0x18005e38c  mov     rcx, [rcx+30h]; HeapHandle
0x18005e390  call    cs:__imp_RtlFreeHeap
0x18005e397  nop     dword ptr [rax+rax+00h]
0x18005e39c  lea     rcx, [rbp+57h+var_B0]
0x18005e3a0  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18005e3a5  lea     rcx, [rbp+57h+var_50]
0x18005e3a9  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x18005e3ae  lea     rcx, [rbp+57h+FileHandle]
0x18005e3b2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005e3b7  lea     rcx, [rbp+57h+FileInformation]
0x18005e3bb  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x18005e3c0  mov     eax, ebx
0x18005e3c2  mov     rcx, [rbp+57h+var_30]
0x18005e3c6  xor     rcx, rsp; StackCookie
0x18005e3c9  call    __security_check_cookie
0x18005e3ce  lea     r11, [rsp+120h+var_20]
0x18005e3d6  mov     rbx, [r11+40h]
0x18005e3da  mov     rsi, [r11+48h]
0x18005e3de  mov     rsp, r11
0x18005e3e1  pop     r15
0x18005e3e3  pop     r14
0x18005e3e5  pop     r12
0x18005e3e7  pop     rdi
0x18005e3e8  pop     rbp
0x18005e3e9  retn
0x18005e3eb  test    ebx, ebx
0x18005e3ed  jns     short loc_18005E44E
0x18005e3ef  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005e3f6  mov     [rbp+57h+var_68], ebx
0x18005e3f9  test    rcx, rcx
0x18005e3fc  jz      short loc_18005E444
0x18005e3fe  lea     rax, [rbp+57h+var_A0]
0x18005e402  mov     edi, 3
0x18005e407  mov     r8d, edi
0x18005e40a  mov     [rsp+120h+AllocationSize], rax
0x18005e40f  lea     r9, aFailedQuerying_1; "Failed querying hard link information f"...
0x18005e416  xor     edx, edx
0x18005e418  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18005e41d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005e424  lea     rax, [rbp+57h+var_68]
0x18005e428  mov     qword ptr [rbp+57h+var_C0], rax
0x18005e42c  lea     r9, asc_1802EE7AC; ": {}"
0x18005e433  lea     rax, [rbp+57h+var_C0]
0x18005e437  mov     r8d, edi
0x18005e43a  mov     [rsp+120h+AllocationSize], rax
0x18005e43f  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18005e444  mov     edx, 14Ah
0x18005e449  jmp     loc_18005E2E1
0x18005e44e  cmp     [rbp+57h+IoStatusBlock.Information], r12
0x18005e452  jnz     short loc_18005E484
0x18005e454  cmp     [rbp+57h+NtPathName.Length], r12w
0x18005e459  jz      short loc_18005E47A
0x18005e45b  mov     rcx, gs:60h
0x18005e464  xor     edx, edx; Flags
0x18005e466  mov     r8, [rbp+57h+NtPathName.Buffer]; P
0x18005e46a  mov     rcx, [rcx+30h]; HeapHandle
0x18005e46e  call    cs:__imp_RtlFreeHeap
0x18005e475  nop     dword ptr [rax+rax+00h]
0x18005e47a  mov     ebx, 80070002h
0x18005e47f  jmp     loc_18005E39C
0x18005e484  lea     rdi, [rsi+8]
0x18005e488  mov     r14d, r12d
0x18005e48b  cmp     [rsi+4], r12d
0x18005e48f  jbe     loc_18005E5F4
0x18005e495  xorps   xmm0, xmm0
0x18005e498  lea     rcx, [rbp+57h+var_50]
0x18005e49c  movups  xmmword ptr [rbp+57h+var_C0], xmm0
0x18005e4a0  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18005e4a5  mov     rdx, [rdi+8]; __int64
0x18005e4a9  mov     r8, rax; struct _FILE_NAME_INFORMATION **
0x18005e4ac  mov     rcx, [rbp+57h+FileHandle]; void *
0x18005e4b0  call    ?FindParent@@YAJPEAX_JPEAPEAU_FILE_NAME_INFORMATION@@@Z; FindParent(void *,__int64,_FILE_NAME_INFORMATION * *)
0x18005e4b5  mov     ebx, eax
0x18005e4b7  test    eax, eax
0x18005e4b9  js      loc_18005E59C
0x18005e4bf  mov     rcx, [rbp+57h+var_50]
0x18005e4c3  lea     rdx, [rbp+57h+var_C0]
0x18005e4c7  lea     rax, [rcx+4]
0x18005e4cb  mov     qword ptr [rbp+57h+var_C0+8], rax
0x18005e4cf  movzx   eax, word ptr [rcx]
0x18005e4d2  lea     rcx, [rbp+57h+var_B0]
0x18005e4d6  mov     word ptr [rbp+57h+var_C0+2], ax
0x18005e4da  mov     word ptr [rbp+57h+var_C0], ax
0x18005e4de  call    SczAllocConcatUnicodeString
0x18005e4e3  mov     ebx, eax
0x18005e4e5  test    eax, eax
0x18005e4e7  js      loc_18005E58F
0x18005e4ed  lea     rcx, [rbp+57h+var_B0]
0x18005e4f1  call    SczEnsureBackslashTerminated
0x18005e4f6  mov     ebx, eax
0x18005e4f8  test    eax, eax
0x18005e4fa  js      loc_18005E582
0x18005e500  lea     rax, [rdi+14h]
0x18005e504  mov     qword ptr [rbp+57h+var_C0+8], rax
0x18005e508  lea     rdx, [rbp+57h+var_C0]
0x18005e50c  movzx   eax, word ptr [rdi+10h]
0x18005e510  lea     rcx, [rbp+57h+var_B0]
0x18005e514  add     ax, ax
0x18005e517  mov     word ptr [rbp+57h+var_C0+2], ax
0x18005e51b  mov     word ptr [rbp+57h+var_C0], ax
0x18005e51f  call    SczAllocConcatUnicodeString
0x18005e524  mov     ebx, eax
0x18005e526  test    eax, eax
0x18005e528  js      short loc_18005E575
0x18005e52a  mov     rax, [rbp+57h+var_B0]
0x18005e52e  lea     rdx, [rbp+57h+var_C0]
0x18005e532  mov     rcx, r15
0x18005e535  mov     qword ptr [rbp+57h+var_C0], rax
0x18005e539  call    ?Add@?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@QEAAJAEBQEA_W@Z; CCbsArrayBase<wchar_t *,CCbsStringArray>::Add(wchar_t * const &)
0x18005e53e  mov     ebx, eax
0x18005e540  test    eax, eax
  ... truncated ...
```
