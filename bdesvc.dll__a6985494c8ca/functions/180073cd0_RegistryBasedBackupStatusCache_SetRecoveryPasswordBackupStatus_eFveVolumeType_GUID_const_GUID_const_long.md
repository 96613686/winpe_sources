# RegistryBasedBackupStatusCache::SetRecoveryPasswordBackupStatus(eFveVolumeType,_GUID const *,_GUID const *,long)

- ea: `0x180073cd0`
- end: `0x180073f97`
- name: `?SetRecoveryPasswordBackupStatus@RegistryBasedBackupStatusCache@@UEBAJW4eFveVolumeType@@PEBU_GUID@@1J@Z`
- size: `711`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180009f60`
- `0x18001b2f8`
- `0x180034070`
- `0x180034d28`
- `0x180073cd0`
- `0x18007e010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073e32`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073e32`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073eaa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073f1a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073eaa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073f1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073f69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073f69`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180073d2d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180073d2d`

## pseudocode

```c
__int64 RegistryBasedBackupStatusCache::SetRecoveryPasswordBackupStatus(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        ...)
{
  signed int v8; // ebx
  unsigned int RegistrySubKeyForProtector; // eax
  HKEY v10; // rax
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF
  va_list Data; // [rsp+2E0h] [rbp+1E0h] BYREF

  va_start(Data, a4);
  hKey = 0;
  memset_0(SubKey, 0, 0x208u);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
  if ( !v8 )
    goto LABEL_6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      118,
      &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
      (unsigned int)v8);
  if ( v8 >= 0 )
  {
LABEL_6:
    RegistrySubKeyForProtector = RegistryBasedBackupStatusCache::GetRegistrySubKeyForProtector(a1, a2, a3, a4, SubKey);
    v8 = RegistrySubKeyForProtector;
    if ( !RegistrySubKeyForProtector )
      goto LABEL_11;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        119,
        &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
        RegistrySubKeyForProtector);
    if ( v8 >= 0 )
    {
LABEL_11:
      v10 = (HKEY)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
      v11 = RegCreateKeyExW(v10, SubKey, 0, 0, 0, 0x2000000u, 0, &hKey, 0);
      v8 = v11;
      if ( v11 > 0 )
        v8 = (unsigned __int16)v11 | 0x80070000;
      if ( !v8 )
        goto LABEL_18;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          120,
          &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
          (unsigned int)v8);
      if ( v8 >= 0 )
      {
LABEL_18:
        v12 = RegSetValueExW(hKey, L"LastBackupStatus", 0, 4u, (const BYTE *)Data, 4u);
        v8 = v12;
        if ( v12 > 0 )
          v8 = (unsigned __int16)v12 | 0x80070000;
        if ( !v8 )
          goto LABEL_25;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            121,
            &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
            (unsigned int)v8);
        if ( v8 >= 0 )
        {
LABEL_25:
          v13 = RegSetValueExW(hKey, L"LastBackupTime", 0, 0xBu, (const BYTE *)&SystemTimeAsFileTime, 8u);
          v8 = v13;
          if ( v13 > 0 )
            v8 = (unsigned __int16)v13 | 0x80070000;
          if ( v8 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              122,
              &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
              (unsigned int)v8);
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180073cd0  push    rbp
0x180073cd2  push    rbx
0x180073cd3  push    rsi
0x180073cd4  push    rdi
0x180073cd5  push    r14
0x180073cd7  push    r15
0x180073cd9  lea     rbp, [rsp-188h]
0x180073ce1  sub     rsp, 288h
0x180073ce8  mov     rax, cs:__security_cookie
0x180073cef  xor     rax, rsp
0x180073cf2  mov     [rbp+1B0h+var_40], rax
0x180073cf9  mov     r14, r8
0x180073cfc  mov     [rsp+2B0h+hKey], 0
0x180073d05  mov     esi, edx
0x180073d07  mov     rdi, rcx
0x180073d0a  xor     edx, edx; Val
0x180073d0c  lea     rcx, [rsp+2B0h+SubKey]; void *
0x180073d11  mov     r8d, 208h; Size
0x180073d17  mov     r15, r9
0x180073d1a  call    memset_0
0x180073d1f  lea     rcx, [rsp+2B0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180073d24  mov     qword ptr [rsp+2B0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180073d2d  call    cs:__imp_GetSystemTimeAsFileTime
0x180073d34  nop     dword ptr [rax+rax+00h]
0x180073d39  mov     rax, [rdi]
0x180073d3c  mov     rcx, rdi
0x180073d3f  mov     rax, [rax+28h]
0x180073d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073d48  mov     ebx, eax
0x180073d4a  lea     rax, WPP_GLOBAL_Control
0x180073d51  test    ebx, ebx
0x180073d53  jz      short loc_180073D87
0x180073d55  mov     rcx, cs:WPP_GLOBAL_Control
0x180073d5c  cmp     rcx, rax
0x180073d5f  jz      short loc_180073D7F
0x180073d61  test    byte ptr [rcx+1Ch], 40h
0x180073d65  jz      short loc_180073D7F
0x180073d67  mov     rcx, [rcx+10h]
0x180073d6b  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180073d72  mov     edx, 76h ; 'v'
0x180073d77  mov     r9d, ebx
0x180073d7a  call    WPP_SF_d
0x180073d7f  test    ebx, ebx
0x180073d81  js      loc_180073F5F
0x180073d87  lea     rax, [rsp+2B0h+SubKey]
0x180073d8c  mov     r9, r15
0x180073d8f  mov     r8, r14
0x180073d92  mov     qword ptr [rsp+2B0h+dwOptions], rax
0x180073d97  mov     edx, esi
0x180073d99  mov     rcx, rdi
0x180073d9c  call    ?GetRegistrySubKeyForProtector@RegistryBasedBackupStatusCache@@AEBAJW4eFveVolumeType@@PEBU_GUID@@1PEAG_K@Z; RegistryBasedBackupStatusCache::GetRegistrySubKeyForProtector(eFveVolumeType,_GUID const *,_GUID const *,ushort *,unsigned __int64)
0x180073da1  mov     ebx, eax
0x180073da3  test    eax, eax
0x180073da5  jz      short loc_180073DE2
0x180073da7  mov     rcx, cs:WPP_GLOBAL_Control
0x180073dae  lea     rsi, WPP_GLOBAL_Control
0x180073db5  cmp     rcx, rsi
0x180073db8  jz      short loc_180073DD8
0x180073dba  test    byte ptr [rcx+1Ch], 40h
0x180073dbe  jz      short loc_180073DD8
0x180073dc0  mov     rcx, [rcx+10h]
0x180073dc4  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180073dcb  mov     edx, 77h ; 'w'
0x180073dd0  mov     r9d, eax
0x180073dd3  call    WPP_SF_d
0x180073dd8  test    ebx, ebx
0x180073dda  js      loc_180073F5F
0x180073de0  jmp     short loc_180073DE9
0x180073de2  lea     rsi, WPP_GLOBAL_Control
0x180073de9  mov     rax, [rdi]
0x180073dec  mov     rcx, rdi
0x180073def  mov     rax, [rax+18h]
0x180073df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073df8  mov     [rsp+2B0h+lpdwDisposition], 0; lpdwDisposition
0x180073e01  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x180073e06  mov     rcx, rax; hKey
0x180073e09  xor     r9d, r9d; lpClass
0x180073e0c  lea     rax, [rsp+2B0h+hKey]
0x180073e11  xor     r8d, r8d; Reserved
0x180073e14  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180073e19  mov     [rsp+2B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180073e22  mov     [rsp+2B0h+samDesired], 2000000h; samDesired
0x180073e2a  mov     [rsp+2B0h+dwOptions], 0; dwOptions
0x180073e32  call    cs:__imp_RegCreateKeyExW
0x180073e39  nop     dword ptr [rax+rax+00h]
0x180073e3e  mov     ebx, eax
0x180073e40  mov     edi, 80070000h
0x180073e45  test    eax, eax
0x180073e47  jle     short loc_180073E4E
0x180073e49  movzx   ebx, ax
0x180073e4c  or      ebx, edi
0x180073e4e  test    ebx, ebx
0x180073e50  jz      short loc_180073E84
0x180073e52  mov     rcx, cs:WPP_GLOBAL_Control
0x180073e59  cmp     rcx, rsi
0x180073e5c  jz      short loc_180073E7C
0x180073e5e  test    byte ptr [rcx+1Ch], 40h
0x180073e62  jz      short loc_180073E7C
0x180073e64  mov     rcx, [rcx+10h]
0x180073e68  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180073e6f  mov     edx, 78h ; 'x'
0x180073e74  mov     r9d, ebx
0x180073e77  call    WPP_SF_d
0x180073e7c  test    ebx, ebx
0x180073e7e  js      loc_180073F5F
0x180073e84  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180073e89  lea     rax, [rbp+1B0h+Data]
0x180073e90  mov     r9d, 4; dwType
0x180073e96  lea     rdx, aLastbackupstat; "LastBackupStatus"
0x180073e9d  mov     [rsp+2B0h+samDesired], r9d; cbData
0x180073ea2  xor     r8d, r8d; Reserved
0x180073ea5  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x180073eaa  call    cs:__imp_RegSetValueExW
0x180073eb1  nop     dword ptr [rax+rax+00h]
0x180073eb6  mov     ebx, eax
0x180073eb8  test    eax, eax
0x180073eba  jle     short loc_180073EC1
0x180073ebc  movzx   ebx, ax
0x180073ebf  or      ebx, edi
0x180073ec1  test    ebx, ebx
0x180073ec3  jz      short loc_180073EF3
0x180073ec5  mov     rcx, cs:WPP_GLOBAL_Control
0x180073ecc  cmp     rcx, rsi
0x180073ecf  jz      short loc_180073EEF
0x180073ed1  test    byte ptr [rcx+1Ch], 40h
0x180073ed5  jz      short loc_180073EEF
0x180073ed7  mov     rcx, [rcx+10h]
0x180073edb  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180073ee2  mov     edx, 79h ; 'y'
0x180073ee7  mov     r9d, ebx
0x180073eea  call    WPP_SF_d
0x180073eef  test    ebx, ebx
0x180073ef1  js      short loc_180073F5F
0x180073ef3  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180073ef8  lea     rax, [rsp+2B0h+SystemTimeAsFileTime]
0x180073efd  mov     [rsp+2B0h+samDesired], 8; cbData
0x180073f05  lea     rdx, aLastbackuptime; "LastBackupTime"
0x180073f0c  mov     r9d, 0Bh; dwType
0x180073f12  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x180073f17  xor     r8d, r8d; Reserved
0x180073f1a  call    cs:__imp_RegSetValueExW
0x180073f21  nop     dword ptr [rax+rax+00h]
0x180073f26  mov     ebx, eax
0x180073f28  test    eax, eax
0x180073f2a  jle     short loc_180073F31
0x180073f2c  movzx   ebx, ax
0x180073f2f  or      ebx, edi
0x180073f31  test    ebx, ebx
0x180073f33  jz      short loc_180073F5F
0x180073f35  mov     rcx, cs:WPP_GLOBAL_Control
0x180073f3c  cmp     rcx, rsi
0x180073f3f  jz      short loc_180073F5F
0x180073f41  test    byte ptr [rcx+1Ch], 40h
0x180073f45  jz      short loc_180073F5F
0x180073f47  mov     rcx, [rcx+10h]
0x180073f4b  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180073f52  mov     edx, 7Ah ; 'z'
0x180073f57  mov     r9d, ebx
0x180073f5a  call    WPP_SF_d
0x180073f5f  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180073f64  test    rcx, rcx
0x180073f67  jz      short loc_180073F75
0x180073f69  call    cs:__imp_RegCloseKey
0x180073f70  nop     dword ptr [rax+rax+00h]
0x180073f75  mov     eax, ebx
0x180073f77  mov     rcx, [rbp+1B0h+var_40]
0x180073f7e  xor     rcx, rsp; StackCookie
0x180073f81  call    __security_check_cookie
0x180073f86  add     rsp, 288h
0x180073f8d  pop     r15
0x180073f8f  pop     r14
0x180073f91  pop     rdi
0x180073f92  pop     rsi
0x180073f93  pop     rbx
0x180073f94  pop     rbp
0x180073f95  retn
```
