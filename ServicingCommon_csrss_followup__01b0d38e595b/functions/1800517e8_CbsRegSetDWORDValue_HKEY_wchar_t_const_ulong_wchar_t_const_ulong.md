# CbsRegSetDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong)

- ea: `0x1800517e8`
- end: `0x1800519a4`
- name: `?CbsRegSetDWORDValue@@YAJPEAUHKEY__@@PEB_WK1K@Z`
- size: `444`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, unsigned int, const wchar_t *, BYTE Data)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180051a6c`

## callees

- `0x18002d2b0`
- `0x180046bb4`
- `0x180046ca4`
- `0x1800473a8`
- `0x180047c5c`
- `0x18005126c`
- `0x1800517e8`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180051914`
- `ADVAPI32!RegSetValueExW` at `0x180051914`

## string_xrefs

- `0x180051888`: `Failed to open key: {}`
- `0x180051945`: `Failed to set registry value: {}`
- `0x180051816`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SideBySide`

## pseudocode

```c
__int64 CbsRegSetDWORDValue(HKEY a1, const wchar_t *a2, __int64 a3, const wchar_t *a4, ...)
{
  LSTATUS v4; // eax
  int v5; // edx
  int v6; // r8d
  LSTATUS v7; // ebx
  unsigned int v8; // ebx
  int v10; // edx
  unsigned int v11; // eax
  __int64 v12; // rdx
  int v13; // edx
  int v14; // r8d
  int v15; // edx
  unsigned int v16; // eax
  unsigned int lpData; // [rsp+20h] [rbp-50h]
  unsigned int v18; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v19[2]; // [rsp+38h] [rbp-38h] BYREF
  LPCWSTR lpValueName[2]; // [rsp+40h] [rbp-30h] BYREF
  const wchar_t *v21; // [rsp+50h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  va_list va; // [rsp+A0h] [rbp+30h] BYREF

  va_start(va, a4);
  hKey = 0;
  lpValueName[0] = L"MaintenanceFlags";
  v21 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SideBySide";
  v4 = CbsRegOpenKeyExW(a1, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SideBySide", a3, 2u, &hKey);
  v7 = v4;
  if ( v4 == 2 || v4 == 3 )
  {
    v8 = (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    if ( v4 )
    {
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          v5,
          v6,
          (unsigned int)"Failed to open key: {}",
          (__int64)&v21);
        if ( v7 > 0 )
          v11 = (unsigned __int16)v7 | 0x80070000;
        else
          v11 = v7;
        v18 = v11;
        *(_QWORD *)v19 = &v18;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v10,
          3,
          (unsigned int)": {0}",
          (__int64)v19);
      }
      v12 = 669;
    }
    else
    {
      v7 = RegSetValueExW(hKey, lpValueName[0], 0, 4u, (const BYTE *)va, 4u);
      if ( v7 == 2 )
      {
        v8 = -2147024894;
        goto LABEL_4;
      }
      if ( !v7 )
      {
        v8 = 0;
        goto LABEL_4;
      }
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          v13,
          v14,
          (unsigned int)"Failed to set registry value: {}",
          (__int64)lpValueName);
        if ( v7 > 0 )
          v16 = (unsigned __int16)v7 | 0x80070000;
        else
          v16 = v7;
        v18 = v16;
        *(_QWORD *)v19 = &v18;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v15,
          3,
          (unsigned int)": {0}",
          (__int64)v19);
      }
      v12 = 686;
    }
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v12,
           (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
           (const char *)(unsigned int)v7,
           lpData);
  }
LABEL_4:
  Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&hKey);
  return v8;
}

```

## disassembly

```asm
0x1800517e8  mov     [rsp-8+arg_0], rbx
0x1800517ed  push    rbp
0x1800517ee  mov     rbp, rsp
0x1800517f1  sub     rsp, 70h
0x1800517f5  mov     rax, cs:__security_cookie
0x1800517fc  xor     rax, rsp
0x1800517ff  mov     [rbp+var_8], rax
0x180051803  lea     rax, aMaintenancefla; "MaintenanceFlags"
0x18005180a  mov     [rbp+hKey], 0
0x180051812  mov     [rbp+lpValueName], rax
0x180051816  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18005181d  lea     rax, [rbp+hKey]
0x180051821  mov     [rbp+var_20], rdx
0x180051825  mov     r9d, 2; unsigned int
0x18005182b  mov     [rsp+70h+lpData], rax; HKEY *
0x180051830  call    ?CbsRegOpenKeyExW@@YAKPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z; CbsRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x180051835  mov     ebx, eax
0x180051837  cmp     eax, 2
0x18005183a  jz      short loc_180051845
0x18005183c  cmp     eax, 3
0x18005183f  jnz     short loc_180051874
0x180051841  test    eax, eax
0x180051843  jle     short loc_18005184E
0x180051845  movzx   ebx, bx
0x180051848  or      ebx, 80070000h
0x18005184e  lea     rcx, [rbp+hKey]
0x180051852  call    ?Close@?$AutoGenericHandleBase@PEAUHKEY__@@$0A@V?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(void)
0x180051857  mov     eax, ebx
0x180051859  mov     rcx, [rbp+var_8]
0x18005185d  xor     rcx, rsp; StackCookie
0x180051860  call    __security_check_cookie
0x180051865  mov     rbx, [rsp+70h+arg_0]
0x18005186d  add     rsp, 70h
0x180051871  pop     rbp
0x180051872  retn
0x180051874  test    ebx, ebx
0x180051876  jz      short loc_1800518F5
0x180051878  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005187f  test    rcx, rcx
0x180051882  jz      short loc_1800518D6
0x180051884  lea     rax, [rbp+var_20]
0x180051888  lea     r9, aFailedToOpenKe; "Failed to open key: {}"
0x18005188f  mov     [rsp+70h+lpData], rax
0x180051894  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180051899  test    ebx, ebx
0x18005189b  jg      short loc_1800518A1
0x18005189d  mov     eax, ebx
0x18005189f  jmp     short loc_1800518A9
0x1800518a1  movzx   eax, bx
0x1800518a4  or      eax, 80070000h
0x1800518a9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800518b0  lea     r9, a0; ": {0}"
0x1800518b7  mov     [rbp+var_40], eax
0x1800518ba  mov     r8d, 3
0x1800518c0  lea     rax, [rbp+var_40]
0x1800518c4  mov     qword ptr [rbp+var_38], rax
0x1800518c8  lea     rax, [rbp+var_38]
0x1800518cc  mov     [rsp+70h+lpData], rax; unsigned int
0x1800518d1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800518d6  mov     edx, 29Dh; void *
0x1800518db  mov     rcx, [rbp+8]; this
0x1800518df  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x1800518e6  mov     r9d, ebx; char *
0x1800518e9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800518ee  mov     ebx, eax
0x1800518f0  jmp     loc_18005184E
0x1800518f5  mov     rdx, [rbp+lpValueName]; lpValueName
0x1800518f9  lea     rax, [rbp+Data]
0x1800518fd  mov     rcx, [rbp+hKey]; hKey
0x180051901  mov     r9d, 4; dwType
0x180051907  mov     [rsp+70h+cbData], r9d; cbData
0x18005190c  xor     r8d, r8d; Reserved
0x18005190f  mov     [rsp+70h+lpData], rax; lpData
0x180051914  call    cs:__imp_RegSetValueExW
0x18005191b  nop     dword ptr [rax+rax+00h]
0x180051920  mov     ebx, eax
0x180051922  cmp     eax, 2
0x180051925  jnz     short loc_180051931
0x180051927  mov     ebx, 80070002h
0x18005192c  jmp     loc_18005184E
0x180051931  test    ebx, ebx
0x180051933  jz      short loc_18005199D
0x180051935  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005193c  test    rcx, rcx
0x18005193f  jz      short loc_180051993
0x180051941  lea     rax, [rbp+lpValueName]
0x180051945  lea     r9, aFailedToSetReg; "Failed to set registry value: {}"
0x18005194c  mov     [rsp+70h+lpData], rax
0x180051951  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180051956  test    ebx, ebx
0x180051958  jg      short loc_18005195E
0x18005195a  mov     eax, ebx
0x18005195c  jmp     short loc_180051966
0x18005195e  movzx   eax, bx
0x180051961  or      eax, 80070000h
0x180051966  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005196d  lea     r9, a0; ": {0}"
0x180051974  mov     [rbp+var_40], eax
0x180051977  mov     r8d, 3
0x18005197d  lea     rax, [rbp+var_40]
0x180051981  mov     qword ptr [rbp+var_38], rax
0x180051985  lea     rax, [rbp+var_38]
0x180051989  mov     [rsp+70h+lpData], rax
0x18005198e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180051993  mov     edx, 2AEh
0x180051998  jmp     loc_1800518DB
0x18005199d  xor     ebx, ebx
0x18005199f  jmp     loc_18005184E
```
