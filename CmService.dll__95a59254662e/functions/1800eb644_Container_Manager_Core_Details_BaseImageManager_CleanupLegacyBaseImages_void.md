# Container::Manager::Core::Details::BaseImageManager::CleanupLegacyBaseImages(void)

- ea: `0x1800eb644`
- end: `0x1800ebca6`
- name: `?CleanupLegacyBaseImages@BaseImageManager@Details@Core@Manager@Container@@AEAAJXZ`
- size: `1634`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::BaseImageManager *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800ebcb0`

## callees

- `0x180004fc4`
- `0x180005704`
- `0x18000da88`
- `0x18000dab0`
- `0x18002d30c`
- `0x18002dc0c`
- `0x18002fc34`
- `0x180032344`
- `0x180032eb4`
- `0x180033f84`
- `0x1800343f0`
- `0x18003dbf8`
- `0x18003f7d8`
- `0x1800471dc`
- `0x180049a0c`
- `0x1800eb644`
- `0x180194378`
- `0x18019539c`
- `0x180195674`

## import_xrefs

- `ntdll!NtSetInformationJobObject` at `0x1800eb8ff`
- `ntdll!NtSetInformationJobObject` at `0x1800eb8ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eba5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ebc13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ebc4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eba5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ebc13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ebc4e`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800eb7c6`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800eb991`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800eb7c6`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800eb991`

## string_xrefs

- `0x1800eb7fe`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`
- `0x1800eb9c5`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`
- `0x1800eb7ef`: `Failed to delete subkey with name '%ws'`
- `0x1800eb9b6`: `Failed to delete subkey with name '%ws'`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Container::Manager::Core::Details::BaseImageManager::CleanupLegacyBaseImages(HKEY *this)
{
  __m128i si128; // xmm6
  int v3; // eax
  unsigned int v4; // ebx
  LPCWSTR *i; // rbx
  bool v6; // r14
  int StringValue; // esi
  int v8; // eax
  const char *v9; // rsi
  unsigned int v10; // eax
  unsigned int v11; // eax
  const char *v12; // r9
  int v13; // eax
  int *v14; // rsi
  LPCWSTR v15; // rsi
  unsigned int v16; // eax
  struct _PROCESS_INFORMATION *v17; // rdx
  void *v18; // rsi
  __int64 v19; // rdx
  __int64 v20; // rdx
  struct _PROCESS_INFORMATION *v21; // rdx
  void *v22; // rbx
  int v24; // [rsp+28h] [rbp-E0h]
  void *v25; // [rsp+38h] [rbp-D0h] BYREF
  char *v26; // [rsp+40h] [rbp-C8h]
  __int16 v27; // [rsp+48h] [rbp-C0h] BYREF
  void *v28[2]; // [rsp+58h] [rbp-B0h] BYREF
  utl::_RefCountBase *v29; // [rsp+68h] [rbp-A0h]
  void *v30[2]; // [rsp+70h] [rbp-98h] BYREF
  _WORD v31[8]; // [rsp+80h] [rbp-88h] BYREF
  __m128i v32; // [rsp+90h] [rbp-78h] BYREF
  __int64 v33; // [rsp+A0h] [rbp-68h]
  __m128i v34; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v35; // [rsp+B8h] [rbp-50h]
  _QWORD v36[5]; // [rsp+C0h] [rbp-48h] BYREF
  _QWORD pv[2]; // [rsp+E8h] [rbp-20h] BYREF
  _WORD v38[8]; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v39; // [rsp+108h] [rbp+0h]
  HANDLE JobHandle[2]; // [rsp+118h] [rbp+10h]
  __int128 v41; // [rsp+128h] [rbp+20h]
  __int64 v42; // [rsp+138h] [rbp+30h]
  __int128 v43; // [rsp+148h] [rbp+40h]
  __int128 v44; // [rsp+158h] [rbp+50h]
  __int64 v45; // [rsp+168h] [rbp+60h]
  _BYTE JobInformation[36]; // [rsp+178h] [rbp+70h] BYREF
  int v47; // [rsp+19Ch] [rbp+94h]
  __int64 v48; // [rsp+1E8h] [rbp+E0h]
  wil::details::in1diag3 *retaddr; // [rsp+240h] [rbp+138h]
  HKEY hKey; // [rsp+248h] [rbp+140h] BYREF

  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v34 = si128;
  v35 = -1;
  v3 = Csl::RegistryKey::EnumerateSubkeys(this, &v34);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
      (const char *)(unsigned int)v3,
      v24);
    goto LABEL_75;
  }
  for ( i = (LPCWSTR *)v34.m128i_i64[0]; ; i += 4 )
  {
    if ( i == (LPCWSTR *)v34.m128i_i64[1] )
    {
      v4 = 0;
      goto LABEL_75;
    }
    v32 = si128;
    v33 = -1;
    v36[0] = *i;
    v36[1] = ((__int64)i[1] - v36[0]) >> 1;
    if ( (unsigned __int8)Csl::StringSplit(v36, 45, &v32) )
    {
      StringValue = 0;
      v6 = v32.m128i_i64[1] - v32.m128i_i64[0] == 64;
    }
    else
    {
      v6 = 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
        (const char *)0x8007000ELL,
        v24);
      StringValue = -2147024882;
    }
    utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(&v32);
    if ( StringValue < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x534,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
        (const char *)(unsigned int)StringValue,
        v24);
      goto LABEL_73;
    }
    if ( v6 )
      break;
LABEL_39:
    ;
  }
  hKey = 0;
  v8 = Csl::OpenRegistryKey(*this, *i, 131103, &hKey);
  StringValue = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53D,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
      (const char *)(unsigned int)v8,
      v24);
    goto LABEL_70;
  }
  v25 = &v27;
  v26 = (char *)&v27;
  v27 = 0;
  StringValue = Csl::RegistryKey::GetStringValue(&hKey, L"Path", &v25);
  if ( StringValue == -2147024894 )
  {
    v9 = (const char *)*i;
    v10 = RegDeleteKeyW(*this, *i);
    if ( v10 != 2 )
    {
      if ( v10 )
      {
        StringValue = wil::details::in1diag3::Return_Win32Msg(
                        retaddr,
                        (void *)0x10B,
                        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslregistry.cpp",
                        (const char *)v10,
                        (unsigned int)"Failed to delete subkey with name '%ws'",
                        v9);
        if ( StringValue < 0 )
          goto LABEL_41;
      }
LABEL_35:
      if ( v25 != &v27 )
        operator delete(v25, (const struct std::nothrow_t *)&std::nothrow);
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_39;
    }
    StringValue = -2147024894;
LABEL_41:
    v19 = 1353;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
      (const char *)(unsigned int)StringValue,
      v24);
    goto LABEL_43;
  }
  if ( StringValue < 0 )
  {
    v19 = 1359;
    goto LABEL_42;
  }
  v30[0] = v31;
  v30[1] = v31;
  v31[0] = 0;
  v36[2] = v25;
  v36[3] = (v26 - (_BYTE *)v25) >> 1;
  if ( (unsigned __int8)Csl::Path::Assign((Csl::Path *)v30) )
  {
    pv[0] = v38;
    pv[1] = v38;
    v38[0] = 0;
    v39 = 0;
    *(_OWORD *)JobHandle = 0;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = 0;
    LOBYTE(v43) = 0;
    StringValue = Container::Manager::CmImageWorker::Initialize(
                    pv,
                    (const struct Container::Manager::CmImageWorkerCleanupContext *)v30);
    if ( StringValue < 0 )
    {
      v20 = 1368;
      goto LABEL_59;
    }
    memset_0(JobInformation, 0, 0x90u);
    v48 = 10;
    v47 = 1;
    v11 = NtSetInformationJobObject(
            JobHandle[0],
            MaxJobObjectInfoClass|JobObjectBasicProcessIdList|0x10,
            JobInformation,
            0x90u);
    v12 = 0;
    if ( v11 != -1073741822 )
      v12 = (const char *)v11;
    if ( (int)v12 < 0 )
    {
      StringValue = wil::details::in1diag3::Return_NtStatus(
                      retaddr,
                      (void *)0x2B8,
                      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimageworker\\lib\\cmimageworker.cpp",
                      v12,
                      v24);
      if ( StringValue < 0 )
      {
        v20 = 1371;
LABEL_59:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
          (const char *)(unsigned int)StringValue,
          v24);
        goto LABEL_60;
      }
    }
    *(_OWORD *)v28 = 0;
    v29 = 0;
    v13 = Container::Manager::CmImageWorker::Start((__int64)pv, (__int64)v28);
    StringValue = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x55F,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
        (const char *)(unsigned int)v13,
        v24);
      Csl::AsyncOperation<void>::Cleanup(v28);
      if ( v29 )
        utl::_RefCountBase::_DecStrong(v29);
      goto LABEL_56;
    }
    v14 = (int *)v28[1];
    if ( !(unsigned __int8)wil::slim_event_t<1>::wait((char *)v28[1] + 4) )
    {
      StringValue = -2147023436;
LABEL_51:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x562,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
        (const char *)(unsigned int)StringValue,
        v24);
      Csl::AsyncOperation<void>::Cleanup(v28);
      if ( v29 )
        utl::_RefCountBase::_DecStrong(v29);
      goto LABEL_56;
    }
    StringValue = *v14;
    if ( StringValue < 0 )
      goto LABEL_51;
    v15 = *i;
    v16 = RegDeleteKeyW(*this, *i);
    if ( v16 == 2 )
    {
      StringValue = -2147024894;
LABEL_47:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x565,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
        (const char *)(unsigned int)StringValue,
        v24);
      Csl::AsyncOperation<void>::Cleanup(v28);
      if ( v29 )
        utl::_RefCountBase::_DecStrong(v29);
LABEL_56:
      v22 = v28[0];
      if ( v28[0] )
      {
        Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>((_DWORD *)v28[0]);
        operator delete(v22, (const struct std::nothrow_t *)0x30);
      }
LABEL_60:
      Container::Manager::CmImageWorker::~CmImageWorker((Container::Manager::CmImageWorker *)pv, v21);
      if ( v30[0] != v31 )
        operator delete(v30[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_43:
      if ( v25 != &v27 )
        operator delete(v25, (const struct std::nothrow_t *)&std::nothrow);
LABEL_70:
      if ( hKey )
        RegCloseKey(hKey);
LABEL_73:
      v4 = StringValue;
      goto LABEL_75;
    }
    if ( v16 )
    {
      StringValue = wil::details::in1diag3::Return_Win32Msg(
                      retaddr,
                      (void *)0x10B,
                      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslregistry.cpp",
                      (const char *)v16,
                      (unsigned int)"Failed to delete subkey with name '%ws'",
                      (const char *)v15);
      if ( StringValue < 0 )
        goto LABEL_47;
    }
    Csl::AsyncOperation<void>::Cleanup(v28);
    if ( v29 )
      utl::_RefCountBase::_DecStrong(v29);
    v18 = v28[0];
    if ( v28[0] )
    {
      Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>((_DWORD *)v28[0]);
      operator delete(v18, (const struct std::nothrow_t *)0x30);
    }
    Container::Manager::CmImageWorker::~CmImageWorker((Container::Manager::CmImageWorker *)pv, v17);
    if ( v30[0] != v31 )
      operator delete(v30[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_35;
  }
  v4 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x554,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
    (const char *)0x8007000ELL,
    v24);
  if ( v30[0] != v31 )
    operator delete(v30[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v25 != &v27 )
    operator delete(v25, (const struct std::nothrow_t *)&std::nothrow);
  if ( hKey )
    RegCloseKey(hKey);
LABEL_75:
  utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(&v34);
  return v4;
}

```

## disassembly

```asm
0x1800eb644  mov     rax, rsp
0x1800eb647  mov     [rax+10h], rbx
0x1800eb64b  mov     [rax+18h], rsi
0x1800eb64f  push    rbp
0x1800eb650  push    rdi
0x1800eb651  push    r13
0x1800eb653  push    r14
0x1800eb655  push    r15
0x1800eb657  lea     rbp, [rax-138h]
0x1800eb65e  sub     rsp, 210h
0x1800eb665  movaps  xmmword ptr [rax-38h], xmm6
0x1800eb669  mov     r15, rcx
0x1800eb66c  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800eb674  movdqu  [rbp+130h+var_190], xmm6
0x1800eb679  mov     [rbp+130h+var_180], 0FFFFFFFFFFFFFFFFh
0x1800eb681  lea     rdx, [rbp+130h+var_190]
0x1800eb685  call    ?EnumerateSubkeys@RegistryKey@Csl@@QEBAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z; Csl::RegistryKey::EnumerateSubkeys(utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x1800eb68a  mov     ebx, eax
0x1800eb68c  test    eax, eax
0x1800eb68e  jns     short loc_1800EB6B0
0x1800eb690  mov     rcx, [rbp+138h]; this
0x1800eb697  mov     r9d, eax; char *
0x1800eb69a  lea     r8, aOnecoreBaseGen_31; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800eb6a1  mov     edx, 52Eh; void *
0x1800eb6a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eb6ab  jmp     loc_1800EBC79
0x1800eb6b0  mov     rbx, qword ptr [rbp+130h+var_190]
0x1800eb6b4  lea     rdi, aOnecoreBaseGen_31; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800eb6bb  lea     r13, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800eb6c2  cmp     rbx, qword ptr [rbp+130h+var_190+8]
0x1800eb6c6  jz      loc_1800EBC77
0x1800eb6cc  movdqu  [rbp+130h+var_1A8], xmm6
0x1800eb6d1  mov     [rbp+130h+var_198], 0FFFFFFFFFFFFFFFFh
0x1800eb6d9  mov     rax, [rbx]
0x1800eb6dc  mov     [rbp+130h+var_178], rax
0x1800eb6e0  mov     rcx, [rbx+8]
0x1800eb6e4  sub     rcx, rax
0x1800eb6e7  sar     rcx, 1
0x1800eb6ea  mov     [rbp+130h+var_170], rcx
0x1800eb6ee  mov     edx, 2Dh ; '-'
0x1800eb6f3  lea     r8, [rbp+130h+var_1A8]
0x1800eb6f7  lea     rcx, [rbp+130h+var_178]
0x1800eb6fb  call    ?StringSplit@Csl@@YA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@GAEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@3@@Z; Csl::StringSplit(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,ushort,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x1800eb700  test    al, al
0x1800eb702  jnz     short loc_1800EB728
0x1800eb704  xor     r14b, r14b
0x1800eb707  mov     rcx, [rbp+138h]; this
0x1800eb70e  mov     r9d, 8007000Eh; char *
0x1800eb714  mov     r8, rdi; unsigned int
0x1800eb717  mov     edx, 67h ; 'g'; void *
0x1800eb71c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eb721  mov     esi, 8007000Eh
0x1800eb726  jmp     short loc_1800EB73A
0x1800eb728  xor     esi, esi
0x1800eb72a  mov     rax, qword ptr [rbp+130h+var_1A8+8]
0x1800eb72e  sub     rax, qword ptr [rbp+130h+var_1A8]
0x1800eb732  cmp     rax, 40h ; '@'
0x1800eb736  setz    r14b
0x1800eb73a  lea     rcx, [rbp+130h+var_1A8]
0x1800eb73e  call    ?_Uninit@?$vector@UOverlayDirectory@Details@Core@Manager@Container@@V?$allocator@UOverlayDirectory@Details@Core@Manager@Container@@@utl@@@utl@@AEAAXXZ; utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(void)
0x1800eb743  test    esi, esi
0x1800eb745  js      loc_1800EBC5C
0x1800eb74b  test    r14b, r14b
0x1800eb74e  jz      loc_1800EBA69
0x1800eb754  mov     [rbp+130h+hKey], 0
0x1800eb75f  lea     r9, [rbp+130h+hKey]
0x1800eb766  mov     r8d, 2001Fh
0x1800eb76c  mov     rdx, [rbx]
0x1800eb76f  mov     rcx, [r15]
0x1800eb772  call    ?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x1800eb777  mov     esi, eax
0x1800eb779  test    eax, eax
0x1800eb77b  js      loc_1800EBC2B
0x1800eb781  lea     rax, [rsp+230h+var_1F0]
0x1800eb786  mov     [rsp+230h+var_200], rax
0x1800eb78b  lea     rax, [rsp+230h+var_1F0]
0x1800eb790  mov     [rsp+230h+var_1F8], rax
0x1800eb795  xor     eax, eax
0x1800eb797  mov     [rsp+230h+var_1F0], ax
0x1800eb79c  lea     r8, [rsp+230h+var_200]
0x1800eb7a1  lea     rdx, aPath; "Path"
0x1800eb7a8  lea     rcx, [rbp+130h+hKey]
0x1800eb7af  call    ?GetStringValue@RegistryKey@Csl@@QEBAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::RegistryKey::GetStringValue(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1800eb7b4  mov     esi, eax
0x1800eb7b6  cmp     eax, 80070002h
0x1800eb7bb  jnz     short loc_1800EB81E
0x1800eb7bd  mov     rsi, [rbx]
0x1800eb7c0  mov     rdx, rsi; lpSubKey
0x1800eb7c3  mov     rcx, [r15]; hKey
0x1800eb7c6  call    cs:__imp_RegDeleteKeyW
0x1800eb7cd  nop     dword ptr [rax+rax+00h]
0x1800eb7d2  cmp     eax, 2
0x1800eb7d5  jz      loc_1800EBA72
0x1800eb7db  test    eax, eax
0x1800eb7dd  jz      loc_1800EBA3A
0x1800eb7e3  mov     rcx, [rbp+138h]; this
0x1800eb7ea  mov     [rsp+230h+var_208], rsi; char *
0x1800eb7ef  lea     rdx, aFailedToDelete_0; "Failed to delete subkey with name '%ws'"
0x1800eb7f6  mov     qword ptr [rsp+230h+var_210], rdx; unsigned int
0x1800eb7fb  mov     r9d, eax; char *
0x1800eb7fe  lea     r8, aOnecoreBaseGen_77; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800eb805  mov     edx, 10Bh; void *
0x1800eb80a  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800eb80f  mov     esi, eax
0x1800eb811  test    eax, eax
0x1800eb813  js      loc_1800EBA77
0x1800eb819  jmp     loc_1800EBA3A
0x1800eb81e  test    esi, esi
0x1800eb820  js      loc_1800EBC21
0x1800eb826  lea     rax, [rsp+230h+var_1B8]
0x1800eb82b  mov     [rsp+230h+var_1C8], rax
0x1800eb830  lea     rax, [rsp+230h+var_1B8]
0x1800eb835  mov     qword ptr [rsp+230h+var_1C0], rax
0x1800eb83a  xor     eax, eax
0x1800eb83c  mov     [rsp+230h+var_1B8], ax
0x1800eb841  mov     rax, [rsp+230h+var_200]
0x1800eb846  mov     [rbp+130h+var_168], rax
0x1800eb84a  mov     rcx, [rsp+230h+var_1F8]
0x1800eb84f  sub     rcx, rax
0x1800eb852  sar     rcx, 1
0x1800eb855  mov     [rbp+130h+var_160], rcx
0x1800eb859  lea     rdx, [rbp+130h+var_168]
0x1800eb85d  lea     rcx, [rsp+230h+var_1C8]; this
0x1800eb862  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1800eb867  test    al, al
0x1800eb869  jz      loc_1800EBBBD
0x1800eb86f  lea     rax, [rbp+130h+var_140]
0x1800eb873  mov     [rbp+130h+pv], rax
0x1800eb877  lea     rax, [rbp+130h+var_140]
0x1800eb87b  mov     [rbp+130h+var_148], rax
0x1800eb87f  xor     eax, eax
0x1800eb881  mov     [rbp+130h+var_140], ax
0x1800eb885  xorps   xmm0, xmm0
0x1800eb888  movdqa  [rbp+130h+var_130], xmm0
0x1800eb88d  xorps   xmm1, xmm1
0x1800eb890  movdqa  xmmword ptr [rbp+130h+JobHandle], xmm1
0x1800eb895  movups  [rbp+130h+var_110], xmm0
0x1800eb899  mov     [rbp+130h+var_100], rax
0x1800eb89d  movups  [rbp+130h+var_F0], xmm1
0x1800eb8a1  movups  [rbp+130h+var_E0], xmm1
0x1800eb8a5  mov     [rbp+130h+var_D0], rax
0x1800eb8a9  mov     byte ptr [rbp+130h+var_F0], al
0x1800eb8ac  mov     byte ptr [rbp+130h+var_D0], al
0x1800eb8af  lea     rdx, [rsp+230h+var_1C8]; struct Container::Manager::CmImageWorkerCleanupContext *
0x1800eb8b4  lea     rcx, [rbp+130h+pv]; pv
0x1800eb8b8  call    ?Initialize@CmImageWorker@Manager@Container@@QEAAJAEBUCmImageWorkerCleanupContext@23@@Z; Container::Manager::CmImageWorker::Initialize(Container::Manager::CmImageWorkerCleanupContext const &)
0x1800eb8bd  mov     esi, eax
0x1800eb8bf  test    eax, eax
0x1800eb8c1  js      loc_1800EBB7D
0x1800eb8c7  mov     r14d, 90h
0x1800eb8cd  mov     r8d, r14d; Size
0x1800eb8d0  xor     edx, edx; Val
0x1800eb8d2  lea     rcx, [rbp+130h+JobInformation]; void *
0x1800eb8d6  call    memset_0
0x1800eb8db  mov     [rbp+130h+var_50], 0Ah
0x1800eb8e6  mov     [rbp+130h+var_9C], 1
0x1800eb8f0  mov     r9d, r14d; JobInformationLength
0x1800eb8f3  lea     r8, [rbp+130h+JobInformation]; JobInformation
0x1800eb8f7  lea     edx, [r14-71h]; JobInformationClass
0x1800eb8fb  mov     rcx, [rbp+130h+JobHandle]; JobHandle
0x1800eb8ff  call    cs:__imp_NtSetInformationJobObject
0x1800eb906  nop     dword ptr [rax+rax+00h]
0x1800eb90b  xor     r9d, r9d
0x1800eb90e  cmp     eax, 0C0000002h
0x1800eb913  cmovnz  r9d, eax; char *
0x1800eb917  test    r9d, r9d
0x1800eb91a  jns     short loc_1800EB93E
0x1800eb91c  mov     rcx, [rbp+138h]; this
0x1800eb923  lea     r8, aOnecoreBaseGen_16; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x1800eb92a  mov     edx, 2B8h; void *
0x1800eb92f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800eb934  mov     esi, eax
0x1800eb936  test    eax, eax
0x1800eb938  js      loc_1800EBAAE
0x1800eb93e  xorps   xmm0, xmm0
0x1800eb941  movdqu  xmmword ptr [rsp+230h+var_1E8+8], xmm0
0x1800eb947  mov     [rsp+230h+var_1D0], 0
0x1800eb950  lea     rdx, [rsp+230h+var_1E8+8]
0x1800eb955  lea     rcx, [rbp+130h+pv]
0x1800eb959  call    ?Start@CmImageWorker@Manager@Container@@QEAAJAEAV?$AsyncOperation@X@Csl@@@Z; Container::Manager::CmImageWorker::Start(Csl::AsyncOperation<void> &)
0x1800eb95e  mov     esi, eax
0x1800eb960  test    eax, eax
0x1800eb962  js      loc_1800EBB2A
0x1800eb968  mov     rsi, [rsp+230h+var_1D8]
0x1800eb96d  lea     rcx, [rsi+4]; Address
0x1800eb971  call    ?wait@?$slim_event_t@$00@wil@@QEAA_NXZ; wil::slim_event_t<1>::wait(void)
0x1800eb976  test    al, al
0x1800eb978  jz      loc_1800EBAF1
0x1800eb97e  mov     esi, [rsi]
0x1800eb980  test    esi, esi
0x1800eb982  js      loc_1800EBAF6
0x1800eb988  mov     rsi, [rbx]
0x1800eb98b  mov     rdx, rsi; lpSubKey
0x1800eb98e  mov     rcx, [r15]; hKey
0x1800eb991  call    cs:__imp_RegDeleteKeyW
0x1800eb998  nop     dword ptr [rax+rax+00h]
0x1800eb99d  cmp     eax, 2
0x1800eb9a0  jz      loc_1800EBAB8
0x1800eb9a6  test    eax, eax
0x1800eb9a8  jz      short loc_1800EB9E0
0x1800eb9aa  mov     rcx, [rbp+138h]; this
0x1800eb9b1  mov     [rsp+230h+var_208], rsi; char *
0x1800eb9b6  lea     rdx, aFailedToDelete_0; "Failed to delete subkey with name '%ws'"
0x1800eb9bd  mov     qword ptr [rsp+230h+var_210], rdx; unsigned int
0x1800eb9c2  mov     r9d, eax; char *
0x1800eb9c5  lea     r8, aOnecoreBaseGen_77; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800eb9cc  mov     edx, 10Bh; void *
0x1800eb9d1  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800eb9d6  mov     esi, eax
0x1800eb9d8  test    eax, eax
0x1800eb9da  js      loc_1800EBABD
0x1800eb9e0  lea     rcx, [rsp+230h+var_1E8+8]
0x1800eb9e5  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
0x1800eb9ea  nop
0x1800eb9eb  mov     rcx, [rsp+230h+var_1D0]; this
0x1800eb9f0  test    rcx, rcx
0x1800eb9f3  jz      short loc_1800EB9FB
0x1800eb9f5  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800eb9fa  nop
0x1800eb9fb  mov     rsi, [rsp+230h+var_1E8+8]
0x1800eba00  test    rsi, rsi
0x1800eba03  jz      short loc_1800EBA1A
0x1800eba05  mov     rcx, rsi
0x1800eba08  call    ??1?$AsyncOperationImpl@X@Details@Csl@@QEAA@XZ; Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(void)
0x1800eba0d  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x1800eba12  mov     rcx, rsi; void *
0x1800eba15  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800eba1a  lea     rcx, [rbp+130h+pv]; this
0x1800eba1e  call    ??1CmImageWorker@Manager@Container@@QEAA@XZ; Container::Manager::CmImageWorker::~CmImageWorker(void)
0x1800eba23  mov     rcx, [rsp+230h+var_1C8]; void *
0x1800eba28  lea     rax, [rsp+230h+var_1B8]
0x1800eba2d  cmp     rcx, rax
0x1800eba30  jz      short loc_1800EBA3A
0x1800eba32  mov     rdx, r13; struct std::nothrow_t *
0x1800eba35  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800eba3a  lea     rax, [rsp+230h+var_1F0]
0x1800eba3f  mov     rcx, [rsp+230h+var_200]; void *
0x1800eba44  cmp     rcx, rax
0x1800eba47  jz      short loc_1800EBA51
0x1800eba49  mov     rdx, r13; struct std::nothrow_t *
0x1800eba4c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800eba51  mov     rcx, [rbp+130h+hKey]; hKey
0x1800eba58  test    rcx, rcx
0x1800eba5b  jz      short loc_1800EBA69
0x1800eba5d  call    cs:__imp_RegCloseKey
0x1800eba64  nop     dword ptr [rax+rax+00h]
0x1800eba69  add     rbx, 20h ; ' '
0x1800eba6d  jmp     loc_1800EB6C2
0x1800eba72  mov     esi, 80070002h
0x1800eba77  mov     edx, 549h; void *
0x1800eba7c  mov     r8, rdi; unsigned int
0x1800eba7f  mov     r9d, esi; char *
0x1800eba82  mov     rcx, [rbp+138h]; this
0x1800eba89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eba8e  lea     rax, [rsp+230h+var_1F0]
0x1800eba93  mov     rcx, [rsp+230h+var_200]; void *
0x1800eba98  cmp     rcx, rax
0x1800eba9b  jz      loc_1800EBC42
0x1800ebaa1  mov     rdx, r13; struct std::nothrow_t *
0x1800ebaa4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ebaa9  jmp     loc_1800EBC42
0x1800ebaae  mov     edx, 55Bh
0x1800ebab3  jmp     loc_1800EBB82
0x1800ebab8  mov     esi, 80070002h
0x1800ebabd  mov     rcx, [rbp+138h]; this
0x1800ebac4  mov     r9d, esi; char *
0x1800ebac7  mov     r8, rdi; unsigned int
0x1800ebaca  mov     edx, 565h; void *
0x1800ebacf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ebad4  lea     rcx, [rsp+230h+var_1E8+8]
0x1800ebad9  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
0x1800ebade  nop
0x1800ebadf  mov     rcx, [rsp+230h+var_1D0]; this
0x1800ebae4  test    rcx, rcx
0x1800ebae7  jz      short loc_1800EBAEF
0x1800ebae9  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800ebaee  nop
0x1800ebaef  jmp     short loc_1800EBB5C
0x1800ebaf1  mov     esi, 800705B4h
0x1800ebaf6  mov     rcx, [rbp+138h]; this
0x1800ebafd  mov     r9d, esi; char *
0x1800ebb00  mov     r8, rdi; unsigned int
0x1800ebb03  mov     edx, 562h; void *
0x1800ebb08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ebb0d  lea     rcx, [rsp+230h+var_1E8+8]
0x1800ebb12  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
0x1800ebb17  nop
0x1800ebb18  mov     rcx, [rsp+230h+var_1D0]; this
0x1800ebb1d  test    rcx, rcx
0x1800ebb20  jz      short loc_1800EBB28
0x1800ebb22  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800ebb27  nop
0x1800ebb28  jmp     short loc_1800EBB5C
0x1800ebb2a  mov     rcx, [rbp+138h]; this
0x1800ebb31  mov     r9d, esi; char *
0x1800ebb34  mov     r8, rdi; unsigned int
0x1800ebb37  mov     edx, 55Fh; void *
0x1800ebb3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ebb41  lea     rcx, [rsp+230h+var_1E8+8]
0x1800ebb46  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
  ... truncated ...
```
