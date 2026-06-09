# CUserTileBroker::_SaveImages(ushort const *,USERTILE_SIZE_MAPPING *,uint)

- ea: `0x1800ca398`
- end: `0x1800ca64c`
- name: `?_SaveImages@CUserTileBroker@@AEAAJPEBGPEAUUSERTILE_SIZE_MAPPING@@I@Z`
- size: `692`
- prototype: `__int64 __fastcall(CUserTileBroker *__hidden this, const unsigned __int16 *, struct USERTILE_SIZE_MAPPING *, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002ddf0`

## callees

- `0x180009eec`
- `0x180013e00`
- `0x18001a3d0`
- `0x18002be34`
- `0x18002d8a4`
- `0x18003217c`
- `0x180034db4`
- `0x18003d858`
- `0x18004e63c`
- `0x180050210`
- `0x180050ba0`
- `0x1800c9638`
- `0x1800ca228`
- `0x1800ca2f8`
- `0x1800ca398`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800ca403`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800ca403`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1800ca5be`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1800ca5d9`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1800ca5ec`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1800ca5be`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1800ca5d9`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1800ca5ec`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800ca4a8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800ca4a8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800ca487`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800ca487`

## string_xrefs

- `0x1800ca424`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x1800ca464`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x1800ca50e`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x1800ca555`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x1800ca5a3`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CUserTileBroker::_SaveImages(
        CUserTileBroker *this,
        unsigned __int16 *a2,
        struct USERTILE_SIZE_MAPPING *a3)
{
  int CallerSIDString; // eax
  int v6; // ebx
  __int64 v7; // rdx
  CUserTileBroker *v8; // rcx
  HRESULT TileFolder; // eax
  __int64 v10; // rdx
  __int64 v11; // rdi
  struct IStream *v12; // r8
  CUserTileBroker *v13; // rcx
  int UserTileRegKey; // eax
  __int64 v15; // rdi
  const unsigned __int16 *v16; // r9
  const unsigned __int16 *v17; // rsi
  int v18; // eax
  int v20; // [rsp+20h] [rbp-79h]
  HKEY hkey; // [rsp+40h] [rbp-59h] BYREF
  struct IShellItem *v22; // [rsp+48h] [rbp-51h] BYREF
  LPCWSTR psz; // [rsp+50h] [rbp-49h] BYREF
  GUID pguid; // [rsp+58h] [rbp-41h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  psz = 0;
  CallerSIDString = CImpersonateCaller::GetCallerSIDString((unsigned __int16 **)&psz);
  v6 = CallerSIDString;
  if ( a2 )
  {
    if ( CallerSIDString >= 0 )
      _o__wcsicmp(psz, a2);
  }
  else
  {
    if ( CallerSIDString < 0 )
    {
      v7 = 647;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
        (const char *)(unsigned int)CallerSIDString,
        v20);
      goto LABEL_35;
    }
    a2 = (unsigned __int16 *)psz;
  }
  CallerSIDString = EnsurePublicFolderandRegKey(a2);
  v6 = CallerSIDString;
  if ( CallerSIDString < 0 )
  {
    v7 = 661;
    goto LABEL_9;
  }
  v22 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  TileFolder = CUserTileBroker::_GetTileFolder(v8, a2, &v22);
  v6 = TileFolder;
  if ( TileFolder < 0 )
  {
    v10 = 664;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
      (const char *)(unsigned int)TileFolder,
      v20);
    goto LABEL_34;
  }
  pguid = 0;
  TileFolder = CoCreateGuid(&pguid);
  v6 = TileFolder;
  if ( TileFolder < 0 )
  {
    v10 = 667;
    goto LABEL_12;
  }
  StringFromGUID2(&pguid, sz, 39);
  v6 = 0;
  v11 = 0;
  do
  {
    if ( v6 < 0 )
      break;
    v12 = (struct IStream *)*((_QWORD *)a3 + 12 * v11 + 2);
    if ( v12 )
      v6 = CUserTileBroker::_SaveImage(
             (struct USERTILE_SIZE_MAPPING *)((char *)a3 + 96 * v11 + 24),
             v22,
             v12,
             sz,
             (const unsigned __int16 *)a3 + 48 * v11 + 22,
             (const unsigned __int16 *)a3 + 48 * v11 + 12,
             (LPWSTR *)a3 + 12 * v11 + 11);
    v11 = (unsigned int)(v11 + 1);
  }
  while ( (unsigned int)v11 < 0xE );
  if ( v6 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2AB,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
      (const char *)(unsigned int)v6,
      v20);
    goto LABEL_33;
  }
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  UserTileRegKey = GetUserTileRegKey(a2, 0x2011Fu, &hkey);
  v6 = UserTileRegKey;
  if ( UserTileRegKey < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2AF,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
      (const char *)(unsigned int)UserTileRegKey,
      v20);
    goto LABEL_32;
  }
  v15 = 0;
  while ( v6 >= 0 )
  {
    v16 = (const unsigned __int16 *)*((_QWORD *)a3 + 12 * v15 + 11);
    v17 = (const unsigned __int16 *)((char *)a3 + 96 * v15);
    if ( !v16 )
      goto LABEL_29;
    v18 = SHRegSetString(hkey, 0, v17 + 22, v16);
    v6 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2B7,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
        (const char *)(unsigned int)v18,
        v20);
LABEL_29:
      SHDeleteValueW(hkey, 0, v17 + 22);
    }
    v15 = (unsigned int)(v15 + 1);
    if ( (unsigned int)v15 >= 0xE )
      break;
  }
  SHDeleteValueW(hkey, 0, L"Image200");
  SHDeleteValueW(hkey, 0, L"Video200");
LABEL_32:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
LABEL_33:
  CUserTileBroker::_CleanUpFiles(v13, v22, v6 >= 0, sz);
LABEL_34:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
LABEL_35:
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&psz);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800ca398  mov     [rsp-8+arg_0], rbx
0x1800ca39d  push    rbp
0x1800ca39e  push    rsi
0x1800ca39f  push    rdi
0x1800ca3a0  push    r12
0x1800ca3a2  push    r14
0x1800ca3a4  lea     rbp, [rsp-37h]
0x1800ca3a9  sub     rsp, 0D0h
0x1800ca3b0  mov     rax, cs:__security_cookie
0x1800ca3b7  xor     rax, rsp
0x1800ca3ba  mov     [rbp+57h+var_30], rax
0x1800ca3be  mov     r14, r8
0x1800ca3c1  mov     rsi, rdx
0x1800ca3c4  mov     [rbp+57h+psz], 0
0x1800ca3cc  lea     rcx, [rbp+57h+psz]; unsigned __int16 **
0x1800ca3d0  call    ?GetCallerSIDString@CImpersonateCaller@@SAJPEAPEAG@Z; CImpersonateCaller::GetCallerSIDString(ushort * *)
0x1800ca3d5  mov     ebx, eax
0x1800ca3d7  mov     r12d, 1
0x1800ca3dd  test    rsi, rsi
0x1800ca3e0  jnz     short loc_1800CA3F6
0x1800ca3e2  test    eax, eax
0x1800ca3e4  jns     short loc_1800CA3ED
0x1800ca3e6  mov     edx, 287h
0x1800ca3eb  jmp     short loc_1800CA424
0x1800ca3ed  mov     edi, r12d
0x1800ca3f0  mov     rsi, [rbp+57h+psz]
0x1800ca3f4  jmp     short loc_1800CA40F
0x1800ca3f6  xor     edi, edi
0x1800ca3f8  test    eax, eax
0x1800ca3fa  js      short loc_1800CA40F
0x1800ca3fc  mov     rdx, rsi
0x1800ca3ff  mov     rcx, [rbp+57h+psz]
0x1800ca403  call    cs:__imp__o__wcsicmp
0x1800ca409  test    eax, eax
0x1800ca40b  cmovz   edi, r12d
0x1800ca40f  mov     edx, edi
0x1800ca411  mov     rcx, rsi; unsigned __int16 *
0x1800ca414  call    EnsurePublicFolderandRegKey
0x1800ca419  mov     ebx, eax
0x1800ca41b  test    eax, eax
0x1800ca41d  jns     short loc_1800CA43C
0x1800ca41f  mov     edx, 295h; void *
0x1800ca424  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800ca42b  mov     r9d, eax; char *
0x1800ca42e  mov     rcx, [rbp+5Fh]; this
0x1800ca432  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ca437  jmp     loc_1800CA61E
0x1800ca43c  mov     [rbp+57h+var_A8], 0
0x1800ca444  lea     rcx, [rbp+57h+var_A8]
0x1800ca448  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ca44d  lea     r8, [rbp+57h+var_A8]; struct IShellItem **
0x1800ca451  mov     rdx, rsi; unsigned __int16 *
0x1800ca454  call    ?_GetTileFolder@CUserTileBroker@@AEAAJPEBGPEAPEAUIShellItem@@@Z; CUserTileBroker::_GetTileFolder(ushort const *,IShellItem * *)
0x1800ca459  mov     ebx, eax
0x1800ca45b  test    eax, eax
0x1800ca45d  jns     short loc_1800CA47C
0x1800ca45f  mov     edx, 298h; void *
0x1800ca464  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800ca46b  mov     r9d, eax; char *
0x1800ca46e  mov     rcx, [rbp+5Fh]; this
0x1800ca472  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ca477  jmp     loc_1800CA614
0x1800ca47c  xorps   xmm0, xmm0
0x1800ca47f  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x1800ca483  lea     rcx, [rbp+57h+pguid]; pguid
0x1800ca487  call    cs:__imp_CoCreateGuid
0x1800ca48d  mov     ebx, eax
0x1800ca48f  test    eax, eax
0x1800ca491  jns     short loc_1800CA49A
0x1800ca493  mov     edx, 29Bh
0x1800ca498  jmp     short loc_1800CA464
0x1800ca49a  mov     r8d, 27h ; '''; cchMax
0x1800ca4a0  lea     rdx, [rbp+57h+sz]; lpsz
0x1800ca4a4  lea     rcx, [rbp+57h+pguid]; rguid
0x1800ca4a8  call    cs:__imp_StringFromGUID2
0x1800ca4ae  xor     ebx, ebx
0x1800ca4b0  xor     edi, edi
0x1800ca4b2  test    ebx, ebx
0x1800ca4b4  js      short loc_1800CA503
0x1800ca4b6  lea     rdx, [rdi+rdi*2]
0x1800ca4ba  shl     rdx, 5
0x1800ca4be  mov     r8, [rdx+r14+10h]; struct IStream *
0x1800ca4c3  test    r8, r8
0x1800ca4c6  jz      short loc_1800CA4FB
0x1800ca4c8  lea     rax, [r14+58h]
0x1800ca4cc  add     rax, rdx
0x1800ca4cf  lea     rcx, [r14+18h]
0x1800ca4d3  add     rcx, rdx; this
0x1800ca4d6  lea     r9, [r14+2Ch]
0x1800ca4da  add     r9, rdx
0x1800ca4dd  mov     [rsp+0F0h+ppwsz], rax; ppwsz
0x1800ca4e2  mov     [rsp+0F0h+var_C8], rcx; unsigned __int16 *
0x1800ca4e7  mov     [rsp+0F0h+var_D0], r9; int
0x1800ca4ec  lea     r9, [rbp+57h+sz]; unsigned __int16 *
0x1800ca4f0  mov     rdx, [rbp+57h+var_A8]; struct IShellItem *
0x1800ca4f4  call    ?_SaveImage@CUserTileBroker@@AEAAJPEAUIShellItem@@PEAUIStream@@PEBG22PEAPEAG@Z; CUserTileBroker::_SaveImage(IShellItem *,IStream *,ushort const *,ushort const *,ushort const *,ushort * *)
0x1800ca4f9  mov     ebx, eax
0x1800ca4fb  add     edi, r12d
0x1800ca4fe  cmp     edi, 0Eh
0x1800ca501  jb      short loc_1800CA4B2
0x1800ca503  mov     rcx, [rbp+5Fh]; this
0x1800ca507  test    ebx, ebx
0x1800ca509  jns     short loc_1800CA524
0x1800ca50b  mov     r9d, ebx; char *
0x1800ca50e  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800ca515  mov     edx, 2ABh; void *
0x1800ca51a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ca51f  jmp     loc_1800CA5FC
0x1800ca524  mov     [rbp+57h+hkey], 0
0x1800ca52c  xor     edx, edx
0x1800ca52e  lea     rcx, [rbp+57h+hkey]
0x1800ca532  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800ca537  lea     r8, [rbp+57h+hkey]; phkResult
0x1800ca53b  mov     edx, 2011Fh; samDesired
0x1800ca540  mov     rcx, rsi; psz
0x1800ca543  call    GetUserTileRegKey
0x1800ca548  mov     ebx, eax
0x1800ca54a  mov     rcx, [rbp+5Fh]; this
0x1800ca54e  test    eax, eax
0x1800ca550  jns     short loc_1800CA56B
0x1800ca552  mov     r9d, eax; char *
0x1800ca555  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800ca55c  mov     edx, 2AFh; void *
0x1800ca561  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ca566  jmp     loc_1800CA5F3
0x1800ca56b  xor     edi, edi
0x1800ca56d  test    ebx, ebx
0x1800ca56f  js      short loc_1800CA5CC
0x1800ca571  lea     rcx, [rdi+rdi*2]
0x1800ca575  shl     rcx, 5
0x1800ca579  mov     r9, [rcx+r14+58h]; unsigned __int16 *
0x1800ca57e  lea     rsi, [rcx+r14]
0x1800ca582  test    r9, r9
0x1800ca585  jz      short loc_1800CA5B4
0x1800ca587  lea     r8, [rsi+2Ch]; unsigned __int16 *
0x1800ca58b  xor     edx, edx; unsigned __int16 *
0x1800ca58d  mov     rcx, [rbp+57h+hkey]; HKEY
0x1800ca591  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800ca596  mov     ebx, eax
0x1800ca598  mov     rcx, [rbp+5Fh]; this
0x1800ca59c  test    eax, eax
0x1800ca59e  jns     short loc_1800CA5C4
0x1800ca5a0  mov     r9d, eax; char *
0x1800ca5a3  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800ca5aa  mov     edx, 2B7h; void *
0x1800ca5af  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ca5b4  lea     r8, [rsi+2Ch]; pszValue
0x1800ca5b8  xor     edx, edx; pszSubKey
0x1800ca5ba  mov     rcx, [rbp+57h+hkey]; hkey
0x1800ca5be  call    cs:__imp_SHDeleteValueW
0x1800ca5c4  add     edi, r12d
0x1800ca5c7  cmp     edi, 0Eh
0x1800ca5ca  jb      short loc_1800CA56D
0x1800ca5cc  lea     r8, aImage200; "Image200"
0x1800ca5d3  xor     edx, edx; pszSubKey
0x1800ca5d5  mov     rcx, [rbp+57h+hkey]; hkey
0x1800ca5d9  call    cs:__imp_SHDeleteValueW
0x1800ca5df  lea     r8, aVideo200; "Video200"
0x1800ca5e6  xor     edx, edx; pszSubKey
0x1800ca5e8  mov     rcx, [rbp+57h+hkey]; hkey
0x1800ca5ec  call    cs:__imp_SHDeleteValueW
0x1800ca5f2  nop
0x1800ca5f3  lea     rcx, [rbp+57h+hkey]
0x1800ca5f7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ca5fc  mov     r8d, ebx
0x1800ca5ff  shr     r8d, 1Fh
0x1800ca603  xor     r8b, r12b; bool
0x1800ca606  lea     r9, [rbp+57h+sz]; unsigned __int16 *
0x1800ca60a  mov     rdx, [rbp+57h+var_A8]; struct IShellItem *
0x1800ca60e  call    ?_CleanUpFiles@CUserTileBroker@@AEAAXPEAUIShellItem@@_NPEBG@Z; CUserTileBroker::_CleanUpFiles(IShellItem *,bool,ushort const *)
0x1800ca613  nop
0x1800ca614  lea     rcx, [rbp+57h+var_A8]
0x1800ca618  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ca61d  nop
0x1800ca61e  lea     rcx, [rbp+57h+psz]
0x1800ca622  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800ca627  mov     eax, ebx
0x1800ca629  mov     rcx, [rbp+57h+var_30]
0x1800ca62d  xor     rcx, rsp; StackCookie
0x1800ca630  call    __security_check_cookie
0x1800ca635  mov     rbx, [rsp+0F0h+arg_0]
0x1800ca63d  add     rsp, 0D0h
0x1800ca644  pop     r14
0x1800ca646  pop     r12
0x1800ca648  pop     rdi
0x1800ca649  pop     rsi
0x1800ca64a  pop     rbp
0x1800ca64b  retn
```
