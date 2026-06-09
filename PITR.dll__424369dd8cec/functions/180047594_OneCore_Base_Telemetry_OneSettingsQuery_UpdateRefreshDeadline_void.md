# OneCore::Base::Telemetry::OneSettingsQuery::UpdateRefreshDeadline(void)

- ea: `0x180047594`
- end: `0x1800476e6`
- name: `?UpdateRefreshDeadline@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `338`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180044ba0`
- `0x180046b54`

## callees

- `0x18001c5bc`
- `0x180047594`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800476a8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800476a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180047668`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180047668`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800476be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800476be`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800475dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800475dd`

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
0x180047594  mov     [rsp-8+arg_8], rbx
0x180047599  push    rbp
0x18004759a  lea     rbp, [rsp-170h]
0x1800475a2  sub     rsp, 270h
0x1800475a9  mov     rax, cs:__security_cookie
0x1800475b0  xor     rax, rsp
0x1800475b3  mov     [rbp+170h+var_10], rax
0x1800475ba  mov     rbx, rcx
0x1800475bd  mov     qword ptr [rsp+270h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800475c6  lea     rcx, [rsp+270h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800475cb  mov     qword ptr [rsp+270h+Data], 0
0x1800475d4  mov     [rsp+270h+hKey], 0
0x1800475dd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800475e3  mov     eax, [rsp+270h+SystemTimeAsFileTime.dwHighDateTime]
0x1800475e7  lea     r9, [rbx+438h]
0x1800475ee  mov     ecx, [rbx+18h]
0x1800475f1  lea     r8, aLsLsLs; "%ls\\%ls\\%ls"
0x1800475f8  mov     dword ptr [rsp+270h+Data+4], eax
0x1800475fc  mov     eax, [rsp+270h+SystemTimeAsFileTime.dwLowDateTime]
0x180047600  imul    rdx, rcx, 23C34600h
0x180047607  mov     dword ptr [rsp+270h+Data], eax
0x18004760b  lea     rcx, [rbx+28h]
0x18004760f  mov     rax, qword ptr [rsp+270h+Data]
0x180047614  add     rdx, rax
0x180047617  mov     [rbx+640h], rax
0x18004761e  lea     rax, [rbx+230h]
0x180047625  mov     qword ptr [rsp+270h+Data], rdx
0x18004762a  mov     qword ptr [rsp+270h+cbData], rax
0x18004762f  mov     edx, 104h; unsigned __int64
0x180047634  mov     [rsp+270h+phkResult], rcx
0x180047639  lea     rcx, [rsp+270h+SubKey]; unsigned __int16 *
0x18004763e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180047643  mov     ebx, eax
0x180047645  test    eax, eax
0x180047647  js      short loc_1800476B4
0x180047649  lea     rax, [rsp+270h+hKey]
0x18004764e  mov     r9d, 0F003Fh; samDesired
0x180047654  xor     r8d, r8d; ulOptions
0x180047657  mov     [rsp+270h+phkResult], rax; phkResult
0x18004765c  lea     rdx, [rsp+270h+SubKey]; lpSubKey
0x180047661  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180047668  call    cs:__imp_RegOpenKeyExW
0x18004766e  mov     ebx, eax
0x180047670  test    eax, eax
0x180047672  jz      short loc_180047681
0x180047674  jle     short loc_1800476B4
0x180047676  movzx   ebx, ax
0x180047679  or      ebx, 80070000h
0x18004767f  jmp     short loc_1800476B4
0x180047681  mov     rcx, [rsp+270h+hKey]; hKey
0x180047686  lea     rax, [rsp+270h+Data]
0x18004768b  mov     [rsp+270h+cbData], 8; cbData
0x180047693  lea     rdx, aRefreshafter; "RefreshAfter"
0x18004769a  mov     r9d, 0Bh; dwType
0x1800476a0  mov     [rsp+270h+phkResult], rax; lpData
0x1800476a5  xor     r8d, r8d; Reserved
0x1800476a8  call    cs:__imp_RegSetValueExW
0x1800476ae  mov     ebx, eax
0x1800476b0  test    eax, eax
0x1800476b2  jnz     short loc_180047674
0x1800476b4  mov     rcx, [rsp+270h+hKey]; hKey
0x1800476b9  test    rcx, rcx
0x1800476bc  jz      short loc_1800476C4
0x1800476be  call    cs:__imp_RegCloseKey
0x1800476c4  mov     eax, ebx
0x1800476c6  mov     rcx, [rbp+170h+var_10]
0x1800476cd  xor     rcx, rsp; StackCookie
0x1800476d0  call    __security_check_cookie
0x1800476d5  mov     rbx, [rsp+270h+arg_8]
0x1800476dd  add     rsp, 270h
0x1800476e4  pop     rbp
0x1800476e5  retn
```
