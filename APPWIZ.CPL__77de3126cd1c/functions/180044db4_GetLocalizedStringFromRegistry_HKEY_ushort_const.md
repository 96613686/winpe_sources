# GetLocalizedStringFromRegistry(HKEY__ *,ushort const *)

- ea: `0x180044db4`
- end: `0x180044f78`
- name: `?GetLocalizedStringFromRegistry@@YAPEAGPEAUHKEY__@@PEBG@Z`
- size: `452`
- prototype: `unsigned __int16 *__fastcall(HKEY hkey, LPCWSTR lpString1)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001bebc`
- `0x180029da8`
- `0x18002a3e0`
- `0x18002a9e0`
- `0x18002af50`
- `0x18002cce8`

## callees

- `0x180007960`
- `0x180044db4`
- `0x1800582e0`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x180044e42`
- `SHCORE!SHStrDupW` at `0x180044ecf`
- `SHCORE!SHStrDupW` at `0x180044f0b`
- `SHCORE!SHStrDupW` at `0x180044e42`
- `SHCORE!SHStrDupW` at `0x180044ecf`
- `SHCORE!SHStrDupW` at `0x180044f0b`
- `SHCORE!SHQueryValueExW` at `0x180044e70`
- `SHCORE!SHQueryValueExW` at `0x180044eac`
- `SHCORE!SHQueryValueExW` at `0x180044e70`
- `SHCORE!SHQueryValueExW` at `0x180044eac`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x180044e28`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x180044e28`
- `SHLWAPI!PathFileExistsW` at `0x180044f25`
- `SHLWAPI!PathFileExistsW` at `0x180044f25`
- `SHLWAPI!PathParseIconLocationW` at `0x180044f1a`
- `SHLWAPI!PathParseIconLocationW` at `0x180044f1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044ed8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044ed8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180044e81`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180044e81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044f32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044f41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044f32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044f41`
- `KERNEL32!lstrcmpW` at `0x180044ef2`
- `KERNEL32!lstrcmpW` at `0x180044ef2`

## pseudocode

```c
unsigned __int16 *__fastcall GetLocalizedStringFromRegistry(HKEY hkey, LPCWSTR lpString1)
{
  WCHAR *pvData; // rbx
  unsigned __int16 *result; // rax
  BOOL v6; // ebx
  DWORD pcbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pdwType; // [rsp+34h] [rbp-CCh] BYREF
  LPWSTR ppwsz; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR pszIconFile; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v11[32]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR psz[264]; // [rsp+90h] [rbp-70h] BYREF

  pcbData = 0;
  pdwType = 0;
  ppwsz = 0;
  if ( StringCchPrintfW(v11, 0x20u, L"%s_Localized", lpString1) >= 0
    && (int)SHLoadRegUIStringW(hkey, v11, psz, 260) >= 0
    && psz[0] )
  {
    SHStrDupW(psz, &ppwsz);
  }
  if ( ppwsz )
    goto LABEL_21;
  if ( !SHQueryValueExW(hkey, lpString1, 0, &pdwType, 0, &pcbData) )
  {
    pvData = (WCHAR *)LocalAlloc(0x40u, pcbData);
    if ( pvData )
    {
      if ( !SHQueryValueExW(hkey, lpString1, 0, &pdwType, pvData, &pcbData) )
      {
        if ( pdwType - 1 <= 1 && *pvData )
          SHStrDupW(pvData, &ppwsz);
        LocalFree(pvData);
      }
    }
  }
  result = ppwsz;
  if ( ppwsz )
  {
LABEL_21:
    if ( lstrcmpW(lpString1, L"DisplayIcon") )
      return ppwsz;
    pszIconFile = 0;
    if ( SHStrDupW(ppwsz, &pszIconFile) >= 0
      && (PathParseIconLocationW(pszIconFile), v6 = PathFileExistsW(pszIconFile), CoTaskMemFree(pszIconFile), v6) )
    {
      return ppwsz;
    }
    else
    {
      CoTaskMemFree(ppwsz);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180044db4  mov     [rsp-8+arg_10], rbx
0x180044db9  mov     [rsp-8+arg_18], rsi
0x180044dbe  push    rbp
0x180044dbf  push    rdi
0x180044dc0  push    r14
0x180044dc2  lea     rbp, [rsp-1B0h]
0x180044dca  sub     rsp, 2B0h
0x180044dd1  mov     rax, cs:__security_cookie
0x180044dd8  xor     rax, rsp
0x180044ddb  mov     [rbp+1C0h+var_20], rax
0x180044de2  xor     r14d, r14d
0x180044de5  lea     r8, aSLocalized; "%s_Localized"
0x180044dec  mov     rdi, rdx
0x180044def  mov     [rsp+2C0h+var_290], r14d
0x180044df4  mov     rsi, rcx
0x180044df7  mov     [rsp+2C0h+pdwType], r14d
0x180044dfc  mov     r9, rdx
0x180044dff  mov     [rsp+2C0h+ppwsz], r14
0x180044e04  lea     edx, [r14+20h]; unsigned __int64
0x180044e08  lea     rcx, [rsp+2C0h+var_270]; unsigned __int16 *
0x180044e0d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180044e12  test    eax, eax
0x180044e14  js      short loc_180044E48
0x180044e16  mov     r9d, 104h
0x180044e1c  lea     r8, [rbp+1C0h+psz]
0x180044e20  lea     rdx, [rsp+2C0h+var_270]
0x180044e25  mov     rcx, rsi
0x180044e28  call    cs:__imp_SHLoadRegUIStringW
0x180044e2e  test    eax, eax
0x180044e30  js      short loc_180044E48
0x180044e32  cmp     [rbp+1C0h+psz], r14w
0x180044e37  jz      short loc_180044E48
0x180044e39  lea     rdx, [rsp+2C0h+ppwsz]; ppwsz
0x180044e3e  lea     rcx, [rbp+1C0h+psz]; psz
0x180044e42  call    cs:__imp_SHStrDupW
0x180044e48  cmp     [rsp+2C0h+ppwsz], r14
0x180044e4d  jnz     loc_180044EE8
0x180044e53  lea     rax, [rsp+2C0h+var_290]
0x180044e58  xor     r8d, r8d; pdwReserved
0x180044e5b  mov     [rsp+2C0h+pcbData], rax; pcbData
0x180044e60  lea     r9, [rsp+2C0h+pdwType]; pdwType
0x180044e65  mov     rdx, rdi; pszValue
0x180044e68  mov     [rsp+2C0h+pvData], r14; pvData
0x180044e6d  mov     rcx, rsi; hkey
0x180044e70  call    cs:__imp_SHQueryValueExW
0x180044e76  test    eax, eax
0x180044e78  jnz     short loc_180044EDE
0x180044e7a  mov     edx, [rsp+2C0h+var_290]; uBytes
0x180044e7e  lea     ecx, [rax+40h]; uFlags
0x180044e81  call    cs:__imp_LocalAlloc
0x180044e87  mov     rbx, rax
0x180044e8a  test    rax, rax
0x180044e8d  jz      short loc_180044EDE
0x180044e8f  lea     rax, [rsp+2C0h+var_290]
0x180044e94  xor     r8d, r8d; pdwReserved
0x180044e97  mov     [rsp+2C0h+pcbData], rax; pcbData
0x180044e9c  lea     r9, [rsp+2C0h+pdwType]; pdwType
0x180044ea1  mov     rdx, rdi; pszValue
0x180044ea4  mov     [rsp+2C0h+pvData], rbx; pvData
0x180044ea9  mov     rcx, rsi; hkey
0x180044eac  call    cs:__imp_SHQueryValueExW
0x180044eb2  test    eax, eax
0x180044eb4  jnz     short loc_180044EDE
0x180044eb6  mov     eax, [rsp+2C0h+pdwType]
0x180044eba  dec     eax
0x180044ebc  cmp     eax, 1
0x180044ebf  ja      short loc_180044ED5
0x180044ec1  cmp     [rbx], r14w
0x180044ec5  jz      short loc_180044ED5
0x180044ec7  lea     rdx, [rsp+2C0h+ppwsz]; ppwsz
0x180044ecc  mov     rcx, rbx; psz
0x180044ecf  call    cs:__imp_SHStrDupW
0x180044ed5  mov     rcx, rbx; hMem
0x180044ed8  call    cs:__imp_LocalFree
0x180044ede  mov     rax, [rsp+2C0h+ppwsz]
0x180044ee3  test    rax, rax
0x180044ee6  jz      short loc_180044F51
0x180044ee8  lea     rdx, aDisplayicon; "DisplayIcon"
0x180044eef  mov     rcx, rdi; lpString1
0x180044ef2  call    cs:__imp_lstrcmpW
0x180044ef8  test    eax, eax
0x180044efa  jnz     short loc_180044F4C
0x180044efc  mov     rcx, [rsp+2C0h+ppwsz]; psz
0x180044f01  lea     rdx, [rsp+2C0h+pszIconFile]; ppwsz
0x180044f06  mov     [rsp+2C0h+pszIconFile], r14
0x180044f0b  call    cs:__imp_SHStrDupW
0x180044f11  test    eax, eax
0x180044f13  js      short loc_180044F3C
0x180044f15  mov     rcx, [rsp+2C0h+pszIconFile]; pszIconFile
0x180044f1a  call    cs:__imp_PathParseIconLocationW
0x180044f20  mov     rcx, [rsp+2C0h+pszIconFile]; pszPath
0x180044f25  call    cs:__imp_PathFileExistsW
0x180044f2b  mov     rcx, [rsp+2C0h+pszIconFile]; pv
0x180044f30  mov     ebx, eax
0x180044f32  call    cs:__imp_CoTaskMemFree
0x180044f38  test    ebx, ebx
0x180044f3a  jnz     short loc_180044F4C
0x180044f3c  mov     rcx, [rsp+2C0h+ppwsz]; pv
0x180044f41  call    cs:__imp_CoTaskMemFree
0x180044f47  mov     rax, r14
0x180044f4a  jmp     short loc_180044F51
0x180044f4c  mov     rax, [rsp+2C0h+ppwsz]
0x180044f51  mov     rcx, [rbp+1C0h+var_20]
0x180044f58  xor     rcx, rsp; StackCookie
0x180044f5b  call    __security_check_cookie
0x180044f60  lea     r11, [rsp+2C0h+var_10]
0x180044f68  mov     rbx, [r11+30h]
0x180044f6c  mov     rsi, [r11+38h]
0x180044f70  mov     rsp, r11
0x180044f73  pop     r14
0x180044f75  pop     rdi
0x180044f76  pop     rbp
0x180044f77  retn
```
