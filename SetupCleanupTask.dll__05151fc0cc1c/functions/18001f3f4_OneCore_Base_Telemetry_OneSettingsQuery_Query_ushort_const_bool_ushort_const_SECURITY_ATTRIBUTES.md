# OneCore::Base::Telemetry::OneSettingsQuery::Query(ushort const *,bool,ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x18001f3f4`
- end: `0x18001f58b`
- name: `?Query@OneSettingsQuery@Telemetry@Base@OneCore@@QEAAJPEBG_N0PEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `407`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *this, wchar_t *String1, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001cc9c`

## callees

- `0x180003850`
- `0x18001acb4`
- `0x18001ae7c`
- `0x18001e200`
- `0x18001e2d8`
- `0x18001f3f4`
- `0x180020728`
- `0x180022028`
- `0x180022a14`
- `0x180023818`
- `0x1800239bc`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001f523`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001f523`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f490`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f490`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001f47a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001f47a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f49b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f49b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f52c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f52c`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
    v13 = OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsDirectly((void **)this, String1, v17);
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
0x18001f3f4  mov     [rsp+arg_10], rbx
0x18001f3f9  mov     [rsp+arg_18], rbp
0x18001f3fe  push    rsi
0x18001f3ff  push    rdi
0x18001f400  push    r14
0x18001f402  sub     rsp, 260h
0x18001f409  mov     rax, cs:__security_cookie
0x18001f410  xor     rax, rsp
0x18001f413  mov     [rsp+278h+var_28], rax
0x18001f41b  mov     rdi, rcx
0x18001f41e  xor     r14d, r14d
0x18001f421  add     rcx, 28h ; '('
0x18001f425  mov     rbp, rdx
0x18001f428  cmp     [rcx], r14w
0x18001f42c  jz      loc_18001F55C
0x18001f432  lea     rax, [rdi+230h]
0x18001f439  cmp     [rax], r14w
0x18001f43d  jz      loc_18001F55C
0x18001f443  mov     [rsp+278h+var_250], rax
0x18001f448  lea     r9, aGlobalOnesetti; "Global\\OneSettingQueryMutex"
0x18001f44f  mov     [rsp+278h+var_258], rcx
0x18001f454  lea     r8, aSSS; "%s+%s+%s"
0x18001f45b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18001f460  mov     edx, 104h; unsigned __int64
0x18001f465  mov     esi, r14d
0x18001f468  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001f46d  test    eax, eax
0x18001f46f  js      short loc_18001F4A1
0x18001f471  lea     r8, [rsp+278h+Name]; lpName
0x18001f476  xor     edx, edx; bInitialOwner
0x18001f478  xor     ecx, ecx; lpMutexAttributes
0x18001f47a  call    cs:__imp_CreateMutexW
0x18001f480  mov     rsi, rax
0x18001f483  test    rax, rax
0x18001f486  jz      short loc_18001F49B
0x18001f488  mov     edx, 0EA60h; dwMilliseconds
0x18001f48d  mov     rcx, rax; hHandle
0x18001f490  call    cs:__imp_WaitForSingleObject
0x18001f496  cmp     eax, 0FFFFFFFFh
0x18001f499  jnz     short loc_18001F4A1
0x18001f49b  call    cs:__imp_GetLastError
0x18001f4a1  mov     rcx, rdi; this
0x18001f4a4  mov     ebx, 1
0x18001f4a9  call    ?SettingsFresh@OneSettingsQuery@Telemetry@Base@OneCore@@QEAA_NXZ; OneCore::Base::Telemetry::OneSettingsQuery::SettingsFresh(void)
0x18001f4ae  test    al, al
0x18001f4b0  jnz     loc_18001F549
0x18001f4b6  mov     rcx, rdi; this
0x18001f4b9  call    ?LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ; OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)
0x18001f4be  mov     ebx, eax
0x18001f4c0  test    eax, eax
0x18001f4c2  js      short loc_18001F4D1
0x18001f4c4  mov     rdx, rbp; String1
0x18001f4c7  mov     rcx, rdi; this
0x18001f4ca  call    ?DownloadSettingsFromCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG0@Z; OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsFromCommonClient(ushort const *,ushort const *)
0x18001f4cf  jmp     short loc_18001F502
0x18001f4d1  mov     r9d, 4F7Ch; unsigned __int16
0x18001f4d7  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x18001f4dc  test    al, al
0x18001f4de  jnz     short loc_18001F51B
0x18001f4e0  mov     r9d, 47BBh; unsigned __int16
0x18001f4e6  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x18001f4eb  test    al, al
0x18001f4ed  jz      short loc_18001F4F7
0x18001f4ef  cmp     ebx, 8007007Eh
0x18001f4f5  jnz     short loc_18001F504
0x18001f4f7  mov     rdx, rbp; unsigned __int16 *
0x18001f4fa  mov     rcx, rdi; this
0x18001f4fd  call    ?DownloadSettingsDirectly@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG0@Z; OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsDirectly(ushort const *,ushort const *)
0x18001f502  mov     ebx, eax
0x18001f504  test    ebx, ebx
0x18001f506  jnz     short loc_18001F534
0x18001f508  mov     rcx, rdi; this
0x18001f50b  call    ?SaveSettingsToRegistry@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ; OneCore::Base::Telemetry::OneSettingsQuery::SaveSettingsToRegistry(void)
0x18001f510  mov     rcx, rdi; this
0x18001f513  call    ?UpdateRefreshDeadline@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ; OneCore::Base::Telemetry::OneSettingsQuery::UpdateRefreshDeadline(void)
0x18001f518  mov     ebx, r14d
0x18001f51b  test    rsi, rsi
0x18001f51e  jz      short loc_18001F561
0x18001f520  mov     rcx, rsi; hMutex
0x18001f523  call    cs:__imp_ReleaseMutex
0x18001f529  mov     rcx, rsi; hObject
0x18001f52c  call    cs:__imp_CloseHandle
0x18001f532  jmp     short loc_18001F561
0x18001f534  cmp     ebx, 1
0x18001f537  jnz     short loc_18001F549
0x18001f539  mov     rcx, rdi; this
0x18001f53c  call    ?UpdateQueryParameters@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ; OneCore::Base::Telemetry::OneSettingsQuery::UpdateQueryParameters(void)
0x18001f541  mov     rcx, rdi; this
0x18001f544  call    ?UpdateRefreshDeadline@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ; OneCore::Base::Telemetry::OneSettingsQuery::UpdateRefreshDeadline(void)
0x18001f549  mov     rcx, rdi; this
0x18001f54c  call    ?ReadSavedSettingsFromRegistry@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ; OneCore::Base::Telemetry::OneSettingsQuery::ReadSavedSettingsFromRegistry(void)
0x18001f551  test    eax, eax
0x18001f553  jns     short loc_18001F518
0x18001f555  test    ebx, ebx
0x18001f557  cmovns  ebx, eax
0x18001f55a  jmp     short loc_18001F51B
0x18001f55c  mov     ebx, 80070057h
0x18001f561  mov     eax, ebx
0x18001f563  mov     rcx, [rsp+278h+var_28]
0x18001f56b  xor     rcx, rsp; StackCookie
0x18001f56e  call    __security_check_cookie
0x18001f573  lea     r11, [rsp+278h+var_18]
0x18001f57b  mov     rbx, [r11+30h]
0x18001f57f  mov     rbp, [r11+38h]
0x18001f583  mov     rsp, r11
0x18001f586  pop     r14
0x18001f588  pop     rdi
0x18001f589  pop     rsi
0x18001f58a  retn
```
