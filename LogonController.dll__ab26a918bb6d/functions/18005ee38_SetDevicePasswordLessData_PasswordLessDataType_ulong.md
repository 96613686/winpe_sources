# SetDevicePasswordLessData(PasswordLessDataType,ulong)

- ea: `0x18005ee38`
- end: `0x18005ef7d`
- name: `?SetDevicePasswordLessData@@YAJW4PasswordLessDataType@@K@Z`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005eab4`

## callees

- `0x18000ba40`
- `0x18000baa4`
- `0x18005d5a0`
- `0x18005ee38`
- `0x18005f3bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ee78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005eefc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ef52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ef64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ee78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005eefc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ef52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ef64`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005ef25`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005ef25`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005eecf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005eecf`

## string_xrefs

- `0x18005eee0`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x18005ef36`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 SetDevicePasswordLessData()
{
  const WCHAR *StringName; // rdi
  HKEY v1; // rbx
  unsigned int v2; // eax
  unsigned int v3; // ebx
  unsigned int v5; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-40h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-40h]
  BYTE Data[16]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  HKEY hKey; // [rsp+80h] [rbp+20h] BYREF
  char v11; // [rsp+88h] [rbp+28h] BYREF

  *(_DWORD *)Data = 2;
  hKey = 0;
  StringName = (const WCHAR *)GetStringName(0);
  v1 = hKey;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
    RegCloseKey(v1);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
  }
  hKey = 0;
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\PasswordLess\\Device",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         0);
  if ( v2 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x170,
           (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
           (const char *)v2,
           dwOptions);
    if ( hKey )
      RegCloseKey(hKey);
    return v3;
  }
  v5 = RegSetValueExW(hKey, StringName, 0, 4u, Data, 4u);
  if ( v5 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x178,
           (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
           (const char *)v5,
           dwOptionsa);
    if ( hKey )
      RegCloseKey(hKey);
    return v3;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18005ee38  mov     [rsp-8+arg_0], rbx
0x18005ee3d  mov     [rsp-8+arg_8], rdi
0x18005ee42  push    rbp
0x18005ee43  mov     rbp, rsp
0x18005ee46  sub     rsp, 60h
0x18005ee4a  mov     dword ptr [rbp+Data], 2
0x18005ee51  mov     [rbp+hKey], 0
0x18005ee59  xor     ecx, ecx
0x18005ee5b  call    ?GetStringName@@YAPEBGW4PasswordLessDataType@@@Z; GetStringName(PasswordLessDataType)
0x18005ee60  mov     rdi, rax
0x18005ee63  mov     rbx, [rbp+hKey]
0x18005ee67  test    rbx, rbx
0x18005ee6a  jz      short loc_18005EE88
0x18005ee6c  lea     rcx, [rbp+arg_18]; this
0x18005ee70  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005ee75  mov     rcx, rbx; hKey
0x18005ee78  call    cs:__imp_RegCloseKey
0x18005ee7e  lea     rcx, [rbp+arg_18]; this
0x18005ee82  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005ee87  nop
0x18005ee88  mov     [rbp+hKey], 0
0x18005ee90  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x18005ee99  lea     rax, [rbp+hKey]
0x18005ee9d  mov     [rsp+60h+phkResult], rax; phkResult
0x18005eea2  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18005eeab  mov     [rsp+60h+samDesired], 20006h; samDesired
0x18005eeb3  mov     [rsp+60h+dwOptions], 0; unsigned int
0x18005eebb  xor     r9d, r9d; lpClass
0x18005eebe  xor     r8d, r8d; Reserved
0x18005eec1  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18005eec8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005eecf  call    cs:__imp_RegCreateKeyExW
0x18005eed5  test    eax, eax
0x18005eed7  jz      short loc_18005EF07
0x18005eed9  mov     rcx, [rbp+8]; this
0x18005eedd  mov     r9d, eax; char *
0x18005eee0  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x18005eee7  mov     edx, 170h; void *
0x18005eeec  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005eef1  mov     ebx, eax
0x18005eef3  mov     rcx, [rbp+hKey]; hKey
0x18005eef7  test    rcx, rcx
0x18005eefa  jz      short loc_18005EF03
0x18005eefc  call    cs:__imp_RegCloseKey
0x18005ef02  nop
0x18005ef03  mov     eax, ebx
0x18005ef05  jmp     short loc_18005EF6D
0x18005ef07  mov     r9d, 4; dwType
0x18005ef0d  mov     [rsp+60h+samDesired], r9d; cbData
0x18005ef12  lea     rax, [rbp+Data]
0x18005ef16  mov     qword ptr [rsp+60h+dwOptions], rax; unsigned int
0x18005ef1b  xor     r8d, r8d; Reserved
0x18005ef1e  mov     rdx, rdi; lpValueName
0x18005ef21  mov     rcx, [rbp+hKey]; hKey
0x18005ef25  call    cs:__imp_RegSetValueExW
0x18005ef2b  test    eax, eax
0x18005ef2d  jz      short loc_18005EF5B
0x18005ef2f  mov     rcx, [rbp+8]; this
0x18005ef33  mov     r9d, eax; char *
0x18005ef36  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x18005ef3d  mov     edx, 178h; void *
0x18005ef42  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005ef47  mov     ebx, eax
0x18005ef49  mov     rcx, [rbp+hKey]; hKey
0x18005ef4d  test    rcx, rcx
0x18005ef50  jz      short loc_18005EF59
0x18005ef52  call    cs:__imp_RegCloseKey
0x18005ef58  nop
0x18005ef59  jmp     short loc_18005EF03
0x18005ef5b  mov     rcx, [rbp+hKey]; hKey
0x18005ef5f  test    rcx, rcx
0x18005ef62  jz      short loc_18005EF6B
0x18005ef64  call    cs:__imp_RegCloseKey
0x18005ef6a  nop
0x18005ef6b  xor     eax, eax
0x18005ef6d  mov     rbx, [rsp+60h+arg_0]
0x18005ef72  mov     rdi, [rsp+60h+arg_8]
0x18005ef77  add     rsp, 60h
0x18005ef7b  pop     rbp
0x18005ef7c  retn
```
