# EnterpriseDB::Initialize(void)

- ea: `0x1800312e4`
- end: `0x180031534`
- name: `?Initialize@EnterpriseDB@@QEAAJXZ`
- size: `592`
- prototype: `__int64 __fastcall(EnterpriseDB *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029b94`

## callees

- `0x180006ac0`
- `0x1800312e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031385`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031403`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031385`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031403`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800313a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031422`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800313a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031422`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003150c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003150c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031314`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031314`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031365`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800313e3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031461`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031365`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800313e3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031461`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031494`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031494`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031396`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031414`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800314bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800314fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031396`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031414`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800314bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800314fc`

## string_xrefs

- `0x1800314d8`: `Registry Init Failed`

## pseudocode

```c
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
0x1800312e4  mov     [rsp-28h+arg_10], rbx
0x1800312e9  mov     [rsp-28h+arg_18], rsi
0x1800312ee  mov     qword ptr [rsp-28h+dwDisposition], rcx
0x1800312f3  push    rbp
0x1800312f4  push    rdi
0x1800312f5  push    r12
0x1800312f7  push    r14
0x1800312f9  push    r15
0x1800312fb  mov     rbp, rsp
0x1800312fe  sub     rsp, 50h
0x180031302  mov     rsi, cs:?m_pEntDB@EnterpriseConfig@@0PEAVEnterpriseDB@@EA; EnterpriseDB * EnterpriseConfig::m_pEntDB
0x180031309  mov     [rbp+dwDisposition], 0
0x180031310  lea     rcx, [rsi+18h]; lpCriticalSection
0x180031314  call    cs:__imp_EnterCriticalSection
0x18003131b  nop     dword ptr [rax+rax+00h]
0x180031320  xor     edi, edi
0x180031322  cmp     [rsi], edi
0x180031324  jnz     loc_180031508
0x18003132a  lea     rax, [rbp+dwDisposition]
0x18003132e  mov     [rbp+hKey], rdi
0x180031332  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x180031337  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\EnterpriseAppManag"...
0x18003133e  lea     rax, [rbp+hKey]
0x180031342  xor     r9d, r9d; lpClass
0x180031345  mov     [rsp+50h+phkResult], rax; phkResult
0x18003134a  xor     r8d, r8d; Reserved
0x18003134d  mov     [rsp+50h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180031352  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031359  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x180031361  mov     [rsp+50h+dwOptions], edi; dwOptions
0x180031365  call    cs:__imp_RegCreateKeyExW
0x18003136c  nop     dword ptr [rax+rax+00h]
0x180031371  test    eax, eax
0x180031373  jnz     loc_1800314A4
0x180031379  lea     r15, [rsi+8]
0x18003137d  mov     r14, [r15]
0x180031380  test    r14, r14
0x180031383  jz      short loc_1800313B0
0x180031385  call    cs:__imp_GetLastError
0x18003138c  nop     dword ptr [rax+rax+00h]
0x180031391  mov     rcx, r14; hKey
0x180031394  mov     ebx, eax
0x180031396  call    cs:__imp_RegCloseKey
0x18003139d  nop     dword ptr [rax+rax+00h]
0x1800313a2  mov     ecx, ebx; dwErrCode
0x1800313a4  call    cs:__imp_SetLastError
0x1800313ab  nop     dword ptr [rax+rax+00h]
0x1800313b0  mov     rcx, [rbp+hKey]; hKey
0x1800313b4  lea     rax, [rbp+dwDisposition]
0x1800313b8  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x1800313bd  xor     r9d, r9d; lpClass
0x1800313c0  mov     [rsp+50h+phkResult], r15; phkResult
0x1800313c5  xor     r8d, r8d; Reserved
0x1800313c8  mov     [rsp+50h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800313cd  mov     [r15], rdi
0x1800313d0  mov     rdx, cs:?g_TableInfo@@3PAUTABLE_INFO@@A; lpSubKey
0x1800313d7  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x1800313df  mov     [rsp+50h+dwOptions], edi; dwOptions
0x1800313e3  call    cs:__imp_RegCreateKeyExW
0x1800313ea  nop     dword ptr [rax+rax+00h]
0x1800313ef  test    eax, eax
0x1800313f1  jnz     loc_1800314A4
0x1800313f7  lea     r15, [rsi+10h]
0x1800313fb  mov     r14, [r15]
0x1800313fe  test    r14, r14
0x180031401  jz      short loc_18003142E
0x180031403  call    cs:__imp_GetLastError
0x18003140a  nop     dword ptr [rax+rax+00h]
0x18003140f  mov     rcx, r14; hKey
0x180031412  mov     ebx, eax
0x180031414  call    cs:__imp_RegCloseKey
0x18003141b  nop     dword ptr [rax+rax+00h]
0x180031420  mov     ecx, ebx; dwErrCode
0x180031422  call    cs:__imp_SetLastError
0x180031429  nop     dword ptr [rax+rax+00h]
0x18003142e  mov     rcx, [rbp+hKey]; hKey
0x180031432  lea     rax, [rbp+dwDisposition]
0x180031436  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x18003143b  xor     r9d, r9d; lpClass
0x18003143e  mov     [rsp+50h+phkResult], r15; phkResult
0x180031443  xor     r8d, r8d; Reserved
0x180031446  mov     [rsp+50h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18003144b  mov     [r15], rdi
0x18003144e  mov     rdx, cs:lpSubKey; lpSubKey
0x180031455  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x18003145d  mov     [rsp+50h+dwOptions], edi; dwOptions
0x180031461  call    cs:__imp_RegCreateKeyExW
0x180031468  nop     dword ptr [rax+rax+00h]
0x18003146d  test    eax, eax
0x18003146f  jnz     short loc_1800314A4
0x180031471  mov     rcx, [rbp+hKey]; hKey
0x180031475  lea     r9d, [rax+4]; dwType
0x180031479  lea     rax, Data
0x180031480  mov     [rsp+50h+samDesired], r9d; cbData
0x180031485  xor     r8d, r8d; Reserved
0x180031488  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x18003148d  lea     rdx, aVersion; "Version"
0x180031494  call    cs:__imp_RegSetValueExW
0x18003149b  nop     dword ptr [rax+rax+00h]
0x1800314a0  test    eax, eax
0x1800314a2  jz      short loc_1800314ED
0x1800314a4  jg      short loc_1800314AA
0x1800314a6  mov     edi, eax
0x1800314a8  jmp     short loc_1800314B3
0x1800314aa  movzx   edi, ax
0x1800314ad  or      edi, 80070000h
0x1800314b3  mov     rcx, [rbp+hKey]; hKey
0x1800314b7  test    rcx, rcx
0x1800314ba  jz      short loc_1800314C8
0x1800314bc  call    cs:__imp_RegCloseKey
0x1800314c3  nop     dword ptr [rax+rax+00h]
0x1800314c8  test    edi, edi
0x1800314ca  jns     short loc_180031508
0x1800314cc  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits+1, 1
0x1800314d3  jz      short loc_180031508
0x1800314d5  mov     r9d, edi
0x1800314d8  lea     r8, aRegistryInitFa; "Registry Init Failed"
0x1800314df  lea     rdx, EnterpriseAppDBError
0x1800314e6  call    McTemplateU0zq_EventWriteTransfer
0x1800314eb  jmp     short loc_180031508
0x1800314ed  mov     rcx, [rbp+hKey]; hKey
0x1800314f1  mov     dword ptr [rsi], 1
0x1800314f7  test    rcx, rcx
0x1800314fa  jz      short loc_180031508
0x1800314fc  call    cs:__imp_RegCloseKey
0x180031503  nop     dword ptr [rax+rax+00h]
0x180031508  lea     rcx, [rsi+18h]; lpCriticalSection
0x18003150c  call    cs:__imp_LeaveCriticalSection
0x180031513  nop     dword ptr [rax+rax+00h]
0x180031518  lea     r11, [rsp+50h+var_s0]
0x18003151d  mov     eax, edi
0x18003151f  mov     rbx, [r11+40h]
0x180031523  mov     rsi, [r11+48h]
0x180031527  mov     rsp, r11
0x18003152a  pop     r15
0x18003152c  pop     r14
0x18003152e  pop     r12
0x180031530  pop     rdi
0x180031531  pop     rbp
0x180031532  retn
```
