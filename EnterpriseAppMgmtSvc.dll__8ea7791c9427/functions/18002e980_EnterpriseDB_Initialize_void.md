# EnterpriseDB::Initialize(void)

- ea: `0x18002e980`
- end: `0x18002eb7b`
- name: `?Initialize@EnterpriseDB@@QEAAJXZ`
- size: `507`
- prototype: `__int64 __fastcall(EnterpriseDB *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027a18`

## callees

- `0x180006858`
- `0x18002e980`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ea28`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ea8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ea28`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ea8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002eb5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002eb5a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e9b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e9b0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002e9fb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ea61`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002eac7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002e9fb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ea61`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002eac7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002eaf4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002eaf4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ea20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ea86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eb16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eb50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ea20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ea86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eb16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eb50`

## string_xrefs

- `0x18002eb2c`: `Registry Init Failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EnterpriseDB::Initialize(EnterpriseDB *this)
{
  struct EnterpriseDB *v1; // rsi
  unsigned int v2; // edi
  LSTATUS v3; // eax
  bool v4; // cc
  HKEY v5; // r14
  DWORD LastError; // ebx
  HKEY v7; // rcx
  HKEY v8; // r14
  DWORD v9; // ebx
  HKEY v10; // rcx
  HKEY v11; // rcx
  HKEY v12; // rcx
  DWORD dwDisposition; // [rsp+80h] [rbp+30h] BYREF
  int v15; // [rsp+84h] [rbp+34h]
  HKEY hKey; // [rsp+88h] [rbp+38h] BYREF

  v15 = HIDWORD(this);
  v1 = EnterpriseConfig::m_pEntDB;
  dwDisposition = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)EnterpriseConfig::m_pEntDB + 24));
  v2 = 0;
  if ( !*(_DWORD *)v1 )
  {
    hKey = 0;
    v3 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\EnterpriseAppManagement\\Database",
           0,
           0,
           0,
           0xF003Fu,
           0,
           &hKey,
           &dwDisposition);
    v4 = v3 <= 0;
    if ( v3 )
      goto LABEL_10;
    v5 = (HKEY)*((_QWORD *)v1 + 1);
    if ( v5 )
    {
      LastError = GetLastError();
      RegCloseKey(v5);
      SetLastError(LastError);
    }
    v7 = hKey;
    *((_QWORD *)v1 + 1) = 0;
    v3 = RegCreateKeyExW(v7, g_TableInfo, 0, 0, 0, 0xF003Fu, 0, (PHKEY)v1 + 1, &dwDisposition);
    v4 = v3 <= 0;
    if ( v3 )
      goto LABEL_10;
    v8 = (HKEY)*((_QWORD *)v1 + 2);
    if ( v8 )
    {
      v9 = GetLastError();
      RegCloseKey(v8);
      SetLastError(v9);
    }
    v10 = hKey;
    *((_QWORD *)v1 + 2) = 0;
    v3 = RegCreateKeyExW(v10, lpSubKey, 0, 0, 0, 0xF003Fu, 0, (PHKEY)v1 + 2, &dwDisposition);
    v4 = v3 <= 0;
    if ( v3 || (v3 = RegSetValueExW(hKey, L"Version", 0, 4u, &Data, 4u), v4 = v3 <= 0, v3) )
    {
LABEL_10:
      if ( v4 )
        v2 = v3;
      else
        v2 = (unsigned __int16)v3 | 0x80070000;
      v11 = hKey;
      if ( hKey )
        RegCloseKey(hKey);
      if ( (v2 & 0x80000000) != 0 && (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 0x100) != 0 )
        McTemplateU0zq_EventWriteTransfer(v11, EnterpriseAppDBError, L"Registry Init Failed", v2);
    }
    else
    {
      v12 = hKey;
      *(_DWORD *)v1 = 1;
      if ( v12 )
        RegCloseKey(v12);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 24));
  return v2;
}

```

## disassembly

```asm
0x18002e980  mov     [rsp-28h+arg_10], rbx
0x18002e985  mov     [rsp-28h+arg_18], rsi
0x18002e98a  mov     qword ptr [rsp-28h+dwDisposition], rcx
0x18002e98f  push    rbp
0x18002e990  push    rdi
0x18002e991  push    r12
0x18002e993  push    r14
0x18002e995  push    r15
0x18002e997  mov     rbp, rsp
0x18002e99a  sub     rsp, 50h
0x18002e99e  mov     rsi, cs:?m_pEntDB@EnterpriseConfig@@0PEAVEnterpriseDB@@EA; EnterpriseDB * EnterpriseConfig::m_pEntDB
0x18002e9a5  mov     [rbp+dwDisposition], 0
0x18002e9ac  lea     rcx, [rsi+18h]; lpCriticalSection
0x18002e9b0  call    cs:__imp_EnterCriticalSection
0x18002e9b6  xor     edi, edi
0x18002e9b8  cmp     [rsi], edi
0x18002e9ba  jnz     loc_18002EB56
0x18002e9c0  lea     rax, [rbp+dwDisposition]
0x18002e9c4  mov     [rbp+hKey], rdi
0x18002e9c8  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x18002e9cd  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\EnterpriseAppManag"...
0x18002e9d4  lea     rax, [rbp+hKey]
0x18002e9d8  xor     r9d, r9d; lpClass
0x18002e9db  mov     [rsp+50h+phkResult], rax; phkResult
0x18002e9e0  xor     r8d, r8d; Reserved
0x18002e9e3  mov     [rsp+50h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18002e9e8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e9ef  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x18002e9f7  mov     [rsp+50h+dwOptions], edi; dwOptions
0x18002e9fb  call    cs:__imp_RegCreateKeyExW
0x18002ea01  test    eax, eax
0x18002ea03  jnz     loc_18002EAFE
0x18002ea09  lea     r15, [rsi+8]
0x18002ea0d  mov     r14, [r15]
0x18002ea10  test    r14, r14
0x18002ea13  jz      short loc_18002EA2E
0x18002ea15  call    cs:__imp_GetLastError
0x18002ea1b  mov     rcx, r14; hKey
0x18002ea1e  mov     ebx, eax
0x18002ea20  call    cs:__imp_RegCloseKey
0x18002ea26  mov     ecx, ebx; dwErrCode
0x18002ea28  call    cs:__imp_SetLastError
0x18002ea2e  mov     rcx, [rbp+hKey]; hKey
0x18002ea32  lea     rax, [rbp+dwDisposition]
0x18002ea36  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x18002ea3b  xor     r9d, r9d; lpClass
0x18002ea3e  mov     [rsp+50h+phkResult], r15; phkResult
0x18002ea43  xor     r8d, r8d; Reserved
0x18002ea46  mov     [rsp+50h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18002ea4b  mov     [r15], rdi
0x18002ea4e  mov     rdx, cs:?g_TableInfo@@3PAUTABLE_INFO@@A; lpSubKey
0x18002ea55  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x18002ea5d  mov     [rsp+50h+dwOptions], edi; dwOptions
0x18002ea61  call    cs:__imp_RegCreateKeyExW
0x18002ea67  test    eax, eax
0x18002ea69  jnz     loc_18002EAFE
0x18002ea6f  lea     r15, [rsi+10h]
0x18002ea73  mov     r14, [r15]
0x18002ea76  test    r14, r14
0x18002ea79  jz      short loc_18002EA94
0x18002ea7b  call    cs:__imp_GetLastError
0x18002ea81  mov     rcx, r14; hKey
0x18002ea84  mov     ebx, eax
0x18002ea86  call    cs:__imp_RegCloseKey
0x18002ea8c  mov     ecx, ebx; dwErrCode
0x18002ea8e  call    cs:__imp_SetLastError
0x18002ea94  mov     rcx, [rbp+hKey]; hKey
0x18002ea98  lea     rax, [rbp+dwDisposition]
0x18002ea9c  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x18002eaa1  xor     r9d, r9d; lpClass
0x18002eaa4  mov     [rsp+50h+phkResult], r15; phkResult
0x18002eaa9  xor     r8d, r8d; Reserved
0x18002eaac  mov     [rsp+50h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18002eab1  mov     [r15], rdi
0x18002eab4  mov     rdx, cs:lpSubKey; lpSubKey
0x18002eabb  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x18002eac3  mov     [rsp+50h+dwOptions], edi; dwOptions
0x18002eac7  call    cs:__imp_RegCreateKeyExW
0x18002eacd  test    eax, eax
0x18002eacf  jnz     short loc_18002EAFE
0x18002ead1  mov     rcx, [rbp+hKey]; hKey
0x18002ead5  lea     r9d, [rax+4]; dwType
0x18002ead9  lea     rax, Data
0x18002eae0  mov     [rsp+50h+samDesired], r9d; cbData
0x18002eae5  xor     r8d, r8d; Reserved
0x18002eae8  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x18002eaed  lea     rdx, aVersion; "Version"
0x18002eaf4  call    cs:__imp_RegSetValueExW
0x18002eafa  test    eax, eax
0x18002eafc  jz      short loc_18002EB41
0x18002eafe  jg      short loc_18002EB04
0x18002eb00  mov     edi, eax
0x18002eb02  jmp     short loc_18002EB0D
0x18002eb04  movzx   edi, ax
0x18002eb07  or      edi, 80070000h
0x18002eb0d  mov     rcx, [rbp+hKey]; hKey
0x18002eb11  test    rcx, rcx
0x18002eb14  jz      short loc_18002EB1C
0x18002eb16  call    cs:__imp_RegCloseKey
0x18002eb1c  test    edi, edi
0x18002eb1e  jns     short loc_18002EB56
0x18002eb20  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits+1, 1
0x18002eb27  jz      short loc_18002EB56
0x18002eb29  mov     r9d, edi
0x18002eb2c  lea     r8, aRegistryInitFa; "Registry Init Failed"
0x18002eb33  lea     rdx, EnterpriseAppDBError
0x18002eb3a  call    McTemplateU0zq_EventWriteTransfer
0x18002eb3f  jmp     short loc_18002EB56
0x18002eb41  mov     rcx, [rbp+hKey]; hKey
0x18002eb45  mov     dword ptr [rsi], 1
0x18002eb4b  test    rcx, rcx
0x18002eb4e  jz      short loc_18002EB56
0x18002eb50  call    cs:__imp_RegCloseKey
0x18002eb56  lea     rcx, [rsi+18h]; lpCriticalSection
0x18002eb5a  call    cs:__imp_LeaveCriticalSection
0x18002eb60  lea     r11, [rsp+50h+var_s0]
0x18002eb65  mov     eax, edi
0x18002eb67  mov     rbx, [r11+40h]
0x18002eb6b  mov     rsi, [r11+48h]
0x18002eb6f  mov     rsp, r11
0x18002eb72  pop     r15
0x18002eb74  pop     r14
0x18002eb76  pop     r12
0x18002eb78  pop     rdi
0x18002eb79  pop     rbp
0x18002eb7a  retn
```
