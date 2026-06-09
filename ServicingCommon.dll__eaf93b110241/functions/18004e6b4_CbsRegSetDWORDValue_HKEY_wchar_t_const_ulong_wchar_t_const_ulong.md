# CbsRegSetDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong)

- ea: `0x18004e6b4`
- end: `0x18004e870`
- name: `?CbsRegSetDWORDValue@@YAJPEAUHKEY__@@PEB_WK1K@Z`
- size: `444`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, unsigned int, const wchar_t *, BYTE Data)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004e938`

## callees

- `0x1800293a0`
- `0x18003d7d4`
- `0x180041de8`
- `0x180043c00`
- `0x180044274`
- `0x18004e134`
- `0x18004e6b4`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18004e7e0`
- `ADVAPI32!RegSetValueExW` at `0x18004e7e0`

## string_xrefs

- `0x18004e754`: `Failed to open key: {}`
- `0x18004e811`: `Failed to set registry value: {}`
- `0x18004e6e2`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SideBySide`

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
0x18004e6b4  mov     [rsp-8+arg_0], rbx
0x18004e6b9  push    rbp
0x18004e6ba  mov     rbp, rsp
0x18004e6bd  sub     rsp, 70h
0x18004e6c1  mov     rax, cs:__security_cookie
0x18004e6c8  xor     rax, rsp
0x18004e6cb  mov     [rbp+var_8], rax
0x18004e6cf  lea     rax, aMaintenancefla; "MaintenanceFlags"
0x18004e6d6  mov     [rbp+hKey], 0
0x18004e6de  mov     [rbp+lpValueName], rax
0x18004e6e2  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18004e6e9  lea     rax, [rbp+hKey]
0x18004e6ed  mov     [rbp+var_20], rdx
0x18004e6f1  mov     r9d, 2; unsigned int
0x18004e6f7  mov     [rsp+70h+lpData], rax; HKEY *
0x18004e6fc  call    ?CbsRegOpenKeyExW@@YAKPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z; CbsRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x18004e701  mov     ebx, eax
0x18004e703  cmp     eax, 2
0x18004e706  jz      short loc_18004E711
0x18004e708  cmp     eax, 3
0x18004e70b  jnz     short loc_18004E740
0x18004e70d  test    eax, eax
0x18004e70f  jle     short loc_18004E71A
0x18004e711  movzx   ebx, bx
0x18004e714  or      ebx, 80070000h
0x18004e71a  lea     rcx, [rbp+hKey]
0x18004e71e  call    ?Close@?$AutoGenericHandleBase@PEAUHKEY__@@$0A@V?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(void)
0x18004e723  mov     eax, ebx
0x18004e725  mov     rcx, [rbp+var_8]
0x18004e729  xor     rcx, rsp; StackCookie
0x18004e72c  call    __security_check_cookie
0x18004e731  mov     rbx, [rsp+70h+arg_0]
0x18004e739  add     rsp, 70h
0x18004e73d  pop     rbp
0x18004e73e  retn
0x18004e740  test    ebx, ebx
0x18004e742  jz      short loc_18004E7C1
0x18004e744  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e74b  test    rcx, rcx
0x18004e74e  jz      short loc_18004E7A2
0x18004e750  lea     rax, [rbp+var_20]
0x18004e754  lea     r9, aFailedToOpenKe; "Failed to open key: {}"
0x18004e75b  mov     [rsp+70h+lpData], rax
0x18004e760  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004e765  test    ebx, ebx
0x18004e767  jg      short loc_18004E76D
0x18004e769  mov     eax, ebx
0x18004e76b  jmp     short loc_18004E775
0x18004e76d  movzx   eax, bx
0x18004e770  or      eax, 80070000h
0x18004e775  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e77c  lea     r9, a0; ": {0}"
0x18004e783  mov     [rbp+var_40], eax
0x18004e786  mov     r8d, 3
0x18004e78c  lea     rax, [rbp+var_40]
0x18004e790  mov     qword ptr [rbp+var_38], rax
0x18004e794  lea     rax, [rbp+var_38]
0x18004e798  mov     [rsp+70h+lpData], rax; unsigned int
0x18004e79d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004e7a2  mov     edx, 29Dh; void *
0x18004e7a7  mov     rcx, [rbp+8]; this
0x18004e7ab  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x18004e7b2  mov     r9d, ebx; char *
0x18004e7b5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004e7ba  mov     ebx, eax
0x18004e7bc  jmp     loc_18004E71A
0x18004e7c1  mov     rdx, [rbp+lpValueName]; lpValueName
0x18004e7c5  lea     rax, [rbp+Data]
0x18004e7c9  mov     rcx, [rbp+hKey]; hKey
0x18004e7cd  mov     r9d, 4; dwType
0x18004e7d3  mov     [rsp+70h+cbData], r9d; cbData
0x18004e7d8  xor     r8d, r8d; Reserved
0x18004e7db  mov     [rsp+70h+lpData], rax; lpData
0x18004e7e0  call    cs:__imp_RegSetValueExW
0x18004e7e7  nop     dword ptr [rax+rax+00h]
0x18004e7ec  mov     ebx, eax
0x18004e7ee  cmp     eax, 2
0x18004e7f1  jnz     short loc_18004E7FD
0x18004e7f3  mov     ebx, 80070002h
0x18004e7f8  jmp     loc_18004E71A
0x18004e7fd  test    ebx, ebx
0x18004e7ff  jz      short loc_18004E869
0x18004e801  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e808  test    rcx, rcx
0x18004e80b  jz      short loc_18004E85F
0x18004e80d  lea     rax, [rbp+lpValueName]
0x18004e811  lea     r9, aFailedToSetReg; "Failed to set registry value: {}"
0x18004e818  mov     [rsp+70h+lpData], rax
0x18004e81d  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004e822  test    ebx, ebx
0x18004e824  jg      short loc_18004E82A
0x18004e826  mov     eax, ebx
0x18004e828  jmp     short loc_18004E832
0x18004e82a  movzx   eax, bx
0x18004e82d  or      eax, 80070000h
0x18004e832  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e839  lea     r9, a0; ": {0}"
0x18004e840  mov     [rbp+var_40], eax
0x18004e843  mov     r8d, 3
0x18004e849  lea     rax, [rbp+var_40]
0x18004e84d  mov     qword ptr [rbp+var_38], rax
0x18004e851  lea     rax, [rbp+var_38]
0x18004e855  mov     [rsp+70h+lpData], rax
0x18004e85a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004e85f  mov     edx, 2AEh
0x18004e864  jmp     loc_18004E7A7
0x18004e869  xor     ebx, ebx
0x18004e86b  jmp     loc_18004E71A
```
