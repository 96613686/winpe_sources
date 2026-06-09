# OneCore::Base::Telemetry::OneSettingsQuery::UpdateRefreshDeadline(void)

- ea: `0x180062740`
- end: `0x180062892`
- name: `?UpdateRefreshDeadline@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `338`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18005fd5c`
- `0x180061c04`

## callees

- `0x180012864`
- `0x180062740`
- `0x18006c690`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180062854`
- `ADVAPI32!RegSetValueExW` at `0x180062854`
- `ADVAPI32!RegCloseKey` at `0x18006286a`
- `ADVAPI32!RegCloseKey` at `0x18006286a`
- `ADVAPI32!RegOpenKeyExW` at `0x180062814`
- `ADVAPI32!RegOpenKeyExW` at `0x180062814`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180062789`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180062789`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::UpdateRefreshDeadline(struct _FILETIME *this)
{
  __int64 v2; // rdx
  signed int v3; // ebx
  LSTATUS v4; // eax
  bool v5; // cc
  BYTE Data[8]; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  SystemTimeAsFileTime = 0;
  *(_QWORD *)Data = 0;
  hKey = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v2 = *(_QWORD *)&SystemTimeAsFileTime + 600000000LL * this[3].dwLowDateTime;
  this[200] = SystemTimeAsFileTime;
  v3 = StringCchPrintfW(SubKey, 0x104u, L"%ls\\%ls\\%ls", &this[135], &this[5], &this[70], v2);
  if ( v3 >= 0 )
  {
    v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0xF003Fu, &hKey);
    v3 = v4;
    v5 = v4 <= 0;
    if ( v4 || (v4 = RegSetValueExW(hKey, L"RefreshAfter", 0, 0xBu, Data, 8u), v3 = v4, v5 = v4 <= 0, v4) )
    {
      if ( !v5 )
        v3 = (unsigned __int16)v4 | 0x80070000;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180062740  mov     [rsp-8+arg_8], rbx
0x180062745  push    rbp
0x180062746  lea     rbp, [rsp-170h]
0x18006274e  sub     rsp, 270h
0x180062755  mov     rax, cs:__security_cookie
0x18006275c  xor     rax, rsp
0x18006275f  mov     [rbp+170h+var_10], rax
0x180062766  mov     rbx, rcx
0x180062769  mov     qword ptr [rsp+270h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180062772  lea     rcx, [rsp+270h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180062777  mov     qword ptr [rsp+270h+Data], 0
0x180062780  mov     [rsp+270h+hKey], 0
0x180062789  call    cs:__imp_GetSystemTimeAsFileTime
0x18006278f  mov     eax, [rsp+270h+SystemTimeAsFileTime.dwHighDateTime]
0x180062793  lea     r9, [rbx+438h]
0x18006279a  mov     ecx, [rbx+18h]
0x18006279d  lea     r8, aLsLsLs; "%ls\\%ls\\%ls"
0x1800627a4  mov     dword ptr [rsp+270h+Data+4], eax
0x1800627a8  mov     eax, [rsp+270h+SystemTimeAsFileTime.dwLowDateTime]
0x1800627ac  imul    rdx, rcx, 23C34600h
0x1800627b3  mov     dword ptr [rsp+270h+Data], eax
0x1800627b7  lea     rcx, [rbx+28h]
0x1800627bb  mov     rax, qword ptr [rsp+270h+Data]
0x1800627c0  add     rdx, rax
0x1800627c3  mov     [rbx+640h], rax
0x1800627ca  lea     rax, [rbx+230h]
0x1800627d1  mov     qword ptr [rsp+270h+Data], rdx
0x1800627d6  mov     qword ptr [rsp+270h+cbData], rax
0x1800627db  mov     edx, 104h; unsigned __int64
0x1800627e0  mov     [rsp+270h+phkResult], rcx
0x1800627e5  lea     rcx, [rsp+270h+SubKey]; unsigned __int16 *
0x1800627ea  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800627ef  mov     ebx, eax
0x1800627f1  test    eax, eax
0x1800627f3  js      short loc_180062860
0x1800627f5  lea     rax, [rsp+270h+hKey]
0x1800627fa  mov     r9d, 0F003Fh; samDesired
0x180062800  xor     r8d, r8d; ulOptions
0x180062803  mov     [rsp+270h+phkResult], rax; phkResult
0x180062808  lea     rdx, [rsp+270h+SubKey]; lpSubKey
0x18006280d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180062814  call    cs:__imp_RegOpenKeyExW
0x18006281a  mov     ebx, eax
0x18006281c  test    eax, eax
0x18006281e  jz      short loc_18006282D
0x180062820  jle     short loc_180062860
0x180062822  movzx   ebx, ax
0x180062825  or      ebx, 80070000h
0x18006282b  jmp     short loc_180062860
0x18006282d  mov     rcx, [rsp+270h+hKey]; hKey
0x180062832  lea     rax, [rsp+270h+Data]
0x180062837  mov     [rsp+270h+cbData], 8; cbData
0x18006283f  lea     rdx, aRefreshafter; "RefreshAfter"
0x180062846  mov     r9d, 0Bh; dwType
0x18006284c  mov     [rsp+270h+phkResult], rax; lpData
0x180062851  xor     r8d, r8d; Reserved
0x180062854  call    cs:__imp_RegSetValueExW
0x18006285a  mov     ebx, eax
0x18006285c  test    eax, eax
0x18006285e  jnz     short loc_180062820
0x180062860  mov     rcx, [rsp+270h+hKey]; hKey
0x180062865  test    rcx, rcx
0x180062868  jz      short loc_180062870
0x18006286a  call    cs:__imp_RegCloseKey
0x180062870  mov     eax, ebx
0x180062872  mov     rcx, [rbp+170h+var_10]
0x180062879  xor     rcx, rsp; StackCookie
0x18006287c  call    __security_check_cookie
0x180062881  mov     rbx, [rsp+270h+arg_8]
0x180062889  add     rsp, 270h
0x180062890  pop     rbp
0x180062891  retn
```
