# Broker::SebBroker::UpdateEventPolicyTable(Broker::_EventPolicy *)

- ea: `0x18001f6ec`
- end: `0x18001f86a`
- name: `?UpdateEventPolicyTable@SebBroker@Broker@@AEAAXPEAU_EventPolicy@2@@Z`
- size: `382`
- prototype: `void __fastcall(Broker::SebBroker *__hidden this, struct Broker::_EventPolicy *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001c228`

## callees

- `0x18001f6ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f7a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f7e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f821`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f7a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f7e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f821`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f73b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f76f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f73b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f76f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f83a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f85a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f83a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f85a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
void __fastcall Broker::SebBroker::UpdateEventPolicyTable(Broker::SebBroker *this, struct Broker::_EventPolicy *a2)
{
  const WCHAR *v2; // rdx
  __int64 v3; // rdi
  __int64 v4; // rbx
  int Data; // [rsp+60h] [rbp+28h] BYREF
  struct Broker::_EventPolicy *cbData; // [rsp+68h] [rbp+30h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+40h] BYREF

  cbData = a2;
  v2 = (const WCHAR *)*((_QWORD *)this + 16);
  hKey = 0;
  phkResult = 0;
  Data = 0;
  LODWORD(cbData) = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 1u, &hKey) )
  {
    v3 = 0;
    v4 = 0;
    do
    {
      if ( !RegOpenKeyExW(hKey, *(LPCWSTR *)((char *)&Broker::EventPolicyTable + v4 + 40), 0, 1u, &phkResult) )
      {
        LODWORD(cbData) = 4;
        if ( !RegQueryValueExW(phkResult, L"QuotaLimit", 0, 0, (LPBYTE)&Data, (LPDWORD)&cbData) )
          *(_DWORD *)((char *)&Broker::EventPolicyTable + v4) = Data;
        LODWORD(cbData) = 4;
        if ( !RegQueryValueExW(phkResult, L"RequiresData", 0, 0, (LPBYTE)&Data, (LPDWORD)&cbData) )
          *(_DWORD *)((char *)&Broker::EventPolicyTable + v4 + 4) = Data != 0;
        LODWORD(cbData) = 4;
        if ( !RegQueryValueExW(phkResult, L"Critical", 0, 0, (LPBYTE)&Data, (LPDWORD)&cbData) )
          *(_DWORD *)((char *)&Broker::EventPolicyTable + v4 + 16) = Data != 0;
        RegCloseKey(phkResult);
      }
      ++v3;
      v4 += 48;
    }
    while ( v3 != 76 );
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18001f6ec  mov     [rsp-20h+cbData], rdx
0x18001f6f1  push    rbp
0x18001f6f2  push    rbx
0x18001f6f3  push    rdi
0x18001f6f4  push    r14
0x18001f6f6  mov     rbp, rsp
0x18001f6f9  sub     rsp, 38h
0x18001f6fd  mov     rdx, [rcx+80h]; lpSubKey
0x18001f704  lea     rax, [rbp+hKey]
0x18001f708  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f70f  mov     [rsp+38h+phkResult], rax; phkResult
0x18001f714  mov     r9d, 1; samDesired
0x18001f71a  mov     [rbp+hKey], 0
0x18001f722  xor     r8d, r8d; ulOptions
0x18001f725  mov     [rbp+arg_10], 0
0x18001f72d  mov     [rbp+Data], 0
0x18001f734  mov     dword ptr [rbp+cbData], 0
0x18001f73b  call    cs:__imp_RegOpenKeyExW
0x18001f741  test    eax, eax
0x18001f743  jnz     loc_18001F851
0x18001f749  xor     edi, edi
0x18001f74b  lea     r14, ?EventPolicyTable@Broker@@3PAU_EventPolicy@1@A; Broker::_EventPolicy near * Broker::EventPolicyTable
0x18001f752  xor     ebx, ebx
0x18001f754  mov     rdx, [rbx+r14+28h]; lpSubKey
0x18001f759  lea     rax, [rbp+arg_10]
0x18001f75d  mov     rcx, [rbp+hKey]; hKey
0x18001f761  mov     r9d, 1; samDesired
0x18001f767  xor     r8d, r8d; ulOptions
0x18001f76a  mov     [rsp+38h+phkResult], rax; phkResult
0x18001f76f  call    cs:__imp_RegOpenKeyExW
0x18001f775  test    eax, eax
0x18001f777  jnz     loc_18001F840
0x18001f77d  mov     rcx, [rbp+arg_10]; hKey
0x18001f781  lea     rax, [rbp+cbData]
0x18001f785  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18001f78a  lea     rdx, aQuotalimit; "QuotaLimit"
0x18001f791  lea     rax, [rbp+Data]
0x18001f795  mov     dword ptr [rbp+cbData], 4
0x18001f79c  xor     r9d, r9d; lpType
0x18001f79f  mov     [rsp+38h+phkResult], rax; lpData
0x18001f7a4  xor     r8d, r8d; lpReserved
0x18001f7a7  call    cs:__imp_RegQueryValueExW
0x18001f7ad  test    eax, eax
0x18001f7af  jnz     short loc_18001F7B8
0x18001f7b1  mov     eax, [rbp+Data]
0x18001f7b4  mov     [rbx+r14], eax
0x18001f7b8  mov     rcx, [rbp+arg_10]; hKey
0x18001f7bc  lea     rax, [rbp+cbData]
0x18001f7c0  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18001f7c5  lea     rdx, aRequiresdata; "RequiresData"
0x18001f7cc  lea     rax, [rbp+Data]
0x18001f7d0  mov     dword ptr [rbp+cbData], 4
0x18001f7d7  xor     r9d, r9d; lpType
0x18001f7da  mov     [rsp+38h+phkResult], rax; lpData
0x18001f7df  xor     r8d, r8d; lpReserved
0x18001f7e2  call    cs:__imp_RegQueryValueExW
0x18001f7e8  test    eax, eax
0x18001f7ea  jnz     short loc_18001F7F7
0x18001f7ec  cmp     [rbp+Data], eax
0x18001f7ef  setnz   al
0x18001f7f2  mov     [rbx+r14+4], eax
0x18001f7f7  mov     rcx, [rbp+arg_10]; hKey
0x18001f7fb  lea     rax, [rbp+cbData]
0x18001f7ff  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18001f804  lea     rdx, aCritical; "Critical"
0x18001f80b  lea     rax, [rbp+Data]
0x18001f80f  mov     dword ptr [rbp+cbData], 4
0x18001f816  xor     r9d, r9d; lpType
0x18001f819  mov     [rsp+38h+phkResult], rax; lpData
0x18001f81e  xor     r8d, r8d; lpReserved
0x18001f821  call    cs:__imp_RegQueryValueExW
0x18001f827  test    eax, eax
0x18001f829  jnz     short loc_18001F836
0x18001f82b  cmp     [rbp+Data], eax
0x18001f82e  setnz   al
0x18001f831  mov     [rbx+r14+10h], eax
0x18001f836  mov     rcx, [rbp+arg_10]; hKey
0x18001f83a  call    cs:__imp_RegCloseKey
0x18001f840  inc     rdi
0x18001f843  add     rbx, 30h ; '0'
0x18001f847  cmp     rdi, 4Ch ; 'L'
0x18001f84b  jnz     loc_18001F754
0x18001f851  mov     rcx, [rbp+hKey]; hKey
0x18001f855  test    rcx, rcx
0x18001f858  jz      short loc_18001F860
0x18001f85a  call    cs:__imp_RegCloseKey
0x18001f860  add     rsp, 38h
0x18001f864  pop     r14
0x18001f866  pop     rdi
0x18001f867  pop     rbx
0x18001f868  pop     rbp
0x18001f869  retn
```
