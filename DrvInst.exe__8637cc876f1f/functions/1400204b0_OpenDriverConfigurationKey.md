# OpenDriverConfigurationKey

- ea: `0x1400204b0`
- end: `0x1400205e0`
- name: `OpenDriverConfigurationKey`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140020bbc`

## callees

- `0x140009794`
- `0x1400204b0`
- `0x1400205e8`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002052a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002052a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400205ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400205ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002059a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002059a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400205b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400205b2`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140020520`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140020520`

## string_xrefs

- `0x14002054c`: `Configurations`

## pseudocode

```c
HKEY __fastcall OpenDriverConfigurationKey(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rdx
  DWORD LastError; // ebx
  HKEY v7; // rdi
  int v9; // [rsp+30h] [rbp-678h]
  int v10; // [rsp+40h] [rbp-668h]
  HKEY phkResult; // [rsp+58h] [rbp-650h] BYREF
  _BYTE v12[528]; // [rsp+60h] [rbp-648h] BYREF
  wchar_t pszDest[520]; // [rsp+270h] [rbp-438h] BYREF

  v10 = 0;
  v9 = 520;
  phkResult = 0;
  if ( (unsigned int)DriverStoreGetObjectPropertyW(a1, 3, a2, DEVPKEY_DriverInfFile_ActiveDriverPackage)
    && (v7 = (HKEY)OpenDriverDatabaseObject(a1, v5, v12)) != 0 )
  {
    if ( StringCchPrintfW(pszDest, 0x208u, L"%ws\\%ws", L"Configurations", a3, v12, v9, 0, v10) >= 0 )
    {
      LastError = RegOpenKeyExW(v7, pszDest, 0, 1u, &phkResult);
      if ( LastError )
        phkResult = 0;
    }
    else
    {
      LastError = 13;
    }
    RegCloseKey(v7);
  }
  else
  {
    LastError = GetLastError();
  }
  SetLastError(LastError);
  return phkResult;
}

```

## disassembly

```asm
0x1400204b0  push    rbx
0x1400204b2  push    rsi
0x1400204b3  push    rdi
0x1400204b4  sub     rsp, 690h
0x1400204bb  mov     rax, cs:__security_cookie
0x1400204c2  xor     rax, rsp
0x1400204c5  mov     [rsp+6A8h+var_28], rax
0x1400204cd  mov     [rsp+6A8h+var_668], 0
0x1400204d5  lea     rax, [rsp+6A8h+var_648]
0x1400204da  mov     [rsp+6A8h+var_670], 0
0x1400204e3  lea     r9, DEVPKEY_DriverInfFile_ActiveDriverPackage
0x1400204ea  mov     [rsp+6A8h+var_678], 208h
0x1400204f2  mov     rsi, r8
0x1400204f5  mov     [rsp+6A8h+var_680], rax
0x1400204fa  mov     r8, rdx
0x1400204fd  lea     rax, [rsp+6A8h+var_658]
0x140020502  mov     [rsp+6A8h+var_650], 0
0x14002050b  mov     edx, 3
0x140020510  mov     [rsp+6A8h+phkResult], rax
0x140020515  mov     rbx, rcx
0x140020518  mov     [rsp+6A8h+var_658], 0
0x140020520  call    cs:__imp_DriverStoreGetObjectPropertyW
0x140020526  test    eax, eax
0x140020528  jnz     short loc_140020537
0x14002052a  call    cs:__imp_GetLastError
0x140020530  mov     ebx, eax
0x140020532  jmp     loc_1400205B8
0x140020537  lea     r8, [rsp+6A8h+var_648]
0x14002053c  mov     rcx, rbx
0x14002053f  call    OpenDriverDatabaseObject
0x140020544  mov     rdi, rax
0x140020547  test    rax, rax
0x14002054a  jz      short loc_14002052A
0x14002054c  lea     r9, aConfigurations; "Configurations"
0x140020553  mov     [rsp+6A8h+phkResult], rsi
0x140020558  lea     r8, aWsWs_0; "%ws\\%ws"
0x14002055f  mov     edx, 208h; cchDest
0x140020564  lea     rcx, [rsp+6A8h+pszDest]; pszDest
0x14002056c  call    StringCchPrintfW
0x140020571  test    eax, eax
0x140020573  jns     short loc_14002057C
0x140020575  mov     ebx, 0Dh
0x14002057a  jmp     short loc_1400205AF
0x14002057c  lea     rax, [rsp+6A8h+var_650]
0x140020581  mov     r9d, 1; samDesired
0x140020587  xor     r8d, r8d; ulOptions
0x14002058a  mov     [rsp+6A8h+phkResult], rax; phkResult
0x14002058f  lea     rdx, [rsp+6A8h+pszDest]; lpSubKey
0x140020597  mov     rcx, rdi; hKey
0x14002059a  call    cs:__imp_RegOpenKeyExW
0x1400205a0  mov     ebx, eax
0x1400205a2  test    eax, eax
0x1400205a4  jz      short loc_1400205AF
0x1400205a6  mov     [rsp+6A8h+var_650], 0
0x1400205af  mov     rcx, rdi; hKey
0x1400205b2  call    cs:__imp_RegCloseKey
0x1400205b8  mov     ecx, ebx; dwErrCode
0x1400205ba  call    cs:__imp_SetLastError
0x1400205c0  mov     rax, [rsp+6A8h+var_650]
0x1400205c5  mov     rcx, [rsp+6A8h+var_28]
0x1400205cd  xor     rcx, rsp; StackCookie
0x1400205d0  call    __security_check_cookie
0x1400205d5  add     rsp, 690h
0x1400205dc  pop     rdi
0x1400205dd  pop     rsi
0x1400205de  pop     rbx
0x1400205df  retn
```
