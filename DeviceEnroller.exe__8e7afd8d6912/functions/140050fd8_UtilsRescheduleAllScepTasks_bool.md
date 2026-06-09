# UtilsRescheduleAllScepTasks(bool)

- ea: `0x140050fd8`
- end: `0x1400516e4`
- name: `?UtilsRescheduleAllScepTasks@@YAJ_N@Z`
- size: `1804`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140019a6c`

## callees

- `0x1400042f0`
- `0x1400095b4`
- `0x14000a6c4`
- `0x14000a6e4`
- `0x14001e784`
- `0x14001ed14`
- `0x140028284`
- `0x14003d0d0`
- `0x1400508bc`
- `0x140050fd8`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x14005106a`
- `DMCmnUtils!DmGetActiveUserSid` at `0x14005106a`
- `DMCmnUtils!DmRevertToSelf` at `0x140051115`
- `DMCmnUtils!DmRevertToSelf` at `0x1400511cd`
- `DMCmnUtils!DmRevertToSelf` at `0x140051227`
- `DMCmnUtils!DmRevertToSelf` at `0x140051115`
- `DMCmnUtils!DmRevertToSelf` at `0x1400511cd`
- `DMCmnUtils!DmRevertToSelf` at `0x140051227`
- `DMCmnUtils!DmImpersonate` at `0x1400510d7`
- `DMCmnUtils!DmImpersonate` at `0x1400510d7`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x14005141b`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x14005141b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051047`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005116c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051047`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005116c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005105a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005117f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005105a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005117f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140051266`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140051333`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140051266`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140051333`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005109d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005113d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051177`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400511f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051298`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400512a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051365`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051376`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051387`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005144e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005145f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051470`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051583`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051594`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400515a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051622`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051637`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051648`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005109d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005113d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051177`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400511f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051298`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400512a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051365`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051376`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051387`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005144e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005145f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051470`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051583`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051594`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400515a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051622`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051637`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051648`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400512f9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400513d7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14005160c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400512f9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400513d7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14005160c`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x140051198`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x140051198`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140051052`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400510b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140051155`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005120d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400512c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005139f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140051488`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400515bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140051660`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140051052`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400510b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140051155`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005120d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400512c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005139f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140051488`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400515bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140051660`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14005111d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400511d5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14005122f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14005111d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400511d5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14005122f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400510a4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140051144`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400511fc`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400512b0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14005138e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140051477`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400515ac`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14005164f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400510a4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140051144`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400511fc`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400512b0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14005138e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140051477`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400515ac`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14005164f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140051017`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140051017`

## string_xrefs

- `0x140051692`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall UtilsRescheduleAllScepTasks()
{
  HRESULT v0; // eax
  int ActiveUserSid; // eax
  unsigned int v2; // ebx
  const char *v3; // r9
  __int64 result; // rax
  int v5; // eax
  unsigned int v6; // ebx
  unsigned int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // ebx
  int v13; // esi
  LSTATUS v14; // ebx
  unsigned int v15; // eax
  unsigned int v16; // ebx
  DWORD v17; // edi
  DWORD i; // edx
  const unsigned __int16 *v19; // r8
  int DWORD; // eax
  unsigned int v21; // ebx
  const unsigned __int16 *p_Src; // rdx
  int v23; // eax
  unsigned int v24; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-4E8h]
  int phkResulta; // [rsp+20h] [rbp-4E8h]
  unsigned int phkResultb; // [rsp+20h] [rbp-4E8h]
  unsigned int phkResultc; // [rsp+20h] [rbp-4E8h]
  int phkResultd; // [rsp+20h] [rbp-4E8h]
  HKEY hKey; // [rsp+40h] [rbp-4C8h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-4C0h] BYREF
  unsigned int v32; // [rsp+50h] [rbp-4B8h] BYREF
  HKEY v33; // [rsp+58h] [rbp-4B0h] BYREF
  char v34; // [rsp+60h] [rbp-4A8h]
  DWORD v35; // [rsp+64h] [rbp-4A4h] BYREF
  DWORD cchName; // [rsp+68h] [rbp-4A0h] BYREF
  HKEY v37; // [rsp+70h] [rbp-498h] BYREF
  __int128 Src; // [rsp+80h] [rbp-488h] BYREF
  __int128 v39; // [rsp+90h] [rbp-478h]
  WCHAR v40[264]; // [rsp+A0h] [rbp-468h] BYREF
  WCHAR Name[264]; // [rsp+2B0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+508h] [rbp+0h]

  cchName = 261;
  v35 = 261;
  hMem = 0;
  v0 = CoInitializeEx(0, 0);
  try
  {
    if ( v0 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x14D3,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        (const char *)(unsigned int)v0,
        phkResult);
    v34 = 1;
    hKey = 0;
    hMem = 0;
    ActiveUserSid = DmGetActiveUserSid((unsigned __int16 **)&hMem);
    v2 = ActiveUserSid;
    if ( ActiveUserSid >= 0 )
    {
      LOBYTE(v37) = 0;
      BYTE2(v37) = 0;
      v5 = DmImpersonate((const unsigned __int16 *)hMem);
      v6 = v5;
      if ( v5 >= 0 )
      {
        hKey = 0;
        v7 = RegOpenCurrentUser(0x20019u, &hKey);
        if ( v7 )
        {
          v8 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0xC8F,
                 (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
                 (const char *)v7,
                 phkResult);
          v9 = DmRevertToSelf();
          if ( v9 < 0 )
            wil::details::in1diag3::_FailFast_Hr(
              retaddr,
              (void *)0x2C,
              (unsigned int)"onecoreuap\\admin\\dm\\published\\inc\\dmraii.hxx",
              (const char *)(unsigned int)v9,
              phkResulta);
          if ( hKey )
            RegCloseKey(hKey);
          CoUninitialize();
          if ( hMem )
            LocalFree(hMem);
          result = v8;
        }
        else
        {
          v10 = DmRevertToSelf();
          if ( v10 < 0 )
            wil::details::in1diag3::_FailFast_Hr(
              retaddr,
              (void *)0x2C,
              (unsigned int)"onecoreuap\\admin\\dm\\published\\inc\\dmraii.hxx",
              (const char *)(unsigned int)v10,
              phkResult);
          v33 = 0;
          v11 = RegOpenKeyExW(hKey, L"Software\\Microsoft\\SCEP\\", 0, 0x20019u, &v33);
          if ( v11 )
          {
            v12 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0xC98,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
                    (const char *)v11,
                    phkResultb);
            if ( v33 )
              RegCloseKey(v33);
            if ( hKey )
              RegCloseKey(hKey);
            CoUninitialize();
            if ( hMem )
              LocalFree(hMem);
            result = v12;
          }
          else
          {
            v13 = 0;
            v14 = RegEnumKeyExW(v33, 0, Name, &cchName, 0, 0, 0, 0);
            while ( !v14 )
            {
              cchName = 261;
              v37 = 0;
              v15 = RegOpenKeyExW(v33, Name, 0, 0x20019u, &v37);
              if ( v15 )
              {
                v16 = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0xCA2,
                        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
                        (const char *)v15,
                        phkResultc);
                if ( v37 )
                  RegCloseKey(v37);
                if ( v33 )
                  RegCloseKey(v33);
                if ( hKey )
                  RegCloseKey(hKey);
                CoUninitialize();
                if ( hMem )
                  LocalFree(hMem);
                return v16;
              }
              v17 = 0;
              for ( i = 0; !RegEnumKeyExW(v37, i, v40, &v35, 0, 0, 0, 0); i = v17 )
              {
                v32 = 0;
                v35 = 261;
                v19 = (const unsigned __int16 *)&qword_14007E700;
                if ( (unsigned __int64)qword_14007E718 > 7 )
                  v19 = (const unsigned __int16 *)qword_14007E700;
                DWORD = OmaDmRegistryGetDWORD(v37, v40, v19, &v32);
                v21 = DWORD;
                if ( DWORD < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xCAD,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
                    (const char *)(unsigned int)DWORD,
                    phkResultd);
                  if ( v37 )
                    RegCloseKey(v37);
                  if ( v33 )
                    RegCloseKey(v33);
                  if ( hKey )
                    RegCloseKey(hKey);
                  CoUninitialize();
                  if ( hMem )
                    LocalFree(hMem);
                  return v21;
                }
                if ( ((v32 - 2) & 0xFFFFFFFD) == 0 )
                {
                  Src = 0;
                  v39 = 0;
                  std::wstring::_Construct<1,unsigned short const *>(
                    (char **)&Src,
                    L"Software\\Microsoft\\SCEP\\",
                    0x18u);
                  std::wstring::append(&Src, Name);
                  std::wstring::append(&Src, (void *)L"\\");
                  std::wstring::append(&Src, v40);
                  p_Src = (const unsigned __int16 *)&Src;
                  if ( *((_QWORD *)&v39 + 1) > 7u )
                    p_Src = (const unsigned __int16 *)Src;
                  v23 = UtilsRemakeSCEPInstallationTask(hKey, p_Src, v40, (const unsigned __int16 *)hMem);
                  v24 = v23;
                  if ( v23 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xCB6,
                      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
                      (const char *)(unsigned int)v23,
                      phkResultd);
                    std::wstring::~wstring((char **)&Src);
                    if ( v37 )
                      RegCloseKey(v37);
                    if ( v33 )
                      RegCloseKey(v33);
                    if ( hKey )
                      RegCloseKey(hKey);
                    CoUninitialize();
                    if ( hMem )
                      LocalFree(hMem);
                    return v24;
                  }
                  std::wstring::~wstring((char **)&Src);
                }
                ++v17;
              }
              v14 = RegEnumKeyExW(v33, ++v13, Name, &cchName, 0, 0, 0, 0);
              if ( v37 )
                RegCloseKey(v37);
            }
            if ( v33 )
              RegCloseKey(v33);
            if ( hKey )
              RegCloseKey(hKey);
            CoUninitialize();
            if ( hMem )
              LocalFree(hMem);
            result = 0;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC8E,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
          (const char *)(unsigned int)v5,
          phkResult);
        CoUninitialize();
        if ( hMem )
          LocalFree(hMem);
        result = v6;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC8C,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
        (const char *)(unsigned int)ActiveUserSid,
        phkResult);
      CoUninitialize();
      if ( hMem )
        LocalFree(hMem);
      result = v2;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xCC2,
                           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x140050fd8  push    rbx
0x140050fda  push    rsi
0x140050fdb  push    rdi
0x140050fdc  push    r12
0x140050fde  push    r14
0x140050fe0  push    r15
0x140050fe2  sub     rsp, 4D8h
0x140050fe9  mov     rax, cs:__security_cookie
0x140050ff0  xor     rax, rsp
0x140050ff3  mov     [rsp+508h+var_48], rax
0x140050ffb  xor     r15d, r15d
0x140050ffe  mov     [rsp+508h+cchName], 105h
0x140051006  mov     [rsp+508h+var_4A4], 105h
0x14005100e  mov     [rsp+508h+hMem], r15
0x140051013  xor     edx, edx; dwCoInit
0x140051015  xor     ecx, ecx; pvReserved
0x140051017  call    cs:__imp_CoInitializeEx
0x14005101d  mov     rcx, [rsp+508h]; this
0x140051025  test    eax, eax
0x140051027  js      loc_14005168F
0x14005102d  mov     r12d, 1
0x140051033  mov     [rsp+508h+var_4A8], r12b
0x140051038  mov     [rsp+508h+hKey], r15
0x14005103d  mov     rdi, [rsp+508h+hMem]
0x140051042  test    rdi, rdi
0x140051045  jz      short loc_140051060
0x140051047  call    cs:__imp_GetLastError
0x14005104d  mov     ebx, eax
0x14005104f  mov     rcx, rdi; hMem
0x140051052  call    cs:__imp_LocalFree
0x140051058  mov     ecx, ebx; dwErrCode
0x14005105a  call    cs:__imp_SetLastError
0x140051060  mov     [rsp+508h+hMem], r15
0x140051065  lea     rcx, [rsp+508h+hMem]
0x14005106a  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x140051070  mov     ebx, eax
0x140051072  test    eax, eax
0x140051074  jns     short loc_1400510C2
0x140051076  mov     rcx, [rsp+508h]; this
0x14005107e  mov     r9d, eax; char *
0x140051081  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x140051088  mov     edx, 0C8Ch; void *
0x14005108d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140051092  nop
0x140051093  mov     rcx, [rsp+508h+hKey]; hKey
0x140051098  test    rcx, rcx
0x14005109b  jz      short loc_1400510A4
0x14005109d  call    cs:__imp_RegCloseKey
0x1400510a3  nop
0x1400510a4  call    cs:__imp_CoUninitialize
0x1400510aa  nop
0x1400510ab  mov     rcx, [rsp+508h+hMem]; hMem
0x1400510b0  test    rcx, rcx
0x1400510b3  jz      short loc_1400510BB
0x1400510b5  call    cs:__imp_LocalFree
0x1400510bb  mov     eax, ebx
0x1400510bd  jmp     loc_14005166E
0x1400510c2  mov     sil, r15b
0x1400510c5  mov     byte ptr [rsp+508h+var_498], r15b
0x1400510ca  mov     dil, r15b
0x1400510cd  mov     byte ptr [rsp+508h+var_498+2], r15b
0x1400510d2  mov     rcx, [rsp+508h+hMem]
0x1400510d7  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x1400510dd  mov     ebx, eax
0x1400510df  test    eax, eax
0x1400510e1  js      short loc_1400510EB
0x1400510e3  mov     sil, r12b
0x1400510e6  mov     dil, r12b
0x1400510e9  jmp     short loc_140051162
0x1400510eb  mov     rcx, [rsp+508h]; this
0x1400510f3  mov     r9d, ebx; char *
0x1400510f6  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1400510fd  mov     edx, 0C8Eh; void *
0x140051102  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140051107  nop
0x140051108  mov     eax, r15d
0x14005110b  test    sil, sil
0x14005110e  jz      short loc_140051123
0x140051110  test    dil, dil
0x140051113  jz      short loc_14005111D
0x140051115  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x14005111b  jmp     short loc_140051123
0x14005111d  call    cs:__imp_CoRevertToSelf
0x140051123  mov     rcx, [rsp+508h]; this
0x14005112b  test    eax, eax
0x14005112d  js      loc_1400516A4
0x140051133  mov     rcx, [rsp+508h+hKey]; hKey
0x140051138  test    rcx, rcx
0x14005113b  jz      short loc_140051144
0x14005113d  call    cs:__imp_RegCloseKey
0x140051143  nop
0x140051144  call    cs:__imp_CoUninitialize
0x14005114a  nop
0x14005114b  mov     rcx, [rsp+508h+hMem]; hMem
0x140051150  test    rcx, rcx
0x140051153  jz      short loc_14005115B
0x140051155  call    cs:__imp_LocalFree
0x14005115b  mov     eax, ebx
0x14005115d  jmp     loc_14005166E
0x140051162  mov     r14, [rsp+508h+hKey]
0x140051167  test    r14, r14
0x14005116a  jz      short loc_140051185
0x14005116c  call    cs:__imp_GetLastError
0x140051172  mov     ebx, eax
0x140051174  mov     rcx, r14; hKey
0x140051177  call    cs:__imp_RegCloseKey
0x14005117d  mov     ecx, ebx; dwErrCode
0x14005117f  call    cs:__imp_SetLastError
0x140051185  mov     [rsp+508h+hKey], r15
0x14005118a  lea     rdx, [rsp+508h+hKey]; phkResult
0x14005118f  mov     r14d, 20019h
0x140051195  mov     ecx, r14d; samDesired
0x140051198  call    cs:__imp_RegOpenCurrentUser
0x14005119e  test    eax, eax
0x1400511a0  jz      short loc_14005121A
0x1400511a2  mov     rcx, [rsp+508h]; this
0x1400511aa  mov     r9d, eax; char *
0x1400511ad  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1400511b4  mov     edx, 0C8Fh; void *
0x1400511b9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400511be  mov     ebx, eax
0x1400511c0  mov     eax, r15d
0x1400511c3  test    sil, sil
0x1400511c6  jz      short loc_1400511DB
0x1400511c8  test    dil, dil
0x1400511cb  jz      short loc_1400511D5
0x1400511cd  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x1400511d3  jmp     short loc_1400511DB
0x1400511d5  call    cs:__imp_CoRevertToSelf
0x1400511db  mov     rcx, [rsp+508h]; this
0x1400511e3  test    eax, eax
0x1400511e5  js      loc_1400516B9
0x1400511eb  mov     rcx, [rsp+508h+hKey]; hKey
0x1400511f0  test    rcx, rcx
0x1400511f3  jz      short loc_1400511FC
0x1400511f5  call    cs:__imp_RegCloseKey
0x1400511fb  nop
0x1400511fc  call    cs:__imp_CoUninitialize
0x140051202  nop
0x140051203  mov     rcx, [rsp+508h+hMem]; hMem
0x140051208  test    rcx, rcx
0x14005120b  jz      short loc_140051213
0x14005120d  call    cs:__imp_LocalFree
0x140051213  mov     eax, ebx
0x140051215  jmp     loc_14005166E
0x14005121a  mov     eax, r15d
0x14005121d  test    sil, sil
0x140051220  jz      short loc_140051235
0x140051222  test    dil, dil
0x140051225  jz      short loc_14005122F
0x140051227  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x14005122d  jmp     short loc_140051235
0x14005122f  call    cs:__imp_CoRevertToSelf
0x140051235  mov     rcx, [rsp+508h]; this
0x14005123d  test    eax, eax
0x14005123f  js      loc_1400516CE
0x140051245  mov     [rsp+508h+var_4B0], r15
0x14005124a  lea     rax, [rsp+508h+var_4B0]
0x14005124f  mov     [rsp+508h+phkResult], rax; unsigned int
0x140051254  mov     r9d, r14d; samDesired
0x140051257  xor     r8d, r8d; ulOptions
0x14005125a  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\SCEP\\"
0x140051261  mov     rcx, [rsp+508h+hKey]; hKey
0x140051266  call    cs:__imp_RegOpenKeyExW
0x14005126c  test    eax, eax
0x14005126e  jz      short loc_1400512CE
0x140051270  mov     rcx, [rsp+508h]; this
0x140051278  mov     r9d, eax; char *
0x14005127b  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x140051282  mov     edx, 0C98h; void *
0x140051287  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14005128c  mov     ebx, eax
0x14005128e  mov     rcx, [rsp+508h+var_4B0]; hKey
0x140051293  test    rcx, rcx
0x140051296  jz      short loc_14005129F
0x140051298  call    cs:__imp_RegCloseKey
0x14005129e  nop
0x14005129f  mov     rcx, [rsp+508h+hKey]; hKey
0x1400512a4  test    rcx, rcx
0x1400512a7  jz      short loc_1400512B0
0x1400512a9  call    cs:__imp_RegCloseKey
0x1400512af  nop
0x1400512b0  call    cs:__imp_CoUninitialize
0x1400512b6  nop
0x1400512b7  mov     rcx, [rsp+508h+hMem]; hMem
0x1400512bc  test    rcx, rcx
0x1400512bf  jz      short loc_1400512C7
0x1400512c1  call    cs:__imp_LocalFree
0x1400512c7  mov     eax, ebx
0x1400512c9  jmp     loc_14005166E
0x1400512ce  mov     esi, r15d
0x1400512d1  mov     [rsp+508h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1400512d6  mov     [rsp+508h+lpcchClass], r15; lpcchClass
0x1400512db  mov     [rsp+508h+lpClass], r15; lpClass
0x1400512e0  mov     [rsp+508h+phkResult], r15; lpReserved
0x1400512e5  lea     r9, [rsp+508h+cchName]; lpcchName
0x1400512ea  lea     r8, [rsp+508h+Name]; lpName
0x1400512f2  xor     edx, edx; dwIndex
0x1400512f4  mov     rcx, [rsp+508h+var_4B0]; hKey
0x1400512f9  call    cs:__imp_RegEnumKeyExW
0x1400512ff  mov     ebx, eax
0x140051301  test    ebx, ebx
0x140051303  jnz     loc_14005162D
0x140051309  mov     [rsp+508h+cchName], 105h
0x140051311  mov     [rsp+508h+var_498], r15
0x140051316  lea     rax, [rsp+508h+var_498]
0x14005131b  mov     [rsp+508h+phkResult], rax; unsigned int
0x140051320  mov     r9d, r14d; samDesired
0x140051323  xor     r8d, r8d; ulOptions
0x140051326  lea     rdx, [rsp+508h+Name]; lpSubKey
0x14005132e  mov     rcx, [rsp+508h+var_4B0]; hKey
0x140051333  call    cs:__imp_RegOpenKeyExW
0x140051339  test    eax, eax
0x14005133b  jz      short loc_1400513AC
0x14005133d  mov     rcx, [rsp+508h]; this
0x140051345  mov     r9d, eax; char *
0x140051348  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x14005134f  mov     edx, 0CA2h; void *
0x140051354  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140051359  mov     ebx, eax
0x14005135b  mov     rcx, [rsp+508h+var_498]; hKey
0x140051360  test    rcx, rcx
0x140051363  jz      short loc_14005136C
0x140051365  call    cs:__imp_RegCloseKey
0x14005136b  nop
0x14005136c  mov     rcx, [rsp+508h+var_4B0]; hKey
0x140051371  test    rcx, rcx
0x140051374  jz      short loc_14005137D
0x140051376  call    cs:__imp_RegCloseKey
0x14005137c  nop
0x14005137d  mov     rcx, [rsp+508h+hKey]; hKey
0x140051382  test    rcx, rcx
0x140051385  jz      short loc_14005138E
0x140051387  call    cs:__imp_RegCloseKey
0x14005138d  nop
0x14005138e  call    cs:__imp_CoUninitialize
0x140051394  nop
0x140051395  mov     rcx, [rsp+508h+hMem]; hMem
0x14005139a  test    rcx, rcx
0x14005139d  jz      short loc_1400513A5
0x14005139f  call    cs:__imp_LocalFree
0x1400513a5  mov     eax, ebx
0x1400513a7  jmp     loc_14005166E
0x1400513ac  mov     edi, r15d
0x1400513af  xor     edx, edx; dwIndex
0x1400513b1  mov     [rsp+508h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1400513b6  mov     [rsp+508h+lpcchClass], r15; lpcchClass
0x1400513bb  mov     [rsp+508h+lpClass], r15; lpClass
0x1400513c0  mov     [rsp+508h+phkResult], r15; int
0x1400513c5  lea     r9, [rsp+508h+var_4A4]; lpcchName
0x1400513ca  lea     r8, [rsp+508h+var_468]; lpName
0x1400513d2  mov     rcx, [rsp+508h+var_498]; hKey
0x1400513d7  call    cs:__imp_RegEnumKeyExW
0x1400513dd  test    eax, eax
0x1400513df  jnz     loc_1400515E1
0x1400513e5  mov     [rsp+508h+var_4B8], r15d
0x1400513ea  mov     [rsp+508h+var_4A4], 105h
0x1400513f2  lea     r8, qword_14007E700
0x1400513f9  cmp     cs:qword_14007E718, 7
0x140051401  cmova   r8, cs:qword_14007E700
0x140051409  lea     r9, [rsp+508h+var_4B8]
0x14005140e  lea     rdx, [rsp+508h+var_468]
0x140051416  mov     rcx, [rsp+508h+var_498]
0x14005141b  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140051421  mov     ebx, eax
0x140051423  test    eax, eax
0x140051425  jns     short loc_140051495
0x140051427  mov     rcx, [rsp+508h]; this
0x14005142f  mov     r9d, eax; char *
0x140051432  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x140051439  mov     edx, 0CADh; void *
0x14005143e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140051443  nop
0x140051444  mov     rcx, [rsp+508h+var_498]; hKey
0x140051449  test    rcx, rcx
0x14005144c  jz      short loc_140051455
0x14005144e  call    cs:__imp_RegCloseKey
0x140051454  nop
0x140051455  mov     rcx, [rsp+508h+var_4B0]; hKey
0x14005145a  test    rcx, rcx
0x14005145d  jz      short loc_140051466
0x14005145f  call    cs:__imp_RegCloseKey
0x140051465  nop
0x140051466  mov     rcx, [rsp+508h+hKey]; hKey
0x14005146b  test    rcx, rcx
0x14005146e  jz      short loc_140051477
0x140051470  call    cs:__imp_RegCloseKey
0x140051476  nop
0x140051477  call    cs:__imp_CoUninitialize
0x14005147d  nop
0x14005147e  mov     rcx, [rsp+508h+hMem]; hMem
0x140051483  test    rcx, rcx
0x140051486  jz      short loc_14005148E
0x140051488  call    cs:__imp_LocalFree
0x14005148e  mov     eax, ebx
0x140051490  jmp     loc_14005166E
0x140051495  mov     eax, [rsp+508h+var_4B8]
0x140051499  add     eax, 0FFFFFFFEh
0x14005149c  test    eax, 0FFFFFFFDh
0x1400514a1  jnz     loc_1400515D7
  ... truncated ...
```
