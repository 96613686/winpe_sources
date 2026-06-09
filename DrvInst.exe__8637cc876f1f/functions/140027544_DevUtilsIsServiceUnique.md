# DevUtilsIsServiceUnique

- ea: `0x140027544`
- end: `0x140027667`
- name: `DevUtilsIsServiceUnique`
- size: `291`
- prototype: `__int64 __fastcall(wchar_t *String2)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1400274b4`

## callees

- `0x140001b64`
- `0x140007100`
- `0x140027544`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140027644`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140027644`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400275bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400275bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002763c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002763c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400275fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400275fd`

## string_xrefs

- `0x14002756b`: `System\CurrentControlSet\Services\%ws`

## pseudocode

```c
__int64 __fastcall DevUtilsIsServiceUnique(wchar_t *String2)
{
  unsigned int v1; // ebx
  LSTATUS v3; // edi
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[256]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Data[256]; // [rsp+240h] [rbp+140h] BYREF

  v1 = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( StringCchPrintfW(SubKey, 0x100u, L"System\\CurrentControlSet\\Services\\%ws", String2) >= 0 )
  {
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey);
    if ( !v3 )
    {
      cbData = 512;
      v3 = RegQueryValueExW(hKey, L"OriginalName", 0, &Type, (LPBYTE)Data, &cbData);
      if ( !v3 )
      {
        if ( Type == 1 && cbData >= 2 )
          LOBYTE(v1) = wcsicmp_0(Data, String2) != 0;
        else
          v3 = 13;
      }
    }
  }
  else
  {
    v3 = 87;
  }
  if ( hKey )
    RegCloseKey(hKey);
  SetLastError(v3);
  return v1;
}

```

## disassembly

```asm
0x140027544  push    rbp
0x140027546  push    rbx
0x140027547  push    rsi
0x140027548  push    rdi
0x140027549  lea     rbp, [rsp-358h]
0x140027551  sub     rsp, 458h
0x140027558  mov     rax, cs:__security_cookie
0x14002755f  xor     rax, rsp
0x140027562  mov     [rbp+370h+var_30], rax
0x140027569  xor     ebx, ebx
0x14002756b  lea     r8, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\%w"...
0x140027572  mov     rsi, rcx
0x140027575  mov     [rsp+470h+hKey], rbx
0x14002757a  mov     r9, rcx
0x14002757d  mov     [rsp+470h+Type], ebx
0x140027581  lea     rcx, [rsp+470h+SubKey]; unsigned __int16 *
0x140027586  mov     [rsp+470h+cbData], ebx
0x14002758a  mov     edx, 100h; unsigned __int64
0x14002758f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140027594  test    eax, eax
0x140027596  jns     short loc_1400275A0
0x140027598  lea     edi, [rbx+57h]
0x14002759b  jmp     loc_140027632
0x1400275a0  lea     rax, [rsp+470h+hKey]
0x1400275a5  mov     r9d, 1; samDesired
0x1400275ab  xor     r8d, r8d; ulOptions
0x1400275ae  mov     [rsp+470h+phkResult], rax; phkResult
0x1400275b3  lea     rdx, [rsp+470h+SubKey]; lpSubKey
0x1400275b8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400275bf  call    cs:__imp_RegOpenKeyExW
0x1400275c5  mov     edi, eax
0x1400275c7  test    eax, eax
0x1400275c9  jnz     short loc_140027632
0x1400275cb  mov     rcx, [rsp+470h+hKey]; hKey
0x1400275d0  lea     rax, [rsp+470h+cbData]
0x1400275d5  mov     [rsp+470h+lpcbData], rax; lpcbData
0x1400275da  lea     r9, [rsp+470h+Type]; lpType
0x1400275df  lea     rax, [rbp+370h+Data]
0x1400275e6  mov     [rsp+470h+cbData], 200h
0x1400275ee  xor     r8d, r8d; lpReserved
0x1400275f1  mov     [rsp+470h+phkResult], rax; lpData
0x1400275f6  lea     rdx, aOriginalname; "OriginalName"
0x1400275fd  call    cs:__imp_RegQueryValueExW
0x140027603  mov     edi, eax
0x140027605  test    eax, eax
0x140027607  jnz     short loc_140027632
0x140027609  cmp     [rsp+470h+Type], 1
0x14002760e  jnz     short loc_14002762D
0x140027610  cmp     [rsp+470h+cbData], 2
0x140027615  jb      short loc_14002762D
0x140027617  mov     rdx, rsi; String2
0x14002761a  lea     rcx, [rbp+370h+Data]; String1
0x140027621  call    _wcsicmp_0
0x140027626  test    eax, eax
0x140027628  setnz   bl
0x14002762b  jmp     short loc_140027632
0x14002762d  mov     edi, 0Dh
0x140027632  mov     rcx, [rsp+470h+hKey]; hKey
0x140027637  test    rcx, rcx
0x14002763a  jz      short loc_140027642
0x14002763c  call    cs:__imp_RegCloseKey
0x140027642  mov     ecx, edi; dwErrCode
0x140027644  call    cs:__imp_SetLastError
0x14002764a  mov     eax, ebx
0x14002764c  mov     rcx, [rbp+370h+var_30]
0x140027653  xor     rcx, rsp; StackCookie
0x140027656  call    __security_check_cookie
0x14002765b  add     rsp, 458h
0x140027662  pop     rdi
0x140027663  pop     rsi
0x140027664  pop     rbx
0x140027665  pop     rbp
0x140027666  retn
```
