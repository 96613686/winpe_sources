# ForEachUniqueDirectoryHandle(std::filesystem::path const &,winrt::delegate<void (std::filesystem::path const &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &)>)

- ea: `0x1800299f4`
- end: `0x180029fc8`
- name: `?ForEachUniqueDirectoryHandle@@YAJAEBVpath@filesystem@std@@U?$delegate@$$A6AXAEBVpath@filesystem@std@@AEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z@winrt@@@Z`
- size: `1492`
- prototype: `__int64 __fastcall(struct std::filesystem::path *, _QWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002bf50`

## callees

- `0x180002590`
- `0x180002f98`
- `0x18000ab14`
- `0x18000f29c`
- `0x180013890`
- `0x180024f28`
- `0x1800253a8`
- `0x1800285f0`
- `0x18002869c`
- `0x1800290a4`
- `0x1800299f4`
- `0x18002c7c0`
- `0x18002dbb4`
- `0x18002e12c`
- `0x18002e27c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029bb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029bb4`
- `ntdll!NtCreateFile` at `0x180029d6f`
- `ntdll!NtCreateFile` at `0x180029d6f`
- `ntdll!RtlInitUnicodeString` at `0x180029cdc`
- `ntdll!RtlInitUnicodeString` at `0x180029cdc`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180029b9c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180029b9c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180029bfa`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180029e88`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180029f59`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180029bfa`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180029e88`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180029f59`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180029f3e`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180029f3e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180029e00`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180029e00`

## string_xrefs

- `0x180029abf`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`
- `0x180029bdb`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`

## pseudocode

```c
__int64 __fastcall ForEachUniqueDirectoryHandle(struct std::filesystem::path *a1, _QWORD *a2)
{
  unsigned int *any_status; // rax
  __int64 v5; // rcx
  __int64 v6; // rdx
  int DirHandle; // eax
  unsigned int v9; // r14d
  volatile signed __int32 *v10; // rbx
  __int64 v11; // r8
  const WCHAR *v12; // rcx
  char *FirstFileW; // rbx
  signed int LastError; // eax
  __int64 v15; // r8
  __int64 v16; // rax
  const WCHAR *v17; // rdx
  void *v18; // rax
  void **v19; // rax
  __int64 v20; // r8
  const WCHAR *v21; // rcx
  DWORD FileAttributesW; // eax
  PCWSTR *v23; // rcx
  volatile signed __int32 *v24; // r14
  volatile signed __int32 *v25; // rbx
  volatile signed __int32 *v26; // r14
  volatile signed __int32 *v27; // rbx
  int AllocationSize; // [rsp+20h] [rbp-E0h]
  __int128 v29; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v30; // [rsp+70h] [rbp-90h] BYREF
  char *v31; // [rsp+80h] [rbp-80h]
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v34[16]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD *v35; // [rsp+D8h] [rbp-28h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp-20h] BYREF
  LPCWSTR Src[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v38; // [rsp+100h] [rbp+0h]
  unsigned __int64 v39; // [rsp+108h] [rbp+8h]
  PCWSTR SourceString[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v41; // [rsp+120h] [rbp+20h]
  unsigned __int64 v42; // [rsp+128h] [rbp+28h]
  LPCWSTR lpFileName[4]; // [rsp+130h] [rbp+30h] BYREF
  _OWORD v44[2]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v45[32]; // [rsp+170h] [rbp+70h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+190h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+418h] [rbp+318h]

  v35 = a2;
  any_status = (unsigned int *)std::filesystem::_Get_any_status(v34, a1);
  v5 = *any_status;
  v6 = any_status[2];
  if ( (_DWORD)v6 )
  {
    if ( (((_DWORD)v5 - 1) & 0xFFFFFFF7) != 0 )
      std::filesystem::_Throw_fs_error(v5, v6, a1);
    goto LABEL_3;
  }
  if ( (_DWORD)v5 != 3 )
  {
LABEL_3:
    if ( *a2 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
    return 2147942487LL;
  }
  v30 = 0;
  DirHandle = TryGetDirHandle(a1);
  v9 = DirHandle;
  if ( DirHandle < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17B,
      (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
      (const char *)(unsigned int)DirHandle,
      AllocationSize);
    v10 = (volatile signed __int32 *)*((_QWORD *)&v30 + 1);
    if ( !*((_QWORD *)&v30 + 1) )
    {
LABEL_12:
      if ( *a2 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
      return v9;
    }
LABEL_9:
    if ( !_InterlockedDecrement(v10 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( !_InterlockedDecrement(v10 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
    goto LABEL_12;
  }
  v11 = -1;
  do
    ++v11;
  while ( asc_180037830[v11] );
  *(_OWORD *)Src = 0;
  v38 = 0;
  v39 = 0;
  std::wstring::_Construct<1,unsigned short const *>(Src, L"{????????-????-????-????-????????????}", v11);
  std::filesystem::operator/(lpFileName, a1, (std::filesystem *)Src);
  std::wstring::~wstring(Src);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v12 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v12 = lpFileName[0];
  FirstFileW = (char *)FindFirstFileW(v12, &FindFileData);
  v31 = FirstFileW;
  if ( ((unsigned __int64)(FirstFileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( (v9 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x184,
        (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
        (const char *)v9,
        AllocationSize);
      if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        FindClose(FirstFileW);
      std::wstring::~wstring(lpFileName);
      v10 = (volatile signed __int32 *)*((_QWORD *)&v30 + 1);
      if ( !*((_QWORD *)&v30 + 1) )
        goto LABEL_12;
      goto LABEL_9;
    }
  }
  while ( 1 )
  {
    v29 = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59302972>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59302972>::GetImpl'::`2'::impl) )
      break;
    if ( (int)CreateAndGetLockFile(&v30, &v29) >= 0 )
      goto LABEL_41;
LABEL_63:
    v26 = (volatile signed __int32 *)*((_QWORD *)&v29 + 1);
    if ( *((_QWORD *)&v29 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v29 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
        if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
      }
    }
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
    {
      if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        FindClose(FirstFileW);
      std::wstring::~wstring(lpFileName);
      v27 = (volatile signed __int32 *)*((_QWORD *)&v30 + 1);
      if ( *((_QWORD *)&v30 + 1) )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v30 + 1) + 8LL)) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
          if ( !_InterlockedDecrement(v27 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
        }
      }
      if ( *a2 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
      return 2147943568LL;
    }
  }
  memset(v44, 0, sizeof(v44));
  v15 = -1;
  do
    ++v15;
  while ( FindFileData.cFileName[v15] );
  std::wstring::_Construct<1,unsigned short const *>(v44, FindFileData.cFileName, v15);
  v16 = std::operator+<unsigned short>(v45, v44, L"\\");
  std::operator+<unsigned short>(SourceString, v16, L"secure_file.lock");
  std::wstring::~wstring(v45);
  std::wstring::~wstring(v44);
  DestinationString = 0;
  v17 = (const WCHAR *)SourceString;
  if ( v42 > 7 )
    v17 = SourceString[0];
  RtlInitUnicodeString(&DestinationString, v17);
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ObjectAttributes.Length = 48;
  if ( (_QWORD)v30 )
    v18 = *(void **)v30;
  else
    v18 = 0;
  ObjectAttributes.RootDirectory = v18;
  ObjectAttributes.Attributes = 4160;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  v19 = (void **)wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>::operator&(&v29);
  if ( NtCreateFile(v19, 0x13019Fu, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 3u, 0x1060u, 0, 0) < 0
    || !(_QWORD)v29
    || (unsigned __int64)(*(_QWORD *)v29 - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v23 = SourceString;
    goto LABEL_62;
  }
  std::wstring::~wstring(SourceString);
LABEL_41:
  v20 = -1;
  do
    ++v20;
  while ( FindFileData.cFileName[v20] );
  *(_OWORD *)SourceString = 0;
  v41 = 0;
  v42 = 0;
  std::wstring::_Construct<1,unsigned short const *>(SourceString, FindFileData.cFileName, v20);
  std::filesystem::operator/(Src, a1, (std::filesystem *)SourceString);
  std::wstring::~wstring(SourceString);
  v21 = (const WCHAR *)Src;
  if ( v39 > 7 )
    v21 = Src[0];
  FileAttributesW = GetFileAttributesW(v21);
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
  {
    v23 = Src;
LABEL_62:
    std::wstring::~wstring(v23);
    goto LABEL_63;
  }
  (*(void (__fastcall **)(_QWORD, LPCWSTR *, __int128 *))(*(_QWORD *)*a2 + 24LL))(*a2, Src, &v29);
  std::wstring::~wstring(Src);
  v24 = (volatile signed __int32 *)*((_QWORD *)&v29 + 1);
  if ( *((_QWORD *)&v29 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v29 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
      if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
    }
  }
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose(FirstFileW);
  std::wstring::~wstring(lpFileName);
  v25 = (volatile signed __int32 *)*((_QWORD *)&v30 + 1);
  if ( *((_QWORD *)&v30 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v30 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
      if ( !_InterlockedDecrement(v25 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
    }
  }
  if ( *a2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
  return 0;
}

```

## disassembly

```asm
0x1800299f4  mov     [rsp-8+arg_10], rbx
0x1800299f9  mov     [rsp-8+arg_18], rsi
0x1800299fe  push    rbp
0x1800299ff  push    rdi
0x180029a00  push    r12
0x180029a02  push    r14
0x180029a04  push    r15
0x180029a06  lea     rbp, [rsp-2F0h]
0x180029a0e  sub     rsp, 3F0h
0x180029a15  mov     rax, cs:__security_cookie
0x180029a1c  xor     rax, rsp
0x180029a1f  mov     [rbp+310h+var_30], rax
0x180029a26  mov     rsi, rdx
0x180029a29  mov     r15, rcx
0x180029a2c  mov     [rbp+310h+var_338], rdx
0x180029a30  xor     r12d, r12d
0x180029a33  mov     rdx, rcx
0x180029a36  lea     rcx, [rbp+310h+var_348]
0x180029a3a  call    ?_Get_any_status@filesystem@std@@YA?AU_File_status_and_error@12@AEBVpath@12@W4__std_fs_stats_flags@@@Z; std::filesystem::_Get_any_status(std::filesystem::path const &,__std_fs_stats_flags)
0x180029a3f  mov     ecx, [rax]
0x180029a41  mov     edx, [rax+8]
0x180029a44  test    edx, edx
0x180029a46  jz      short loc_180029A93
0x180029a48  lea     eax, [rcx-1]
0x180029a4b  test    eax, 0FFFFFFF7h
0x180029a50  jnz     loc_180029FBF
0x180029a56  cmp     [rsi], r12
0x180029a59  jz      short loc_180029A63
0x180029a5b  mov     rcx, rsi
0x180029a5e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180029a63  mov     eax, 80070057h
0x180029a68  mov     rcx, [rbp+310h+var_30]
0x180029a6f  xor     rcx, rsp; StackCookie
0x180029a72  call    __security_check_cookie
0x180029a77  lea     r11, [rsp+410h+var_20]
0x180029a7f  mov     rbx, [r11+40h]
0x180029a83  mov     rsi, [r11+48h]
0x180029a87  mov     rsp, r11
0x180029a8a  pop     r15
0x180029a8c  pop     r14
0x180029a8e  pop     r12
0x180029a90  pop     rdi
0x180029a91  pop     rbp
0x180029a92  retn
0x180029a93  cmp     ecx, 3
0x180029a96  jnz     short loc_180029A56
0x180029a98  xorps   xmm1, xmm1
0x180029a9b  movdqu  [rsp+410h+var_3A0], xmm1
0x180029aa1  lea     rdx, [rsp+410h+var_3A0]
0x180029aa6  mov     rcx, r15; struct std::filesystem::path *
0x180029aa9  call    ?TryGetDirHandle@@YAJAEBVpath@filesystem@std@@AEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; TryGetDirHandle(std::filesystem::path const &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &)
0x180029aae  mov     r14d, eax
0x180029ab1  test    eax, eax
0x180029ab3  jns     short loc_180029B28
0x180029ab5  mov     rcx, [rbp+318h]; this
0x180029abc  mov     r9d, eax; char *
0x180029abf  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x180029ac6  mov     edx, 17Bh; void *
0x180029acb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029ad0  nop
0x180029ad1  mov     rbx, qword ptr [rsp+410h+var_3A0+8]
0x180029ad6  test    rbx, rbx
0x180029ad9  jz      short loc_180029B13
0x180029adb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180029adf  mov     eax, edi
0x180029ae1  lock xadd [rbx+8], eax
0x180029ae6  add     eax, edi
0x180029ae8  jnz     short loc_180029B13
0x180029aea  mov     rax, [rbx]
0x180029aed  mov     rcx, rbx
0x180029af0  mov     rax, [rax]
0x180029af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029af8  mov     eax, edi
0x180029afa  lock xadd [rbx+0Ch], eax
0x180029aff  add     eax, edi
0x180029b01  jnz     short loc_180029B13
0x180029b03  mov     rax, [rbx]
0x180029b06  mov     rcx, rbx
0x180029b09  mov     rax, [rax+8]
0x180029b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b12  nop
0x180029b13  cmp     [rsi], r12
0x180029b16  jz      short loc_180029B20
0x180029b18  mov     rcx, rsi
0x180029b1b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180029b20  mov     eax, r14d
0x180029b23  jmp     loc_180029A68
0x180029b28  mov     rdx, cs:off_180034638; "{????????-????-????-????-????????????}"
0x180029b2f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180029b33  mov     r8, rdi
0x180029b36  inc     r8
0x180029b39  cmp     [rdx+r8*2], r12w
0x180029b3e  jnz     short loc_180029B36
0x180029b40  xorps   xmm0, xmm0
0x180029b43  movups  xmmword ptr [rbp+310h+Src], xmm0
0x180029b47  mov     [rbp+310h+var_310], r12
0x180029b4b  mov     [rbp+310h+var_308], r12
0x180029b4f  lea     rcx, [rbp+310h+Src]
0x180029b53  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180029b58  nop
0x180029b59  lea     r8, [rbp+310h+Src]; this
0x180029b5d  mov     rdx, r15; struct std::filesystem::path *
0x180029b60  lea     rcx, [rbp+310h+lpFileName]; Src
0x180029b64  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180029b69  nop
0x180029b6a  lea     rcx, [rbp+310h+Src]
0x180029b6e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029b73  xor     edx, edx; Val
0x180029b75  mov     r8d, 250h; Size
0x180029b7b  lea     rcx, [rbp+310h+FindFileData]; void *
0x180029b82  call    memset_0
0x180029b87  lea     rcx, [rbp+310h+lpFileName]
0x180029b8b  cmp     [rbp+310h+var_2C8], 7
0x180029b90  cmova   rcx, [rbp+310h+lpFileName]; lpFileName
0x180029b95  lea     rdx, [rbp+310h+FindFileData]; lpFindFileData
0x180029b9c  call    cs:__imp_FindFirstFileW
0x180029ba2  mov     rbx, rax
0x180029ba5  mov     [rbp+310h+var_390], rax
0x180029ba9  inc     rax
0x180029bac  test    rax, 0FFFFFFFFFFFFFFFEh
0x180029bb2  jnz     short loc_180029C1E
0x180029bb4  call    cs:__imp_GetLastError
0x180029bba  mov     r14d, eax
0x180029bbd  test    eax, eax
0x180029bbf  jle     short loc_180029BCC
0x180029bc1  movzx   r14d, ax
0x180029bc5  or      r14d, 80070000h
0x180029bcc  test    r14d, r14d
0x180029bcf  jns     short loc_180029C1E
0x180029bd1  mov     rcx, [rbp+318h]; this
0x180029bd8  mov     r9d, r14d; char *
0x180029bdb  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x180029be2  mov     edx, 184h; void *
0x180029be7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029bec  nop
0x180029bed  lea     rax, [rbx-1]
0x180029bf1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180029bf5  ja      short loc_180029C01
0x180029bf7  mov     rcx, rbx; hFindFile
0x180029bfa  call    cs:__imp_FindClose
0x180029c00  nop
0x180029c01  lea     rcx, [rbp+310h+lpFileName]
0x180029c05  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029c0a  nop
0x180029c0b  mov     rbx, qword ptr [rsp+410h+var_3A0+8]
0x180029c10  test    rbx, rbx
0x180029c13  jz      loc_180029B13
0x180029c19  jmp     loc_180029ADF
0x180029c1e  xorps   xmm1, xmm1
0x180029c21  movdqu  [rsp+410h+var_3B0], xmm1
0x180029c27  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59302972@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59302972@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59302972> `wil::Feature<__WilFeatureTraits_Feature_59302972>::GetImpl(void)'::`2'::impl
0x180029c2e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59302972@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59302972>::__private_IsEnabled(void)
0x180029c33  test    al, al
0x180029c35  jz      short loc_180029C53
0x180029c37  lea     rdx, [rsp+410h+var_3B0]
0x180029c3c  lea     rcx, [rsp+410h+var_3A0]
0x180029c41  call    ?CreateAndGetLockFile@@YAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@0@Z; CreateAndGetLockFile(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &)
0x180029c46  test    eax, eax
0x180029c48  jns     loc_180029DA4
0x180029c4e  jmp     loc_180029EF5
0x180029c53  xorps   xmm0, xmm0
0x180029c56  movups  [rbp+310h+var_2C0], xmm0
0x180029c5a  xorps   xmm1, xmm1
0x180029c5d  movdqu  [rbp+310h+var_2B0], xmm1
0x180029c62  lea     rax, [rbp+310h+FindFileData.cFileName]
0x180029c69  mov     r8, rdi
0x180029c6c  inc     r8
0x180029c6f  cmp     [rax+r8*2], r12w
0x180029c74  jnz     short loc_180029C6C
0x180029c76  lea     rdx, [rbp+310h+FindFileData.cFileName]
0x180029c7d  lea     rcx, [rbp+310h+var_2C0]
0x180029c81  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180029c86  nop
0x180029c87  lea     r8, asc_1800356F8; "\\"
0x180029c8e  lea     rdx, [rbp+310h+var_2C0]
0x180029c92  lea     rcx, [rbp+310h+var_2A0]
0x180029c96  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180029c9b  nop
0x180029c9c  lea     r8, aSecureFileLock; "secure_file.lock"
0x180029ca3  mov     rdx, rax
0x180029ca6  lea     rcx, [rbp+310h+SourceString]
0x180029caa  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180029caf  nop
0x180029cb0  lea     rcx, [rbp+310h+var_2A0]
0x180029cb4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029cb9  nop
0x180029cba  lea     rcx, [rbp+310h+var_2C0]
0x180029cbe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029cc3  xorps   xmm0, xmm0
0x180029cc6  movups  xmmword ptr [rbp+310h+DestinationString.Length], xmm0
0x180029cca  lea     rdx, [rbp+310h+SourceString]
0x180029cce  cmp     [rbp+310h+var_2E8], 7
0x180029cd3  cmova   rdx, [rbp+310h+SourceString]; SourceString
0x180029cd8  lea     rcx, [rbp+310h+DestinationString]; DestinationString
0x180029cdc  call    cs:__imp_RtlInitUnicodeString
0x180029ce2  xorps   xmm0, xmm0
0x180029ce5  movups  xmmword ptr [rbp+310h+ObjectAttributes.Length], xmm0
0x180029ce9  movups  xmmword ptr [rbp+310h+ObjectAttributes.ObjectName], xmm0
0x180029ced  movups  xmmword ptr [rbp+310h+ObjectAttributes.SecurityDescriptor], xmm0
0x180029cf1  mov     [rbp+310h+ObjectAttributes.Length], 30h ; '0'
0x180029cf8  mov     rax, qword ptr [rsp+410h+var_3A0]
0x180029cfd  test    rax, rax
0x180029d00  jz      short loc_180029D07
0x180029d02  mov     rax, [rax]
0x180029d05  jmp     short loc_180029D0A
0x180029d07  mov     rax, r12
0x180029d0a  mov     [rbp+310h+ObjectAttributes.RootDirectory], rax
0x180029d0e  mov     [rbp+310h+ObjectAttributes.Attributes], 1040h
0x180029d15  lea     rax, [rbp+310h+DestinationString]
0x180029d19  mov     [rbp+310h+ObjectAttributes.ObjectName], rax
0x180029d1d  movdqu  xmmword ptr [rbp+310h+ObjectAttributes.SecurityDescriptor], xmm0
0x180029d22  movups  xmmword ptr [rbp+310h+IoStatusBlock], xmm0
0x180029d26  lea     rcx, [rsp+410h+var_3B0]
0x180029d2b  call    ??I?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>::operator&(void)
0x180029d30  mov     rcx, rax; FileHandle
0x180029d33  mov     [rsp+410h+EaLength], r12d; EaLength
0x180029d38  mov     [rsp+410h+EaBuffer], r12; EaBuffer
0x180029d3d  mov     [rsp+410h+CreateOptions], 1060h; CreateOptions
0x180029d45  mov     [rsp+410h+CreateDisposition], 3; CreateDisposition
0x180029d4d  mov     [rsp+410h+ShareAccess], 3; ShareAccess
0x180029d55  mov     [rsp+410h+FileAttributes], 80h; FileAttributes
0x180029d5d  mov     [rsp+410h+AllocationSize], r12; AllocationSize
0x180029d62  lea     r9, [rbp+310h+IoStatusBlock]; IoStatusBlock
0x180029d66  lea     r8, [rbp+310h+ObjectAttributes]; ObjectAttributes
0x180029d6a  mov     edx, 13019Fh; DesiredAccess
0x180029d6f  call    cs:__imp_NtCreateFile
0x180029d75  test    eax, eax
0x180029d77  js      loc_180029EEB
0x180029d7d  mov     rax, qword ptr [rsp+410h+var_3B0]
0x180029d82  test    rax, rax
0x180029d85  jz      loc_180029EEB
0x180029d8b  mov     rax, [rax]
0x180029d8e  dec     rax
0x180029d91  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180029d95  ja      loc_180029EEB
0x180029d9b  lea     rcx, [rbp+310h+SourceString]
0x180029d9f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029da4  lea     rax, [rbp+310h+FindFileData.cFileName]
0x180029dab  mov     r8, rdi
0x180029dae  inc     r8
0x180029db1  cmp     [rax+r8*2], r12w
0x180029db6  jnz     short loc_180029DAE
0x180029db8  xorps   xmm0, xmm0
0x180029dbb  movups  xmmword ptr [rbp+310h+SourceString], xmm0
0x180029dbf  mov     [rbp+310h+var_2F0], r12
0x180029dc3  mov     [rbp+310h+var_2E8], r12
0x180029dc7  lea     rdx, [rbp+310h+FindFileData.cFileName]
0x180029dce  lea     rcx, [rbp+310h+SourceString]
0x180029dd2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180029dd7  nop
0x180029dd8  lea     r8, [rbp+310h+SourceString]; this
0x180029ddc  mov     rdx, r15; struct std::filesystem::path *
0x180029ddf  lea     rcx, [rbp+310h+Src]; Src
0x180029de3  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180029de8  nop
0x180029de9  lea     rcx, [rbp+310h+SourceString]
0x180029ded  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029df2  lea     rcx, [rbp+310h+Src]
0x180029df6  cmp     [rbp+310h+var_308], 7
0x180029dfb  cmova   rcx, [rbp+310h+Src]; lpFileName
0x180029e00  call    cs:__imp_GetFileAttributesW
0x180029e06  cmp     eax, 0FFFFFFFFh
0x180029e09  jnz     short loc_180029E14
0x180029e0b  lea     rcx, [rbp+310h+Src]
0x180029e0f  jmp     loc_180029EEF
0x180029e14  test    al, 10h
0x180029e16  jz      short loc_180029E0B
0x180029e18  mov     rcx, [rsi]
0x180029e1b  mov     rax, [rcx]
0x180029e1e  lea     r8, [rsp+410h+var_3B0]
0x180029e23  lea     rdx, [rbp+310h+Src]
0x180029e27  mov     rax, [rax+18h]
0x180029e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e30  nop
0x180029e31  lea     rcx, [rbp+310h+Src]
0x180029e35  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029e3a  nop
0x180029e3b  mov     r14, qword ptr [rsp+410h+var_3B0+8]
0x180029e40  test    r14, r14
0x180029e43  jz      short loc_180029E7B
0x180029e45  mov     eax, edi
0x180029e47  lock xadd [r14+8], eax
0x180029e4d  add     eax, edi
0x180029e4f  jnz     short loc_180029E7B
0x180029e51  mov     rax, [r14]
0x180029e54  mov     rcx, r14
0x180029e57  mov     rax, [rax]
0x180029e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e5f  mov     eax, edi
0x180029e61  lock xadd [r14+0Ch], eax
0x180029e67  add     eax, edi
0x180029e69  jnz     short loc_180029E7B
0x180029e6b  mov     rax, [r14]
0x180029e6e  mov     rcx, r14
0x180029e71  mov     rax, [rax+8]
0x180029e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e7a  nop
0x180029e7b  lea     rax, [rbx-1]
0x180029e7f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180029e83  ja      short loc_180029E8F
  ... truncated ...
```
