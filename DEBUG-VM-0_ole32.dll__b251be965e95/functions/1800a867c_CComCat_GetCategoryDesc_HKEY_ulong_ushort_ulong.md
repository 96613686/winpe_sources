# CComCat::GetCategoryDesc(HKEY__ *,ulong,ushort * *,ulong *)

- ea: `0x1800a867c`
- end: `0x1800a89b1`
- name: `?GetCategoryDesc@CComCat@@SAJPEAUHKEY__@@KPEAPEAGPEAK@Z`
- size: `821`
- prototype: `HRESULT __fastcall(HKEY__ *hKey, unsigned int lcid, wchar_t **ppszDesc, unsigned int *plcid)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a89c0`
- `0x1800ad180`

## callees

- `0x18001775c`
- `0x180052390`
- `0x1800a867c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800a8832`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800a892c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800a8832`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800a892c`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1800a8850`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1800a8850`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800a88a3`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800a88a3`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800a8737`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800a8819`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800a8912`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800a8737`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800a8819`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800a8912`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800a86f4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800a86f4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a8782`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a87de`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a8895`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a88e3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a896a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a8782`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a87de`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a8895`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a88e3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a896a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a893a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a893a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8977`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8977`

## pseudocode

```c
HRESULT __fastcall CComCat::GetCategoryDesc(HKEY hKey, unsigned int lcid, LPVOID *ppszDesc, unsigned int *plcid)
{
  __int64 UserDefaultLCID; // rbx
  HRESULT result; // eax
  __int16 v9; // r12
  DWORD v10; // esi
  wchar_t *v11; // rax
  unsigned int cb; // [rsp+60h] [rbp-49h] BYREF
  unsigned int dwSizeNameBuf; // [rsp+64h] [rbp-45h] BYREF
  unsigned int dwNumValues; // [rsp+68h] [rbp-41h] BYREF
  wchar_t *EndPtr; // [rsp+70h] [rbp-39h] BYREF
  wchar_t szLCID[32]; // [rsp+78h] [rbp-31h] BYREF

  LODWORD(UserDefaultLCID) = lcid;
  cb = 0;
  dwNumValues = 0;
  dwSizeNameBuf = 16;
  if ( RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &dwNumValues, 0, 0, 0, 0) || !dwNumValues )
    return -2147221151;
  if ( dwNumValues == 1 )
  {
    RegEnumValueW(hKey, 0, szLCID, &dwSizeNameBuf, 0, 0, 0, &cb);
LABEL_17:
    EndPtr = 0;
    LODWORD(UserDefaultLCID) = wcstoul(szLCID, &EndPtr, 16);
    goto $process;
  }
  result = StringCchPrintfW(szLCID, 0x1Eu, L"%#x", (unsigned int)UserDefaultLCID);
  if ( result < 0 )
    return result;
  if ( RegQueryValueExW(hKey, szLCID, 0, 0, 0, &cb) )
  {
    v9 = UserDefaultLCID & 0x3FF;
    LODWORD(UserDefaultLCID) = UserDefaultLCID & 0x3FF | 0x400;
    result = StringCchPrintfW(szLCID, 0x1Eu, L"%#x", (unsigned int)UserDefaultLCID);
    if ( result < 0 )
      return result;
    v10 = 0;
    if ( RegQueryValueExW(hKey, szLCID, 0, 0, 0, &cb) )
    {
      while ( 1 )
      {
        dwSizeNameBuf = 16;
        if ( RegEnumValueW(hKey, v10, szLCID, &dwSizeNameBuf, 0, 0, 0, &cb) )
          break;
        EndPtr = 0;
        LODWORD(UserDefaultLCID) = wcstoul(szLCID, &EndPtr, 16);
        if ( (UserDefaultLCID & 0x3FF) == v9 )
          goto $process;
        ++v10;
      }
      UserDefaultLCID = GetUserDefaultLCID();
      result = StringCchPrintfW(szLCID, 0x1Eu, L"%#x", UserDefaultLCID);
      if ( result < 0 )
        return result;
      if ( RegQueryValueExW(hKey, szLCID, 0, 0, 0, &cb) )
      {
        UserDefaultLCID = GetSystemDefaultLCID();
        result = StringCchPrintfW(szLCID, 0x1Eu, L"%#x", UserDefaultLCID);
        if ( result < 0 )
          return result;
        if ( RegQueryValueExW(hKey, szLCID, 0, 0, 0, &cb) )
        {
          if ( RegEnumValueW(hKey, 0, szLCID, &dwSizeNameBuf, 0, 0, 0, &cb) )
            return -2147221151;
          goto LABEL_17;
        }
      }
    }
  }
$process:
  v11 = (wchar_t *)CoTaskMemAlloc(2 * cb);
  *ppszDesc = v11;
  if ( !v11 )
    return -2147024882;
  if ( RegQueryValueExW(hKey, szLCID, 0, 0, (LPBYTE)v11, &cb) )
  {
    CoTaskMemFree(*ppszDesc);
    *ppszDesc = 0;
    return -2147221151;
  }
  if ( plcid )
    *plcid = UserDefaultLCID;
  return 0;
}

```

## disassembly

```asm
0x1800a867c  push    rbp
0x1800a867e  push    rbx
0x1800a867f  push    rsi
0x1800a8680  push    rdi
0x1800a8681  push    r12
0x1800a8683  push    r13
0x1800a8685  push    r14
0x1800a8687  push    r15
0x1800a8689  lea     rbp, [rsp-1Fh]
0x1800a868e  sub     rsp, 0C8h
0x1800a8695  mov     rax, cs:__security_cookie
0x1800a869c  xor     rax, rsp
0x1800a869f  mov     [rbp+57h+var_48], rax
0x1800a86a3  xor     r13d, r13d
0x1800a86a6  lea     rax, [rbp+57h+dwNumValues]
0x1800a86aa  mov     [rsp+100h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800a86af  mov     r15, plcid
0x1800a86b2  mov     [rsp+100h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x1800a86b7  mov     r14, ppszDesc
0x1800a86ba  mov     [rsp+100h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x1800a86bf  mov     ebx, lcid
0x1800a86c1  mov     [rsp+100h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x1800a86c6  lea     esi, [r13+10h]
0x1800a86ca  mov     [rsp+100h+lpcValues], rax; lpcValues
0x1800a86cf  xor     r9d, r9d; lpReserved
0x1800a86d2  mov     [rsp+100h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x1800a86d7  xor     r8d, r8d; lpcchClass
0x1800a86da  mov     [rsp+100h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x1800a86df  xor     lcid, lcid; lpClass
0x1800a86e1  mov     [rsp+100h+lpcSubKeys], r13; lpcSubKeys
0x1800a86e6  mov     rdi, hKey
0x1800a86e9  mov     [rbp+57h+cb], r13d
0x1800a86ed  mov     [rbp+57h+dwNumValues], r13d
0x1800a86f1  mov     [rbp+57h+dwSizeNameBuf], esi
0x1800a86f4  call    cs:__imp_RegQueryInfoKeyW
0x1800a86fa  test    eax, eax
0x1800a86fc  jnz     loc_1800A8980
0x1800a8702  mov     eax, [rbp+57h+dwNumValues]
0x1800a8705  test    eax, eax
0x1800a8707  jz      loc_1800A8980
0x1800a870d  cmp     eax, 1
0x1800a8710  jnz     short loc_1800A8745
0x1800a8712  lea     rax, [rbp+57h+cb]
0x1800a8716  xor     lcid, lcid; dwIndex
0x1800a8718  mov     [rsp+100h+lpcValues], rax; lpcbData
0x1800a871d  lea     plcid, [rbp+57h+dwSizeNameBuf]; lpcchValueName
0x1800a8721  mov     [rsp+100h+lpcbMaxClassLen], r13; lpData
0x1800a8726  lea     ppszDesc, [rbp+57h+szLCID]; lpValueName
0x1800a872a  mov     [rsp+100h+lpcbMaxSubKeyLen], r13; lpType
0x1800a872f  mov     hKey, rdi; hKey
0x1800a8732  mov     [rsp+100h+lpcSubKeys], r13; lpReserved
0x1800a8737  call    cs:__imp_RegEnumValueW
0x1800a873d  mov     r8d, esi
0x1800a8740  jmp     loc_1800A8920
0x1800a8745  mov     esi, 1Eh
0x1800a874a  lea     ppszDesc, asc_1800E06D0; "%#x"
0x1800a8751  mov     lcid, esi; cchDest
0x1800a8753  lea     hKey, [rbp+57h+szLCID]; pszDest
0x1800a8757  mov     r9d, ebx
0x1800a875a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a875f  test    eax, eax
0x1800a8761  js      loc_1800A8985
0x1800a8767  lea     rax, [rbp+57h+cb]
0x1800a876b  xor     r9d, r9d; lpType
0x1800a876e  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800a8773  lea     rdx, [rbp+57h+szLCID]; lpValueName
0x1800a8777  xor     r8d, r8d; lpReserved
0x1800a877a  mov     [rsp+100h+lpcSubKeys], r13; lpData
0x1800a877f  mov     hKey, rdi; hKey
0x1800a8782  call    cs:__imp_RegQueryValueExW
0x1800a8788  test    eax, eax
0x1800a878a  jz      $process
0x1800a8790  mov     eax, 3FFh
0x1800a8795  lea     ppszDesc, asc_1800E06D0; "%#x"
0x1800a879c  and     bx, ax
0x1800a879f  lea     hKey, [rbp+57h+szLCID]; pszDest
0x1800a87a3  movzx   r12d, bx
0x1800a87a7  mov     lcid, esi; cchDest
0x1800a87a9  mov     ebx, r12d
0x1800a87ac  bts     ebx, 0Ah
0x1800a87b0  mov     r9d, ebx
0x1800a87b3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a87b8  test    eax, eax
0x1800a87ba  js      loc_1800A8985
0x1800a87c0  lea     rax, [rbp+57h+cb]
0x1800a87c4  xor     r9d, r9d; lpType
0x1800a87c7  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800a87cc  lea     rdx, [rbp+57h+szLCID]; lpValueName
0x1800a87d0  xor     r8d, r8d; lpReserved
0x1800a87d3  mov     [rsp+100h+lpcSubKeys], r13; lpData
0x1800a87d8  mov     hKey, rdi; hKey
0x1800a87db  mov     esi, r13d
0x1800a87de  call    cs:__imp_RegQueryValueExW
0x1800a87e4  test    eax, eax
0x1800a87e6  jz      $process
0x1800a87ec  lea     rax, [rbp+57h+cb]
0x1800a87f0  mov     ebx, 10h
0x1800a87f5  mov     [rsp+100h+lpcValues], rax; lpcbData
0x1800a87fa  lea     plcid, [rbp+57h+dwSizeNameBuf]; lpcchValueName
0x1800a87fe  mov     [rsp+100h+lpcbMaxClassLen], r13; lpData
0x1800a8803  lea     ppszDesc, [rbp+57h+szLCID]; lpValueName
0x1800a8807  mov     [rsp+100h+lpcbMaxSubKeyLen], r13; lpType
0x1800a880c  mov     lcid, esi; dwIndex
0x1800a880e  mov     hKey, rdi; hKey
0x1800a8811  mov     [rsp+100h+lpcSubKeys], r13; lpReserved
0x1800a8816  mov     [rbp+57h+dwSizeNameBuf], ebx
0x1800a8819  call    cs:__imp_RegEnumValueW
0x1800a881f  test    eax, eax
0x1800a8821  jnz     short loc_1800A8850
0x1800a8823  mov     r8d, ebx; Radix
0x1800a8826  mov     [rbp+57h+EndPtr], r13
0x1800a882a  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x1800a882e  lea     hKey, [rbp+57h+szLCID]; String
0x1800a8832  call    cs:__imp_wcstoul
0x1800a8838  mov     ecx, 3FFh
0x1800a883d  mov     ebx, eax
0x1800a883f  and     ax, cx
0x1800a8842  cmp     ax, r12w
0x1800a8846  jz      $process
0x1800a884c  inc     esi
0x1800a884e  jmp     short loc_1800A87EC
0x1800a8850  call    cs:__imp_GetUserDefaultLCID
0x1800a8856  mov     esi, 1Eh
0x1800a885b  lea     ppszDesc, asc_1800E06D0; "%#x"
0x1800a8862  mov     r9d, eax
0x1800a8865  lea     hKey, [rbp+57h+szLCID]; pszDest
0x1800a8869  mov     lcid, esi; cchDest
0x1800a886b  mov     ebx, eax
0x1800a886d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a8872  test    eax, eax
0x1800a8874  js      loc_1800A8985
0x1800a887a  lea     rax, [rbp+57h+cb]
0x1800a887e  xor     r9d, r9d; lpType
0x1800a8881  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800a8886  lea     rdx, [rbp+57h+szLCID]; lpValueName
0x1800a888a  xor     r8d, r8d; lpReserved
0x1800a888d  mov     [rsp+100h+lpcSubKeys], r13; lpData
0x1800a8892  mov     hKey, rdi; hKey
0x1800a8895  call    cs:__imp_RegQueryValueExW
0x1800a889b  test    eax, eax
0x1800a889d  jz      $process
0x1800a88a3  call    cs:__imp_GetSystemDefaultLCID
0x1800a88a9  lea     ppszDesc, asc_1800E06D0; "%#x"
0x1800a88b0  mov     lcid, esi; cchDest
0x1800a88b2  mov     r9d, eax
0x1800a88b5  lea     hKey, [rbp+57h+szLCID]; pszDest
0x1800a88b9  mov     ebx, eax
0x1800a88bb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a88c0  test    eax, eax
0x1800a88c2  js      loc_1800A8985
0x1800a88c8  lea     rax, [rbp+57h+cb]
0x1800a88cc  xor     r9d, r9d; lpType
0x1800a88cf  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800a88d4  lea     rdx, [rbp+57h+szLCID]; lpValueName
0x1800a88d8  xor     r8d, r8d; lpReserved
0x1800a88db  mov     [rsp+100h+lpcSubKeys], r13; lpData
0x1800a88e0  mov     hKey, rdi; hKey
0x1800a88e3  call    cs:__imp_RegQueryValueExW
0x1800a88e9  test    eax, eax
0x1800a88eb  jz      short $process
0x1800a88ed  lea     rax, [rbp+57h+cb]
0x1800a88f1  xor     lcid, lcid; dwIndex
0x1800a88f3  mov     [rsp+100h+lpcValues], rax; lpcbData
0x1800a88f8  lea     plcid, [rbp+57h+dwSizeNameBuf]; lpcchValueName
0x1800a88fc  mov     [rsp+100h+lpcbMaxClassLen], r13; lpData
0x1800a8901  lea     ppszDesc, [rbp+57h+szLCID]; lpValueName
0x1800a8905  mov     [rsp+100h+lpcbMaxSubKeyLen], r13; lpType
0x1800a890a  mov     hKey, rdi; hKey
0x1800a890d  mov     [rsp+100h+lpcSubKeys], r13; lpReserved
0x1800a8912  call    cs:__imp_RegEnumValueW
0x1800a8918  test    eax, eax
0x1800a891a  jnz     short loc_1800A8980
0x1800a891c  lea     r8d, [rsi-0Eh]; Radix
0x1800a8920  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x1800a8924  mov     [rbp+57h+EndPtr], r13
0x1800a8928  lea     hKey, [rbp+57h+szLCID]; String
0x1800a892c  call    cs:__imp_wcstoul
0x1800a8932  mov     ebx, eax
0x1800a8934  mov     eax, [rbp+57h+cb]
0x1800a8937  lea     ecx, [rax+rax]; cb
0x1800a893a  call    cs:__imp_CoTaskMemAlloc
0x1800a8940  mov     [r14], rax
0x1800a8943  test    rax, rax
0x1800a8946  jnz     short loc_1800A894F
0x1800a8948  mov     eax, 8007000Eh
0x1800a894d  jmp     short loc_1800A8985
0x1800a894f  lea     hKey, [rbp+57h+cb]
0x1800a8953  xor     r9d, r9d; lpType
0x1800a8956  mov     [rsp+100h+lpcbMaxSubKeyLen], hKey; lpcbData
0x1800a895b  lea     rdx, [rbp+57h+szLCID]; lpValueName
0x1800a895f  mov     hKey, rdi; hKey
0x1800a8962  mov     [rsp+100h+lpcSubKeys], rax; lpData
0x1800a8967  xor     r8d, r8d; lpReserved
0x1800a896a  call    cs:__imp_RegQueryValueExW
0x1800a8970  test    eax, eax
0x1800a8972  jz      short loc_1800A89A5
0x1800a8974  mov     hKey, [r14]; pv
0x1800a8977  call    cs:__imp_CoTaskMemFree
0x1800a897d  mov     [r14], r13
0x1800a8980  mov     eax, 80040161h
0x1800a8985  mov     hKey, [rbp+57h+var_48]
0x1800a8989  xor     hKey, rsp; StackCookie
0x1800a898c  call    __security_check_cookie
0x1800a8991  add     rsp, 0C8h
0x1800a8998  pop     r15
0x1800a899a  pop     r14
0x1800a899c  pop     r13
0x1800a899e  pop     r12
0x1800a89a0  pop     rdi
0x1800a89a1  pop     rsi
0x1800a89a2  pop     rbx
0x1800a89a3  pop     rbp
0x1800a89a4  retn
0x1800a89a5  test    r15, r15
0x1800a89a8  jz      short loc_1800A89AD
0x1800a89aa  mov     [r15], ebx
0x1800a89ad  xor     eax, eax
0x1800a89af  jmp     short loc_1800A8985
```
