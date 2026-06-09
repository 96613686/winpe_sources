# OpenDriverNodeConfiguration

- ea: `0x1400207cc`
- end: `0x140020a04`
- name: `OpenDriverNodeConfiguration`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140020aa8`

## callees

- `0x140001a38`
- `0x1400070bc`
- `0x140009794`
- `0x1400205e8`
- `0x1400207cc`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002083b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002083b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400209cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400209cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002089c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140020995`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002089c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140020995`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400209b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400209c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400209b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400209c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400208e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400208e4`

## string_xrefs

- `0x14002085d`: `Descriptors`
- `0x1400208d8`: `Configuration`
- `0x14002095a`: `Configurations`

## pseudocode

```c
_BOOL8 __fastcall OpenDriverNodeConfiguration(__int64 a1, __int64 a2)
{
  HKEY *phkResult; // r14
  DWORD LastError; // ebx
  HKEY v5; // rdi
  unsigned __int64 v6; // rcx
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  size_t Data[64]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v12; // [rsp+246h] [rbp+146h]
  wchar_t pszDest[520]; // [rsp+250h] [rbp+150h] BYREF

  phkResult = (HKEY *)(a2 + 3968);
  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( *(_QWORD *)(a2 + 3968) )
  {
    LastError = 0;
    goto LABEL_26;
  }
  v5 = (HKEY)OpenDriverDatabaseObject(a1, a2, a2 + 1056);
  if ( !v5 )
  {
    LastError = GetLastError();
    goto LABEL_22;
  }
  if ( StringCchPrintfW(pszDest, 0x208u, L"%ws\\%ws", L"Descriptors", a2 + 1576) < 0 )
    goto LABEL_21;
  LastError = RegOpenKeyExW(v5, pszDest, 0, 1u, &hKey);
  if ( LastError )
  {
    hKey = 0;
LABEL_25:
    RegCloseKey(v5);
    goto LABEL_26;
  }
  Type = 0;
  cbData = 520;
  LastError = RegQueryValueExW(hKey, L"Configuration", 0, &Type, (LPBYTE)Data, &cbData);
  if ( !LastError )
  {
    if ( Type == 1 && cbData >= 2 )
    {
      if ( cbData >= 0x208 )
      {
        v12 = 0;
      }
      else
      {
        v6 = cbData & 0xFFFFFFFE;
        if ( v6 >= 0x208 )
          _report_rangecheckfailure();
        *(_WORD *)((char *)Data + v6) = 0;
      }
      if ( (*(_WORD *)(a2 + 1976) || (int)StringCchCopyW((unsigned __int16 *)(a2 + 1976), 0x104u, Data) >= 0)
        && StringCchPrintfW(pszDest, 0x208u, L"%ws\\%ws", L"Configurations", Data) >= 0 )
      {
        LastError = RegOpenKeyExW(v5, pszDest, 0, 1u, phkResult);
        if ( LastError )
          *phkResult = 0;
        goto LABEL_22;
      }
    }
LABEL_21:
    LastError = 13;
  }
LABEL_22:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v5 )
    goto LABEL_25;
LABEL_26:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x1400207cc  mov     [rsp-8+arg_10], rbx
0x1400207d1  mov     [rsp-8+arg_18], rsi
0x1400207d6  push    rbp
0x1400207d7  push    rdi
0x1400207d8  push    r12
0x1400207da  push    r14
0x1400207dc  push    r15
0x1400207de  lea     rbp, [rsp-570h]
0x1400207e6  sub     rsp, 670h
0x1400207ed  mov     rax, cs:__security_cookie
0x1400207f4  xor     rax, rsp
0x1400207f7  mov     [rbp+590h+var_30], rax
0x1400207fe  xor     r15d, r15d
0x140020801  lea     r14, [rdx+0F80h]
0x140020808  mov     rsi, rdx
0x14002080b  mov     [rsp+690h+hKey], r15
0x140020810  mov     [rsp+690h+Type], r15d
0x140020815  mov     [rsp+690h+cbData], r15d
0x14002081a  cmp     [r14], r15
0x14002081d  jz      short loc_140020827
0x14002081f  mov     ebx, r15d
0x140020822  jmp     loc_1400209C9
0x140020827  lea     r8, [rdx+420h]
0x14002082e  call    OpenDriverDatabaseObject
0x140020833  mov     rdi, rax
0x140020836  test    rax, rax
0x140020839  jnz     short loc_140020848
0x14002083b  call    cs:__imp_GetLastError
0x140020841  mov     ebx, eax
0x140020843  jmp     loc_1400209AB
0x140020848  lea     rax, [rsi+628h]
0x14002084f  mov     r12d, 208h
0x140020855  mov     edx, r12d; cchDest
0x140020858  mov     [rsp+690h+phkResult], rax
0x14002085d  lea     r9, aDescriptors; "Descriptors"
0x140020864  lea     r8, aWsWs_0; "%ws\\%ws"
0x14002086b  lea     rcx, [rbp+590h+pszDest]; pszDest
0x140020872  call    StringCchPrintfW
0x140020877  test    eax, eax
0x140020879  js      loc_1400209A6
0x14002087f  lea     rax, [rsp+690h+hKey]
0x140020884  mov     r9d, 1; samDesired
0x14002088a  xor     r8d, r8d; ulOptions
0x14002088d  mov     [rsp+690h+phkResult], rax; phkResult
0x140020892  lea     rdx, [rbp+590h+pszDest]; lpSubKey
0x140020899  mov     rcx, rdi; hKey
0x14002089c  call    cs:__imp_RegOpenKeyExW
0x1400208a2  mov     ebx, eax
0x1400208a4  test    eax, eax
0x1400208a6  jz      short loc_1400208B2
0x1400208a8  mov     [rsp+690h+hKey], r15
0x1400208ad  jmp     loc_1400209C0
0x1400208b2  mov     rcx, [rsp+690h+hKey]; hKey
0x1400208b7  lea     rax, [rsp+690h+cbData]
0x1400208bc  mov     [rsp+690h+lpcbData], rax; lpcbData
0x1400208c1  lea     r9, [rsp+690h+Type]; lpType
0x1400208c6  lea     rax, [rsp+690h+Data]
0x1400208cb  mov     [rsp+690h+Type], r15d
0x1400208d0  xor     r8d, r8d; lpReserved
0x1400208d3  mov     [rsp+690h+phkResult], rax; lpData
0x1400208d8  lea     rdx, aConfiguration; "Configuration"
0x1400208df  mov     [rsp+690h+cbData], r12d
0x1400208e4  call    cs:__imp_RegQueryValueExW
0x1400208ea  mov     ebx, eax
0x1400208ec  test    eax, eax
0x1400208ee  jnz     loc_1400209AB
0x1400208f4  cmp     [rsp+690h+Type], 1
0x1400208f9  jnz     loc_1400209A6
0x1400208ff  mov     eax, [rsp+690h+cbData]
0x140020903  cmp     eax, 2
0x140020906  jb      loc_1400209A6
0x14002090c  cmp     eax, r12d
0x14002090f  jnb     short loc_14002092A
0x140020911  mov     ecx, eax
0x140020913  and     rcx, 0FFFFFFFFFFFFFFFEh
0x140020917  cmp     rcx, r12
0x14002091a  jnb     short loc_140020924
0x14002091c  mov     word ptr [rsp+rcx+690h+Data], r15w
0x140020922  jmp     short loc_140020932
0x140020924  call    __report_rangecheckfailure
0x14002092a  mov     [rbp+590h+var_44A], r15w
0x140020932  lea     rcx, [rsi+7B8h]; unsigned __int16 *
0x140020939  cmp     [rcx], r15w
0x14002093d  jnz     short loc_140020952
0x14002093f  lea     r8, [rsp+690h+Data]; unsigned __int16 *
0x140020944  mov     edx, 104h; unsigned __int64
0x140020949  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002094e  test    eax, eax
0x140020950  js      short loc_1400209A6
0x140020952  lea     rax, [rsp+690h+Data]
0x140020957  mov     rdx, r12; cchDest
0x14002095a  lea     r9, aConfigurations; "Configurations"
0x140020961  mov     [rsp+690h+phkResult], rax
0x140020966  lea     r8, aWsWs_0; "%ws\\%ws"
0x14002096d  lea     rcx, [rbp+590h+pszDest]; pszDest
0x140020974  call    StringCchPrintfW
0x140020979  test    eax, eax
0x14002097b  js      short loc_1400209A6
0x14002097d  mov     r9d, 1; samDesired
0x140020983  mov     [rsp+690h+phkResult], r14; phkResult
0x140020988  xor     r8d, r8d; ulOptions
0x14002098b  lea     rdx, [rbp+590h+pszDest]; lpSubKey
0x140020992  mov     rcx, rdi; hKey
0x140020995  call    cs:__imp_RegOpenKeyExW
0x14002099b  mov     ebx, eax
0x14002099d  test    eax, eax
0x14002099f  jz      short loc_1400209AB
0x1400209a1  mov     [r14], r15
0x1400209a4  jmp     short loc_1400209AB
0x1400209a6  mov     ebx, 0Dh
0x1400209ab  mov     rcx, [rsp+690h+hKey]; hKey
0x1400209b0  test    rcx, rcx
0x1400209b3  jz      short loc_1400209BB
0x1400209b5  call    cs:__imp_RegCloseKey
0x1400209bb  test    rdi, rdi
0x1400209be  jz      short loc_1400209C9
0x1400209c0  mov     rcx, rdi; hKey
0x1400209c3  call    cs:__imp_RegCloseKey
0x1400209c9  mov     ecx, ebx; dwErrCode
0x1400209cb  call    cs:__imp_SetLastError
0x1400209d1  test    ebx, ebx
0x1400209d3  mov     eax, r15d
0x1400209d6  setz    al
0x1400209d9  mov     rcx, [rbp+590h+var_30]
0x1400209e0  xor     rcx, rsp; StackCookie
0x1400209e3  call    __security_check_cookie
0x1400209e8  lea     r11, [rsp+690h+var_20]
0x1400209f0  mov     rbx, [r11+40h]
0x1400209f4  mov     rsi, [r11+48h]
0x1400209f8  mov     rsp, r11
0x1400209fb  pop     r15
0x1400209fd  pop     r14
0x1400209ff  pop     r12
0x140020a01  pop     rdi
0x140020a02  pop     rbp
0x140020a03  retn
```
