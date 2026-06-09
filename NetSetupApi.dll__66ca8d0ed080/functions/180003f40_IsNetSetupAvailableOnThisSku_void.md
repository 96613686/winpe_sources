# IsNetSetupAvailableOnThisSku(void)

- ea: `0x180003f40`
- end: `0x180004115`
- name: `?IsNetSetupAvailableOnThisSku@@YA_NXZ`
- size: `469`
- prototype: `char(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x180003b90`

## callees

- `0x180003f40`
- `0x180004120`
- `0x18000536c`
- `0x1800065d4`
- `0x18000895c`
- `0x18000fbfc`
- `0x180010798`
- `0x180010c9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003fb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003fcc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003ff2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004001`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000401c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000402b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000403f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003fb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003fcc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003ff2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004001`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000401c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000402b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000403f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003f9f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003f9f`

## string_xrefs

- `0x180003f8d`: `Installer32`
- `0x18000407e`: `Installer32`

## pseudocode

```c
char IsNetSetupAvailableOnThisSku(void)
{
  HKEY v0; // rbx
  LSTATUS Value; // edi
  HKEY v2; // rcx
  HKEY v4; // rcx
  _BYTE pExceptionObject[224]; // [rsp+38h] [rbp-E0h] BYREF
  HKEY v6; // [rsp+120h] [rbp+8h] BYREF
  HKEY v7; // [rsp+128h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+130h] [rbp+18h] BYREF

  v7 = HKEY_LOCAL_MACHINE;
  RegistryKey::OpenSubKey(
    &v7,
    &hKey,
    L"SYSTEM\\CurrentControlSet\\Control\\Class\\{4d36e972-e325-11ce-bfc1-08002be10318}",
    1);
  v0 = hKey;
  Value = RegQueryValueExW(hKey, L"Installer32", 0, 0, 0, 0);
  if ( Value == 2 )
  {
    if ( v0 )
      RegCloseKey(v0);
    v2 = v7;
    if ( !v7 )
      return 1;
    goto LABEL_5;
  }
  if ( Value )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids,
        (unsigned int)L"Installer32",
        Value);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, Value);
    throw (Win32Exception *)pExceptionObject;
  }
  RegistryKey::TryOpenSubKey(&v7, &v6);
  v4 = v6;
  if ( v6 )
  {
    if ( RegistryKey::ValueExists((RegistryKey *)&v6, L"ForceAllowApi") && (unsigned int)RegistryKey::GetValueDword(&v6) )
    {
      if ( v6 )
        RegCloseKey(v6);
      if ( v0 )
        RegCloseKey(v0);
      v2 = v7;
      if ( !v7 )
        return 1;
LABEL_5:
      RegCloseKey(v2);
      return 1;
    }
    v4 = v6;
  }
  if ( v4 )
    RegCloseKey(v4);
  if ( v0 )
    RegCloseKey(v0);
  if ( v7 )
    RegCloseKey(v7);
  return 0;
}

```

## disassembly

```asm
0x180003f40  mov     rax, rsp
0x180003f43  push    rdi
0x180003f44  sub     rsp, 110h
0x180003f4b  mov     [rsp+118h+var_E8], 0FFFFFFFFFFFFFFFEh
0x180003f54  mov     [rax+20h], rbx
0x180003f58  xor     ebx, ebx
0x180003f5a  mov     qword ptr [rax+10h], 0FFFFFFFF80000002h
0x180003f62  mov     r9d, 1
0x180003f68  lea     r8, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Cla"...
0x180003f6f  lea     rdx, [rax+18h]
0x180003f73  lea     rcx, [rax+10h]
0x180003f77  call    ?OpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::OpenSubKey(wchar_t const *,ulong,void *)
0x180003f7c  nop
0x180003f7d  mov     [rsp+118h+lpcbData], rbx; lpcbData
0x180003f82  mov     [rsp+118h+lpData], rbx; lpData
0x180003f87  xor     r9d, r9d; lpType
0x180003f8a  xor     r8d, r8d; lpReserved
0x180003f8d  lea     rdx, ValueName; "Installer32"
0x180003f94  mov     rbx, [rsp+118h+hKey]
0x180003f9c  mov     rcx, rbx; hKey
0x180003f9f  call    cs:__imp_RegQueryValueExW
0x180003fa5  mov     edi, eax
0x180003fa7  cmp     eax, 2
0x180003faa  jnz     loc_180004058
0x180003fb0  test    rbx, rbx
0x180003fb3  jz      short loc_180003FBF
0x180003fb5  mov     rcx, rbx; hKey
0x180003fb8  call    cs:__imp_RegCloseKey
0x180003fbe  nop
0x180003fbf  mov     rcx, [rsp+118h+arg_8]; hKey
0x180003fc7  test    rcx, rcx
0x180003fca  jz      short loc_180003FD2
0x180003fcc  call    cs:__imp_RegCloseKey
0x180003fd2  mov     al, 1
0x180003fd4  mov     rbx, [rsp+118h+arg_18]
0x180003fdc  add     rsp, 110h
0x180003fe3  pop     rdi
0x180003fe4  retn
0x180003fe5  mov     rcx, [rsp+118h+arg_0]; hKey
0x180003fed  test    rcx, rcx
0x180003ff0  jz      short loc_180003FF9
0x180003ff2  call    cs:__imp_RegCloseKey
0x180003ff8  nop
0x180003ff9  test    rbx, rbx
0x180003ffc  jz      short loc_180004008
0x180003ffe  mov     rcx, rbx; hKey
0x180004001  call    cs:__imp_RegCloseKey
0x180004007  nop
0x180004008  mov     rcx, [rsp+118h+arg_8]
0x180004010  test    rcx, rcx
0x180004013  jz      short loc_180003FD2
0x180004015  jmp     short loc_180003FCC
0x180004017  test    rcx, rcx
0x18000401a  jz      short loc_180004023
0x18000401c  call    cs:__imp_RegCloseKey
0x180004022  nop
0x180004023  test    rbx, rbx
0x180004026  jz      short loc_180004032
0x180004028  mov     rcx, rbx; hKey
0x18000402b  call    cs:__imp_RegCloseKey
0x180004031  nop
0x180004032  mov     rcx, [rsp+118h+arg_8]; hKey
0x18000403a  test    rcx, rcx
0x18000403d  jz      short loc_180004045
0x18000403f  call    cs:__imp_RegCloseKey
0x180004045  xor     al, al
0x180004047  mov     rbx, [rsp+118h+arg_18]
0x18000404f  add     rsp, 110h
0x180004056  pop     rdi
0x180004057  retn
0x180004058  test    edi, edi
0x18000405a  jz      short loc_1800040B3
0x18000405c  lea     rax, WPP_GLOBAL_Control
0x180004063  mov     rcx, cs:WPP_GLOBAL_Control
0x18000406a  cmp     rcx, rax
0x18000406d  jz      short loc_180004095
0x18000406f  cmp     byte ptr [rcx+19h], 2
0x180004073  jb      short loc_180004095
0x180004075  mov     edx, 13h
0x18000407a  mov     dword ptr [rsp+118h+lpData], edi
0x18000407e  lea     r9, ValueName; "Installer32"
0x180004085  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x18000408c  mov     rcx, [rcx+10h]
0x180004090  call    WPP_SF_SD
0x180004095  mov     edx, edi; int
0x180004097  lea     rcx, [rsp+118h+pExceptionObject]; this
0x18000409c  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x1800040a1  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x1800040a8  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x1800040ad  call    _CxxThrowException_0
0x1800040b3  lea     rdx, [rsp+118h+arg_0]
0x1800040bb  lea     rcx, [rsp+118h+arg_8]
0x1800040c3  call    ?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)
0x1800040c8  nop
0x1800040c9  mov     rcx, [rsp+118h+arg_0]; hKey
0x1800040d1  test    rcx, rcx
0x1800040d4  jz      loc_180004017
0x1800040da  lea     rdx, aForceallowapi; "ForceAllowApi"
0x1800040e1  lea     rcx, [rsp+118h+arg_0]; this
0x1800040e9  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x1800040ee  test    al, al
0x1800040f0  jz      short loc_180004107
0x1800040f2  lea     rcx, [rsp+118h+arg_0]
0x1800040fa  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x1800040ff  test    eax, eax
0x180004101  jnz     loc_180003FE5
0x180004107  mov     rcx, [rsp+118h+arg_0]
0x18000410f  jmp     loc_180004017
```
