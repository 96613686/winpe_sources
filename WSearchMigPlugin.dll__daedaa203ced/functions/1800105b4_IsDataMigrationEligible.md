# IsDataMigrationEligible

- ea: `0x1800105b4`
- end: `0x18001076e`
- name: `IsDataMigrationEligible`
- size: `442`
- prototype: `bool __fastcall(struct IUnknown *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1800144e0`
- `0x1800149a0`
- `0x180014c50`

## callees

- `0x1800026f0`
- `0x1800105b4`
- `0x180010c50`
- `0x180011220`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800106de`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800106de`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001066a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001066a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001071e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001071e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001061d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001061d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010742`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010742`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall IsDataMigrationEligible(struct IUnknown *a1)
{
  bool v1; // bl
  HKEY v2; // rdi
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  DWORD Type[2]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF

  v1 = 0;
  MapRegKeyPathIfNeeded(a1, (OLECHAR *)L"SYSTEM\\Setup\\Upgrade\\WSearch");
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
  {
    cbData = 0;
    *(_QWORD *)Type = 0;
    if ( RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x2001Fu, 0, (PHKEY)Type, &cbData) )
      return v1;
    v2 = *(HKEY *)Type;
    *(_DWORD *)Data = IsWindows8Point1OrGreater();
    if ( !RegSetValueExW(v2, L"DataMigrationSupport", 0, 4u, Data, 4u) )
      v1 = IsWindows8Point1OrGreater();
  }
  else
  {
    v2 = hKey;
    *(_DWORD *)Data = 0;
    Type[0] = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"DataMigrationSupport", 0, Type, Data, &cbData) && Type[0] == 4 )
      v1 = *(_DWORD *)Data == 1;
  }
  if ( v2 )
    RegCloseKey(v2);
  return v1;
}

```

## disassembly

```asm
0x1800105b4  mov     [rsp-8+arg_8], rbx
0x1800105b9  mov     [rsp-8+arg_10], rdi
0x1800105be  push    rbp
0x1800105bf  lea     rbp, [rsp-190h]
0x1800105c7  sub     rsp, 290h
0x1800105ce  mov     rax, cs:__security_cookie
0x1800105d5  xor     rax, rsp
0x1800105d8  mov     [rbp+190h+var_10], rax
0x1800105df  lea     r8, [rsp+290h+SubKey]
0x1800105e4  xor     bl, bl
0x1800105e6  lea     rdx, aSystemSetupUpg; "SYSTEM\\Setup\\Upgrade\\WSearch"
0x1800105ed  call    MapRegKeyPathIfNeeded
0x1800105f2  lea     rax, [rsp+290h+hKey]
0x1800105f7  mov     [rsp+290h+hKey], 0
0x180010600  mov     rdi, 0FFFFFFFF80000002h
0x180010607  mov     [rsp+290h+phkResult], rax; phkResult
0x18001060c  mov     rcx, rdi; hKey
0x18001060f  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x180010614  mov     r9d, 20019h; samDesired
0x18001061a  xor     r8d, r8d; ulOptions
0x18001061d  call    cs:__imp_RegOpenKeyExW
0x180010623  test    eax, eax
0x180010625  lea     rax, [rsp+290h+cbData]
0x18001062a  jnz     short loc_180010697
0x18001062c  mov     rdi, [rsp+290h+hKey]
0x180010631  lea     r9, [rsp+290h+Type]; lpType
0x180010636  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18001063b  lea     rdx, aDatamigrations; "DataMigrationSupport"
0x180010642  lea     rax, [rsp+290h+Data]
0x180010647  mov     dword ptr [rsp+290h+Data], 0
0x18001064f  mov     rcx, rdi; hKey
0x180010652  mov     [rsp+290h+phkResult], rax; lpData
0x180010657  xor     r8d, r8d; lpReserved
0x18001065a  mov     [rsp+290h+Type], 0
0x180010662  mov     [rsp+290h+cbData], 4
0x18001066a  call    cs:__imp_RegQueryValueExW
0x180010670  test    eax, eax
0x180010672  jnz     loc_18001073A
0x180010678  cmp     [rsp+290h+Type], 4
0x18001067d  jnz     loc_18001073A
0x180010683  lea     ecx, [rax+1]
0x180010686  cmp     dword ptr [rsp+290h+Data], ecx
0x18001068a  jnz     loc_18001073A
0x180010690  mov     bl, cl
0x180010692  jmp     loc_18001073A
0x180010697  mov     [rsp+290h+lpdwDisposition], rax; lpdwDisposition
0x18001069c  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x1800106a1  lea     rax, [rsp+290h+Type]
0x1800106a6  mov     [rsp+290h+cbData], 0
0x1800106ae  mov     [rsp+290h+var_258], rax; phkResult
0x1800106b3  xor     r9d, r9d; lpClass
0x1800106b6  mov     [rsp+290h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800106bf  xor     r8d, r8d; Reserved
0x1800106c2  mov     dword ptr [rsp+290h+lpcbData], 2001Fh; samDesired
0x1800106ca  mov     rcx, rdi; hKey
0x1800106cd  mov     dword ptr [rsp+290h+phkResult], 0; dwOptions
0x1800106d5  mov     qword ptr [rsp+290h+Type], 0
0x1800106de  call    cs:__imp_RegCreateKeyExW
0x1800106e4  test    eax, eax
0x1800106e6  jnz     short loc_180010748
0x1800106e8  mov     rdi, qword ptr [rsp+290h+Type]
0x1800106ed  call    ?IsWindows8Point1OrGreater@@YA_NXZ; IsWindows8Point1OrGreater(void)
0x1800106f2  movzx   eax, al
0x1800106f5  lea     rdx, aDatamigrations; "DataMigrationSupport"
0x1800106fc  mov     dword ptr [rsp+290h+Data], eax
0x180010700  mov     r9d, 4; dwType
0x180010706  lea     rax, [rsp+290h+Data]
0x18001070b  mov     dword ptr [rsp+290h+lpcbData], 4; cbData
0x180010713  xor     r8d, r8d; Reserved
0x180010716  mov     [rsp+290h+phkResult], rax; lpData
0x18001071b  mov     rcx, rdi; hKey
0x18001071e  call    cs:__imp_RegSetValueExW
0x180010724  test    eax, eax
0x180010726  jnz     short loc_18001073A
0x180010728  call    ?IsWindows8Point1OrGreater@@YA_NXZ; IsWindows8Point1OrGreater(void)
0x18001072d  test    al, al
0x18001072f  movzx   ebx, bl
0x180010732  mov     ecx, 1
0x180010737  cmovnz  ebx, ecx
0x18001073a  test    rdi, rdi
0x18001073d  jz      short loc_180010748
0x18001073f  mov     rcx, rdi; hKey
0x180010742  call    cs:__imp_RegCloseKey
0x180010748  mov     al, bl
0x18001074a  mov     rcx, [rbp+190h+var_10]
0x180010751  xor     rcx, rsp; StackCookie
0x180010754  call    __security_check_cookie
0x180010759  lea     r11, [rsp+290h+var_s0]
0x180010761  mov     rbx, [r11+18h]
0x180010765  mov     rdi, [r11+20h]
0x180010769  mov     rsp, r11
0x18001076c  pop     rbp
0x18001076d  retn
```
