# CRAGroupPolicy::SetSDToRegistry(ushort *,ushort *,_SECURITY_DESCRIPTOR *)

- ea: `0x1400111c8`
- end: `0x14001138b`
- name: `?SetSDToRegistry@CRAGroupPolicy@@AEAAKPEAG0PEAU_SECURITY_DESCRIPTOR@@@Z`
- size: `451`
- prototype: `__int64 __fastcall(CRAGroupPolicy *this, unsigned __int16 *, unsigned __int16 *, struct _SECURITY_DESCRIPTOR *)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140010178`
- `0x140010594`
- `0x140010868`
- `0x140010dc4`

## callees

- `0x1400111c8`
- `0x140015240`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x14001131a`
- `ADVAPI32!RegSetValueExW` at `0x14001131a`
- `ADVAPI32!RegCreateKeyExW` at `0x1400112ea`
- `ADVAPI32!RegCreateKeyExW` at `0x1400112ea`
- `ADVAPI32!RegCloseKey` at `0x140011355`
- `ADVAPI32!RegCloseKey` at `0x140011355`
- `ADVAPI32!MakeSelfRelativeSD` at `0x140011204`
- `ADVAPI32!MakeSelfRelativeSD` at `0x140011271`
- `ADVAPI32!MakeSelfRelativeSD` at `0x140011204`
- `ADVAPI32!MakeSelfRelativeSD` at `0x140011271`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x140011291`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x140011291`
- `KERNEL32!GetLastError` at `0x14001120e`
- `KERNEL32!GetLastError` at `0x14001121b`
- `KERNEL32!GetLastError` at `0x14001127b`
- `KERNEL32!GetLastError` at `0x14001120e`
- `KERNEL32!GetLastError` at `0x14001121b`
- `KERNEL32!GetLastError` at `0x14001127b`
- `KERNEL32!HeapAlloc` at `0x140011243`
- `KERNEL32!HeapAlloc` at `0x140011243`
- `KERNEL32!GetProcessHeap` at `0x140011235`
- `KERNEL32!GetProcessHeap` at `0x140011368`
- `KERNEL32!GetProcessHeap` at `0x140011235`
- `KERNEL32!GetProcessHeap` at `0x140011368`
- `KERNEL32!HeapFree` at `0x140011376`
- `KERNEL32!HeapFree` at `0x140011376`

## string_xrefs

- `0x14001133b`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x140011334`: `CRAGroupPolicy::SetSDToRegistry`

## pseudocode

```c
__int64 __fastcall CRAGroupPolicy::SetSDToRegistry(
        CRAGroupPolicy *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct _SECURITY_DESCRIPTOR *a4)
{
  BYTE *v7; // rdi
  DWORD LastError; // ebx
  const struct _EVENT_DESCRIPTOR *v9; // rdx
  DWORD v10; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *v12; // rax
  const struct _EVENT_DESCRIPTOR *v13; // rdx
  const struct _EVENT_DESCRIPTOR *v14; // rdx
  unsigned int v15; // r9d
  HANDLE v16; // rax
  DWORD dwDisposition; // [rsp+50h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-10h] BYREF
  DWORD dwBufferLength; // [rsp+A0h] [rbp+38h] BYREF
  int v21; // [rsp+A4h] [rbp+3Ch]

  v21 = HIDWORD(this);
  dwBufferLength = 0;
  dwDisposition = 0;
  hKey = 0;
  if ( !MakeSelfRelativeSD(a4, 0, &dwBufferLength) && GetLastError() != 122 )
  {
    v7 = 0;
    LastError = GetLastError();
    CEventLogger::LogError(
      (CEventLogger *)L"CRAGroupPolicy::SetSDToRegistry",
      v9,
      L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
      0x12Eu,
      L"CRAGroupPolicy::SetSDToRegistry",
      0);
    goto LABEL_15;
  }
  v10 = dwBufferLength;
  ProcessHeap = GetProcessHeap();
  v12 = (BYTE *)HeapAlloc(ProcessHeap, 0, v10);
  v7 = v12;
  if ( !v12 )
  {
    LastError = 8;
    CEventLogger::LogError(
      (CEventLogger *)L"CRAGroupPolicy::SetSDToRegistry",
      v13,
      L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
      0x138u,
      L"CRAGroupPolicy::SetSDToRegistry",
      0x8007000E);
    goto LABEL_15;
  }
  if ( MakeSelfRelativeSD(a4, v12, &dwBufferLength) )
  {
    if ( IsValidSecurityDescriptor(a4) )
    {
      LastError = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, (LPWSTR)&Class, 0, 2u, 0, &hKey, &dwDisposition);
      if ( LastError )
      {
        v15 = 344;
      }
      else
      {
        LastError = RegSetValueExW(hKey, a3, 0, 3u, v7, dwBufferLength);
        if ( !LastError )
          goto LABEL_15;
        v15 = 359;
      }
    }
    else
    {
      LastError = 1338;
      v15 = 328;
    }
  }
  else
  {
    LastError = GetLastError();
    v15 = 322;
  }
  CEventLogger::LogError(
    (CEventLogger *)L"CRAGroupPolicy::SetSDToRegistry",
    v14,
    L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
    v15,
    L"CRAGroupPolicy::SetSDToRegistry",
    0);
LABEL_15:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v7 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v7);
  }
  return LastError;
}

```

## disassembly

```asm
0x1400111c8  mov     qword ptr [rsp-30h+dwBufferLength], rcx
0x1400111cd  push    rbp
0x1400111ce  push    rbx
0x1400111cf  push    rsi
0x1400111d0  push    rdi
0x1400111d1  push    r14
0x1400111d3  push    r15
0x1400111d5  mov     rbp, rsp
0x1400111d8  sub     rsp, 68h
0x1400111dc  mov     r14, r8
0x1400111df  mov     [rbp+dwBufferLength], 0
0x1400111e6  mov     r15, rdx
0x1400111e9  mov     [rbp+dwDisposition], 0
0x1400111f0  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x1400111f4  mov     [rbp+hKey], 0
0x1400111fc  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x1400111fe  mov     rcx, r9; pAbsoluteSecurityDescriptor
0x140011201  mov     rsi, r9
0x140011204  call    cs:__imp_MakeSelfRelativeSD
0x14001120a  test    eax, eax
0x14001120c  jnz     short loc_140011232
0x14001120e  call    cs:__imp_GetLastError
0x140011214  cmp     eax, 7Ah ; 'z'
0x140011217  jz      short loc_140011232
0x140011219  xor     edi, edi
0x14001121b  call    cs:__imp_GetLastError
0x140011221  mov     [rsp+68h+samDesired], edi
0x140011225  mov     r9d, 12Eh
0x14001122b  mov     ebx, eax
0x14001122d  jmp     loc_140011334
0x140011232  mov     ebx, [rbp+dwBufferLength]
0x140011235  call    cs:__imp_GetProcessHeap
0x14001123b  mov     r8d, ebx; dwBytes
0x14001123e  xor     edx, edx; dwFlags
0x140011240  mov     rcx, rax; hHeap
0x140011243  call    cs:__imp_HeapAlloc
0x140011249  mov     rdi, rax
0x14001124c  test    rax, rax
0x14001124f  jnz     short loc_140011267
0x140011251  lea     ebx, [rax+8]
0x140011254  mov     [rsp+68h+samDesired], 8007000Eh
0x14001125c  mov     r9d, 138h
0x140011262  jmp     loc_140011334
0x140011267  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x14001126b  mov     rdx, rdi; pSelfRelativeSecurityDescriptor
0x14001126e  mov     rcx, rsi; pAbsoluteSecurityDescriptor
0x140011271  call    cs:__imp_MakeSelfRelativeSD
0x140011277  test    eax, eax
0x140011279  jnz     short loc_14001128E
0x14001127b  call    cs:__imp_GetLastError
0x140011281  mov     ebx, eax
0x140011283  mov     r9d, 142h
0x140011289  jmp     loc_14001132C
0x14001128e  mov     rcx, rsi; pSecurityDescriptor
0x140011291  call    cs:__imp_IsValidSecurityDescriptor
0x140011297  test    eax, eax
0x140011299  jnz     short loc_1400112AB
0x14001129b  mov     ebx, 53Ah
0x1400112a0  mov     r9d, 148h
0x1400112a6  jmp     loc_14001132C
0x1400112ab  lea     rax, [rbp+dwDisposition]
0x1400112af  xor     r8d, r8d; Reserved
0x1400112b2  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x1400112b7  lea     r9, Class; lpClass
0x1400112be  lea     rax, [rbp+hKey]
0x1400112c2  mov     rdx, r15; lpSubKey
0x1400112c5  mov     [rsp+68h+phkResult], rax; phkResult
0x1400112ca  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400112d1  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1400112da  mov     [rsp+68h+samDesired], 2; samDesired
0x1400112e2  mov     [rsp+68h+dwOptions], 0; dwOptions
0x1400112ea  call    cs:__imp_RegCreateKeyExW
0x1400112f0  mov     ebx, eax
0x1400112f2  test    eax, eax
0x1400112f4  jz      short loc_1400112FE
0x1400112f6  mov     r9d, 158h
0x1400112fc  jmp     short loc_14001132C
0x1400112fe  mov     eax, [rbp+dwBufferLength]
0x140011301  mov     r9d, 3; dwType
0x140011307  mov     rcx, [rbp+hKey]; hKey
0x14001130b  xor     r8d, r8d; Reserved
0x14001130e  mov     [rsp+68h+samDesired], eax; cbData
0x140011312  mov     rdx, r14; lpValueName
0x140011315  mov     qword ptr [rsp+68h+dwOptions], rdi; lpData
0x14001131a  call    cs:__imp_RegSetValueExW
0x140011320  mov     ebx, eax
0x140011322  test    eax, eax
0x140011324  jz      short loc_14001134C
0x140011326  mov     r9d, 167h; unsigned int
0x14001132c  mov     [rsp+68h+samDesired], 0; unsigned int
0x140011334  lea     rcx, aCragrouppolicy_2; "CRAGroupPolicy::SetSDToRegistry"
0x14001133b  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x140011342  mov     qword ptr [rsp+68h+dwOptions], rcx; unsigned __int16 *
0x140011347  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14001134c  mov     rcx, [rbp+hKey]; hKey
0x140011350  test    rcx, rcx
0x140011353  jz      short loc_140011363
0x140011355  call    cs:__imp_RegCloseKey
0x14001135b  mov     [rbp+hKey], 0
0x140011363  test    rdi, rdi
0x140011366  jz      short loc_14001137C
0x140011368  call    cs:__imp_GetProcessHeap
0x14001136e  mov     r8, rdi; lpMem
0x140011371  xor     edx, edx; dwFlags
0x140011373  mov     rcx, rax; hHeap
0x140011376  call    cs:__imp_HeapFree
0x14001137c  mov     eax, ebx
0x14001137e  add     rsp, 68h
0x140011382  pop     r15
0x140011384  pop     r14
0x140011386  pop     rdi
0x140011387  pop     rsi
0x140011388  pop     rbx
0x140011389  pop     rbp
0x14001138a  retn
```
