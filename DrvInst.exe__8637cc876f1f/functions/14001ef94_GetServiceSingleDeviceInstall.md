# GetServiceSingleDeviceInstall

- ea: `0x14001ef94`
- end: `0x14001f0c5`
- name: `GetServiceSingleDeviceInstall`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x14001ef04`

## callees

- `0x140009794`
- `0x14001ef94`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001f096`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001f096`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001f021`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001f021`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001f08e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001f08e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001f05d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001f05d`

## string_xrefs

- `0x14001efd3`: `System\CurrentControlSet\Services\%ws\Parameters`
- `0x14001f056`: `SingleDeviceInstall`

## pseudocode

```c
_BOOL8 __fastcall GetServiceSingleDeviceInstall(__int64 a1)
{
  LSTATUS v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[256]; // [rsp+50h] [rbp-B0h] BYREF

  *(_DWORD *)Data = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( StringCchPrintfW(pszDest, 0x100u, L"System\\CurrentControlSet\\Services\\%ws\\Parameters", a1) >= 0 )
  {
    v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 1u, &hKey);
    if ( !v1 )
    {
      cbData = 4;
      v1 = RegQueryValueExW(hKey, L"SingleDeviceInstall", 0, &Type, Data, &cbData);
      if ( !v1 && (Type != 4 || cbData != 4) )
      {
        *(_DWORD *)Data = 0;
        v1 = 13;
      }
    }
  }
  else
  {
    v1 = 87;
  }
  if ( hKey )
    RegCloseKey(hKey);
  SetLastError(v1);
  return *(_DWORD *)Data != 0;
}

```

## disassembly

```asm
0x14001ef94  mov     [rsp-8+arg_8], rbx
0x14001ef99  push    rbp
0x14001ef9a  lea     rbp, [rsp-160h]
0x14001efa2  sub     rsp, 260h
0x14001efa9  mov     rax, cs:__security_cookie
0x14001efb0  xor     rax, rsp
0x14001efb3  mov     [rbp+160h+var_10], rax
0x14001efba  mov     r9, rcx
0x14001efbd  mov     dword ptr [rsp+260h+Data], 0
0x14001efc5  lea     rcx, [rsp+260h+pszDest]; pszDest
0x14001efca  mov     [rsp+260h+hKey], 0
0x14001efd3  lea     r8, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\%w"...
0x14001efda  mov     [rsp+260h+Type], 0
0x14001efe2  mov     edx, 100h; cchDest
0x14001efe7  mov     [rsp+260h+cbData], 0
0x14001efef  call    StringCchPrintfW
0x14001eff4  test    eax, eax
0x14001eff6  jns     short loc_14001F002
0x14001eff8  mov     ebx, 57h ; 'W'
0x14001effd  jmp     loc_14001F084
0x14001f002  lea     rax, [rsp+260h+hKey]
0x14001f007  mov     r9d, 1; samDesired
0x14001f00d  xor     r8d, r8d; ulOptions
0x14001f010  mov     [rsp+260h+phkResult], rax; phkResult
0x14001f015  lea     rdx, [rsp+260h+pszDest]; lpSubKey
0x14001f01a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001f021  call    cs:__imp_RegOpenKeyExW
0x14001f027  mov     ebx, eax
0x14001f029  test    eax, eax
0x14001f02b  jnz     short loc_14001F084
0x14001f02d  mov     rcx, [rsp+260h+hKey]; hKey
0x14001f032  lea     rax, [rsp+260h+cbData]
0x14001f037  mov     [rsp+260h+lpcbData], rax; lpcbData
0x14001f03c  lea     r9, [rsp+260h+Type]; lpType
0x14001f041  lea     rax, [rsp+260h+Data]
0x14001f046  mov     [rsp+260h+cbData], 4
0x14001f04e  xor     r8d, r8d; lpReserved
0x14001f051  mov     [rsp+260h+phkResult], rax; lpData
0x14001f056  lea     rdx, aSingledevicein; "SingleDeviceInstall"
0x14001f05d  call    cs:__imp_RegQueryValueExW
0x14001f063  mov     ebx, eax
0x14001f065  test    eax, eax
0x14001f067  jnz     short loc_14001F084
0x14001f069  cmp     [rsp+260h+Type], 4
0x14001f06e  jnz     short loc_14001F077
0x14001f070  cmp     [rsp+260h+cbData], 4
0x14001f075  jz      short loc_14001F084
0x14001f077  mov     dword ptr [rsp+260h+Data], 0
0x14001f07f  mov     ebx, 0Dh
0x14001f084  mov     rcx, [rsp+260h+hKey]; hKey
0x14001f089  test    rcx, rcx
0x14001f08c  jz      short loc_14001F094
0x14001f08e  call    cs:__imp_RegCloseKey
0x14001f094  mov     ecx, ebx; dwErrCode
0x14001f096  call    cs:__imp_SetLastError
0x14001f09c  xor     eax, eax
0x14001f09e  cmp     dword ptr [rsp+260h+Data], eax
0x14001f0a2  setnz   al
0x14001f0a5  mov     rcx, [rbp+160h+var_10]
0x14001f0ac  xor     rcx, rsp; StackCookie
0x14001f0af  call    __security_check_cookie
0x14001f0b4  mov     rbx, [rsp+260h+arg_8]
0x14001f0bc  add     rsp, 260h
0x14001f0c3  pop     rbp
0x14001f0c4  retn
```
