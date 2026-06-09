# OneSettings::UpdateNextRefreshTime(void)

- ea: `0x140019e9c`
- end: `0x140019f8b`
- name: `?UpdateNextRefreshTime@OneSettings@@AEAAJXZ`
- size: `239`
- prototype: `__int64 __fastcall(OneSettings *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x140018a94`

## callees

- `0x140019e9c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140019eb4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140019eb4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140019f1a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140019f1a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140019f5d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140019f5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140019f7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140019f7b`

## pseudocode

```c
__int64 __fastcall OneSettings::UpdateNextRefreshTime(OneSettings *this)
{
  unsigned int v2; // ebx
  const WCHAR *v3; // rdx
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  struct _FILETIME Data; // [rsp+78h] [rbp+28h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+38h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v3 = (const WCHAR *)((char *)this + 128);
  hKey = 0;
  Data = SystemTimeAsFileTime;
  Data = (struct _FILETIME)(600000000LL * *((unsigned int *)this + 48) + *(_QWORD *)&SystemTimeAsFileTime);
  if ( *((_QWORD *)this + 19) > 7u )
    v3 = *(const WCHAR **)v3;
  v4 = RegCreateKeyExW(*((HKEY *)this + 20), v3, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  if ( v4 )
  {
    if ( v4 > 0 )
      v2 = (unsigned __int16)v4 | 0x80070000;
    else
      v2 = v4;
  }
  else
  {
    v5 = RegSetValueExW(hKey, L"RefreshAfter", 0, 0xBu, (const BYTE *)&Data, 8u);
    if ( v5 )
    {
      if ( v5 > 0 )
        v2 = (unsigned __int16)v5 | 0x80070000;
      else
        v2 = v5;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x140019e9c  push    rbp
0x140019e9e  push    rbx
0x140019e9f  push    rdi
0x140019ea0  mov     rbp, rsp
0x140019ea3  sub     rsp, 50h
0x140019ea7  mov     rdi, rcx
0x140019eaa  xor     ebx, ebx
0x140019eac  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140019eb0  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rbx
0x140019eb4  call    cs:__imp_GetSystemTimeAsFileTime
0x140019eba  xor     eax, eax
0x140019ebc  lea     rdx, [rdi+80h]
0x140019ec3  mov     [rbp+hKey], rax
0x140019ec7  mov     eax, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x140019eca  mov     dword ptr [rbp+Data+4], eax
0x140019ecd  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140019ed0  mov     dword ptr [rbp+Data], eax
0x140019ed3  mov     eax, [rdi+0C0h]
0x140019ed9  imul    rcx, rax, 23C34600h
0x140019ee0  add     [rbp+Data], rcx
0x140019ee4  cmp     qword ptr [rdx+18h], 7
0x140019ee9  jbe     short loc_140019EEE
0x140019eeb  mov     rdx, [rdx]; lpSubKey
0x140019eee  mov     rcx, [rdi+0A0h]; hKey
0x140019ef5  lea     rax, [rbp+hKey]
0x140019ef9  mov     [rsp+50h+lpdwDisposition], rbx; lpdwDisposition
0x140019efe  xor     r9d, r9d; lpClass
0x140019f01  mov     [rsp+50h+phkResult], rax; phkResult
0x140019f06  xor     r8d, r8d; Reserved
0x140019f09  mov     [rsp+50h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x140019f0e  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x140019f16  mov     [rsp+50h+dwOptions], ebx; dwOptions
0x140019f1a  call    cs:__imp_RegCreateKeyExW
0x140019f20  mov     edi, 80070000h
0x140019f25  test    eax, eax
0x140019f27  jz      short loc_140019F38
0x140019f29  jg      short loc_140019F2F
0x140019f2b  mov     ebx, eax
0x140019f2d  jmp     short loc_140019F34
0x140019f2f  movzx   ebx, ax
0x140019f32  or      ebx, edi
0x140019f34  test    ebx, ebx
0x140019f36  js      short loc_140019F72
0x140019f38  mov     rcx, [rbp+hKey]; hKey
0x140019f3c  lea     rax, [rbp+Data]
0x140019f40  mov     [rsp+50h+samDesired], 8; cbData
0x140019f48  lea     rdx, aRefreshafter; "RefreshAfter"
0x140019f4f  mov     r9d, 0Bh; dwType
0x140019f55  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x140019f5a  xor     r8d, r8d; Reserved
0x140019f5d  call    cs:__imp_RegSetValueExW
0x140019f63  test    eax, eax
0x140019f65  jz      short loc_140019F72
0x140019f67  jg      short loc_140019F6D
0x140019f69  mov     ebx, eax
0x140019f6b  jmp     short loc_140019F72
0x140019f6d  movzx   ebx, ax
0x140019f70  or      ebx, edi
0x140019f72  mov     rcx, [rbp+hKey]; hKey
0x140019f76  test    rcx, rcx
0x140019f79  jz      short loc_140019F81
0x140019f7b  call    cs:__imp_RegCloseKey
0x140019f81  mov     eax, ebx
0x140019f83  add     rsp, 50h
0x140019f87  pop     rdi
0x140019f88  pop     rbx
0x140019f89  pop     rbp
0x140019f8a  retn
```
