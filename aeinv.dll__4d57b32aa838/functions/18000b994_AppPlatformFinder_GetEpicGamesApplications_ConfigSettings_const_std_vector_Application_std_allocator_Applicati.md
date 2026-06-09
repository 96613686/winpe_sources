# AppPlatformFinder::GetEpicGamesApplications(ConfigSettings const &,std::vector<Application,std::allocator<Application>> &)

- ea: `0x18000b994`
- end: `0x18000c20e`
- name: `?GetEpicGamesApplications@AppPlatformFinder@@CAXAEBVConfigSettings@@AEAV?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@@Z`
- size: `2170`
- prototype: `__int64 __fastcall(struct ConfigSettings *, __int64)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180104368`

## callees

- `0x1800056f0`
- `0x18000b364`
- `0x18000b7cc`
- `0x18000b994`
- `0x18000c220`
- `0x18000c24c`
- `0x18000d8e8`
- `0x1800118d0`
- `0x1800175b0`
- `0x180017c98`
- `0x180018450`
- `0x180018a60`
- `0x1800197d4`
- `0x18001becc`
- `0x180022340`
- `0x180022500`
- `0x1800404c4`
- `0x180040500`
- `0x180044c88`
- `0x180044d04`
- `0x180045468`
- `0x180046c78`
- `0x18004e93c`
- `0x180059920`
- `0x18005a8bc`
- `0x18005d690`
- `0x1800679f8`
- `0x1800f7e8c`
- `0x1801146d0`

## import_xrefs

- `KERNEL32!FindFirstFileW` at `0x18000baf0`
- `KERNEL32!FindFirstFileW` at `0x18000baf0`
- `KERNEL32!FindNextFileW` at `0x18000c0f2`
- `KERNEL32!FindNextFileW` at `0x18000c0f2`
- `KERNEL32!FindClose` at `0x18000c1f3`
- `KERNEL32!FindClose` at `0x18000c1f3`
- `KERNEL32!GetFileAttributesW` at `0x18000ba5f`
- `KERNEL32!GetFileAttributesW` at `0x18000ba5f`
- `KERNEL32!LocalFree` at `0x18000c1df`
- `KERNEL32!LocalFree` at `0x18000c202`
- `KERNEL32!LocalFree` at `0x18000c1df`
- `KERNEL32!LocalFree` at `0x18000c202`

## string_xrefs

- `0x18000bc7c`: `"InstallLocation"`
- `0x18000ba35`: `\Epic\EpicGamesLauncher\Data\Manifests`
- `0x18000c115`: `Failed to open Epic Games manifest file %ws`
- `0x18000babb`: `base\appcompat\inventory\software\inv2\lib\appplatformfinder.cpp`

## pseudocode

```c
__int64 __fastcall AppPlatformFinder::GetEpicGamesApplications(struct ConfigSettings *a1, __int64 a2)
{
  __int128 v3; // xmm0
  const WCHAR *v4; // rcx
  const WCHAR *v5; // rcx
  int v6; // eax
  WCHAR *v7; // rdi
  char *FirstFileW; // r14
  const WCHAR *v9; // rcx
  int v10; // eax
  HLOCAL v11; // rbx
  __int128 v12; // xmm0
  char v13; // r12
  char v14; // r13
  char v15; // si
  __int128 v16; // xmm0
  struct ConfigSettings *v17; // rdi
  __int64 v18; // rax
  __int64 v19; // rax
  unsigned __int16 *v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  unsigned __int16 *v24; // rax
  __int64 v25; // rax
  __int128 *v26; // r9
  __int128 *v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  unsigned __int16 *v30; // rax
  __int64 v31; // rax
  const struct Application *v32; // rax
  int v34; // [rsp+28h] [rbp-E0h]
  LPCWSTR v35; // [rsp+38h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-C8h] BYREF
  char *v37; // [rsp+48h] [rbp-C0h] BYREF
  struct ConfigSettings *v38; // [rsp+50h] [rbp-B8h]
  __int64 v39; // [rsp+58h] [rbp-B0h]
  _QWORD v40[34]; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v41; // [rsp+178h] [rbp+70h] BYREF
  unsigned __int64 v42; // [rsp+188h] [rbp+80h]
  unsigned __int64 v43; // [rsp+190h] [rbp+88h]
  LPCWSTR lpFileName[3]; // [rsp+198h] [rbp+90h] BYREF
  unsigned __int64 v45; // [rsp+1B0h] [rbp+A8h]
  _BYTE v46[32]; // [rsp+1B8h] [rbp+B0h] BYREF
  _OWORD Src[2]; // [rsp+1D8h] [rbp+D0h] BYREF
  __int128 v48; // [rsp+1F8h] [rbp+F0h] BYREF
  __int64 v49; // [rsp+208h] [rbp+100h]
  unsigned __int64 v50; // [rsp+210h] [rbp+108h]
  _OWORD v51[2]; // [rsp+218h] [rbp+110h] BYREF
  _OWORD v52[2]; // [rsp+238h] [rbp+130h] BYREF
  _BYTE v53[16]; // [rsp+258h] [rbp+150h] BYREF
  __int128 v54; // [rsp+278h] [rbp+170h] BYREF
  __int128 v55; // [rsp+288h] [rbp+180h]
  __int128 v56; // [rsp+298h] [rbp+190h] BYREF
  __int128 v57; // [rsp+2A8h] [rbp+1A0h]
  _OWORD v58[2]; // [rsp+2B8h] [rbp+1B0h] BYREF
  _OWORD v59[2]; // [rsp+2D8h] [rbp+1D0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+2F8h] [rbp+1F0h] BYREF
  _QWORD v61[126]; // [rsp+548h] [rbp+440h] BYREF
  _BYTE v62[1008]; // [rsp+938h] [rbp+830h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D70h] [rbp+C68h]

  v39 = -2;
  v38 = a1;
  v3 = 0;
  memset(v59, 0, sizeof(v59));
  *(double *)&v3 = std::wstring::_Construct_empty(v59);
  v58[0] = v3;
  v58[1] = 0;
  std::wstring::_Construct_empty(v58);
  Utility::GetProgramDataPath(lpFileName);
  if ( !lpFileName[2] )
    goto LABEL_47;
  std::wstring::_Append<unsigned short>(lpFileName);
  v4 = (const WCHAR *)lpFileName;
  if ( v45 > 7 )
    v4 = lpFileName[0];
  if ( (GetFileAttributesW(v4) & 0x10) == 0 )
    goto LABEL_47;
  v35 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v35,
    0);
  v5 = (const WCHAR *)lpFileName;
  if ( v45 > 7 )
    v5 = lpFileName[0];
  v6 = PathAllocCombine(v5, L"*.item", 0, (unsigned __int16 **)&v35);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x293,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\appplatformfinder.cpp",
      (const char *)(unsigned int)v6,
      v34);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v7 = (WCHAR *)v35;
  FirstFileW = (char *)FindFirstFileW(v35, &FindFileData);
  v37 = FirstFileW;
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
LABEL_46:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v37);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
    goto LABEL_47;
  }
  while ( 2 )
  {
    hMem = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &hMem,
      0);
    v9 = (const WCHAR *)lpFileName;
    if ( v45 > 7 )
      v9 = lpFileName[0];
    v10 = PathAllocCombine(v9, FindFileData.cFileName, 0, (unsigned __int16 **)&hMem);
    v11 = hMem;
    if ( v10 < 0 )
      goto LABEL_43;
    v12 = 0;
    memset(v52, 0, sizeof(v52));
    *(double *)&v12 = std::wstring::_Construct_empty(v52);
    v51[0] = v12;
    v51[1] = 0;
    *(double *)&v12 = std::wstring::_Construct_empty(v51);
    Src[0] = v12;
    Src[1] = 0;
    std::wstring::_Construct_empty(Src);
    std::basic_ifstream<unsigned short>::basic_ifstream<unsigned short>(v40, v11);
    if ( !v40[18] )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"AppPlatformFinder::GetEpicGamesApplications",
        682,
        (unsigned int)"Failed to open Epic Games manifest file %ws");
      std::basic_ifstream<unsigned short>::`vbase destructor'(v40);
      std::wstring::~wstring(Src);
      std::wstring::~wstring(v51);
      std::wstring::~wstring(v52);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
      goto LABEL_46;
    }
    v13 = 0;
    v14 = 0;
    v15 = 0;
    v16 = 0;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    *(double *)&v16 = std::wstring::_Construct_empty(&v41);
    v56 = v16;
    v57 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v56);
    v48 = 0;
    v49 = 0;
    v50 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v48);
    v54 = 0;
    v55 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v54);
    if ( (*((_BYTE *)&v40[2] + *(int *)(v40[0] + 4LL)) & 1) != 0 )
      goto LABEL_42;
    v17 = v38;
    do
    {
      std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v40, &v41);
      if ( v42 > 2 )
      {
        if ( !v15 )
        {
          v18 = std::wstring::find(&v41, &v54);
          if ( v18 != -1 )
          {
            v19 = std::wstring::substr(&v41, v46, v18 + v55, v42 - (v18 + v55));
            std::wstring::operator=(&v41, v19);
            std::wstring::~wstring(v46);
            v20 = Utility::TrimSpace(&v41);
            std::wstring::operator=(&v41, v20);
            v21 = std::wstring::substr(&v41, v46, 3, v42 - 5);
            std::wstring::operator=(Src, v21);
            std::wstring::~wstring(v46);
            std::wstring::wstring(v53, L"\\\\");
            while ( std::wstring::find(Src, v53) != -1 )
            {
              std::wstring::find(Src, v53);
              std::wstring::_Replace<unsigned short>(Src, 1);
            }
            v15 = 1;
            std::wstring::~wstring(v53);
            continue;
          }
        }
        if ( !v13 )
        {
          v22 = std::wstring::find(&v41, &v56);
          if ( v22 != -1 )
          {
            v23 = std::wstring::substr(&v41, v46, v22 + v57, v42 - (v22 + v57));
            std::wstring::operator=(&v41, v23);
            std::wstring::~wstring(v46);
            v24 = Utility::TrimSpace(&v41);
            std::wstring::operator=(&v41, v24);
            v25 = std::wstring::substr(&v41, v46, 3, v42 - 5);
            std::wstring::operator=(v52, v25);
            std::wstring::~wstring(v46);
            v13 = 1;
            continue;
          }
        }
        if ( !v14 )
        {
          v26 = &v48;
          if ( v50 > 7 )
            LODWORD(v26) = v48;
          v27 = &v41;
          if ( v43 > 7 )
            LODWORD(v27) = v41;
          v28 = std::_Traits_find<std::char_traits<unsigned short>>((_DWORD)v27, v42, 0, (_DWORD)v26, v49);
          if ( v28 != -1 )
          {
            v29 = std::wstring::substr(&v41, v46, v28 + v49, v42 - (v28 + v49));
            std::wstring::operator=(&v41, v29);
            std::wstring::~wstring(v46);
            v30 = Utility::TrimSpace(&v41);
            std::wstring::operator=(&v41, v30);
            v31 = std::wstring::substr(&v41, v46, 3, v42 - 5);
            std::wstring::operator=(v51, v31);
            std::wstring::~wstring(v46);
            v14 = 1;
            continue;
          }
        }
      }
      if ( v13 && v14 && v15 )
      {
        v13 = 0;
        v14 = 0;
        v15 = 0;
        v32 = (const struct Application *)EpicGamesApplication::EpicGamesApplication(
                                            (SteamApplication *)v61,
                                            v17,
                                            (__int64)Src);
        Application::Application((Application *)v62, v32);
        v61[0] = &EpicGamesApplication::`vftable'{for `IAmiInventoryTelemetryItem'};
        v61[1] = &AppvApplication::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
        v61[2] = &SteamApplication::`vftable';
        Application::~Application((Application *)v61);
        if ( *(_QWORD *)(a2 + 8) == *(_QWORD *)(a2 + 16) )
        {
          std::vector<Application>::_Emplace_reallocate<Application const &>(a2, *(_QWORD *)(a2 + 8), v62);
        }
        else
        {
          Application::Application(*(Application **)(a2 + 8), (const struct Application *)v62);
          *(_QWORD *)(a2 + 8) += 1008LL;
        }
        Application::~Application((Application *)v62);
      }
    }
    while ( (*((_BYTE *)&v40[2] + *(int *)(v40[0] + 4LL)) & 1) == 0 );
    v7 = (WCHAR *)v35;
LABEL_42:
    std::wstring::~wstring(&v54);
    std::wstring::~wstring(&v48);
    std::wstring::~wstring(&v56);
    std::wstring::~wstring(&v41);
    std::basic_ifstream<unsigned short>::`vbase destructor'(v40);
    std::wstring::~wstring(Src);
    std::wstring::~wstring(v51);
    std::wstring::~wstring(v52);
LABEL_43:
    if ( FindNextFileW(FirstFileW, &FindFileData) )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
      continue;
    }
    break;
  }
  if ( v11 )
    LocalFree(v11);
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose(FirstFileW);
  if ( v7 )
    LocalFree(v7);
LABEL_47:
  std::wstring::~wstring(lpFileName);
  std::wstring::~wstring(v58);
  return std::wstring::~wstring(v59);
}

```

## disassembly

```asm
0x18000b994  mov     rax, rsp
0x18000b997  push    rbp
0x18000b998  push    rsi
0x18000b999  push    rdi
0x18000b99a  push    r12
0x18000b99c  push    r13
0x18000b99e  push    r14
0x18000b9a0  push    r15
0x18000b9a2  lea     rbp, [rax-0C68h]
0x18000b9a9  sub     rsp, 0D30h
0x18000b9b0  mov     [rsp+0D60h+var_D10], 0FFFFFFFFFFFFFFFEh
0x18000b9b9  mov     [rax+18h], rbx
0x18000b9bd  mov     rax, cs:__security_cookie
0x18000b9c4  xor     rax, rsp
0x18000b9c7  mov     [rbp+0C60h+var_40], rax
0x18000b9ce  mov     r15, rdx
0x18000b9d1  mov     [rsp+0D60h+var_D18], rcx
0x18000b9d6  xorps   xmm0, xmm0
0x18000b9d9  movups  [rbp+0C60h+var_A90], xmm0
0x18000b9e0  xorps   xmm1, xmm1
0x18000b9e3  movdqu  [rbp+0C60h+var_A80], xmm1
0x18000b9eb  lea     rcx, [rbp+0C60h+var_A90]
0x18000b9f2  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000b9f7  nop
0x18000b9f8  movups  [rbp+0C60h+var_AB0], xmm0
0x18000b9ff  movdqu  [rbp+0C60h+var_AA0], xmm1
0x18000ba07  lea     rcx, [rbp+0C60h+var_AB0]
0x18000ba0e  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000ba13  nop
0x18000ba14  lea     rcx, [rbp+0C60h+lpFileName]
0x18000ba1b  call    ?GetProgramDataPath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Utility::GetProgramDataPath(void)
0x18000ba20  nop
0x18000ba21  cmp     [rbp+0C60h+var_BC0], 0
0x18000ba29  jz      loc_18000C187
0x18000ba2f  mov     r8d, 26h ; '&'
0x18000ba35  lea     rdx, aEpicEpicgamesl; "\\Epic\\EpicGamesLauncher\\Data\\Manife"...
0x18000ba3c  lea     rcx, [rbp+0C60h+lpFileName]; Src
0x18000ba43  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000ba48  lea     rcx, [rbp+0C60h+lpFileName]
0x18000ba4f  cmp     [rbp+0C60h+var_BB8], 7
0x18000ba57  cmova   rcx, [rbp+0C60h+lpFileName]; lpFileName
0x18000ba5f  call    cs:__imp_GetFileAttributesW
0x18000ba65  test    al, 10h
0x18000ba67  jz      loc_18000C187
0x18000ba6d  mov     [rsp+0D60h+var_D30], 0
0x18000ba76  xor     edx, edx
0x18000ba78  lea     rcx, [rsp+0D60h+var_D30]
0x18000ba7d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000ba82  lea     rcx, [rbp+0C60h+lpFileName]
0x18000ba89  cmp     [rbp+0C60h+var_BB8], 7
0x18000ba91  cmova   rcx, [rbp+0C60h+lpFileName]; pszPathIn
0x18000ba99  lea     r9, [rsp+0D60h+var_D30]; unsigned __int16 **
0x18000ba9e  xor     r8d, r8d; dwFlags
0x18000baa1  lea     rdx, pszMore; "*.item"
0x18000baa8  call    ?PathAllocCombine@@YAJPEBG0W4PATHCCH_OPTIONS@@PEAPEAG@Z; PathAllocCombine(ushort const *,ushort const *,PATHCCH_OPTIONS,ushort * *)
0x18000baad  mov     rcx, [rbp+0C68h]; this
0x18000bab4  test    eax, eax
0x18000bab6  jns     short loc_18000BACD
0x18000bab8  mov     r9d, eax; char *
0x18000babb  lea     r8, aBaseAppcompatI_4; "base\\appcompat\\inventory\\software\\i"...
0x18000bac2  mov     edx, 293h; void *
0x18000bac7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000bacd  xor     edx, edx; Val
0x18000bacf  mov     r8d, 250h; Size
0x18000bad5  lea     rcx, [rbp+0C60h+FindFileData]; void *
0x18000badc  call    memset_0
0x18000bae1  lea     rdx, [rbp+0C60h+FindFileData]; lpFindFileData
0x18000bae8  mov     rdi, [rsp+0D60h+var_D30]
0x18000baed  mov     rcx, rdi; lpFileName
0x18000baf0  call    cs:__imp_FindFirstFileW
0x18000baf6  mov     r14, rax
0x18000baf9  mov     [rsp+0D60h+var_D20], rax
0x18000bafe  dec     rax
0x18000bb01  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000bb05  ja      loc_18000C171
0x18000bb0b  mov     [rsp+0D60h+hMem], 0
0x18000bb14  xor     edx, edx
0x18000bb16  lea     rcx, [rsp+0D60h+hMem]
0x18000bb1b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000bb20  lea     rcx, [rbp+0C60h+lpFileName]
0x18000bb27  cmp     [rbp+0C60h+var_BB8], 7
0x18000bb2f  cmova   rcx, [rbp+0C60h+lpFileName]; pszPathIn
0x18000bb37  lea     r9, [rsp+0D60h+hMem]; unsigned __int16 **
0x18000bb3c  xor     r8d, r8d; dwFlags
0x18000bb3f  lea     rdx, [rbp+0C60h+FindFileData.cFileName]; pszMore
0x18000bb46  call    ?PathAllocCombine@@YAJPEBG0W4PATHCCH_OPTIONS@@PEAPEAG@Z; PathAllocCombine(ushort const *,ushort const *,PATHCCH_OPTIONS,ushort * *)
0x18000bb4b  mov     rbx, [rsp+0D60h+hMem]
0x18000bb50  test    eax, eax
0x18000bb52  js      loc_18000C0E8
0x18000bb58  xorps   xmm0, xmm0
0x18000bb5b  movups  [rbp+0C60h+var_B30], xmm0
0x18000bb62  xorps   xmm1, xmm1
0x18000bb65  movdqu  [rbp+0C60h+var_B20], xmm1
0x18000bb6d  lea     rcx, [rbp+0C60h+var_B30]
0x18000bb74  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000bb79  nop
0x18000bb7a  movups  [rbp+0C60h+var_B50], xmm0
0x18000bb81  movdqu  [rbp+0C60h+var_B40], xmm1
0x18000bb89  lea     rcx, [rbp+0C60h+var_B50]
0x18000bb90  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000bb95  nop
0x18000bb96  movups  [rbp+0C60h+Src], xmm0
0x18000bb9d  movdqu  [rbp+0C60h+var_B80], xmm1
0x18000bba5  lea     rcx, [rbp+0C60h+Src]
0x18000bbac  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000bbb1  nop
0x18000bbb2  mov     rdx, rbx
0x18000bbb5  lea     rcx, [rsp+60h]
0x18000bbba  call    ??0?$basic_ifstream@GU?$char_traits@G@std@@@std@@QEAA@PEBGHH@Z; std::basic_ifstream<ushort>::basic_ifstream<ushort>(ushort const *,int,int)
0x18000bbbf  nop
0x18000bbc0  cmp     [rbp+0C60h+var_C70], 0
0x18000bbc5  jz      loc_18000C110
0x18000bbcb  xor     r12b, r12b
0x18000bbce  xor     r13b, r13b
0x18000bbd1  xor     sil, sil
0x18000bbd4  xorps   xmm0, xmm0
0x18000bbd7  movups  [rbp+0C60h+var_BF0], xmm0
0x18000bbdb  mov     [rbp+0C60h+var_BE0], 0
0x18000bbe6  mov     [rbp+0C60h+var_BD8], 0
0x18000bbf1  lea     rcx, [rbp+0C60h+var_BF0]
0x18000bbf5  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000bbfa  nop
0x18000bbfb  movups  [rbp+0C60h+var_AD0], xmm0
0x18000bc02  xorps   xmm1, xmm1
0x18000bc05  movdqu  [rbp+0C60h+var_AC0], xmm1
0x18000bc0d  mov     r8d, 0Dh
0x18000bc13  lea     rdx, aDisplayname; "\"DisplayName\""
0x18000bc1a  lea     rcx, [rbp+0C60h+var_AD0]
0x18000bc21  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000bc26  nop
0x18000bc27  xorps   xmm0, xmm0
0x18000bc2a  movups  [rbp+0C60h+var_B70], xmm0
0x18000bc31  mov     [rbp+0C60h+var_B60], 0
0x18000bc3c  mov     [rbp+0C60h+var_B58], 0
0x18000bc47  mov     r8d, 12h
0x18000bc4d  lea     rdx, aAppversionstri; "\"AppVersionString\""
0x18000bc54  lea     rcx, [rbp+0C60h+var_B70]
0x18000bc5b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000bc60  nop
0x18000bc61  xorps   xmm0, xmm0
0x18000bc64  movups  [rbp+0C60h+var_AF0], xmm0
0x18000bc6b  xorps   xmm1, xmm1
0x18000bc6e  movdqu  [rbp+0C60h+var_AE0], xmm1
0x18000bc76  mov     r8d, 11h
0x18000bc7c  lea     rdx, aInstalllocatio_0; "\"InstallLocation\""
0x18000bc83  lea     rcx, [rbp+0C60h+var_AF0]
0x18000bc8a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000bc8f  nop
0x18000bc90  mov     rax, [rsp+60h]
0x18000bc95  movsxd  rcx, dword ptr [rax+4]
0x18000bc99  test    byte ptr [rsp+rcx+70h], 1
0x18000bc9e  jnz     loc_18000C086
0x18000bca4  mov     rdi, [rsp+0D60h+var_D18]
0x18000bca9  lea     rdx, [rbp+0C60h+var_BF0]
0x18000bcad  lea     rcx, [rsp+60h]
0x18000bcb2  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x18000bcb7  cmp     [rbp+0C60h+var_BE0], 2
0x18000bcbf  jbe     loc_18000BF97
0x18000bcc5  test    sil, sil
0x18000bcc8  jnz     loc_18000BDF4
0x18000bcce  lea     rdx, [rbp+0C60h+var_AF0]
0x18000bcd5  lea     rcx, [rbp+0C60h+var_BF0]
0x18000bcd9  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x18000bcde  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000bce2  jz      loc_18000BDF4
0x18000bce8  mov     r8, qword ptr [rbp+0C60h+var_AE0]
0x18000bcef  add     r8, rax
0x18000bcf2  mov     r9, [rbp+0C60h+var_BE0]
0x18000bcf9  sub     r9, r8
0x18000bcfc  lea     rdx, [rbp+0C60h+var_BB0]
0x18000bd03  lea     rcx, [rbp+0C60h+var_BF0]
0x18000bd07  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18000bd0c  mov     rdx, rax
0x18000bd0f  lea     rcx, [rbp+0C60h+var_BF0]
0x18000bd13  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000bd18  lea     rcx, [rbp+0C60h+var_BB0]
0x18000bd1f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000bd24  lea     rcx, [rbp+0C60h+var_BF0]
0x18000bd28  call    ?TrimSpace@Utility@@SAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; Utility::TrimSpace(std::wstring &)
0x18000bd2d  mov     rdx, rax
0x18000bd30  lea     rcx, [rbp+0C60h+var_BF0]
0x18000bd34  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000bd39  mov     r9, [rbp+0C60h+var_BE0]
0x18000bd40  add     r9, 0FFFFFFFFFFFFFFFBh
0x18000bd44  mov     r8d, 3
0x18000bd4a  lea     rdx, [rbp+0C60h+var_BB0]
0x18000bd51  lea     rcx, [rbp+0C60h+var_BF0]
0x18000bd55  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18000bd5a  mov     rdx, rax
0x18000bd5d  lea     rcx, [rbp+0C60h+Src]
0x18000bd64  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000bd69  lea     rcx, [rbp+0C60h+var_BB0]
0x18000bd70  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000bd75  lea     rdx, asc_180138A6C; "\\\\"
0x18000bd7c  lea     rcx, [rbp+0C60h+var_B10]
0x18000bd83  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000bd88  nop
0x18000bd89  jmp     short loc_18000BDC7
0x18000bd8b  mov     rsi, [rbp+0C60h+var_B00]
0x18000bd92  lea     rdx, [rbp+0C60h+var_B10]
0x18000bd99  lea     rcx, [rbp+0C60h+Src]
0x18000bda0  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x18000bda5  mov     qword ptr [rsp+20h], 1; __int64
0x18000bdae  lea     r9, SubBlock; "\\"
0x18000bdb5  mov     r8, rsi
0x18000bdb8  mov     rdx, rax
0x18000bdbb  lea     rcx, [rbp+0C60h+Src]; Src
0x18000bdc2  call    ??$_Replace@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_K_KQEBG0@Z; std::wstring::_Replace<ushort>(unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x18000bdc7  lea     rdx, [rbp+0C60h+var_B10]
0x18000bdce  lea     rcx, [rbp+0C60h+Src]
0x18000bdd5  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x18000bdda  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000bdde  jnz     short loc_18000BD8B
0x18000bde0  mov     sil, 1
0x18000bde3  lea     rcx, [rbp+0C60h+var_B10]
0x18000bdea  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000bdef  jmp     loc_18000C06D
0x18000bdf4  test    r12b, r12b
0x18000bdf7  jnz     loc_18000BEAC
0x18000bdfd  lea     rdx, [rbp+0C60h+var_AD0]
0x18000be04  lea     rcx, [rbp+0C60h+var_BF0]
0x18000be08  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x18000be0d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000be11  jz      loc_18000BEAC
0x18000be17  mov     r8, qword ptr [rbp+0C60h+var_AC0]
0x18000be1e  add     r8, rax
0x18000be21  mov     r9, [rbp+0C60h+var_BE0]
0x18000be28  sub     r9, r8
0x18000be2b  lea     rdx, [rbp+0C60h+var_BB0]
0x18000be32  lea     rcx, [rbp+0C60h+var_BF0]
0x18000be36  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18000be3b  mov     rdx, rax
0x18000be3e  lea     rcx, [rbp+0C60h+var_BF0]
0x18000be42  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000be47  lea     rcx, [rbp+0C60h+var_BB0]
0x18000be4e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000be53  lea     rcx, [rbp+0C60h+var_BF0]
0x18000be57  call    ?TrimSpace@Utility@@SAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; Utility::TrimSpace(std::wstring &)
0x18000be5c  mov     rdx, rax
0x18000be5f  lea     rcx, [rbp+0C60h+var_BF0]
0x18000be63  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000be68  mov     r9, [rbp+0C60h+var_BE0]
0x18000be6f  add     r9, 0FFFFFFFFFFFFFFFBh
0x18000be73  mov     r8d, 3
0x18000be79  lea     rdx, [rbp+0C60h+var_BB0]
0x18000be80  lea     rcx, [rbp+0C60h+var_BF0]
0x18000be84  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18000be89  mov     rdx, rax
0x18000be8c  lea     rcx, [rbp+0C60h+var_B30]
0x18000be93  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000be98  lea     rcx, [rbp+0C60h+var_BB0]
0x18000be9f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000bea4  mov     r12b, 1
0x18000bea7  jmp     loc_18000C06D
0x18000beac  test    r13b, r13b
0x18000beaf  jnz     loc_18000BF97
0x18000beb5  mov     rax, [rbp+0C60h+var_B60]
0x18000bebc  lea     r9, [rbp+0C60h+var_B70]
0x18000bec3  cmp     [rbp+0C60h+var_B58], 7
0x18000becb  cmova   r9, qword ptr [rbp+0C60h+var_B70]
0x18000bed3  lea     rcx, [rbp+0C60h+var_BF0]
0x18000bed7  cmp     [rbp+0C60h+var_BD8], 7
0x18000bedf  cmova   rcx, qword ptr [rbp+0C60h+var_BF0]
0x18000bee4  mov     [rsp+20h], rax
0x18000bee9  xor     r8d, r8d
0x18000beec  mov     rdx, [rbp+0C60h+var_BE0]
0x18000bef3  call    ??$_Traits_find@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x18000bef8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000befc  jz      loc_18000BF97
0x18000bf02  mov     r8, [rbp+0C60h+var_B60]
0x18000bf09  add     r8, rax
0x18000bf0c  mov     r9, [rbp+0C60h+var_BE0]
0x18000bf13  sub     r9, r8
0x18000bf16  lea     rdx, [rbp+0C60h+var_BB0]
0x18000bf1d  lea     rcx, [rbp+0C60h+var_BF0]
0x18000bf21  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18000bf26  mov     rdx, rax
0x18000bf29  lea     rcx, [rbp+0C60h+var_BF0]
0x18000bf2d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000bf32  lea     rcx, [rbp+0C60h+var_BB0]
0x18000bf39  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000bf3e  lea     rcx, [rbp+0C60h+var_BF0]
0x18000bf42  call    ?TrimSpace@Utility@@SAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; Utility::TrimSpace(std::wstring &)
0x18000bf47  mov     rdx, rax
0x18000bf4a  lea     rcx, [rbp+0C60h+var_BF0]
0x18000bf4e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000bf53  mov     r9, [rbp+0C60h+var_BE0]
0x18000bf5a  add     r9, 0FFFFFFFFFFFFFFFBh
0x18000bf5e  mov     r8d, 3
0x18000bf64  lea     rdx, [rbp+0C60h+var_BB0]
0x18000bf6b  lea     rcx, [rbp+0C60h+var_BF0]
0x18000bf6f  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18000bf74  mov     rdx, rax
0x18000bf77  lea     rcx, [rbp+0C60h+var_B50]
0x18000bf7e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000bf83  lea     rcx, [rbp+0C60h+var_BB0]
0x18000bf8a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000bf8f  mov     r13b, 1
0x18000bf92  jmp     loc_18000C06D
0x18000bf97  test    r12b, r12b
  ... truncated ...
```
