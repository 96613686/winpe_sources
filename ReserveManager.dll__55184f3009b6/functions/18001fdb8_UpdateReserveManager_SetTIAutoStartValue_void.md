# UpdateReserveManager::SetTIAutoStartValue(void)

- ea: `0x18001fdb8`
- end: `0x18001ff68`
- name: `?SetTIAutoStartValue@UpdateReserveManager@@AEAAJXZ`
- size: `432`
- prototype: `__int64 __fastcall(HKEY *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18001bd30`
- `0x18001c23c`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x18001fdb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fea1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fea1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff3c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001fe22`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001fe22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fe97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ff32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fe97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ff32`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001fee1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001fee1`

## string_xrefs

- `0x18001fe32`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001feed`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001fe17`: `Services\TrustedInstaller`
- `0x18001fe3d`: `UpdateReserveManager::SetTIAutoStartValue`
- `0x18001fef8`: `UpdateReserveManager::SetTIAutoStartValue`
- `0x18001fe50`: `::RegCreateKeyExW(m_CurrentControlSetKey, L"Services\\TrustedInstaller", 0, nullptr, (0x00000004L), ((((0x00020000L)) | (0x0001) | (0x0008) | (0x0010)) & (~(0x00100000L))) | ((((0x00020000L)) | (0x0002) | (0x0004)) & (~(0x00100000L))), nullptr, &TrustedInstallerKey, nullptr)`
- `0x18001ff0b`: `::RegSetValueExW(TrustedInstallerKey, L"Start", 0, ( 4ul ), reinterpret_cast<BYTE*>(&Value), sizeof(Value))`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::SetTIAutoStartValue(HKEY *this)
{
  int v1; // ebx
  const char *v2; // rax
  const char *v4; // [rsp+58h] [rbp+17h] BYREF
  const char *v5; // [rsp+60h] [rbp+1Fh]
  __int64 v6; // [rsp+68h] [rbp+27h]
  const char *v7; // [rsp+70h] [rbp+2Fh]
  __int64 v8; // [rsp+78h] [rbp+37h]
  HKEY hKey; // [rsp+80h] [rbp+3Fh] BYREF
  BYTE Data[8]; // [rsp+88h] [rbp+47h] BYREF

  v8 = -2;
  hKey = 0;
  v1 = RegCreateKeyExW(this[15], L"Services\\TrustedInstaller", 0, 0, 4u, 0x2001Fu, 0, &hKey, 0);
  if ( v1 )
  {
    v4 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v5 = "UpdateReserveManager::SetTIAutoStartValue";
    v6 = 4131;
    v2 = "::RegCreateKeyExW(m_CurrentControlSetKey, L\"Services\\\\TrustedInstaller\", 0, nullptr, (0x00000004L), ((((0x0"
         "0020000L)) | (0x0001) | (0x0008) | (0x0010)) & (~(0x00100000L))) | ((((0x00020000L)) | (0x0002) | (0x0004)) & ("
         "~(0x00100000L))), nullptr, &TrustedInstallerKey, nullptr)";
LABEL_3:
    v7 = v2;
    if ( v1 > 0 )
      v1 = (unsigned __int16)v1 | 0x80070000;
    RtlReportErrorOrigination(&v4, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v1);
    if ( hKey && ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL )
    {
      if ( RegCloseKey(hKey) )
      {
        GetLastError();
        __fastfail(7u);
      }
    }
    return (unsigned int)v1;
  }
  *(_DWORD *)Data = 2;
  v1 = RegSetValueExW(hKey, L"Start", 0, 4u, Data, 4u);
  if ( v1 )
  {
    v4 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v5 = "UpdateReserveManager::SetTIAutoStartValue";
    v6 = 4139;
    v2 = "::RegSetValueExW(TrustedInstallerKey, L\"Start\", 0, ( 4ul ), reinterpret_cast<BYTE*>(&Value), sizeof(Value))";
    goto LABEL_3;
  }
  if ( hKey && ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
  {
    GetLastError();
    __fastfail(7u);
  }
  return 0;
}

```

## disassembly

```asm
0x18001fdb8  mov     r11, rsp
0x18001fdbb  push    rbp
0x18001fdbc  lea     rbp, [r11-5Fh]
0x18001fdc0  sub     rsp, 90h
0x18001fdc7  mov     [rbp+57h+var_20], 0FFFFFFFFFFFFFFFEh
0x18001fdcf  mov     [r11+10h], rbx
0x18001fdd3  mov     rax, cs:__security_cookie
0x18001fdda  xor     rax, rsp
0x18001fddd  mov     [rbp+57h+var_8], rax
0x18001fde1  mov     [rbp+57h+hKey], 0
0x18001fde9  mov     qword ptr [r11-58h], 0
0x18001fdf1  lea     rax, [rbp+57h+hKey]
0x18001fdf5  mov     [r11-60h], rax
0x18001fdf9  mov     qword ptr [r11-68h], 0
0x18001fe01  mov     dword ptr [rsp+28h], 2001Fh; samDesired
0x18001fe09  mov     [rsp+90h+dwOptions], 4; dwOptions
0x18001fe11  xor     r9d, r9d; lpClass
0x18001fe14  xor     r8d, r8d; Reserved
0x18001fe17  lea     rdx, aServicesTruste; "Services\\TrustedInstaller"
0x18001fe1e  mov     rcx, [rcx+78h]; hKey
0x18001fe22  call    cs:__imp_RegCreateKeyExW
0x18001fe28  mov     ebx, eax
0x18001fe2a  test    eax, eax
0x18001fe2c  jz      loc_18001FEB5
0x18001fe32  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001fe39  mov     [rbp+57h+var_40], rax
0x18001fe3d  lea     rax, aUpdatereservem_35; "UpdateReserveManager::SetTIAutoStartVal"...
0x18001fe44  mov     [rbp+57h+var_38], rax
0x18001fe48  mov     [rbp+57h+var_30], 1023h
0x18001fe50  lea     rax, aRegcreatekeyex_1; "::RegCreateKeyExW(m_CurrentControlSetKe"...
0x18001fe57  test    ebx, ebx
0x18001fe59  mov     [rbp+57h+var_28], rax
0x18001fe5d  jle     short loc_18001FE68
0x18001fe5f  movzx   ebx, bx
0x18001fe62  or      ebx, 80070000h
0x18001fe68  mov     r8d, ebx
0x18001fe6b  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001fe72  lea     rcx, [rbp+57h+var_40]
0x18001fe76  call    RtlReportErrorOrigination
0x18001fe7b  nop
0x18001fe7c  mov     rcx, [rbp+57h+hKey]; hKey
0x18001fe80  test    rcx, rcx
0x18001fe83  jz      short loc_18001FEAE
0x18001fe85  mov     rax, rcx
0x18001fe88  mov     rdx, 0FFFFFFFF80000000h
0x18001fe8f  and     rax, rdx
0x18001fe92  cmp     rax, rdx
0x18001fe95  jz      short loc_18001FEAE
0x18001fe97  call    cs:__imp_RegCloseKey
0x18001fe9d  test    eax, eax
0x18001fe9f  jz      short loc_18001FEAE
0x18001fea1  call    cs:__imp_GetLastError
0x18001fea7  mov     ecx, 7
0x18001feac  int     29h; Win8: RtlFailFast(ecx)
0x18001feae  mov     eax, ebx
0x18001feb0  jmp     loc_18001FF4B
0x18001feb5  mov     dword ptr [rbp+57h+Data], 2
0x18001febc  mov     dword ptr [rsp+28h], 4; cbData
0x18001fec4  lea     rax, [rbp+57h+Data]
0x18001fec8  mov     qword ptr [rsp+90h+dwOptions], rax; lpData
0x18001fecd  mov     r9d, 4; dwType
0x18001fed3  xor     r8d, r8d; Reserved
0x18001fed6  lea     rdx, aStart; "Start"
0x18001fedd  mov     rcx, [rbp+57h+hKey]; hKey
0x18001fee1  call    cs:__imp_RegSetValueExW
0x18001fee7  mov     ebx, eax
0x18001fee9  test    eax, eax
0x18001feeb  jz      short loc_18001FF17
0x18001feed  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001fef4  mov     [rbp+57h+var_40], rax
0x18001fef8  lea     rax, aUpdatereservem_35; "UpdateReserveManager::SetTIAutoStartVal"...
0x18001feff  mov     [rbp+57h+var_38], rax
0x18001ff03  mov     [rbp+57h+var_30], 102Bh
0x18001ff0b  lea     rax, aRegsetvalueexw_3; "::RegSetValueExW(TrustedInstallerKey, L"...
0x18001ff12  jmp     loc_18001FE57
0x18001ff17  mov     rcx, [rbp+57h+hKey]; hKey
0x18001ff1b  test    rcx, rcx
0x18001ff1e  jz      short loc_18001FF49
0x18001ff20  mov     rax, rcx
0x18001ff23  mov     rdx, 0FFFFFFFF80000000h
0x18001ff2a  and     rax, rdx
0x18001ff2d  cmp     rax, rdx
0x18001ff30  jz      short loc_18001FF49
0x18001ff32  call    cs:__imp_RegCloseKey
0x18001ff38  test    eax, eax
0x18001ff3a  jz      short loc_18001FF49
0x18001ff3c  call    cs:__imp_GetLastError
0x18001ff42  mov     ecx, 7
0x18001ff47  int     29h; Win8: RtlFailFast(ecx)
0x18001ff49  xor     eax, eax
0x18001ff4b  mov     rcx, [rbp+57h+var_8]
0x18001ff4f  xor     rcx, rsp; StackCookie
0x18001ff52  call    __security_check_cookie
0x18001ff57  mov     rbx, [rsp+90h+arg_8]
0x18001ff5f  add     rsp, 90h
0x18001ff66  pop     rbp
0x18001ff67  retn
```
