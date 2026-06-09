# CodeIntegrity::Management::BeginUpsertSystemCIPolicy(_GUID const *)

- ea: `0x1800123e0`
- end: `0x18001288c`
- name: `?BeginUpsertSystemCIPolicy@Management@CodeIntegrity@@YAXPEBU_GUID@@@Z`
- size: `1196`
- prototype: `void __fastcall(CodeIntegrity::Management *this, struct _GUID *, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180008b50`

## callees

- `0x180002a90`
- `0x180004c7c`
- `0x180004e28`
- `0x180004e34`
- `0x180005600`
- `0x18000828c`
- `0x1800082ac`
- `0x180008474`
- `0x18000d470`
- `0x18000f068`
- `0x180010500`
- `0x1800112ac`
- `0x180011308`
- `0x1800114d8`
- `0x1800114f8`
- `0x1800116d8`
- `0x1800123e0`
- `0x1800154c0`
- `0x1800154e8`
- `0x18001758c`
- `0x180021bd8`
- `0x1800273c8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001276c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001276c`
- `ntdll!NtOpenFile` at `0x18001258b`
- `ntdll!NtOpenFile` at `0x18001258b`
- `ntdll!NtQueryInformationFile` at `0x1800125e4`
- `ntdll!NtQueryInformationFile` at `0x1800125e4`
- `ntdll!NtReadFile` at `0x18001267d`
- `ntdll!NtReadFile` at `0x18001267d`

## string_xrefs

- `0x1800127d8`: `onecore\base\ci\management\dll\manageci.cpp`
- `0x1800127ed`: `onecore\base\ci\management\dll\manageci.cpp`
- `0x1800127fe`: `onecore\base\ci\management\dll\manageci.cpp`
- `0x180012810`: `onecore\base\ci\management\dll\manageci.cpp`
- `0x180012824`: `onecore\base\ci\management\dll\manageci.cpp`
- `0x180012859`: `onecore\base\ci\management\dll\manageci.cpp`
- `0x180012430`: `\SystemRoot\System32\CodeIntegrity\CiPolicies\Reserved`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::BeginUpsertSystemCIPolicy(
        CodeIntegrity::Management *this,
        struct _GUID *a2,
        unsigned int a3,
        const char *a4)
{
  __int64 SystemPolicyDefinitionByID; // rbx
  __int64 v6; // rax
  NTSTATUS v7; // eax
  NTSTATUS v8; // eax
  ULONG v9; // esi
  __int64 v10; // r9
  const char *v11; // r9
  unsigned __int8 *v12; // rbx
  NTSTATUS v13; // eax
  int updated; // eax
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int v17; // eax
  unsigned int v18; // r8d
  unsigned int v19; // eax
  unsigned int v20; // r8d
  int ShareAccess; // [rsp+20h] [rbp-228h]
  int ShareAccessa; // [rsp+20h] [rbp-228h]
  int ShareAccessb; // [rsp+20h] [rbp-228h]
  ULONG ShareAccessc[2]; // [rsp+20h] [rbp-228h]
  ULONG OpenOptions[2]; // [rsp+28h] [rbp-220h]
  __int64 Length; // [rsp+30h] [rbp-218h]
  int ByteOffset; // [rsp+38h] [rbp-210h]
  HANDLE v28[2]; // [rsp+50h] [rbp-1F8h] BYREF
  PVOID Buffer; // [rsp+60h] [rbp-1E8h] BYREF
  __int64 v30; // [rsp+68h] [rbp-1E0h]
  __int64 v31; // [rsp+70h] [rbp-1D8h] BYREF
  _WORD v32[2]; // [rsp+78h] [rbp-1D0h] BYREF
  int v33; // [rsp+7Ch] [rbp-1CCh]
  __int64 v34; // [rsp+80h] [rbp-1C8h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-1C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-1B0h] BYREF
  HANDLE *v37; // [rsp+C8h] [rbp-180h] BYREF
  void *FileHandle; // [rsp+D0h] [rbp-178h] BYREF
  char v39; // [rsp+D8h] [rbp-170h]
  __int128 FileInformation; // [rsp+E8h] [rbp-160h] BYREF
  __int64 v41; // [rsp+F8h] [rbp-150h]
  _BYTE v42[16]; // [rsp+100h] [rbp-148h] BYREF
  __int16 v43; // [rsp+110h] [rbp-138h]
  _BYTE v44[32]; // [rsp+120h] [rbp-128h] BYREF
  _BYTE v45[32]; // [rsp+140h] [rbp-108h] BYREF
  __int64 v46[11]; // [rsp+160h] [rbp-E8h] BYREF
  char v47; // [rsp+1BDh] [rbp-8Bh]
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  try
  {
    if ( *(_QWORD *)this != SiPolicyIDPicrootExceptionsEnforce || *((_QWORD *)this + 1) != 0xE30746B4027229A3uLL )
      wil::details::in1diag3::Throw_NtStatus(retaddr, a2, a3, a4, ShareAccess);
    SystemPolicyDefinitionByID = SIPolicyGetSystemPolicyDefinitionByID();
    Buffer = L"\\SystemRoot\\System32\\CodeIntegrity\\CiPolicies\\Reserved";
    v30 = 54;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v44, &Buffer);
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(*(_QWORD *)(SystemPolicyDefinitionByID + 24) + 2 * v6) );
    Buffer = *(PVOID *)(SystemPolicyDefinitionByID + 24);
    v30 = v6;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(&v37, &Buffer);
    std::filesystem::operator/(v45, v44, &v37);
    std::wstring::_Tidy_deallocate(&v37);
    std::wstring::wstring(v42);
    v33 = 0;
    v34 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v42);
    v32[0] = 2 * v43;
    v32[1] = 2 * v43 + 2;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v32;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    IoStatusBlock = 0;
    v28[0] = 0;
    v37 = v28;
    FileHandle = 0;
    v39 = 1;
    v7 = NtOpenFile(&FileHandle, 0x80100000, &ObjectAttributes, &IoStatusBlock, 1u, 0x60u);
    if ( v7 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x165,
        (unsigned int)"onecore\\base\\ci\\management\\dll\\manageci.cpp",
        (const char *)(unsigned int)v7,
        ShareAccessa);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v37);
    FileInformation = 0;
    v41 = 0;
    v8 = NtQueryInformationFile(v28[0], &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x16D,
        (unsigned int)"onecore\\base\\ci\\management\\dll\\manageci.cpp",
        (const char *)(unsigned int)v8,
        ShareAccessb);
    v9 = DWORD2(FileInformation);
    if ( *((_QWORD *)&FileInformation + 1) > 0xFFFFFFFF )
    {
      v9 = -1;
      v10 = 3221225621LL;
    }
    else
    {
      v10 = 0;
    }
    if ( (int)v10 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x171,
        (unsigned int)"onecore\\base\\ci\\management\\dll\\manageci.cpp",
        (const char *)v10,
        ShareAccessb);
    wil::make_unique_hlocal_nothrow<unsigned char [0]>(&Buffer, v9);
    v12 = (unsigned __int8 *)Buffer;
    if ( !Buffer )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x174,
        (unsigned int)"onecore\\base\\ci\\management\\dll\\manageci.cpp",
        v11);
    v13 = NtReadFile(v28[0], 0, 0, 0, &IoStatusBlock, Buffer, v9, 0, 0);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x17F,
        (unsigned int)"onecore\\base\\ci\\management\\dll\\manageci.cpp",
        (const char *)(unsigned int)v13,
        ShareAccessc[0]);
    v31 = 0;
    CodeIntegrity::Management::SiPolicyView::SiPolicyView((CodeIntegrity::Management::SiPolicyView *)v46, v12, v9);
    if ( !v47 )
    {
      v17 = wil::verify_hresult<long>(2147942405LL);
      wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x186, v18, (const char *)v17, ShareAccessc[0]);
    }
    if ( *(_QWORD *)v46[0] != *(_QWORD *)this || *(_QWORD *)(v46[0] + 8) != *((_QWORD *)this + 1) )
    {
      v19 = wil::verify_hresult<long>(2147500037LL);
      wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x18B, v20, (const char *)v19, ShareAccessc[0]);
    }
    v37 = (HANDLE *)&v31;
    FileHandle = 0;
    v39 = 1;
    updated = SIPolicyPmUpdatePolicyBegin(v46[0], v12, v9, &FileHandle);
    if ( updated < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x192,
        (unsigned int)"onecore\\base\\ci\\management\\dll\\manageci.cpp",
        (const char *)(unsigned int)updated,
        ShareAccessc[0]);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v37);
    std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>,0>>::emplace<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,CodeIntegrity::Management::SiPolicyView>(
      qword_180039830,
      &v37,
      &v31,
      v46,
      *(_QWORD *)ShareAccessc,
      *(_QWORD *)OpenOptions,
      Length,
      ByteOffset);
    CodeIntegrity::Management::SiPolicyView::~SiPolicyView((CodeIntegrity::Management::SiPolicyView *)v46);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v31);
    if ( v12 )
      LocalFree(v12);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v28);
    std::wstring::_Tidy_deallocate(v42);
    std::wstring::_Tidy_deallocate(v45);
    std::wstring::_Tidy_deallocate(v44);
  }
  catch ( std::exception )
  {
    wil::details::in1diag3::Throw_CaughtException(retaddr, (void *)0x19A, v15, v16);
  }
}

```

## disassembly

```asm
0x1800123e0  push    rbx
0x1800123e2  push    rsi
0x1800123e3  push    rdi
0x1800123e4  push    r14
0x1800123e6  push    r15
0x1800123e8  sub     rsp, 220h
0x1800123ef  mov     rax, cs:__security_cookie
0x1800123f6  xor     rax, rsp
0x1800123f9  mov     [rsp+248h+var_38], rax
0x180012401  mov     rdi, rcx
0x180012404  xor     r15d, r15d
0x180012407  mov     rax, [rcx]
0x18001240a  cmp     rax, cs:SiPolicyIDPicrootExceptionsEnforce
0x180012411  jnz     loc_1800127C7
0x180012417  mov     rax, [rcx+8]
0x18001241b  cmp     rax, cs:qword_18002F2E0
0x180012422  jnz     loc_1800127C7
0x180012428  call    SIPolicyGetSystemPolicyDefinitionByID
0x18001242d  mov     rbx, rax
0x180012430  lea     rax, aSystemrootSyst; "\\SystemRoot\\System32\\CodeIntegrity\\"...
0x180012437  mov     [rsp+248h+Buffer], rax
0x18001243c  mov     [rsp+248h+var_1E0], 36h ; '6'
0x180012445  lea     rdx, [rsp+248h+Buffer]
0x18001244a  lea     rcx, [rsp+248h+var_128]
0x180012452  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x180012457  nop
0x180012458  mov     rcx, [rbx+18h]
0x18001245c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012460  inc     rax
0x180012463  cmp     [rcx+rax*2], r15w
0x180012468  jnz     short loc_180012460
0x18001246a  mov     [rsp+248h+Buffer], rcx
0x18001246f  mov     [rsp+248h+var_1E0], rax
0x180012474  lea     rdx, [rsp+248h+Buffer]
0x180012479  lea     rcx, [rsp+248h+var_180]
0x180012481  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x180012486  nop
0x180012487  lea     r8, [rsp+248h+var_180]
0x18001248f  lea     rdx, [rsp+248h+var_128]
0x180012497  lea     rcx, [rsp+248h+var_108]
0x18001249f  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1800124a4  nop
0x1800124a5  lea     rcx, [rsp+248h+var_180]
0x1800124ad  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800124b2  lea     rdx, [rsp+248h+var_108]
0x1800124ba  lea     rcx, [rsp+248h+var_148]
0x1800124c2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800124c7  nop
0x1800124c8  mov     [rsp+248h+var_1CC], r15d
0x1800124cd  lea     rcx, [rsp+248h+var_148]
0x1800124d5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800124da  mov     [rsp+248h+var_1C8], rax
0x1800124e2  movzx   eax, [rsp+248h+var_138]
0x1800124ea  add     ax, ax
0x1800124ed  mov     [rsp+248h+var_1D0], ax
0x1800124f2  add     ax, 2
0x1800124f6  mov     [rsp+248h+var_1CE], ax
0x1800124fb  mov     qword ptr [rsp+248h+ObjectAttributes.Length], 30h ; '0'
0x180012507  mov     qword ptr [rsp+248h+ObjectAttributes.Attributes], 40h ; '@'
0x180012513  mov     [rsp+248h+ObjectAttributes.RootDirectory], r15
0x18001251b  lea     rax, [rsp+248h+var_1D0]
0x180012520  mov     [rsp+248h+ObjectAttributes.ObjectName], rax
0x180012528  xorps   xmm0, xmm0
0x18001252b  movdqu  xmmword ptr [rsp+248h+ObjectAttributes.SecurityDescriptor], xmm0
0x180012534  movups  xmmword ptr [rsp+248h+IoStatusBlock], xmm0
0x18001253c  mov     [rsp+248h+var_1F8], r15
0x180012541  lea     rax, [rsp+248h+var_1F8]
0x180012546  mov     [rsp+248h+var_180], rax
0x18001254e  mov     [rsp+248h+FileHandle], r15
0x180012556  mov     [rsp+248h+var_170], 1
0x18001255e  mov     [rsp+248h+OpenOptions], 60h ; '`'; OpenOptions
0x180012566  mov     [rsp+248h+ShareAccess], 1; int
0x18001256e  lea     r9, [rsp+248h+IoStatusBlock]; IoStatusBlock
0x180012576  lea     r8, [rsp+248h+ObjectAttributes]; ObjectAttributes
0x18001257e  mov     edx, 80100000h; DesiredAccess
0x180012583  lea     rcx, [rsp+248h+FileHandle]; FileHandle
0x18001258b  call    cs:__imp_NtOpenFile
0x180012591  mov     rcx, [rsp+248h]; this
0x180012599  test    eax, eax
0x18001259b  js      loc_1800127D5
0x1800125a1  lea     rcx, [rsp+248h+var_180]
0x1800125a9  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x1800125ae  xorps   xmm0, xmm0
0x1800125b1  xor     eax, eax
0x1800125b3  movups  [rsp+248h+FileInformation], xmm0
0x1800125bb  mov     [rsp+248h+var_150], rax
0x1800125c3  mov     [rsp+248h+ShareAccess], 5; int
0x1800125cb  lea     r9d, [rax+18h]; Length
0x1800125cf  lea     r8, [rsp+248h+FileInformation]; FileInformation
0x1800125d7  lea     rdx, [rsp+248h+IoStatusBlock]; IoStatusBlock
0x1800125df  mov     rcx, [rsp+248h+var_1F8]; FileHandle
0x1800125e4  call    cs:__imp_NtQueryInformationFile
0x1800125ea  mov     rcx, [rsp+248h]; this
0x1800125f2  test    eax, eax
0x1800125f4  js      loc_1800127EA
0x1800125fa  mov     eax, 0FFFFFFFFh
0x1800125ff  mov     rsi, qword ptr [rsp+248h+FileInformation+8]
0x180012607  cmp     rsi, rax
0x18001260a  ja      short loc_180012611
0x18001260c  mov     r9d, r15d
0x18001260f  jmp     short loc_180012619
0x180012611  mov     esi, eax
0x180012613  mov     r9d, 0C0000095h; char *
0x180012619  mov     rcx, [rsp+248h]; this
0x180012621  test    r9d, r9d
0x180012624  js      loc_1800127FE
0x18001262a  mov     r14d, esi
0x18001262d  mov     edx, esi
0x18001262f  lea     rcx, [rsp+248h+Buffer]
0x180012634  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x180012639  nop
0x18001263a  mov     rcx, [rsp+248h]; this
0x180012642  mov     rbx, [rsp+248h+Buffer]
0x180012647  test    rbx, rbx
0x18001264a  jz      loc_180012810
0x180012650  mov     [rsp+248h+Key], r15; Key
0x180012655  mov     [rsp+248h+ByteOffset], r15; ByteOffset
0x18001265a  mov     dword ptr [rsp+248h+Length], esi; Length
0x18001265e  mov     qword ptr [rsp+248h+OpenOptions], rbx; Buffer
0x180012663  lea     rax, [rsp+248h+IoStatusBlock]
0x18001266b  mov     qword ptr [rsp+248h+ShareAccess], rax; int
0x180012670  xor     r9d, r9d; ApcContext
0x180012673  xor     r8d, r8d; ApcRoutine
0x180012676  xor     edx, edx; Event
0x180012678  mov     rcx, [rsp+248h+var_1F8]; FileHandle
0x18001267d  call    cs:__imp_NtReadFile
0x180012683  mov     rcx, [rsp+248h]; this
0x18001268b  test    eax, eax
0x18001268d  js      loc_180012821
0x180012693  mov     [rsp+248h+var_1D8], r15
0x180012698  mov     r8, r14; unsigned __int64
0x18001269b  mov     rdx, rbx; unsigned __int8 *
0x18001269e  lea     rcx, [rsp+248h+var_E8]; this
0x1800126a6  call    ??0SiPolicyView@Management@CodeIntegrity@@QEAA@PEBE_K@Z; CodeIntegrity::Management::SiPolicyView::SiPolicyView(uchar const *,unsigned __int64)
0x1800126ab  nop
0x1800126ac  cmp     [rsp+248h+var_8B], r15b
0x1800126b4  jz      loc_180012836
0x1800126ba  mov     rcx, [rsp+248h+var_E8]
0x1800126c2  mov     rax, [rcx]
0x1800126c5  cmp     rax, [rdi]
0x1800126c8  jnz     loc_18001286B
0x1800126ce  mov     rax, [rcx+8]
0x1800126d2  cmp     rax, [rdi+8]
0x1800126d6  jnz     loc_18001286B
0x1800126dc  lea     rax, [rsp+248h+var_1D8]
0x1800126e1  mov     [rsp+248h+var_180], rax
0x1800126e9  mov     [rsp+248h+FileHandle], r15
0x1800126f1  mov     [rsp+248h+var_170], 1
0x1800126f9  lea     r9, [rsp+248h+FileHandle]
0x180012701  mov     r8d, esi
0x180012704  mov     rdx, rbx
0x180012707  call    SIPolicyPmUpdatePolicyBegin
0x18001270c  mov     rcx, [rsp+248h]; this
0x180012714  test    eax, eax
0x180012716  js      loc_180012856
0x18001271c  lea     rcx, [rsp+248h+var_180]
0x180012724  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x180012729  lea     r9, [rsp+248h+var_E8]
0x180012731  lea     r8, [rsp+248h+var_1D8]
0x180012736  lea     rdx, [rsp+248h+var_180]
0x18001273e  mov     rcx, cs:qword_180039830
0x180012745  call    ??$emplace@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@VSiPolicyView@Management@CodeIntegrity@@@?$_Tree@V?$_Tset_traits@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@@std@@_N@1@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAVSiPolicyView@Management@CodeIntegrity@@@Z; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>,0>>::emplace<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,CodeIntegrity::Management::SiPolicyView>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,CodeIntegrity::Management::SiPolicyView &&)
0x18001274a  nop
0x18001274b  lea     rcx, [rsp+248h+var_E8]; this
0x180012753  call    ??1SiPolicyView@Management@CodeIntegrity@@QEAA@XZ; CodeIntegrity::Management::SiPolicyView::~SiPolicyView(void)
0x180012758  nop
0x180012759  lea     rcx, [rsp+248h+var_1D8]
0x18001275e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180012763  nop
0x180012764  test    rbx, rbx
0x180012767  jz      short loc_180012773
0x180012769  mov     rcx, rbx; hMem
0x18001276c  call    cs:__imp_LocalFree
0x180012772  nop
0x180012773  lea     rcx, [rsp+248h+var_1F8]
0x180012778  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001277d  nop
0x18001277e  lea     rcx, [rsp+248h+var_148]
0x180012786  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001278b  nop
0x18001278c  lea     rcx, [rsp+248h+var_108]
0x180012794  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012799  nop
0x18001279a  lea     rcx, [rsp+248h+var_128]
0x1800127a2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800127a7  nop
0x1800127a8  mov     rcx, [rsp+248h+var_38]
0x1800127b0  xor     rcx, rsp; StackCookie
0x1800127b3  call    __security_check_cookie
0x1800127b8  add     rsp, 220h
0x1800127bf  pop     r15
0x1800127c1  pop     r14
0x1800127c3  pop     rdi
0x1800127c4  pop     rsi
0x1800127c5  pop     rbx
0x1800127c6  retn
0x1800127c7  mov     rcx, [rsp+248h]; this
0x1800127cf  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x1800127d5  mov     r9d, eax; char *
0x1800127d8  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x1800127df  mov     edx, 165h; void *
0x1800127e4  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1800127ea  mov     r9d, eax; char *
0x1800127ed  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x1800127f4  mov     edx, 16Dh; void *
0x1800127f9  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1800127fe  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x180012805  mov     edx, 171h; void *
0x18001280a  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180012810  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x180012817  mov     edx, 174h; void *
0x18001281c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180012821  mov     r9d, eax; char *
0x180012824  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x18001282b  mov     edx, 17Fh; void *
0x180012830  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180012836  mov     ecx, 80070005h
0x18001283b  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180012840  mov     r9d, eax; char *
0x180012843  mov     rcx, [rsp+248h]; this
0x18001284b  mov     edx, 186h; void *
0x180012850  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012856  mov     r9d, eax; char *
0x180012859  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x180012860  mov     edx, 192h; void *
0x180012865  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18001286b  mov     ecx, 80004005h
0x180012870  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180012875  mov     r9d, eax; char *
0x180012878  mov     rcx, [rsp+248h]; this
0x180012880  mov     edx, 18Bh; void *
0x180012885  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
