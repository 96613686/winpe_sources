# OneCore::Base::Telemetry::OneSettingsQuery::Query(ushort const *,bool,ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x180044ba0`
- end: `0x180044d37`
- name: `?Query@OneSettingsQuery@Telemetry@Base@OneCore@@QEAAJPEBG_N0PEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `407`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *this, wchar_t *String1, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180042554`

## callees

- `0x18001c5bc`
- `0x180041594`
- `0x18004175c`
- `0x180043fdc`
- `0x1800440b4`
- `0x180044ba0`
- `0x180045c54`
- `0x1800464f8`
- `0x180046b54`
- `0x1800473f0`
- `0x180047594`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180044c3c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180044c3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180044ccf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180044ccf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180044c26`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180044c26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044c47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044c47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044cd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044cd8`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::Query(
        OneCore::Base::Telemetry::OneSettingsQuery *this,
        wchar_t *String1,
        __int64 a3,
        const unsigned __int16 *a4)
{
  _WORD *v5; // rcx
  void *v7; // rsi
  HANDLE MutexW; // rax
  int OneSettingsCommonClient; // ebx
  unsigned __int16 v10; // dx
  unsigned __int16 v11; // cx
  const unsigned __int16 *v12; // r8
  int v13; // eax
  unsigned __int16 v14; // dx
  unsigned __int16 v15; // cx
  unsigned __int16 v16; // r8
  const unsigned __int16 *v17; // r8
  int SavedSettingsFromRegistry; // eax
  WCHAR Name[264]; // [rsp+40h] [rbp-238h] BYREF

  v5 = (_WORD *)((char *)this + 40);
  if ( !*v5 || !*((_WORD *)this + 280) )
    return (unsigned int)-2147024809;
  v7 = 0;
  if ( (int)StringCchPrintfW(Name, 0x104u, L"%s+%s+%s", L"Global\\OneSettingQueryMutex", v5, (char *)this + 560) >= 0 )
  {
    MutexW = CreateMutexW(0, 0, Name);
    v7 = MutexW;
    if ( !MutexW || WaitForSingleObject(MutexW, 0xEA60u) == -1 )
      GetLastError();
  }
  OneSettingsCommonClient = 1;
  if ( OneCore::Base::Telemetry::OneSettingsQuery::SettingsFresh(this) )
  {
LABEL_22:
    SavedSettingsFromRegistry = OneCore::Base::Telemetry::OneSettingsQuery::ReadSavedSettingsFromRegistry(this);
    if ( SavedSettingsFromRegistry < 0 )
    {
      if ( OneSettingsCommonClient >= 0 )
        OneSettingsCommonClient = SavedSettingsFromRegistry;
      goto LABEL_18;
    }
    goto LABEL_17;
  }
  OneSettingsCommonClient = OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(this);
  if ( OneSettingsCommonClient >= 0 )
  {
    v13 = OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsFromCommonClient(this, String1, v12);
LABEL_14:
    OneSettingsCommonClient = v13;
    goto LABEL_15;
  }
  if ( IsWindowsVersionOrGreaterEx(v11, v10, (unsigned __int16)v12, 0x4F7Cu) )
    goto LABEL_18;
  if ( !IsWindowsVersionOrGreaterEx(v15, v14, v16, 0x47BBu) || OneSettingsCommonClient == -2147024770 )
  {
    v13 = OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsDirectly((HINTERNET *)this, String1, v17);
    goto LABEL_14;
  }
LABEL_15:
  if ( OneSettingsCommonClient )
  {
    if ( OneSettingsCommonClient == 1 )
    {
      OneCore::Base::Telemetry::OneSettingsQuery::UpdateQueryParameters(this);
      OneCore::Base::Telemetry::OneSettingsQuery::UpdateRefreshDeadline(this);
    }
    goto LABEL_22;
  }
  OneCore::Base::Telemetry::OneSettingsQuery::SaveSettingsToRegistry(this);
  OneCore::Base::Telemetry::OneSettingsQuery::UpdateRefreshDeadline(this);
LABEL_17:
  OneSettingsCommonClient = 0;
LABEL_18:
  if ( v7 )
  {
    ReleaseMutex(v7);
    CloseHandle(v7);
  }
  return (unsigned int)OneSettingsCommonClient;
}

```

## disassembly

```asm
0x180044ba0  mov     [rsp+arg_10], rbx
0x180044ba5  mov     [rsp+arg_18], rbp
0x180044baa  push    rsi
0x180044bab  push    rdi
0x180044bac  push    r14
0x180044bae  sub     rsp, 260h
0x180044bb5  mov     rax, cs:__security_cookie
0x180044bbc  xor     rax, rsp
0x180044bbf  mov     [rsp+278h+var_28], rax
0x180044bc7  mov     rdi, rcx
0x180044bca  xor     r14d, r14d
0x180044bcd  add     rcx, 28h ; '('
0x180044bd1  mov     rbp, rdx
0x180044bd4  cmp     [rcx], r14w
0x180044bd8  jz      loc_180044D08
0x180044bde  lea     rax, [rdi+230h]
0x180044be5  cmp     [rax], r14w
0x180044be9  jz      loc_180044D08
0x180044bef  mov     [rsp+278h+var_250], rax
0x180044bf4  lea     r9, aGlobalOnesetti; "Global\\OneSettingQueryMutex"
0x180044bfb  mov     [rsp+278h+var_258], rcx
0x180044c00  lea     r8, aSSS; "%s+%s+%s"
0x180044c07  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180044c0c  mov     edx, 104h; unsigned __int64
0x180044c11  mov     esi, r14d
0x180044c14  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180044c19  test    eax, eax
0x180044c1b  js      short loc_180044C4D
0x180044c1d  lea     r8, [rsp+278h+Name]; lpName
0x180044c22  xor     edx, edx; bInitialOwner
0x180044c24  xor     ecx, ecx; lpMutexAttributes
0x180044c26  call    cs:__imp_CreateMutexW
0x180044c2c  mov     rsi, rax
0x180044c2f  test    rax, rax
0x180044c32  jz      short loc_180044C47
0x180044c34  mov     edx, 0EA60h; dwMilliseconds
0x180044c39  mov     rcx, rax; hHandle
0x180044c3c  call    cs:__imp_WaitForSingleObject
0x180044c42  cmp     eax, 0FFFFFFFFh
0x180044c45  jnz     short loc_180044C4D
0x180044c47  call    cs:__imp_GetLastError
0x180044c4d  mov     rcx, rdi; this
0x180044c50  mov     ebx, 1
0x180044c55  call    ?SettingsFresh@OneSettingsQuery@Telemetry@Base@OneCore@@QEAA_NXZ; OneCore::Base::Telemetry::OneSettingsQuery::SettingsFresh(void)
0x180044c5a  test    al, al
0x180044c5c  jnz     loc_180044CF5
0x180044c62  mov     rcx, rdi; this
0x180044c65  call    ?LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ; OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)
0x180044c6a  mov     ebx, eax
0x180044c6c  test    eax, eax
0x180044c6e  js      short loc_180044C7D
0x180044c70  mov     rdx, rbp; String1
0x180044c73  mov     rcx, rdi; this
0x180044c76  call    ?DownloadSettingsFromCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG0@Z; OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsFromCommonClient(ushort const *,ushort const *)
0x180044c7b  jmp     short loc_180044CAE
0x180044c7d  mov     r9d, 4F7Ch; unsigned __int16
0x180044c83  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x180044c88  test    al, al
0x180044c8a  jnz     short loc_180044CC7
0x180044c8c  mov     r9d, 47BBh; unsigned __int16
0x180044c92  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x180044c97  test    al, al
0x180044c99  jz      short loc_180044CA3
0x180044c9b  cmp     ebx, 8007007Eh
0x180044ca1  jnz     short loc_180044CB0
0x180044ca3  mov     rdx, rbp; unsigned __int16 *
0x180044ca6  mov     rcx, rdi; this
0x180044ca9  call    ?DownloadSettingsDirectly@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG0@Z; OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsDirectly(ushort const *,ushort const *)
0x180044cae  mov     ebx, eax
0x180044cb0  test    ebx, ebx
0x180044cb2  jnz     short loc_180044CE0
0x180044cb4  mov     rcx, rdi; this
0x180044cb7  call    ?SaveSettingsToRegistry@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ; OneCore::Base::Telemetry::OneSettingsQuery::SaveSettingsToRegistry(void)
0x180044cbc  mov     rcx, rdi; this
0x180044cbf  call    ?UpdateRefreshDeadline@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ; OneCore::Base::Telemetry::OneSettingsQuery::UpdateRefreshDeadline(void)
0x180044cc4  mov     ebx, r14d
0x180044cc7  test    rsi, rsi
0x180044cca  jz      short loc_180044D0D
0x180044ccc  mov     rcx, rsi; hMutex
0x180044ccf  call    cs:__imp_ReleaseMutex
0x180044cd5  mov     rcx, rsi; hObject
0x180044cd8  call    cs:__imp_CloseHandle
0x180044cde  jmp     short loc_180044D0D
0x180044ce0  cmp     ebx, 1
0x180044ce3  jnz     short loc_180044CF5
0x180044ce5  mov     rcx, rdi; this
0x180044ce8  call    ?UpdateQueryParameters@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ; OneCore::Base::Telemetry::OneSettingsQuery::UpdateQueryParameters(void)
0x180044ced  mov     rcx, rdi; this
0x180044cf0  call    ?UpdateRefreshDeadline@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ; OneCore::Base::Telemetry::OneSettingsQuery::UpdateRefreshDeadline(void)
0x180044cf5  mov     rcx, rdi; this
0x180044cf8  call    ?ReadSavedSettingsFromRegistry@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ; OneCore::Base::Telemetry::OneSettingsQuery::ReadSavedSettingsFromRegistry(void)
0x180044cfd  test    eax, eax
0x180044cff  jns     short loc_180044CC4
0x180044d01  test    ebx, ebx
0x180044d03  cmovns  ebx, eax
0x180044d06  jmp     short loc_180044CC7
0x180044d08  mov     ebx, 80070057h
0x180044d0d  mov     eax, ebx
0x180044d0f  mov     rcx, [rsp+278h+var_28]
0x180044d17  xor     rcx, rsp; StackCookie
0x180044d1a  call    __security_check_cookie
0x180044d1f  lea     r11, [rsp+278h+var_18]
0x180044d27  mov     rbx, [r11+30h]
0x180044d2b  mov     rbp, [r11+38h]
0x180044d2f  mov     rsp, r11
0x180044d32  pop     r14
0x180044d34  pop     rdi
0x180044d35  pop     rsi
0x180044d36  retn
```
