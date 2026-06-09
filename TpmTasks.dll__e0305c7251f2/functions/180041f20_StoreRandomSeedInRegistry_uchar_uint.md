# StoreRandomSeedInRegistry(uchar *,uint)

- ea: `0x180041f20`
- end: `0x18004207a`
- name: `?StoreRandomSeedInRegistry@@YAJPEAEI@Z`
- size: `346`
- prototype: `__int64 __fastcall(BYTE *lpData, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180041728`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x180041f20`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x180041f97`
- `ntdll!RtlGetPersistedStateLocation` at `0x180041f97`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180041ff2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180041ff2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004204a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004204a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004202a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004202a`

## string_xrefs

- `0x180041f79`: `System\CurrentControlSet\Services\TPM\ODUID`

## pseudocode

```c
__int64 __fastcall StoreRandomSeedInRegistry(BYTE *lpData)
{
  int PersistedStateLocation; // eax
  signed int v3; // ebx
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  int v7; // [rsp+50h] [rbp-238h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-230h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-228h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  memset_0(SubKey, 0, 0x208u);
  v7 = 520;
  if ( lpData )
  {
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"OfflineDeviceID",
                               0,
                               L"System\\CurrentControlSet\\Services\\TPM\\ODUID",
                               0,
                               SubKey,
                               520,
                               &v7);
    v3 = PersistedStateLocation;
    if ( PersistedStateLocation > 0 )
      v3 = (unsigned __int16)PersistedStateLocation | 0x80070000;
    if ( v3 >= 0 )
    {
      v4 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 3u, 0, &hKey, 0);
      v3 = v4;
      if ( v4 > 0 )
        v3 = (unsigned __int16)v4 | 0x80070000;
      if ( v3 >= 0 )
      {
        v5 = RegSetValueExW(hKey, L"RandomSeed", 0, 0, lpData, 0x20u);
        v3 = v5;
        if ( v5 > 0 )
          v3 = (unsigned __int16)v5 | 0x80070000;
      }
    }
    if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hKey);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180041f20  mov     [rsp+arg_8], rbx
0x180041f25  push    rdi
0x180041f26  sub     rsp, 280h
0x180041f2d  mov     rax, cs:__security_cookie
0x180041f34  xor     rax, rsp
0x180041f37  mov     [rsp+288h+var_18], rax
0x180041f3f  mov     rdi, rcx
0x180041f42  mov     [rsp+288h+hKey], 0FFFFFFFFFFFFFFFFh
0x180041f4b  mov     ebx, 208h
0x180041f50  lea     rcx, [rsp+288h+SubKey]; void *
0x180041f55  mov     r8d, ebx; Size
0x180041f58  xor     edx, edx; Val
0x180041f5a  call    memset_0
0x180041f5f  mov     [rsp+288h+var_238], ebx
0x180041f63  test    rdi, rdi
0x180041f66  jz      loc_180042052
0x180041f6c  lea     rax, [rsp+288h+var_238]
0x180041f71  xor     r9d, r9d
0x180041f74  mov     [rsp+288h+lpSecurityAttributes], rax
0x180041f79  lea     r8, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\TP"...
0x180041f80  lea     rax, [rsp+288h+SubKey]
0x180041f85  mov     [rsp+288h+samDesired], ebx
0x180041f89  xor     edx, edx
0x180041f8b  mov     qword ptr [rsp+288h+dwOptions], rax
0x180041f90  lea     rcx, aOfflinedevicei_0; "OfflineDeviceID"
0x180041f97  call    cs:__imp_RtlGetPersistedStateLocation
0x180041f9d  mov     ebx, eax
0x180041f9f  test    eax, eax
0x180041fa1  jle     short loc_180041FAC
0x180041fa3  movzx   ebx, ax
0x180041fa6  or      ebx, 80070000h
0x180041fac  test    ebx, ebx
0x180041fae  js      loc_18004203F
0x180041fb4  mov     [rsp+288h+lpdwDisposition], 0; lpdwDisposition
0x180041fbd  lea     rax, [rsp+288h+hKey]
0x180041fc2  mov     [rsp+288h+phkResult], rax; phkResult
0x180041fc7  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x180041fcc  mov     [rsp+288h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180041fd5  xor     r9d, r9d; lpClass
0x180041fd8  mov     [rsp+288h+samDesired], 3; samDesired
0x180041fe0  xor     r8d, r8d; Reserved
0x180041fe3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180041fea  mov     [rsp+288h+dwOptions], 0; dwOptions
0x180041ff2  call    cs:__imp_RegCreateKeyExW
0x180041ff8  mov     ebx, eax
0x180041ffa  test    eax, eax
0x180041ffc  jle     short loc_180042007
0x180041ffe  movzx   ebx, ax
0x180042001  or      ebx, 80070000h
0x180042007  test    ebx, ebx
0x180042009  js      short loc_18004203F
0x18004200b  mov     rcx, [rsp+288h+hKey]; hKey
0x180042010  lea     rdx, aRandomseed; "RandomSeed"
0x180042017  mov     [rsp+288h+samDesired], 20h ; ' '; cbData
0x18004201f  xor     r9d, r9d; dwType
0x180042022  xor     r8d, r8d; Reserved
0x180042025  mov     qword ptr [rsp+288h+dwOptions], rdi; lpData
0x18004202a  call    cs:__imp_RegSetValueExW
0x180042030  mov     ebx, eax
0x180042032  test    eax, eax
0x180042034  jle     short loc_18004203F
0x180042036  movzx   ebx, ax
0x180042039  or      ebx, 80070000h
0x18004203f  mov     rcx, [rsp+288h+hKey]; hKey
0x180042044  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180042048  jz      short loc_180042057
0x18004204a  call    cs:__imp_RegCloseKey
0x180042050  jmp     short loc_180042057
0x180042052  mov     ebx, 80070057h
0x180042057  mov     eax, ebx
0x180042059  mov     rcx, [rsp+288h+var_18]
0x180042061  xor     rcx, rsp; StackCookie
0x180042064  call    __security_check_cookie
0x180042069  mov     rbx, [rsp+288h+arg_8]
0x180042071  add     rsp, 280h
0x180042078  pop     rdi
0x180042079  retn
```
