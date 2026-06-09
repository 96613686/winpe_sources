# _lambda_5cb43ad01037aa628a1cc5978b1aaf7b_::operator()

- ea: `0x18000bafc`
- end: `0x18000c0c3`
- name: `_lambda_5cb43ad01037aa628a1cc5978b1aaf7b_::operator()`
- size: `1479`
- prototype: `__int64 __fastcall(_DWORD **)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000a1ac`

## callees

- `0x180001620`
- `0x180001fd0`
- `0x180005128`
- `0x180006308`
- `0x180006408`
- `0x18000798c`
- `0x180008990`
- `0x180009a68`
- `0x180009da4`
- `0x18000a59c`
- `0x18000ad94`
- `0x18000afd0`
- `0x18000b0d4`
- `0x18000b1a8`
- `0x18000b384`
- `0x18000b3a8`
- `0x18000b474`
- `0x18000bafc`
- `0x18000d2e0`
- `0x18000d96c`
- `0x18000db7c`
- `0x18000de70`
- `0x18000ded8`
- `0x18000ee80`
- `0x180010010`

## string_xrefs

- `0x18000bca4`: `AppSid`
- `0x18000bceb`: `AppCmdlineTemplate`

## pseudocode

```c
__int64 __fastcall lambda_5cb43ad01037aa628a1cc5978b1aaf7b_::operator()(_DWORD **a1)
{
  unsigned int v1; // eax
  unsigned int v2; // r8d
  unsigned int v3; // r15d
  int v4; // r14d
  int v5; // ebx
  int v6; // edi
  int v7; // esi
  int v8; // r12d
  int v9; // r13d
  const char *v10; // r9
  wil::details::in1diag3 *v11; // r11
  const char *v12; // r9
  wil::details::in1diag3 *v13; // r11
  const char *v14; // r9
  wil::details::in1diag3 *v15; // r11
  const char *v16; // r9
  wil::details::in1diag3 *v17; // r11
  const char *v18; // r9
  wil::details::in1diag3 *v19; // r11
  const char *v20; // r9
  wil::details::in1diag3 *v21; // r11
  _QWORD *v22; // rax
  std::_Ref_count_base *v23; // rsi
  _QWORD *v24; // rdi
  _QWORD *v25; // rbx
  _QWORD *v26; // rax
  _DWORD *v27; // rbx
  __int64 v28; // rax
  HKEY v30; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v31; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD *v32; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+68h] [rbp-98h] BYREF
  int v34; // [rsp+70h] [rbp-90h]
  int v35; // [rsp+74h] [rbp-8Ch] BYREF
  int v36; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v37; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v38; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v39; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v40; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v41; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v43; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v44; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v45; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v46; // [rsp+C8h] [rbp-38h] BYREF
  HKEY *v47; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD **v48; // [rsp+D8h] [rbp-28h]
  __int64 *v49; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v50[2]; // [rsp+E8h] [rbp-18h] BYREF
  char v51[8]; // [rsp+F8h] [rbp-8h] BYREF
  char v52[8]; // [rsp+100h] [rbp+0h] BYREF
  std::_Ref_count_base *v53; // [rsp+108h] [rbp+8h]
  int v54; // [rsp+110h] [rbp+10h] BYREF
  _QWORD *v55; // [rsp+118h] [rbp+18h]
  char v56[16]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v57[32]; // [rsp+160h] [rbp+60h] BYREF
  char v58[256]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v59[260]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v60[130]; // [rsp+488h] [rbp+388h] BYREF
  unsigned __int16 v61[520]; // [rsp+58Ch] [rbp+48Ch] BYREF
  unsigned __int16 v62[260]; // [rsp+99Ch] [rbp+89Ch] BYREF
  unsigned __int16 v63[260]; // [rsp+BA4h] [rbp+AA4h] BYREF
  unsigned __int16 v64[260]; // [rsp+DACh] [rbp+CACh] BYREF
  char v65; // [rsp+FB4h] [rbp+EB4h]
  _BYTE v66[528]; // [rsp+FC0h] [rbp+EC0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1228h] [rbp+1128h]

  v48 = a1;
  v33 = 0;
  v34 = 0;
  std::unordered_map<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>>::unordered_map<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>>(&v54);
  v1 = ((__int64 (__fastcall *)(HKEY, const wchar_t *, _QWORD, __int64))AppMon::PortManager::m_monitorInit->pMonitorReg->fpCreateKey)(
         AppMon::PortManager::m_monitorInit->hckRegistryRoot,
         L"Ports",
         0,
         983103);
  if ( v1 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0xC7, v2, (const char *)v1, 0);
  v3 = 0;
  v49 = &v33;
  while ( 1 )
  {
    v32 = 0;
    v46 = 0;
    v45 = 0;
    v44 = 0;
    v43 = 0;
    v42 = 0;
    memset_0(v66, 0, 0x208u);
    v35 = 260;
    v4 = ((__int64 (__fastcall *)(__int64, _QWORD, _BYTE *, int *, _QWORD, HANDLE))AppMon::PortManager::m_monitorInit->pMonitorReg->fpEnumKey)(
           v33,
           v3,
           v66,
           &v35,
           0,
           AppMon::PortManager::m_monitorInit->hSpooler);
    if ( !v4 )
    {
      v30 = 0;
      v38 = 0;
      v39 = 0;
      v31 = 0;
      v37 = 0;
      v40 = 0;
      v41 = 0;
      v4 = ((__int64 (__fastcall *)(__int64, _BYTE *, __int64, HKEY *, HANDLE))AppMon::PortManager::m_monitorInit->pMonitorReg->fpOpenKey)(
             v33,
             v66,
             983103,
             &v30,
             AppMon::PortManager::m_monitorInit->hSpooler);
      if ( !v4 )
      {
        v47 = &v30;
        v5 = AppMon::PortManager::QueryRegistryString(v30, L"Aumid", &v38);
        v6 = AppMon::PortManager::QueryRegistryString(v30, L"AppSid", &v39);
        v7 = AppMon::PortManager::QueryRegistryString(v30, L"PortName", &v31);
        v8 = AppMon::PortManager::QueryRegistryString(v30, L"AppExe", &v37);
        v9 = AppMon::PortManager::QueryRegistryString(v30, L"AppCmdlineTemplate", &v40);
        v36 = AppMon::PortManager::QueryRegistryString(v30, L"AppUap11Parameters", &v41);
        std::unique_ptr<unsigned short>::reset(&v32, v38);
        std::unique_ptr<unsigned short>::reset(&v46, v39);
        std::unique_ptr<unsigned short>::reset(&v45, v31);
        std::unique_ptr<unsigned short>::reset(&v44, v37);
        std::unique_ptr<unsigned short>::reset(&v43, v40);
        std::unique_ptr<unsigned short>::reset(&v42, v41);
        if ( v5 >= 0 && v6 >= 0 && v7 >= 0 && v8 >= 0 && v9 >= 0 )
        {
          memset_0(v58, 0, 0xE36u);
          if ( StringCchCopyW(v59, 0x104u, v31) < 0 )
            wil::details::in1diag3::_Throw_GetLastError(
              v11,
              (void *)0x103,
              (unsigned int)"printscan\\print\\spooler\\monitors\\appmon\\lib\\portmanager.cpp",
              v10);
          if ( StringCchCopyW(v62, 0x104u, v37) < 0 )
            wil::details::in1diag3::_Throw_GetLastError(
              v13,
              (void *)0x104,
              (unsigned int)"printscan\\print\\spooler\\monitors\\appmon\\lib\\portmanager.cpp",
              v12);
          if ( StringCchCopyW(v60, 0x82u, v38) < 0 )
            wil::details::in1diag3::_Throw_GetLastError(
              v15,
              (void *)0x105,
              (unsigned int)"printscan\\print\\spooler\\monitors\\appmon\\lib\\portmanager.cpp",
              v14);
          if ( StringCchCopyW(v61, 0x104u, v39) < 0 )
            wil::details::in1diag3::_Throw_GetLastError(
              v17,
              (void *)0x106,
              (unsigned int)"printscan\\print\\spooler\\monitors\\appmon\\lib\\portmanager.cpp",
              v16);
          if ( StringCchCopyW(v63, 0x104u, v40) < 0 )
            wil::details::in1diag3::_Throw_GetLastError(
              v19,
              (void *)0x107,
              (unsigned int)"printscan\\print\\spooler\\monitors\\appmon\\lib\\portmanager.cpp",
              v18);
          if ( v36 >= 0 )
          {
            v65 = 1;
            if ( StringCchCopyW(v64, 0x104u, v41) < 0 )
              wil::details::in1diag3::_Throw_GetLastError(
                v21,
                (void *)0x10C,
                (unsigned int)"printscan\\print\\spooler\\monitors\\appmon\\lib\\portmanager.cpp",
                v20);
          }
          v22 = (_QWORD *)std::make_shared<AppMon::AppPrinterEndPoint,AppMon::APPINFO &>(v52);
          v50[0] = *v22;
          v23 = (std::_Ref_count_base *)v22[1];
          v50[1] = v23;
          *v22 = 0;
          v22[1] = 0;
          if ( v53 )
            std::_Ref_count_base::_Decref(v53);
          v24 = v55;
          std::wstring::wstring(v57, v31);
          v25 = *(_QWORD **)std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::find(
                              &v54,
                              v51,
                              v57);
          std::wstring::~wstring(v57);
          if ( v24 == v25 )
          {
            std::wstring::wstring(v57, v31);
            v26 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Try_emplace<std::wstring,>(
                              &v54,
                              v56,
                              v57);
            std::shared_ptr<AppMon::AppPrinterEndPointBase>::operator=(*v26 + 48LL, v50);
            std::wstring::~wstring(v57);
          }
          if ( v23 )
            std::_Ref_count_base::_Decref(v23);
        }
        std::unique_ptr<HKEY__ *,AppMon::RegKeyCloser>::~unique_ptr<HKEY__ *,AppMon::RegKeyCloser>(&v47);
      }
    }
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v42);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v43);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v44);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v45);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v46);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v32);
    if ( v4 )
      break;
    ++v3;
  }
  v27 = *v48;
  if ( *v48 != &v54 )
  {
    v32 = *v48;
    *v27 = v54;
    std::list<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>::_Assign_cast<std::pair<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>> &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>>,std::_Iterator_base0>>(
      v27 + 2,
      *v55,
      v55);
    v28 = std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Desired_grow_bucket_count(
            v27,
            *((_QWORD *)v27 + 2));
    std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Forced_rehash(
      v27,
      v28);
    v32 = 0;
    std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Clear_guard::~_Clear_guard(&v32);
  }
  std::unique_ptr<HKEY__ *,AppMon::RegKeyCloser>::~unique_ptr<HKEY__ *,AppMon::RegKeyCloser>(&v49);
  return std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>(&v54);
}

```

## disassembly

```asm
0x18000bafc  push    rbp
0x18000bafe  push    rbx
0x18000baff  push    rsi
0x18000bb00  push    rdi
0x18000bb01  push    r12
0x18000bb03  push    r13
0x18000bb05  push    r14
0x18000bb07  push    r15
0x18000bb09  lea     rbp, [rsp-10E8h]
0x18000bb11  mov     eax, 11E8h
0x18000bb16  call    _alloca_probe
0x18000bb1b  sub     rsp, rax
0x18000bb1e  mov     rax, cs:__security_cookie
0x18000bb25  xor     rax, rsp
0x18000bb28  mov     [rbp+1120h+var_50], rax
0x18000bb2f  mov     [rbp+1120h+var_1148], rcx
0x18000bb33  xor     ebx, ebx
0x18000bb35  mov     [rsp+1220h+var_11B8], rbx
0x18000bb3a  mov     [rsp+1220h+var_11B0], ebx
0x18000bb3e  lea     rcx, [rbp+1120h+var_1110]
0x18000bb42  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>>::unordered_map<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>>(void)
0x18000bb47  nop
0x18000bb48  mov     rcx, cs:?m_monitorInit@PortManager@AppMon@@0PEAU_MONITORINIT@@EA; _MONITORINIT * AppMon::PortManager::m_monitorInit
0x18000bb4f  mov     rax, [rcx+18h]
0x18000bb53  mov     rdx, [rcx+8]
0x18000bb57  mov     [rsp+1220h+var_11E8], rdx
0x18000bb5c  lea     rdx, [rsp+1220h+var_11B0]
0x18000bb61  mov     [rsp+1220h+var_11F0], rdx
0x18000bb66  lea     rdx, [rsp+1220h+var_11B8]
0x18000bb6b  mov     [rsp+1220h+var_11F8], rdx
0x18000bb70  mov     qword ptr [rsp+1220h+var_1200], rbx; unsigned int
0x18000bb75  mov     r9d, 0F003Fh
0x18000bb7b  xor     r8d, r8d
0x18000bb7e  lea     rdx, aPorts; "Ports"
0x18000bb85  mov     rcx, [rcx+10h]
0x18000bb89  mov     rax, [rax+8]
0x18000bb8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb92  mov     rcx, [rbp+1128h]; this
0x18000bb99  test    eax, eax
0x18000bb9b  jnz     loc_18000C04C
0x18000bba1  mov     r15d, ebx
0x18000bba4  lea     rax, [rsp+1220h+var_11B8]
0x18000bba9  mov     [rbp+1120h+var_1140], rax
0x18000bbad  mov     [rsp+1220h+var_11C0], rbx
0x18000bbb2  mov     [rbp+1120h+var_1158], rbx
0x18000bbb6  mov     [rbp+1120h+var_1160], rbx
0x18000bbba  mov     [rbp+1120h+var_1168], rbx
0x18000bbbe  mov     [rbp+1120h+var_1170], rbx
0x18000bbc2  mov     [rbp+1120h+var_1178], rbx
0x18000bbc6  xor     edx, edx; Val
0x18000bbc8  mov     r8d, 208h; Size
0x18000bbce  lea     rcx, [rbp+1120h+var_260]; void *
0x18000bbd5  call    memset_0
0x18000bbda  mov     [rsp+1220h+var_11AC], 104h
0x18000bbe2  mov     rcx, cs:?m_monitorInit@PortManager@AppMon@@0PEAU_MONITORINIT@@EA; _MONITORINIT * AppMon::PortManager::m_monitorInit
0x18000bbe9  mov     rax, [rcx+18h]
0x18000bbed  mov     rcx, [rcx+8]
0x18000bbf1  mov     [rsp+1220h+var_11F8], rcx
0x18000bbf6  mov     qword ptr [rsp+1220h+var_1200], rbx
0x18000bbfb  lea     r9, [rsp+1220h+var_11AC]
0x18000bc00  lea     r8, [rbp+1120h+var_260]
0x18000bc07  mov     edx, r15d
0x18000bc0a  mov     rcx, [rsp+1220h+var_11B8]
0x18000bc0f  mov     rax, [rax+28h]
0x18000bc13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc18  mov     r14d, eax
0x18000bc1b  test    eax, eax
0x18000bc1d  jnz     loc_18000BF60
0x18000bc23  mov     [rsp+1220h+var_11D0], rbx
0x18000bc28  mov     [rbp+1120h+var_1198], rbx
0x18000bc2c  mov     [rbp+1120h+var_1190], rbx
0x18000bc30  mov     [rsp+1220h+var_11C8], rbx
0x18000bc35  mov     [rbp+1120h+var_11A0], rbx
0x18000bc39  mov     [rbp+1120h+var_1188], rbx
0x18000bc3d  mov     [rbp+1120h+var_1180], rbx
0x18000bc41  mov     rcx, cs:?m_monitorInit@PortManager@AppMon@@0PEAU_MONITORINIT@@EA; _MONITORINIT * AppMon::PortManager::m_monitorInit
0x18000bc48  mov     rax, [rcx+18h]
0x18000bc4c  mov     rcx, [rcx+8]
0x18000bc50  mov     qword ptr [rsp+1220h+var_1200], rcx
0x18000bc55  lea     r9, [rsp+1220h+var_11D0]
0x18000bc5a  mov     r8d, 0F003Fh
0x18000bc60  lea     rdx, [rbp+1120h+var_260]
0x18000bc67  mov     rcx, [rsp+1220h+var_11B8]
0x18000bc6c  mov     rax, [rax+10h]
0x18000bc70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc75  mov     r14d, eax
0x18000bc78  test    eax, eax
0x18000bc7a  jnz     loc_18000BF60
0x18000bc80  lea     rax, [rsp+1220h+var_11D0]
0x18000bc85  mov     [rbp+1120h+var_1150], rax
0x18000bc89  lea     r8, [rbp+1120h+var_1198]; unsigned __int16 **
0x18000bc8d  lea     rdx, aAumid; "Aumid"
0x18000bc94  mov     rcx, [rsp+1220h+var_11D0]; HKEY
0x18000bc99  call    ?QueryRegistryString@PortManager@AppMon@@CAJPEAUHKEY__@@PEBGPEAPEAG@Z; AppMon::PortManager::QueryRegistryString(HKEY__ *,ushort const *,ushort * *)
0x18000bc9e  mov     ebx, eax
0x18000bca0  lea     r8, [rbp+1120h+var_1190]; unsigned __int16 **
0x18000bca4  lea     rdx, aAppsid; "AppSid"
0x18000bcab  mov     rcx, [rsp+1220h+var_11D0]; HKEY
0x18000bcb0  call    ?QueryRegistryString@PortManager@AppMon@@CAJPEAUHKEY__@@PEBGPEAPEAG@Z; AppMon::PortManager::QueryRegistryString(HKEY__ *,ushort const *,ushort * *)
0x18000bcb5  mov     edi, eax
0x18000bcb7  lea     r8, [rsp+1220h+var_11C8]; unsigned __int16 **
0x18000bcbc  lea     rdx, aPortname; "PortName"
0x18000bcc3  mov     rcx, [rsp+1220h+var_11D0]; HKEY
0x18000bcc8  call    ?QueryRegistryString@PortManager@AppMon@@CAJPEAUHKEY__@@PEBGPEAPEAG@Z; AppMon::PortManager::QueryRegistryString(HKEY__ *,ushort const *,ushort * *)
0x18000bccd  mov     esi, eax
0x18000bccf  lea     r8, [rbp+1120h+var_11A0]; unsigned __int16 **
0x18000bcd3  lea     rdx, aAppexe; "AppExe"
0x18000bcda  mov     rcx, [rsp+1220h+var_11D0]; HKEY
0x18000bcdf  call    ?QueryRegistryString@PortManager@AppMon@@CAJPEAUHKEY__@@PEBGPEAPEAG@Z; AppMon::PortManager::QueryRegistryString(HKEY__ *,ushort const *,ushort * *)
0x18000bce4  mov     r12d, eax
0x18000bce7  lea     r8, [rbp+1120h+var_1188]; unsigned __int16 **
0x18000bceb  lea     rdx, aAppcmdlinetemp; "AppCmdlineTemplate"
0x18000bcf2  mov     rcx, [rsp+1220h+var_11D0]; HKEY
0x18000bcf7  call    ?QueryRegistryString@PortManager@AppMon@@CAJPEAUHKEY__@@PEBGPEAPEAG@Z; AppMon::PortManager::QueryRegistryString(HKEY__ *,ushort const *,ushort * *)
0x18000bcfc  mov     r13d, eax
0x18000bcff  lea     r8, [rbp+1120h+var_1180]; unsigned __int16 **
0x18000bd03  lea     rdx, aAppuap11parame; "AppUap11Parameters"
0x18000bd0a  mov     rcx, [rsp+1220h+var_11D0]; HKEY
0x18000bd0f  call    ?QueryRegistryString@PortManager@AppMon@@CAJPEAUHKEY__@@PEBGPEAPEAG@Z; AppMon::PortManager::QueryRegistryString(HKEY__ *,ushort const *,ushort * *)
0x18000bd14  mov     [rsp+1220h+var_11A8], eax
0x18000bd18  mov     rdx, [rbp+1120h+var_1198]
0x18000bd1c  lea     rcx, [rsp+1220h+var_11C0]
0x18000bd21  call    ?reset@?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort>::reset(ushort *)
0x18000bd26  mov     rdx, [rbp+1120h+var_1190]
0x18000bd2a  lea     rcx, [rbp+1120h+var_1158]
0x18000bd2e  call    ?reset@?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort>::reset(ushort *)
0x18000bd33  mov     rdx, [rsp+1220h+var_11C8]
0x18000bd38  lea     rcx, [rbp+1120h+var_1160]
0x18000bd3c  call    ?reset@?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort>::reset(ushort *)
0x18000bd41  mov     rdx, [rbp+1120h+var_11A0]
0x18000bd45  lea     rcx, [rbp+1120h+var_1168]
0x18000bd49  call    ?reset@?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort>::reset(ushort *)
0x18000bd4e  mov     rdx, [rbp+1120h+var_1188]
0x18000bd52  lea     rcx, [rbp+1120h+var_1170]
0x18000bd56  call    ?reset@?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort>::reset(ushort *)
0x18000bd5b  mov     rdx, [rbp+1120h+var_1180]
0x18000bd5f  lea     rcx, [rbp+1120h+var_1178]
0x18000bd63  call    ?reset@?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort>::reset(ushort *)
0x18000bd68  test    ebx, ebx
0x18000bd6a  js      loc_18000BF54
0x18000bd70  xor     ebx, ebx
0x18000bd72  test    edi, edi
0x18000bd74  js      loc_18000BF56
0x18000bd7a  test    esi, esi
0x18000bd7c  js      loc_18000BF56
0x18000bd82  test    r12d, r12d
0x18000bd85  js      loc_18000BF56
0x18000bd8b  test    r13d, r13d
0x18000bd8e  js      loc_18000BF56
0x18000bd94  xor     edx, edx; Val
0x18000bd96  mov     r8d, 0E36h; Size
0x18000bd9c  lea     rcx, [rbp+1120h+var_10A0]; void *
0x18000bda3  call    memset_0
0x18000bda8  mov     r11, [rbp+1128h]
0x18000bdaf  mov     r8, [rsp+1220h+var_11C8]; unsigned __int16 *
0x18000bdb4  mov     edx, 104h; unsigned __int64
0x18000bdb9  lea     rcx, [rbp+1120h+var_FA0]; unsigned __int16 *
0x18000bdc0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bdc5  shr     eax, 1Fh
0x18000bdc8  xor     al, 1
0x18000bdca  jz      loc_18000C037
0x18000bdd0  mov     r11, [rbp+1128h]
0x18000bdd7  mov     r8, [rbp+1120h+var_11A0]; unsigned __int16 *
0x18000bddb  mov     edx, 104h; unsigned __int64
0x18000bde0  lea     rcx, [rbp+1120h+var_884]; unsigned __int16 *
0x18000bde7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bdec  shr     eax, 1Fh
0x18000bdef  xor     al, 1
0x18000bdf1  jz      loc_18000C0AE
0x18000bdf7  mov     r11, [rbp+1128h]
0x18000bdfe  mov     r8, [rbp+1120h+var_1198]; unsigned __int16 *
0x18000be02  mov     edx, 82h; unsigned __int64
0x18000be07  lea     rcx, [rbp+1120h+var_D98]; unsigned __int16 *
0x18000be0e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000be13  shr     eax, 1Fh
0x18000be16  xor     al, 1
0x18000be18  jz      loc_18000C099
0x18000be1e  mov     r11, [rbp+1128h]
0x18000be25  mov     r8, [rbp+1120h+var_1190]; unsigned __int16 *
0x18000be29  mov     edx, 104h; unsigned __int64
0x18000be2e  lea     rcx, [rbp+1120h+var_C94]; unsigned __int16 *
0x18000be35  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000be3a  shr     eax, 1Fh
0x18000be3d  xor     al, 1
0x18000be3f  jz      loc_18000C084
0x18000be45  mov     r11, [rbp+1128h]
0x18000be4c  mov     r8, [rbp+1120h+var_1188]; unsigned __int16 *
0x18000be50  mov     edx, 104h; unsigned __int64
0x18000be55  lea     rcx, [rbp+1120h+var_67C]; unsigned __int16 *
0x18000be5c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000be61  shr     eax, 1Fh
0x18000be64  xor     al, 1
0x18000be66  jz      loc_18000C06F
0x18000be6c  cmp     [rsp+1220h+var_11A8], ebx
0x18000be70  jl      short loc_18000BEA0
0x18000be72  mov     [rbp+1120h+var_26C], 1
0x18000be79  mov     r11, [rbp+1128h]
0x18000be80  mov     r8, [rbp+1120h+var_1180]; unsigned __int16 *
0x18000be84  mov     edx, 104h; unsigned __int64
0x18000be89  lea     rcx, [rbp+1120h+var_474]; unsigned __int16 *
0x18000be90  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000be95  shr     eax, 1Fh
0x18000be98  xor     al, 1
0x18000be9a  jz      loc_18000C05A
0x18000bea0  lea     rdx, [rbp+1120h+var_10A0]
0x18000bea7  lea     rcx, [rbp+1120h+var_1120]
0x18000beab  call    ??$make_shared@VAppPrinterEndPoint@AppMon@@AEAUAPPINFO@2@@std@@YA?AV?$shared_ptr@VAppPrinterEndPoint@AppMon@@@0@AEAUAPPINFO@AppMon@@@Z; std::make_shared<AppMon::AppPrinterEndPoint,AppMon::APPINFO &>(AppMon::APPINFO &)
0x18000beb0  mov     rcx, [rax]
0x18000beb3  mov     [rbp+1120h+var_1138], rcx
0x18000beb7  mov     rsi, [rax+8]
0x18000bebb  mov     [rbp+1120h+var_1130], rsi
0x18000bebf  mov     [rax], rbx
0x18000bec2  mov     [rax+8], rbx
0x18000bec6  mov     rcx, [rbp+1120h+var_1118]; this
0x18000beca  test    rcx, rcx
0x18000becd  jz      short loc_18000BED4
0x18000becf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bed4  mov     rdi, [rbp+1120h+var_1108]
0x18000bed8  mov     rdx, [rsp+1220h+var_11C8]
0x18000bedd  lea     rcx, [rbp+1120h+var_10C0]
0x18000bee1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000bee6  lea     r8, [rbp+1120h+var_10C0]
0x18000beea  lea     rdx, [rbp+1120h+var_1128]
0x18000beee  lea     rcx, [rbp+1120h+var_1110]
0x18000bef2  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::find(std::wstring const &)
0x18000bef7  mov     rbx, [rax]
0x18000befa  lea     rcx, [rbp+1120h+var_10C0]
0x18000befe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000bf03  cmp     rdi, rbx
0x18000bf06  jnz     short loc_18000BF43
0x18000bf08  mov     rdx, [rsp+1220h+var_11C8]
0x18000bf0d  lea     rcx, [rbp+1120h+var_10C0]
0x18000bf11  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000bf16  nop
0x18000bf17  lea     r8, [rbp+1120h+var_10C0]
0x18000bf1b  lea     rdx, [rbp+1120h+var_10D0]
0x18000bf1f  lea     rcx, [rbp+1120h+var_1110]
0x18000bf23  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18000bf28  mov     rcx, [rax]
0x18000bf2b  add     rcx, 30h ; '0'
0x18000bf2f  lea     rdx, [rbp+1120h+var_1138]
0x18000bf33  call    ??4?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<AppMon::AppPrinterEndPointBase>::operator=(std::shared_ptr<AppMon::AppPrinterEndPointBase> const &)
0x18000bf38  nop
0x18000bf39  lea     rcx, [rbp+1120h+var_10C0]
0x18000bf3d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000bf42  nop
0x18000bf43  xor     ebx, ebx
0x18000bf45  test    rsi, rsi
0x18000bf48  jz      short loc_18000BF56
0x18000bf4a  mov     rcx, rsi; this
0x18000bf4d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bf52  jmp     short loc_18000BF56
0x18000bf54  xor     ebx, ebx
0x18000bf56  lea     rcx, [rbp+1120h+var_1150]
0x18000bf5a  call    ??1?$unique_ptr@PEAUHKEY__@@URegKeyCloser@AppMon@@@std@@QEAA@XZ; std::unique_ptr<HKEY__ *,AppMon::RegKeyCloser>::~unique_ptr<HKEY__ *,AppMon::RegKeyCloser>(void)
0x18000bf5f  nop
0x18000bf60  lea     rcx, [rbp+1120h+var_1178]
0x18000bf64  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x18000bf69  nop
0x18000bf6a  lea     rcx, [rbp+1120h+var_1170]
0x18000bf6e  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x18000bf73  nop
0x18000bf74  lea     rcx, [rbp+1120h+var_1168]
0x18000bf78  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x18000bf7d  nop
0x18000bf7e  lea     rcx, [rbp+1120h+var_1160]
0x18000bf82  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x18000bf87  nop
0x18000bf88  lea     rcx, [rbp+1120h+var_1158]
0x18000bf8c  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x18000bf91  nop
0x18000bf92  lea     rcx, [rsp+1220h+var_11C0]
0x18000bf97  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x18000bf9c  test    r14d, r14d
0x18000bf9f  jnz     short loc_18000BFA9
0x18000bfa1  inc     r15d
0x18000bfa4  jmp     loc_18000BBAD
0x18000bfa9  mov     rbx, [rbp+1120h+var_1148]
0x18000bfad  mov     rbx, [rbx]
0x18000bfb0  lea     rax, [rbp+1120h+var_1110]
0x18000bfb4  cmp     rbx, rax
0x18000bfb7  jz      short loc_18000C001
0x18000bfb9  mov     [rsp+1220h+var_11C0], rbx
0x18000bfbe  mov     eax, [rbp+1120h+var_1110]
0x18000bfc1  mov     [rbx], eax
0x18000bfc3  mov     rdx, [rbp+1120h+var_1108]
0x18000bfc7  lea     rcx, [rbx+8]
0x18000bfcb  mov     r8, rdx
0x18000bfce  mov     rdx, [rdx]
0x18000bfd1  call    ??$_Assign_cast@AEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@@std@@AEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::list<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>::_Assign_cast<std::pair<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>> &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>>,std::_Iterator_base0>)
0x18000bfd6  mov     rdx, [rbx+10h]
0x18000bfda  mov     rcx, rbx
0x18000bfdd  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x18000bfe2  mov     rdx, rax
0x18000bfe5  mov     rcx, rbx
0x18000bfe8  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Forced_rehash(unsigned __int64)
0x18000bfed  mov     [rsp+1220h+var_11C0], 0
0x18000bff6  lea     rcx, [rsp+1220h+var_11C0]
0x18000bffb  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Clear_guard::~_Clear_guard(void)
0x18000c000  nop
  ... truncated ...
```
