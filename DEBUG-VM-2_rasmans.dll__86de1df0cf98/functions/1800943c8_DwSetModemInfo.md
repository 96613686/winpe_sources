# DwSetModemInfo

- ea: `0x1800943c8`
- end: `0x18009453e`
- name: `DwSetModemInfo`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002b6a0`

## callees

- `0x1800935a8`
- `0x1800943c8`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094439`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094439`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094490`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094490`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094505`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094515`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094505`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094515`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800944c0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800944f0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800944c0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800944f0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18009442f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18009442f`

## pseudocode

```c
__int64 __fastcall DwSetModemInfo(__int64 a1)
{
  unsigned int *v2; // r8
  DWORD LastError; // ebx
  HKEY hKey; // [rsp+30h] [rbp-138h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-130h] BYREF
  WCHAR WideCharStr[136]; // [rsp+40h] [rbp-128h] BYREF

  hKey = 0;
  memset_0(WideCharStr, 0, 0x102u);
  phkResult = 0;
  if ( !MultiByteToWideChar(0, 0, (LPCCH)(a1 + 133), -1, WideCharStr, 129) )
  {
    LastError = GetLastError();
    goto LABEL_10;
  }
  LastError = lrGetRegKeyFromGuid((unsigned __int8 *)WideCharStr, &hKey, v2, 1);
  if ( !LastError )
  {
    if ( !hKey )
      goto LABEL_10;
    LastError = RegOpenKeyExW(hKey, L"Clients\\Ras", 0, 0xF003Fu, &phkResult);
    if ( !LastError )
    {
      LastError = RegSetValueExW(phkResult, L"EnableForRas", 0, 4u, (const BYTE *)(a1 + 56), 4u);
      if ( !LastError )
        LastError = RegSetValueExW(phkResult, L"EnableforRouting", 0, 4u, (const BYTE *)(a1 + 60), 4u);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
LABEL_10:
  if ( phkResult )
    RegCloseKey(phkResult);
  return LastError;
}

```

## disassembly

```asm
0x1800943c8  mov     [rsp+arg_8], rbx
0x1800943cd  push    rsi
0x1800943ce  sub     rsp, 160h
0x1800943d5  mov     rax, cs:__security_cookie
0x1800943dc  xor     rax, rsp
0x1800943df  mov     [rsp+168h+var_18], rax
0x1800943e7  mov     rsi, rcx
0x1800943ea  mov     [rsp+168h+hKey], 0
0x1800943f3  lea     rcx, [rsp+168h+WideCharStr]; void *
0x1800943f8  xor     edx, edx; Val
0x1800943fa  mov     r8d, 102h; Size
0x180094400  call    memset_0
0x180094405  lea     rax, [rsp+168h+WideCharStr]
0x18009440a  mov     [rsp+168h+cchWideChar], 81h; cchWideChar
0x180094412  lea     r8, [rsi+85h]; lpMultiByteStr
0x180094419  mov     [rsp+168h+lpWideCharStr], rax; lpWideCharStr
0x18009441e  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180094422  mov     [rsp+168h+phkResult], 0
0x18009442b  xor     edx, edx; dwFlags
0x18009442d  xor     ecx, ecx; CodePage
0x18009442f  call    cs:__imp_MultiByteToWideChar
0x180094435  test    eax, eax
0x180094437  jnz     short loc_180094446
0x180094439  call    cs:__imp_GetLastError
0x18009443f  mov     ebx, eax
0x180094441  jmp     loc_18009450B
0x180094446  mov     r9d, 1; int
0x18009444c  lea     rdx, [rsp+168h+hKey]; HKEY *
0x180094451  lea     rcx, [rsp+168h+WideCharStr]; unsigned __int8 *
0x180094456  call    ?lrGetRegKeyFromGuid@@YAJPEAEPEAPEAUHKEY__@@PEAKH@Z; lrGetRegKeyFromGuid(uchar *,HKEY__ * *,ulong *,int)
0x18009445b  mov     ebx, eax
0x18009445d  test    eax, eax
0x18009445f  jnz     loc_1800944F8
0x180094465  cmp     [rsp+168h+hKey], 0
0x18009446b  jz      loc_18009450B
0x180094471  mov     rcx, [rsp+168h+hKey]; hKey
0x180094476  lea     rax, [rsp+168h+phkResult]
0x18009447b  mov     r9d, 0F003Fh; samDesired
0x180094481  mov     [rsp+168h+lpWideCharStr], rax; phkResult
0x180094486  xor     r8d, r8d; ulOptions
0x180094489  lea     rdx, aClientsRas; "Clients\\Ras"
0x180094490  call    cs:__imp_RegOpenKeyExW
0x180094496  mov     ebx, eax
0x180094498  test    eax, eax
0x18009449a  jnz     short loc_1800944F8
0x18009449c  mov     rcx, [rsp+168h+phkResult]; hKey
0x1800944a1  lea     rax, [rsi+38h]
0x1800944a5  mov     [rsp+168h+cchWideChar], 4; cbData
0x1800944ad  lea     r9d, [rbx+4]; dwType
0x1800944b1  xor     r8d, r8d; Reserved
0x1800944b4  mov     [rsp+168h+lpWideCharStr], rax; lpData
0x1800944b9  lea     rdx, aEnableforras; "EnableForRas"
0x1800944c0  call    cs:__imp_RegSetValueExW
0x1800944c6  mov     ebx, eax
0x1800944c8  test    eax, eax
0x1800944ca  jnz     short loc_1800944F8
0x1800944cc  mov     rcx, [rsp+168h+phkResult]; hKey
0x1800944d1  lea     rax, [rsi+3Ch]
0x1800944d5  mov     [rsp+168h+cchWideChar], 4; cbData
0x1800944dd  lea     r9d, [rbx+4]; dwType
0x1800944e1  xor     r8d, r8d; Reserved
0x1800944e4  mov     [rsp+168h+lpWideCharStr], rax; lpData
0x1800944e9  lea     rdx, aEnableforrouti_0; "EnableforRouting"
0x1800944f0  call    cs:__imp_RegSetValueExW
0x1800944f6  mov     ebx, eax
0x1800944f8  cmp     [rsp+168h+hKey], 0
0x1800944fe  jz      short loc_18009450B
0x180094500  mov     rcx, [rsp+168h+hKey]; hKey
0x180094505  call    cs:__imp_RegCloseKey
0x18009450b  mov     rcx, [rsp+168h+phkResult]; hKey
0x180094510  test    rcx, rcx
0x180094513  jz      short loc_18009451B
0x180094515  call    cs:__imp_RegCloseKey
0x18009451b  mov     eax, ebx
0x18009451d  mov     rcx, [rsp+168h+var_18]
0x180094525  xor     rcx, rsp; StackCookie
0x180094528  call    __security_check_cookie
0x18009452d  mov     rbx, [rsp+168h+arg_8]
0x180094535  add     rsp, 160h
0x18009453c  pop     rsi
0x18009453d  retn
```
