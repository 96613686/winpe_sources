# CbsRegSetDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong)

- ea: `0x14001acbc`
- end: `0x14001af9d`
- name: `?CbsRegSetDWORDValue@@YAJPEAUHKEY__@@PEB_WK1K@Z`
- size: `737`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, char, const wchar_t *, unsigned int Data)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000d420`
- `0x14002126c`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140006e98`
- `0x140007630`
- `0x140016a40`
- `0x140016bfc`
- `0x140016fb4`
- `0x1400184fc`
- `0x140019c2c`
- `0x14001a0e0`
- `0x14001acbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001aee9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001aee9`

## string_xrefs

- `0x14001adb3`: `Failed to create key: {}`
- `0x14001ae57`: `Failed to open key: {}`
- `0x14001af17`: `Failed to set registry value: {}`

## pseudocode

```c
__int64 __fastcall CbsRegSetDWORDValue(HKEY a1, const wchar_t *a2, char a3, const wchar_t *a4, unsigned int Data)
{
  const WCHAR *v5; // rax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rbx
  HKEY *InitPointer; // rax
  __int64 v11; // r8
  wchar_t *v12; // r9
  __int64 v13; // rdx
  LSTATUS Key; // ebx
  __int64 v15; // r8
  __int64 v16; // rdx
  unsigned int v17; // eax
  __int64 v18; // rdx
  LSTATUS v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  unsigned int v23; // eax
  LSTATUS v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rdx
  unsigned int v28; // eax
  unsigned int lpData; // [rsp+20h] [rbp-21h]
  unsigned int lpDataa; // [rsp+20h] [rbp-21h]
  DWORD cbData; // [rsp+28h] [rbp-19h]
  struct _SECURITY_ATTRIBUTES *v33; // [rsp+30h] [rbp-11h]
  unsigned int v34[2]; // [rsp+50h] [rbp+Fh] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+60h] [rbp+1Fh] BYREF
  const wchar_t *v36; // [rsp+70h] [rbp+2Fh] BYREF
  int v37; // [rsp+78h] [rbp+37h] BYREF
  __int64 v38; // [rsp+80h] [rbp+3Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+57h]

  lpSubKey[0] = a2;
  v5 = a4;
  v36 = a4;
  if ( a4 )
  {
    v38 = 0;
    v9 = -2147483646;
    if ( a2 )
    {
      InitPointer = (HKEY *)Windows::AutoComPtr<IClassFactory>::GetInitPointer(&v38);
      if ( (a3 & 2) != 0 )
      {
        Key = CbsRegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], v11, v12, lpData, cbData, v33, InitPointer);
        if ( Key )
        {
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              v13,
              v15,
              (__int64)"Failed to create key: {}",
              (__int64)lpSubKey);
            if ( Key > 0 )
              v17 = (unsigned __int16)Key | 0x80070000;
            else
              v17 = Key;
            v37 = v17;
            *(_QWORD *)v34 = &v37;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              v16,
              3,
              (__int64)": {0}",
              (__int64)v34);
          }
          v18 = 660;
LABEL_25:
          v7 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)v18,
                 (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
                 (const char *)(unsigned int)Key,
                 lpDataa);
          goto LABEL_38;
        }
      }
      else
      {
        v19 = CbsRegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], v11, 2u, InitPointer);
        Key = v19;
        if ( (a3 & 1) != 0 && (v19 == 2 || v19 == 3) )
        {
          v7 = (unsigned __int16)v19 | 0x80070000;
LABEL_38:
          Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&v38);
          return v7;
        }
        if ( v19 )
        {
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              v20,
              v21,
              (__int64)"Failed to open key: {}",
              (__int64)lpSubKey);
            if ( Key > 0 )
              v23 = (unsigned __int16)Key | 0x80070000;
            else
              v23 = Key;
            v37 = v23;
            *(_QWORD *)v34 = &v37;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              v22,
              3,
              (__int64)": {0}",
              (__int64)v34);
          }
          v18 = 669;
          goto LABEL_25;
        }
      }
      v9 = v38;
      v5 = v36;
    }
    v24 = RegSetValueExW((HKEY)v9, v5, 0, 4u, (const BYTE *)&Data, 4u);
    Key = v24;
    if ( (a3 & 1) != 0 && v24 == 2 )
    {
      v7 = -2147024894;
      goto LABEL_38;
    }
    if ( !v24 )
    {
      v7 = 0;
      goto LABEL_38;
    }
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        v25,
        v26,
        (__int64)"Failed to set registry value: {}",
        (__int64)&v36);
      if ( Key > 0 )
        v28 = (unsigned __int16)Key | 0x80070000;
      else
        v28 = Key;
      v37 = v28;
      *(_QWORD *)v34 = &v37;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v27,
        3,
        (__int64)": {0}",
        (__int64)v34);
    }
    v18 = 686;
    goto LABEL_25;
  }
  v7 = -2147024809;
  v37 = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"No value name specified");
    *(_QWORD *)v34 = &v37;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      v8,
      3,
      (__int64)": {}",
      (__int64)v34);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x28A,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
    (const char *)0x80070057LL,
    lpData);
  return v7;
}

```

## disassembly

```asm
0x14001acbc  mov     [rsp-8+arg_0], rbx
0x14001acc1  mov     [rsp-8+arg_10], rsi
0x14001acc6  push    rbp
0x14001acc7  lea     rbp, [rsp-4Fh]
0x14001accc  sub     rsp, 90h
0x14001acd3  mov     rax, cs:__security_cookie
0x14001acda  xor     rax, rsp
0x14001acdd  mov     [rbp+4Fh+var_8], rax
0x14001ace1  mov     [rbp+4Fh+lpSubKey], rdx
0x14001ace5  mov     rax, r9
0x14001ace8  mov     [rbp+4Fh+var_20], rax
0x14001acec  mov     esi, r8d
0x14001acef  test    r9, r9
0x14001acf2  jnz     short loc_14001AD61
0x14001acf4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001acfb  mov     ebx, 80070057h
0x14001ad00  mov     [rbp+4Fh+var_18], ebx
0x14001ad03  test    rcx, rcx
0x14001ad06  jz      short loc_14001AD44
0x14001ad08  lea     r9, aNoValueNameSpe; "No value name specified"
0x14001ad0f  xor     edx, edx
0x14001ad11  lea     r8d, [rax+3]
0x14001ad15  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001ad1a  lea     rcx, [rbp+4Fh+var_40]
0x14001ad1e  mov     r8d, 3
0x14001ad24  mov     [rsp+90h+lpData], rcx; int
0x14001ad29  lea     rax, [rbp+4Fh+var_18]
0x14001ad2d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ad34  lea     r9, asc_1400353E8; ": {}"
0x14001ad3b  mov     qword ptr [rbp+4Fh+var_40], rax
0x14001ad3f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001ad44  mov     rcx, [rbp+57h]; this
0x14001ad48  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x14001ad4f  mov     r9d, ebx; char *
0x14001ad52  mov     edx, 28Ah; void *
0x14001ad57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001ad5c  jmp     loc_14001AF7A
0x14001ad61  mov     [rbp+4Fh+var_10], 0
0x14001ad69  mov     rbx, 0FFFFFFFF80000002h
0x14001ad70  test    rdx, rdx
0x14001ad73  jz      loc_14001AECC
0x14001ad79  lea     rcx, [rbp+4Fh+var_10]
0x14001ad7d  call    ?GetInitPointer@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAPEAPEAUIClassFactory@@XZ; Windows::AutoComPtr<IClassFactory>::GetInitPointer(void)
0x14001ad82  mov     rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x14001ad86  mov     rcx, rbx; hKey
0x14001ad89  test    sil, 2
0x14001ad8d  jz      short loc_14001AE0B
0x14001ad8f  mov     [rsp+90h+var_58], rax; HKEY *
0x14001ad94  call    ?CbsRegCreateKeyExW@@YAKPEAUHKEY__@@PEB_WKPEA_WKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; CbsRegCreateKeyExW(HKEY__ *,wchar_t const *,ulong,wchar_t *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)
0x14001ad99  mov     ebx, eax
0x14001ad9b  test    eax, eax
0x14001ad9d  jz      loc_14001AEC4
0x14001ada3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001adaa  test    rcx, rcx
0x14001adad  jz      short loc_14001AE01
0x14001adaf  lea     rax, [rbp+4Fh+lpSubKey]
0x14001adb3  lea     r9, aFailedToCreate_22; "Failed to create key: {}"
0x14001adba  mov     [rsp+90h+lpData], rax
0x14001adbf  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001adc4  test    ebx, ebx
0x14001adc6  jg      short loc_14001ADCC
0x14001adc8  mov     eax, ebx
0x14001adca  jmp     short loc_14001ADD4
0x14001adcc  movzx   eax, bx
0x14001adcf  or      eax, 80070000h
0x14001add4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001addb  lea     r9, a0; ": {0}"
0x14001ade2  mov     [rbp+4Fh+var_18], eax
0x14001ade5  mov     r8d, 3
0x14001adeb  lea     rax, [rbp+4Fh+var_18]
0x14001adef  mov     qword ptr [rbp+4Fh+var_40], rax
0x14001adf3  lea     rax, [rbp+4Fh+var_40]
0x14001adf7  mov     [rsp+90h+lpData], rax
0x14001adfc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001ae01  mov     edx, 294h
0x14001ae06  jmp     loc_14001AEAA
0x14001ae0b  mov     r9d, 2; unsigned int
0x14001ae11  mov     [rsp+90h+lpData], rax; HKEY *
0x14001ae16  call    ?CbsRegOpenKeyExW@@YAKPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z; CbsRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x14001ae1b  mov     ebx, eax
0x14001ae1d  test    sil, 1
0x14001ae21  jz      short loc_14001AE43
0x14001ae23  cmp     eax, 2
0x14001ae26  jz      short loc_14001AE35
0x14001ae28  cmp     eax, 3
0x14001ae2b  jnz     short loc_14001AE43
0x14001ae2d  test    eax, eax
0x14001ae2f  jle     loc_14001AF71
0x14001ae35  movzx   ebx, bx
0x14001ae38  or      ebx, 80070000h
0x14001ae3e  jmp     loc_14001AF71
0x14001ae43  test    ebx, ebx
0x14001ae45  jz      short loc_14001AEC4
0x14001ae47  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ae4e  test    rcx, rcx
0x14001ae51  jz      short loc_14001AEA5
0x14001ae53  lea     rax, [rbp+4Fh+lpSubKey]
0x14001ae57  lea     r9, aFailedToOpenKe; "Failed to open key: {}"
0x14001ae5e  mov     [rsp+90h+lpData], rax
0x14001ae63  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001ae68  test    ebx, ebx
0x14001ae6a  jg      short loc_14001AE70
0x14001ae6c  mov     eax, ebx
0x14001ae6e  jmp     short loc_14001AE78
0x14001ae70  movzx   eax, bx
0x14001ae73  or      eax, 80070000h
0x14001ae78  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ae7f  lea     r9, a0; ": {0}"
0x14001ae86  mov     [rbp+4Fh+var_18], eax
0x14001ae89  mov     r8d, 3
0x14001ae8f  lea     rax, [rbp+4Fh+var_18]
0x14001ae93  mov     qword ptr [rbp+4Fh+var_40], rax
0x14001ae97  lea     rax, [rbp+4Fh+var_40]
0x14001ae9b  mov     [rsp+90h+lpData], rax; unsigned int
0x14001aea0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001aea5  mov     edx, 29Dh; void *
0x14001aeaa  mov     rcx, [rbp+57h]; this
0x14001aeae  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x14001aeb5  mov     r9d, ebx; char *
0x14001aeb8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001aebd  mov     ebx, eax
0x14001aebf  jmp     loc_14001AF71
0x14001aec4  mov     rbx, [rbp+4Fh+var_10]
0x14001aec8  mov     rax, [rbp+4Fh+var_20]
0x14001aecc  mov     r9d, 4; dwType
0x14001aed2  lea     rcx, [rbp+4Fh+Data]
0x14001aed6  mov     [rsp+90h+cbData], r9d; cbData
0x14001aedb  xor     r8d, r8d; Reserved
0x14001aede  mov     [rsp+90h+lpData], rcx; lpData
0x14001aee3  mov     rdx, rax; lpValueName
0x14001aee6  mov     rcx, rbx; hKey
0x14001aee9  call    cs:__imp_RegSetValueExW
0x14001aeef  mov     ebx, eax
0x14001aef1  test    sil, 1
0x14001aef5  jz      short loc_14001AF03
0x14001aef7  cmp     eax, 2
0x14001aefa  jnz     short loc_14001AF03
0x14001aefc  mov     ebx, 80070002h
0x14001af01  jmp     short loc_14001AF71
0x14001af03  test    ebx, ebx
0x14001af05  jz      short loc_14001AF6F
0x14001af07  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001af0e  test    rcx, rcx
0x14001af11  jz      short loc_14001AF65
0x14001af13  lea     rax, [rbp+4Fh+var_20]
0x14001af17  lea     r9, aFailedToSetReg; "Failed to set registry value: {}"
0x14001af1e  mov     [rsp+90h+lpData], rax
0x14001af23  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001af28  test    ebx, ebx
0x14001af2a  jg      short loc_14001AF30
0x14001af2c  mov     eax, ebx
0x14001af2e  jmp     short loc_14001AF38
0x14001af30  movzx   eax, bx
0x14001af33  or      eax, 80070000h
0x14001af38  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001af3f  lea     r9, a0; ": {0}"
0x14001af46  mov     [rbp+4Fh+var_18], eax
0x14001af49  mov     r8d, 3
0x14001af4f  lea     rax, [rbp+4Fh+var_18]
0x14001af53  mov     qword ptr [rbp+4Fh+var_40], rax
0x14001af57  lea     rax, [rbp+4Fh+var_40]
0x14001af5b  mov     [rsp+90h+lpData], rax
0x14001af60  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001af65  mov     edx, 2AEh
0x14001af6a  jmp     loc_14001AEAA
0x14001af6f  xor     ebx, ebx
0x14001af71  lea     rcx, [rbp+4Fh+var_10]
0x14001af75  call    ?Close@?$AutoGenericHandleBase@PEAUHKEY__@@$0A@V?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(void)
0x14001af7a  mov     eax, ebx
0x14001af7c  mov     rcx, [rbp+4Fh+var_8]
0x14001af80  xor     rcx, rsp; StackCookie
0x14001af83  call    __security_check_cookie
0x14001af88  lea     r11, [rsp+90h+var_s0]
0x14001af90  mov     rbx, [r11+10h]
0x14001af94  mov     rsi, [r11+20h]
0x14001af98  mov     rsp, r11
0x14001af9b  pop     rbp
0x14001af9c  retn
```
