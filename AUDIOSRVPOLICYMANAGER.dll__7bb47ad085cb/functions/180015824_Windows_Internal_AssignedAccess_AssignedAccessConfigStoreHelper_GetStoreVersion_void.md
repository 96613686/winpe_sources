# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::GetStoreVersion(void)

- ea: `0x180015824`
- end: `0x180015909`
- name: `?GetStoreVersion@AssignedAccessConfigStoreHelper@AssignedAccess@Internal@Windows@@AEAAKXZ`
- size: `229`
- prototype: `unsigned int __fastcall(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180015580`

## callees

- `0x180015824`
- `0x180025db0`
- `0x1800272f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800158c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800158c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015883`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015883`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001584f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800158e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800158f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001584f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800158e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800158f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::GetStoreVersion(LPCWSTR *this)
{
  unsigned int v1; // ebx
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF
  unsigned int Data; // [rsp+68h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, *this, 0, 0x20019u, &hKey)
    || (Type = 0, Data = 0, cbData = 4, RegQueryValueExW(hKey, L"Version", 0, &Type, (LPBYTE)&Data, &cbData))
    || Type != 4 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  else
  {
    v1 = Data;
    if ( hKey )
      RegCloseKey(hKey);
    return v1;
  }
}

```

## disassembly

```asm
0x180015824  push    rbp
0x180015826  push    rbx
0x180015827  push    rdi
0x180015828  mov     rbp, rsp
0x18001582b  sub     rsp, 40h
0x18001582f  mov     rdi, rcx
0x180015832  mov     [rbp+hKey], 0
0x18001583a  mov     rbx, [rbp+hKey]
0x18001583e  test    rbx, rbx
0x180015841  jz      short loc_18001585F
0x180015843  lea     rcx, [rbp+var_10]; this
0x180015847  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001584c  mov     rcx, rbx; hKey
0x18001584f  call    cs:__imp_RegCloseKey
0x180015855  lea     rcx, [rbp+var_10]; this
0x180015859  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001585e  nop
0x18001585f  mov     [rbp+hKey], 0
0x180015867  lea     rax, [rbp+hKey]
0x18001586b  mov     [rsp+40h+phkResult], rax; phkResult
0x180015870  mov     r9d, 20019h; samDesired
0x180015876  xor     r8d, r8d; ulOptions
0x180015879  mov     rdx, [rdi]; lpSubKey
0x18001587c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015883  call    cs:__imp_RegOpenKeyExW
0x180015889  test    eax, eax
0x18001588b  jz      short loc_18001588F
0x18001588d  jmp     short loc_1800158EF
0x18001588f  mov     [rbp+Type], 0
0x180015896  mov     [rbp+Data], 0
0x18001589d  mov     [rbp+cbData], 4
0x1800158a4  lea     rax, [rbp+cbData]
0x1800158a8  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800158ad  lea     rax, [rbp+Data]
0x1800158b1  mov     [rsp+40h+phkResult], rax; lpData
0x1800158b6  lea     r9, [rbp+Type]; lpType
0x1800158ba  xor     r8d, r8d; lpReserved
0x1800158bd  lea     rdx, aVersion; "Version"
0x1800158c4  mov     rcx, [rbp+hKey]; hKey
0x1800158c8  call    cs:__imp_RegQueryValueExW
0x1800158ce  test    eax, eax
0x1800158d0  jnz     short loc_1800158EF
0x1800158d2  cmp     [rbp+Type], 4
0x1800158d6  jnz     short loc_1800158EF
0x1800158d8  mov     ebx, [rbp+Data]
0x1800158db  mov     rcx, [rbp+hKey]; hKey
0x1800158df  test    rcx, rcx
0x1800158e2  jz      short loc_1800158EB
0x1800158e4  call    cs:__imp_RegCloseKey
0x1800158ea  nop
0x1800158eb  mov     eax, ebx
0x1800158ed  jmp     short loc_180015901
0x1800158ef  mov     rcx, [rbp+hKey]; hKey
0x1800158f3  test    rcx, rcx
0x1800158f6  jz      short loc_1800158FF
0x1800158f8  call    cs:__imp_RegCloseKey
0x1800158fe  nop
0x1800158ff  xor     eax, eax
0x180015901  add     rsp, 40h
0x180015905  pop     rdi
0x180015906  pop     rbx
0x180015907  pop     rbp
0x180015908  retn
```
