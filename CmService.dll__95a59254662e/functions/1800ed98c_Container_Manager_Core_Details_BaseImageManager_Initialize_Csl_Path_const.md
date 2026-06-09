# Container::Manager::Core::Details::BaseImageManager::Initialize(Csl::Path const &)

- ea: `0x1800ed98c`
- end: `0x1800edcae`
- name: `?Initialize@BaseImageManager@Details@Core@Manager@Container@@QEAAJAEBVPath@Csl@@@Z`
- size: `802`
- prototype: `__int64 __fastcall(PVOID pv, const struct Path *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18005b2a8`

## callees

- `0x180004fc4`
- `0x18000da68`
- `0x18000da88`
- `0x180016774`
- `0x18002fae4`
- `0x18002fd88`
- `0x180056330`
- `0x1800ec87c`
- `0x1800ed98c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800edc29`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800edc29`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800edb69`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800edb69`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800edbbc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800edc3d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800edbbc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800edc3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800edbab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800edbf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800edbab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800edbf0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800edbca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800edc0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800edbca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800edc0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800edb2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800edc01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800edc51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800edb2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800edc01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800edc51`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::BaseImageManager::Initialize(HKEY *pv, const struct Path *a2)
{
  int RootBaseImagesPath; // ebx
  struct _SECURITY_ATTRIBUTES *v4; // r8
  __int64 v5; // rdx
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // eax
  struct _TP_WORK *ThreadpoolWork; // rbx
  const char *v11; // r9
  PTP_WORK *v12; // r14
  struct _TP_WORK *v13; // r15
  DWORD LastError; // edi
  HKEY v15; // r15
  HKEY v16; // r12
  DWORD v17; // edi
  HKEY v18; // rdi
  int v19; // [rsp+28h] [rbp-39h]
  HKEY hKey; // [rsp+38h] [rbp-29h] BYREF
  char v21; // [rsp+40h] [rbp-21h] BYREF
  const wchar_t *v22; // [rsp+48h] [rbp-19h]
  __int64 v23; // [rsp+50h] [rbp-11h]
  void *v24[2]; // [rsp+58h] [rbp-9h] BYREF
  _WORD v25[8]; // [rsp+68h] [rbp+7h] BYREF
  void *v26[2]; // [rsp+78h] [rbp+17h] BYREF
  _WORD v27[8]; // [rsp+88h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]
  const struct Path *v29; // [rsp+D0h] [rbp+6Fh] BYREF

  v29 = a2;
  v24[0] = v25;
  v24[1] = v25;
  v25[0] = 0;
  RootBaseImagesPath = Container::Manager::Core::Details::_anonymous_namespace_::GetRootBaseImagesPath(v24);
  if ( RootBaseImagesPath < 0 )
  {
    v5 = 1249;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
      (const char *)(unsigned int)RootBaseImagesPath,
      v19);
LABEL_4:
    if ( v24[0] != v25 )
      operator delete(v24[0], (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)RootBaseImagesPath;
  }
  RootBaseImagesPath = Csl::CreateDirectoryRecursive((Csl *)v24, 0, v4);
  if ( RootBaseImagesPath < 0 )
  {
    v5 = 1251;
    goto LABEL_3;
  }
  v26[0] = v27;
  v26[1] = v27;
  v27[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v26,
                           Container::Manager::Core::g_registryRoot,
                           ((__int64)off_18021E510 - Container::Manager::Core::g_registryRoot) >> 1) )
  {
    v7 = 1255;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
      (const char *)0x8007000ELL,
      v19);
    if ( v26[0] != v27 )
      operator delete(v26[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v24[0] != v25 )
      operator delete(v24[0], (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  v23 = 6;
  v22 = L"Images";
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v26) )
  {
    v7 = 1256;
    goto LABEL_13;
  }
  hKey = 0;
  LOBYTE(v29) = 0;
  v9 = Csl::CreateRegistryKey(v8, v26[0], 131103, &hKey);
  RootBaseImagesPath = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4EF,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
      (const char *)(unsigned int)v9,
      (int)&v29);
LABEL_20:
    if ( hKey )
      RegCloseKey(hKey);
    if ( v26[0] != v27 )
      operator delete(v26[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_4;
  }
  ThreadpoolWork = CreateThreadpoolWork(
                     Container::Manager::Core::Details::BaseImageManager::CleanupLegacyBaseImagesWork,
                     pv,
                     0);
  if ( !ThreadpoolWork )
  {
    RootBaseImagesPath = wil::details::in1diag3::Return_GetLastError(
                           retaddr,
                           (void *)0x4F8,
                           (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
                           v11);
    goto LABEL_20;
  }
  v12 = (PTP_WORK *)(pv + 1);
  if ( pv + 1 != (HKEY *)&v21 )
  {
    v13 = *v12;
    if ( *v12 )
    {
      LastError = GetLastError();
      CloseThreadpoolWork(v13);
      SetLastError(LastError);
    }
    *v12 = ThreadpoolWork;
    ThreadpoolWork = 0;
  }
  if ( pv == &hKey )
  {
    v18 = hKey;
  }
  else
  {
    v15 = *pv;
    v16 = hKey;
    if ( *pv )
    {
      v17 = GetLastError();
      RegCloseKey(v15);
      SetLastError(v17);
    }
    *pv = v16;
    v18 = 0;
  }
  SubmitThreadpoolWork(*v12);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
  if ( v18 )
    RegCloseKey(v18);
  if ( v26[0] != v27 )
    operator delete(v26[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v24[0] != v25 )
    operator delete(v24[0], (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x1800ed98c  mov     rax, rsp
0x1800ed98f  mov     [rax+8], rbx
0x1800ed993  mov     [rax+18h], rsi
0x1800ed997  mov     [rax+10h], rdx
0x1800ed99b  push    rbp
0x1800ed99c  push    rdi
0x1800ed99d  push    r12
0x1800ed99f  push    r14
0x1800ed9a1  push    r15
0x1800ed9a3  lea     rbp, [rax-5Fh]
0x1800ed9a7  sub     rsp, 90h
0x1800ed9ae  lea     rax, [rbp+57h+var_50]
0x1800ed9b2  mov     rsi, rcx
0x1800ed9b5  mov     [rbp+57h+var_60], rax
0x1800ed9b9  lea     rcx, [rbp+57h+var_60]
0x1800ed9bd  lea     rax, [rbp+57h+var_50]
0x1800ed9c1  mov     [rbp+57h+var_58], rax
0x1800ed9c5  xor     eax, eax
0x1800ed9c7  mov     [rbp+57h+var_50], ax
0x1800ed9cb  call    Container__Manager__Core__Details___anonymous_namespace___GetRootBaseImagesPath
0x1800ed9d0  mov     ebx, eax
0x1800ed9d2  test    eax, eax
0x1800ed9d4  jns     short loc_1800EDA0E
0x1800ed9d6  mov     edx, 4E1h; void *
0x1800ed9db  mov     rcx, [rbp+5Fh]; this
0x1800ed9df  lea     r8, aOnecoreBaseGen_31; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800ed9e6  mov     r9d, ebx; char *
0x1800ed9e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ed9ee  mov     rcx, [rbp+57h+var_60]; void *
0x1800ed9f2  lea     rax, [rbp+57h+var_50]
0x1800ed9f6  cmp     rcx, rax
0x1800ed9f9  jz      short loc_1800EDA07
0x1800ed9fb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800eda02  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800eda07  mov     eax, ebx
0x1800eda09  jmp     loc_1800EDC91
0x1800eda0e  xor     edx, edx; struct Path *
0x1800eda10  lea     rcx, [rbp+57h+var_60]; this
0x1800eda14  call    ?CreateDirectoryRecursive@Csl@@YAJAEBVPath@1@PEAU_SECURITY_ATTRIBUTES@@@Z; Csl::CreateDirectoryRecursive(Csl::Path const &,_SECURITY_ATTRIBUTES *)
0x1800eda19  mov     ebx, eax
0x1800eda1b  test    eax, eax
0x1800eda1d  jns     short loc_1800EDA26
0x1800eda1f  mov     edx, 4E3h
0x1800eda24  jmp     short loc_1800ED9DB
0x1800eda26  mov     rdx, cs:?g_registryRoot@Core@Manager@Container@@3VPath@Csl@@A; Csl::Path Container::Manager::Core::g_registryRoot
0x1800eda2d  lea     rax, [rbp+57h+var_30]
0x1800eda31  mov     r8, cs:off_18021E510
0x1800eda38  lea     rcx, [rbp+57h+var_40]
0x1800eda3c  mov     [rbp+57h+var_40], rax
0x1800eda40  sub     r8, rdx
0x1800eda43  lea     rax, [rbp+57h+var_30]
0x1800eda47  sar     r8, 1
0x1800eda4a  mov     [rbp+57h+var_38], rax
0x1800eda4e  xor     eax, eax
0x1800eda50  mov     [rbp+57h+var_30], ax
0x1800eda54  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800eda59  test    al, al
0x1800eda5b  jnz     short loc_1800EDA64
0x1800eda5d  mov     edx, 4E7h
0x1800eda62  jmp     short loc_1800EDA8D
0x1800eda64  lea     rax, aImages; "Images"
0x1800eda6b  mov     [rbp+57h+var_68], 6
0x1800eda73  lea     rdx, [rbp+57h+var_70]
0x1800eda77  mov     [rbp+57h+var_70], rax
0x1800eda7b  lea     rcx, [rbp+57h+var_40]; this
0x1800eda7f  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1800eda84  test    al, al
0x1800eda86  jnz     short loc_1800EDADF
0x1800eda88  mov     edx, 4E8h; void *
0x1800eda8d  mov     rcx, [rbp+5Fh]; this
0x1800eda91  lea     r8, aOnecoreBaseGen_31; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800eda98  mov     r9d, 8007000Eh; char *
0x1800eda9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800edaa3  mov     rcx, [rbp+57h+var_40]; void *
0x1800edaa7  lea     rax, [rbp+57h+var_30]
0x1800edaab  cmp     rcx, rax
0x1800edaae  jz      short loc_1800EDABC
0x1800edab0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800edab7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800edabc  mov     rcx, [rbp+57h+var_60]; void *
0x1800edac0  lea     rax, [rbp+57h+var_50]
0x1800edac4  cmp     rcx, rax
0x1800edac7  jz      short loc_1800EDAD5
0x1800edac9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800edad0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800edad5  mov     eax, 8007000Eh
0x1800edada  jmp     loc_1800EDC91
0x1800edadf  mov     rdx, [rbp+57h+var_40]
0x1800edae3  lea     rax, [rbp+57h+arg_8]
0x1800edae7  lea     r9, [rbp+57h+hKey]
0x1800edaeb  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x1800edaf0  mov     r8d, 2001Fh
0x1800edaf6  mov     [rbp+57h+hKey], 0
0x1800edafe  mov     byte ptr [rbp+57h+arg_8], 0
0x1800edb02  call    ?CreateRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@AEA_N@Z; Csl::CreateRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &,bool &)
0x1800edb07  mov     ebx, eax
0x1800edb09  test    eax, eax
0x1800edb0b  jns     short loc_1800EDB5C
0x1800edb0d  mov     rcx, [rbp+5Fh]; this
0x1800edb11  lea     r8, aOnecoreBaseGen_31; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800edb18  mov     r9d, eax; char *
0x1800edb1b  mov     edx, 4EFh; void *
0x1800edb20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800edb25  mov     rcx, [rbp+57h+hKey]; hKey
0x1800edb29  test    rcx, rcx
0x1800edb2c  jz      short loc_1800EDB3A
0x1800edb2e  call    cs:__imp_RegCloseKey
0x1800edb35  nop     dword ptr [rax+rax+00h]
0x1800edb3a  mov     rcx, [rbp+57h+var_40]; void *
0x1800edb3e  lea     rax, [rbp+57h+var_30]
0x1800edb42  cmp     rcx, rax
0x1800edb45  jz      loc_1800ED9EE
0x1800edb4b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800edb52  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800edb57  jmp     loc_1800ED9EE
0x1800edb5c  xor     r8d, r8d; pcbe
0x1800edb5f  lea     rcx, ?CleanupLegacyBaseImagesWork@BaseImageManager@Details@Core@Manager@Container@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800edb66  mov     rdx, rsi; pv
0x1800edb69  call    cs:__imp_CreateThreadpoolWork
0x1800edb70  nop     dword ptr [rax+rax+00h]
0x1800edb75  mov     rbx, rax
0x1800edb78  test    rax, rax
0x1800edb7b  jnz     short loc_1800EDB96
0x1800edb7d  mov     rcx, [rbp+5Fh]; this
0x1800edb81  lea     r8, aOnecoreBaseGen_31; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800edb88  mov     edx, 4F8h; void *
0x1800edb8d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800edb92  mov     ebx, eax
0x1800edb94  jmp     short loc_1800EDB25
0x1800edb96  lea     r14, [rsi+8]
0x1800edb9a  lea     rax, [rbp+57h+var_78]
0x1800edb9e  cmp     r14, rax
0x1800edba1  jz      short loc_1800EDBDB
0x1800edba3  mov     r15, [r14]
0x1800edba6  test    r15, r15
0x1800edba9  jz      short loc_1800EDBD6
0x1800edbab  call    cs:__imp_GetLastError
0x1800edbb2  nop     dword ptr [rax+rax+00h]
0x1800edbb7  mov     rcx, r15; pwk
0x1800edbba  mov     edi, eax
0x1800edbbc  call    cs:__imp_CloseThreadpoolWork
0x1800edbc3  nop     dword ptr [rax+rax+00h]
0x1800edbc8  mov     ecx, edi; dwErrCode
0x1800edbca  call    cs:__imp_SetLastError
0x1800edbd1  nop     dword ptr [rax+rax+00h]
0x1800edbd6  mov     [r14], rbx
0x1800edbd9  xor     ebx, ebx
0x1800edbdb  lea     rax, [rbp+57h+hKey]
0x1800edbdf  cmp     rsi, rax
0x1800edbe2  jz      short loc_1800EDC22
0x1800edbe4  mov     r15, [rsi]
0x1800edbe7  mov     r12, [rbp+57h+hKey]
0x1800edbeb  test    r15, r15
0x1800edbee  jz      short loc_1800EDC1B
0x1800edbf0  call    cs:__imp_GetLastError
0x1800edbf7  nop     dword ptr [rax+rax+00h]
0x1800edbfc  mov     rcx, r15; hKey
0x1800edbff  mov     edi, eax
0x1800edc01  call    cs:__imp_RegCloseKey
0x1800edc08  nop     dword ptr [rax+rax+00h]
0x1800edc0d  mov     ecx, edi; dwErrCode
0x1800edc0f  call    cs:__imp_SetLastError
0x1800edc16  nop     dword ptr [rax+rax+00h]
0x1800edc1b  mov     [rsi], r12
0x1800edc1e  xor     edi, edi
0x1800edc20  jmp     short loc_1800EDC26
0x1800edc22  mov     rdi, [rbp+57h+hKey]
0x1800edc26  mov     rcx, [r14]; pwk
0x1800edc29  call    cs:__imp_SubmitThreadpoolWork
0x1800edc30  nop     dword ptr [rax+rax+00h]
0x1800edc35  test    rbx, rbx
0x1800edc38  jz      short loc_1800EDC49
0x1800edc3a  mov     rcx, rbx; pwk
0x1800edc3d  call    cs:__imp_CloseThreadpoolWork
0x1800edc44  nop     dword ptr [rax+rax+00h]
0x1800edc49  test    rdi, rdi
0x1800edc4c  jz      short loc_1800EDC5D
0x1800edc4e  mov     rcx, rdi; hKey
0x1800edc51  call    cs:__imp_RegCloseKey
0x1800edc58  nop     dword ptr [rax+rax+00h]
0x1800edc5d  mov     rcx, [rbp+57h+var_40]; void *
0x1800edc61  lea     rax, [rbp+57h+var_30]
0x1800edc65  cmp     rcx, rax
0x1800edc68  jz      short loc_1800EDC76
0x1800edc6a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800edc71  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800edc76  mov     rcx, [rbp+57h+var_60]; void *
0x1800edc7a  lea     rax, [rbp+57h+var_50]
0x1800edc7e  cmp     rcx, rax
0x1800edc81  jz      short loc_1800EDC8F
0x1800edc83  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800edc8a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800edc8f  xor     eax, eax
0x1800edc91  lea     r11, [rsp+0B0h+var_20]
0x1800edc99  mov     rbx, [r11+30h]
0x1800edc9d  mov     rsi, [r11+40h]
0x1800edca1  mov     rsp, r11
0x1800edca4  pop     r15
0x1800edca6  pop     r14
0x1800edca8  pop     r12
0x1800edcaa  pop     rdi
0x1800edcab  pop     rbp
0x1800edcac  retn
```
