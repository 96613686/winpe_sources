# OneCore::Base::Telemetry::OneSettingsQuery::UpdateRefreshDeadline(void)

- ea: `0x1800239bc`
- end: `0x180023b0e`
- name: `?UpdateRefreshDeadline@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `338`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18001f3f4`
- `0x180022a14`

## callees

- `0x180003850`
- `0x1800239bc`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023a90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023a90`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023ad0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023ad0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023ae6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023ae6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180023a05`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180023a05`

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
0x1800239bc  mov     [rsp-8+arg_8], rbx
0x1800239c1  push    rbp
0x1800239c2  lea     rbp, [rsp-170h]
0x1800239ca  sub     rsp, 270h
0x1800239d1  mov     rax, cs:__security_cookie
0x1800239d8  xor     rax, rsp
0x1800239db  mov     [rbp+170h+var_10], rax
0x1800239e2  mov     rbx, rcx
0x1800239e5  mov     qword ptr [rsp+270h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800239ee  lea     rcx, [rsp+270h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800239f3  mov     qword ptr [rsp+270h+Data], 0
0x1800239fc  mov     [rsp+270h+hKey], 0
0x180023a05  call    cs:__imp_GetSystemTimeAsFileTime
0x180023a0b  mov     eax, [rsp+270h+SystemTimeAsFileTime.dwHighDateTime]
0x180023a0f  lea     r9, [rbx+438h]
0x180023a16  mov     ecx, [rbx+18h]
0x180023a19  lea     r8, aLsLsLs; "%ls\\%ls\\%ls"
0x180023a20  mov     dword ptr [rsp+270h+Data+4], eax
0x180023a24  mov     eax, [rsp+270h+SystemTimeAsFileTime.dwLowDateTime]
0x180023a28  imul    rdx, rcx, 23C34600h
0x180023a2f  mov     dword ptr [rsp+270h+Data], eax
0x180023a33  lea     rcx, [rbx+28h]
0x180023a37  mov     rax, qword ptr [rsp+270h+Data]
0x180023a3c  add     rdx, rax
0x180023a3f  mov     [rbx+640h], rax
0x180023a46  lea     rax, [rbx+230h]
0x180023a4d  mov     qword ptr [rsp+270h+Data], rdx
0x180023a52  mov     qword ptr [rsp+270h+cbData], rax
0x180023a57  mov     edx, 104h; unsigned __int64
0x180023a5c  mov     [rsp+270h+phkResult], rcx
0x180023a61  lea     rcx, [rsp+270h+SubKey]; unsigned __int16 *
0x180023a66  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023a6b  mov     ebx, eax
0x180023a6d  test    eax, eax
0x180023a6f  js      short loc_180023ADC
0x180023a71  lea     rax, [rsp+270h+hKey]
0x180023a76  mov     r9d, 0F003Fh; samDesired
0x180023a7c  xor     r8d, r8d; ulOptions
0x180023a7f  mov     [rsp+270h+phkResult], rax; phkResult
0x180023a84  lea     rdx, [rsp+270h+SubKey]; lpSubKey
0x180023a89  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180023a90  call    cs:__imp_RegOpenKeyExW
0x180023a96  mov     ebx, eax
0x180023a98  test    eax, eax
0x180023a9a  jz      short loc_180023AA9
0x180023a9c  jle     short loc_180023ADC
0x180023a9e  movzx   ebx, ax
0x180023aa1  or      ebx, 80070000h
0x180023aa7  jmp     short loc_180023ADC
0x180023aa9  mov     rcx, [rsp+270h+hKey]; hKey
0x180023aae  lea     rax, [rsp+270h+Data]
0x180023ab3  mov     [rsp+270h+cbData], 8; cbData
0x180023abb  lea     rdx, aRefreshafter; "RefreshAfter"
0x180023ac2  mov     r9d, 0Bh; dwType
0x180023ac8  mov     [rsp+270h+phkResult], rax; lpData
0x180023acd  xor     r8d, r8d; Reserved
0x180023ad0  call    cs:__imp_RegSetValueExW
0x180023ad6  mov     ebx, eax
0x180023ad8  test    eax, eax
0x180023ada  jnz     short loc_180023A9C
0x180023adc  mov     rcx, [rsp+270h+hKey]; hKey
0x180023ae1  test    rcx, rcx
0x180023ae4  jz      short loc_180023AEC
0x180023ae6  call    cs:__imp_RegCloseKey
0x180023aec  mov     eax, ebx
0x180023aee  mov     rcx, [rbp+170h+var_10]
0x180023af5  xor     rcx, rsp; StackCookie
0x180023af8  call    __security_check_cookie
0x180023afd  mov     rbx, [rsp+270h+arg_8]
0x180023b05  add     rsp, 270h
0x180023b0c  pop     rbp
0x180023b0d  retn
```
