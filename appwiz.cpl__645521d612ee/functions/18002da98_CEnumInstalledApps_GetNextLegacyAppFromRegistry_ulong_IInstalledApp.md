# CEnumInstalledApps::_GetNextLegacyAppFromRegistry(ulong,IInstalledApp * *)

- ea: `0x18002da98`
- end: `0x18002dc51`
- name: `?_GetNextLegacyAppFromRegistry@CEnumInstalledApps@@IEAAJKPEAPEAUIInstalledApp@@@Z`
- size: `441`
- prototype: `int(CEnumInstalledApps *__hidden this, unsigned int, struct IInstalledApp **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002d9cc`

## callees

- `0x18000dd44`
- `0x18002cce8`
- `0x18002da98`
- `0x1800582e0`

## import_xrefs

- `SHCORE!SHQueryValueExW` at `0x18002db9f`
- `SHCORE!SHQueryValueExW` at `0x18002dbe7`
- `SHCORE!SHQueryValueExW` at `0x18002db9f`
- `SHCORE!SHQueryValueExW` at `0x18002dbe7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002db59`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002db59`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002db20`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002db20`

## string_xrefs

- `0x18002dbd8`: `WindowsInstaller`
- `0x18002db75`: `SystemComponent`

## pseudocode

```c
__int64 __fastcall CEnumInstalledApps::_GetNextLegacyAppFromRegistry(
        CEnumInstalledApps *this,
        unsigned int a2,
        struct IInstalledApp **a3)
{
  int Instance; // ebx
  DWORD v7; // edx
  HKEY v8; // rcx
  HKEY v9; // rcx
  int v10; // edi
  const struct _GUID *v11; // r8
  int pvData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pdwType; // [rsp+44h] [rbp-BCh] BYREF
  int v15; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcbData; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD v19; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF

  *a3 = 0;
  Instance = -2147467259;
  while ( 1 )
  {
    v7 = *((_DWORD *)this + 5);
    v8 = (HKEY)*((_QWORD *)this + 4);
    cchName = 260;
    ftLastWriteTime = 0;
    if ( RegEnumKeyExW(v8, v7, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
      break;
    v9 = (HKEY)*((_QWORD *)this + 4);
    v10 = 1;
    ++*((_DWORD *)this + 5);
    phkResult = 0;
    if ( !RegOpenKeyExW(v9, Name, 0, 0x20019u, &phkResult) )
    {
      pdwType = 0;
      pvData = 0;
      pcbData = 4;
      if ( SHQueryValueExW(phkResult, L"SystemComponent", 0, &pdwType, &pvData, &pcbData) || pvData != 1 )
      {
        v15 = 0;
        v19 = 4;
        if ( SHQueryValueExW(phkResult, L"WindowsInstaller", 0, &pdwType, &v15, &v19) || v15 != 1 )
        {
          Instance = CInstalledApp::s_CreateInstance(a2, Name, v11, (void **)a3);
          if ( Instance >= 0 )
            v10 = 0;
        }
      }
    }
    CTSmartObj<HKEY__ *,CAutoHandle_Policy<HKEY__ *>>::Release(&phkResult);
    if ( !v10 )
      return (unsigned int)Instance;
  }
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x18002da98  mov     [rsp-8+arg_18], rbx
0x18002da9d  push    rbp
0x18002da9e  push    rsi
0x18002da9f  push    rdi
0x18002daa0  push    r14
0x18002daa2  push    r15
0x18002daa4  lea     rbp, [rsp-190h]
0x18002daac  sub     rsp, 290h
0x18002dab3  mov     rax, cs:__security_cookie
0x18002daba  xor     rax, rsp
0x18002dabd  mov     [rbp+1B0h+var_30], rax
0x18002dac4  mov     r14, r8
0x18002dac7  mov     qword ptr [r8], 0
0x18002dace  mov     r15d, edx
0x18002dad1  mov     rsi, rcx
0x18002dad4  mov     ebx, 80004005h
0x18002dad9  mov     edx, [rsi+14h]; dwIndex
0x18002dadc  lea     rax, [rsp+2B0h+ftLastWriteTime]
0x18002dae1  mov     rcx, [rsi+20h]; hKey
0x18002dae5  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x18002daea  mov     [rsp+2B0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18002daef  lea     r8, [rsp+2B0h+Name]; lpName
0x18002daf4  mov     [rsp+2B0h+lpcchClass], 0; lpcchClass
0x18002dafd  mov     [rsp+2B0h+lpClass], 0; lpClass
0x18002db06  mov     [rsp+2B0h+lpReserved], 0; lpReserved
0x18002db0f  mov     [rsp+2B0h+cchName], 104h
0x18002db17  mov     qword ptr [rsp+2B0h+ftLastWriteTime.dwLowDateTime], 0
0x18002db20  call    cs:__imp_RegEnumKeyExW
0x18002db26  test    eax, eax
0x18002db28  jnz     loc_18002DC24
0x18002db2e  mov     rcx, [rsi+20h]; hKey
0x18002db32  lea     edi, [rax+1]
0x18002db35  inc     dword ptr [rsi+14h]
0x18002db38  lea     rax, [rsp+2B0h+phkResult]
0x18002db3d  mov     r9d, 20019h; samDesired
0x18002db43  mov     [rsp+2B0h+lpReserved], rax; phkResult
0x18002db48  xor     r8d, r8d; ulOptions
0x18002db4b  mov     [rsp+2B0h+phkResult], 0
0x18002db54  lea     rdx, [rsp+2B0h+Name]; lpSubKey
0x18002db59  call    cs:__imp_RegOpenKeyExW
0x18002db5f  test    eax, eax
0x18002db61  jnz     loc_18002DC10
0x18002db67  mov     rcx, [rsp+2B0h+phkResult]; hkey
0x18002db6c  lea     r9, [rsp+2B0h+pdwType]; pdwType
0x18002db71  mov     [rsp+2B0h+pdwType], eax
0x18002db75  lea     rdx, aSystemcomponen; "SystemComponent"
0x18002db7c  mov     [rsp+2B0h+pvData], eax
0x18002db80  xor     r8d, r8d; pdwReserved
0x18002db83  lea     rax, [rsp+2B0h+pcbData]
0x18002db88  mov     [rsp+2B0h+pcbData], 4
0x18002db90  mov     [rsp+2B0h+lpClass], rax; pcbData
0x18002db95  lea     rax, [rsp+2B0h+pvData]
0x18002db9a  mov     [rsp+2B0h+lpReserved], rax; pvData
0x18002db9f  call    cs:__imp_SHQueryValueExW
0x18002dba5  test    eax, eax
0x18002dba7  jnz     short loc_18002DBAF
0x18002dba9  cmp     [rsp+2B0h+pvData], edi
0x18002dbad  jz      short loc_18002DC10
0x18002dbaf  mov     rcx, [rsp+2B0h+phkResult]; hkey
0x18002dbb4  lea     rax, [rsp+2B0h+var_250]
0x18002dbb9  mov     [rsp+2B0h+lpClass], rax; pcbData
0x18002dbbe  lea     r9, [rsp+2B0h+pdwType]; pdwType
0x18002dbc3  lea     rax, [rsp+2B0h+var_268]
0x18002dbc8  mov     [rsp+2B0h+var_268], 0
0x18002dbd0  xor     r8d, r8d; pdwReserved
0x18002dbd3  mov     [rsp+2B0h+lpReserved], rax; pvData
0x18002dbd8  lea     rdx, aWindowsinstall; "WindowsInstaller"
0x18002dbdf  mov     [rsp+2B0h+var_250], 4
0x18002dbe7  call    cs:__imp_SHQueryValueExW
0x18002dbed  test    eax, eax
0x18002dbef  jnz     short loc_18002DBF7
0x18002dbf1  cmp     [rsp+2B0h+var_268], edi
0x18002dbf5  jz      short loc_18002DC10
0x18002dbf7  mov     r9, r14; void **
0x18002dbfa  lea     rdx, [rsp+2B0h+Name]; szProduct
0x18002dbff  mov     ecx, r15d; unsigned int
0x18002dc02  call    ?s_CreateInstance@CInstalledApp@@SAJKPEBGAEBU_GUID@@PEAPEAX@Z; CInstalledApp::s_CreateInstance(ulong,ushort const *,_GUID const &,void * *)
0x18002dc07  xor     ecx, ecx
0x18002dc09  mov     ebx, eax
0x18002dc0b  test    eax, eax
0x18002dc0d  cmovns  edi, ecx
0x18002dc10  lea     rcx, [rsp+2B0h+phkResult]
0x18002dc15  call    ?Release@?$CTSmartObj@PEAUHKEY__@@V?$CAutoHandle_Policy@PEAUHKEY__@@@@@@QEAAXXZ; CTSmartObj<HKEY__ *,CAutoHandle_Policy<HKEY__ *>>::Release(void)
0x18002dc1a  test    edi, edi
0x18002dc1c  jnz     loc_18002DAD9
0x18002dc22  jmp     short loc_18002DC29
0x18002dc24  mov     ebx, 80004005h
0x18002dc29  mov     eax, ebx
0x18002dc2b  mov     rcx, [rbp+1B0h+var_30]
0x18002dc32  xor     rcx, rsp; StackCookie
0x18002dc35  call    __security_check_cookie
0x18002dc3a  mov     rbx, [rsp+2B0h+arg_18]
0x18002dc42  add     rsp, 290h
0x18002dc49  pop     r15
0x18002dc4b  pop     r14
0x18002dc4d  pop     rdi
0x18002dc4e  pop     rsi
0x18002dc4f  pop     rbp
0x18002dc50  retn
```
