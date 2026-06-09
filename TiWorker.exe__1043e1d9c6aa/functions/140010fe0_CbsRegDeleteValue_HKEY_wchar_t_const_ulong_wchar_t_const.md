# CbsRegDeleteValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *)

- ea: `0x140010fe0`
- end: `0x140011185`
- name: `?CbsRegDeleteValue@@YAJPEAUHKEY__@@PEB_WK1@Z`
- size: `421`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, __int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140007228`

## callees

- `0x140002310`
- `0x140008ef4`
- `0x14000d910`
- `0x14000e610`
- `0x14000f36c`
- `0x140010fe0`
- `0x14001118c`
- `0x140011d38`
- `0x140011ee8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400110b2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400110b2`

## string_xrefs

- `0x140011000`: `DirectoryToDelete`
- `0x140011013`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SideBySide`
- `0x140011055`: `Failed to open key: {}`
- `0x1400110f6`: `Failed to delete registry value: {}`

## pseudocode

```c
__int64 __fastcall CbsRegDeleteValue(HKEY a1, const wchar_t *a2, __int64 a3, const wchar_t *a4)
{
  LSTATUS v4; // ebx
  int v5; // edx
  unsigned int v6; // eax
  __int64 v7; // rdx
  HKEY v8; // rdi
  int v9; // edx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  unsigned int v13; // [rsp+20h] [rbp-50h]
  unsigned int v14; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v15[2]; // [rsp+38h] [rbp-38h] BYREF
  LPCWSTR lpValueName[2]; // [rsp+40h] [rbp-30h] BYREF
  const wchar_t *v17; // [rsp+50h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  hKey = 0;
  lpValueName[0] = L"DirectoryToDelete";
  v17 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SideBySide";
  v4 = CbsRegOpenKeyExW(a1, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SideBySide", a3, 2u, &hKey);
  if ( v4 )
  {
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to open key: {}",
        (__int64)&v17);
      if ( v4 > 0 )
        v6 = (unsigned __int16)v4 | 0x80070000;
      else
        v6 = v4;
      v14 = v6;
      *(_QWORD *)v15 = &v14;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v5,
        3,
        (unsigned int)": {0}",
        (__int64)v15);
    }
    v7 = 968;
  }
  else
  {
    v8 = hKey;
    v4 = RegDeleteValueW(hKey, lpValueName[0]);
    if ( v4 == 5 )
    {
      DumpHandleInfo(v8);
      DumpKeySecurityInfo(v8);
    }
    else if ( !v4 )
    {
      v11 = 0;
      goto LABEL_19;
    }
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to delete registry value: {}",
        (__int64)lpValueName);
      if ( v4 > 0 )
        v10 = (unsigned __int16)v4 | 0x80070000;
      else
        v10 = v4;
      v14 = v10;
      *(_QWORD *)v15 = &v14;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v9,
        3,
        (unsigned int)": {0}",
        (__int64)v15);
    }
    v7 = 986;
  }
  v11 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v7,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
          (const char *)(unsigned int)v4,
          v13);
LABEL_19:
  Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&hKey);
  return v11;
}

```

## disassembly

```asm
0x140010fe0  mov     [rsp-8+arg_0], rbx
0x140010fe5  mov     [rsp-8+arg_8], rdi
0x140010fea  push    rbp
0x140010feb  mov     rbp, rsp
0x140010fee  sub     rsp, 70h
0x140010ff2  mov     rax, cs:__security_cookie
0x140010ff9  xor     rax, rsp
0x140010ffc  mov     [rbp+var_8], rax
0x140011000  lea     rax, aDirectorytodel; "DirectoryToDelete"
0x140011007  mov     [rbp+hKey], 0
0x14001100f  mov     [rbp+lpValueName], rax
0x140011013  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14001101a  lea     rax, [rbp+hKey]
0x14001101e  mov     [rbp+var_20], rdx
0x140011022  mov     r9d, 2; unsigned int
0x140011028  mov     qword ptr [rsp+70h+var_50], rax; HKEY *
0x14001102d  call    ?CbsRegOpenKeyExW@@YAKPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z; CbsRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x140011032  mov     ebx, eax
0x140011034  test    eax, eax
0x140011036  jz      short loc_1400110A7
0x140011038  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001103f  test    rcx, rcx
0x140011042  jz      short loc_14001109D
0x140011044  lea     rax, [rbp+var_20]
0x140011048  mov     edi, 3
0x14001104d  mov     r8d, edi
0x140011050  mov     qword ptr [rsp+70h+var_50], rax
0x140011055  lea     r9, aFailedToOpenKe; "Failed to open key: {}"
0x14001105c  xor     edx, edx
0x14001105e  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140011063  test    ebx, ebx
0x140011065  jg      short loc_14001106B
0x140011067  mov     eax, ebx
0x140011069  jmp     short loc_140011073
0x14001106b  movzx   eax, bx
0x14001106e  or      eax, 80070000h
0x140011073  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001107a  lea     r9, a0; ": {0}"
0x140011081  mov     [rbp+var_40], eax
0x140011084  mov     r8d, edi
0x140011087  lea     rax, [rbp+var_40]
0x14001108b  mov     qword ptr [rbp+var_38], rax
0x14001108f  lea     rax, [rbp+var_38]
0x140011093  mov     qword ptr [rsp+70h+var_50], rax
0x140011098  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001109d  mov     edx, 3C8h
0x1400110a2  jmp     loc_140011143
0x1400110a7  mov     rdi, [rbp+hKey]
0x1400110ab  mov     rdx, [rbp+lpValueName]; lpValueName
0x1400110af  mov     rcx, rdi; hKey
0x1400110b2  call    cs:__imp_RegDeleteValueW
0x1400110b8  mov     ebx, eax
0x1400110ba  cmp     eax, 5
0x1400110bd  jnz     short loc_1400110D1
0x1400110bf  mov     rcx, rdi; Handle
0x1400110c2  call    ?DumpHandleInfo@@YAXPEAUHKEY__@@@Z; DumpHandleInfo(HKEY__ *)
0x1400110c7  mov     rcx, rdi; hKey
0x1400110ca  call    ?DumpKeySecurityInfo@@YAXPEAUHKEY__@@@Z; DumpKeySecurityInfo(HKEY__ *)
0x1400110cf  jmp     short loc_1400110D9
0x1400110d1  test    ebx, ebx
0x1400110d3  jz      loc_14001115A
0x1400110d9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400110e0  test    rcx, rcx
0x1400110e3  jz      short loc_14001113E
0x1400110e5  lea     rax, [rbp+lpValueName]
0x1400110e9  mov     edi, 3
0x1400110ee  mov     r8d, edi
0x1400110f1  mov     qword ptr [rsp+70h+var_50], rax
0x1400110f6  lea     r9, aFailedToDelete; "Failed to delete registry value: {}"
0x1400110fd  xor     edx, edx
0x1400110ff  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140011104  test    ebx, ebx
0x140011106  jg      short loc_14001110C
0x140011108  mov     eax, ebx
0x14001110a  jmp     short loc_140011114
0x14001110c  movzx   eax, bx
0x14001110f  or      eax, 80070000h
0x140011114  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001111b  lea     r9, a0; ": {0}"
0x140011122  mov     [rbp+var_40], eax
0x140011125  mov     r8d, edi
0x140011128  lea     rax, [rbp+var_40]
0x14001112c  mov     qword ptr [rbp+var_38], rax
0x140011130  lea     rax, [rbp+var_38]
0x140011134  mov     qword ptr [rsp+70h+var_50], rax; unsigned int
0x140011139  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001113e  mov     edx, 3DAh; void *
0x140011143  mov     rcx, [rbp+8]; this
0x140011147  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x14001114e  mov     r9d, ebx; char *
0x140011151  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140011156  mov     ebx, eax
0x140011158  jmp     short loc_14001115C
0x14001115a  xor     ebx, ebx
0x14001115c  lea     rcx, [rbp+hKey]
0x140011160  call    ?Close@?$AutoGenericHandleBase@PEAUHKEY__@@$0A@V?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(void)
0x140011165  mov     eax, ebx
0x140011167  mov     rcx, [rbp+var_8]
0x14001116b  xor     rcx, rsp; StackCookie
0x14001116e  call    __security_check_cookie
0x140011173  lea     r11, [rsp+70h+var_s0]
0x140011178  mov     rbx, [r11+10h]
0x14001117c  mov     rdi, [r11+18h]
0x140011180  mov     rsp, r11
0x140011183  pop     rbp
0x140011184  retn
```
