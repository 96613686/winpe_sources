# GetPreferredAccountForUrl(ushort *,ushort * *)

- ea: `0x18001cdf0`
- end: `0x18001cf21`
- name: `?GetPreferredAccountForUrl@@YAKPEAGPEAPEAG@Z`
- size: `305`
- prototype: `unsigned int __fastcall(wchar_t *lpwszUrl, wchar_t **lpwszUserName)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c980`

## callees

- `0x18001cdf0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ceff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cf0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ceff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cf0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ce3c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ce65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ce3c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ce65`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ce94`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001cedc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ce94`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001cedc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cea6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cea6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cef0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cef0`

## string_xrefs

- `0x18001ce20`: `Software\Microsoft\Web Authentication Broker`

## pseudocode

```c
__int64 __fastcall GetPreferredAccountForUrl(wchar_t *lpwszUrl, wchar_t **lpwszUserName)
{
  HLOCAL pvData; // rdi
  unsigned int ValueW; // ebx
  unsigned int dwLocalUserNameSize; // [rsp+78h] [rbp+38h] BYREF
  HKEY__ *hSiteKey; // [rsp+80h] [rbp+40h] BYREF
  HKEY__ *hWABRootKey; // [rsp+88h] [rbp+48h] BYREF

  pvData = 0;
  hWABRootKey = 0;
  *lpwszUserName = 0;
  hSiteKey = 0;
  dwLocalUserNameSize = 0;
  ValueW = RegOpenKeyExW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Web Authentication Broker",
             0,
             0x20019u,
             &hWABRootKey);
  if ( !ValueW )
  {
    ValueW = RegOpenKeyExW(hWABRootKey, lpwszUrl, 0, 0x20019u, &hSiteKey);
    if ( !ValueW )
    {
      ValueW = RegGetValueW(hSiteKey, 0, 0, 2u, 0, 0, &dwLocalUserNameSize);
      if ( !ValueW )
      {
        pvData = LocalAlloc(0x40u, dwLocalUserNameSize);
        if ( pvData )
        {
          ValueW = RegGetValueW(hSiteKey, 0, 0, 2u, 0, pvData, &dwLocalUserNameSize);
          if ( !ValueW )
          {
            *lpwszUserName = (wchar_t *)pvData;
            pvData = 0;
          }
        }
        else
        {
          ValueW = 8;
        }
      }
    }
  }
  LocalFree(pvData);
  if ( hSiteKey )
    RegCloseKey(hSiteKey);
  if ( hWABRootKey )
    RegCloseKey(hWABRootKey);
  return ValueW;
}

```

## disassembly

```asm
0x18001cdf0  push    rbp
0x18001cdf2  push    rbx
0x18001cdf3  push    rsi
0x18001cdf4  push    rdi
0x18001cdf5  push    r14
0x18001cdf7  mov     rbp, rsp
0x18001cdfa  sub     rsp, 40h
0x18001cdfe  xor     edi, edi
0x18001ce00  mov     [rbp+hWABRootKey], 0
0x18001ce08  mov     [lpwszUserName], rdi
0x18001ce0b  lea     rax, [rbp+hWABRootKey]
0x18001ce0f  mov     rsi, lpwszUserName
0x18001ce12  mov     [rbp+hSiteKey], 0
0x18001ce1a  mov     r14, lpwszUrl
0x18001ce1d  mov     [rbp+dwLocalUserNameSize], edi
0x18001ce20  lea     lpwszUserName, aSoftwareMicros_5; "Software\\Microsoft\\Web Authentication"...
0x18001ce27  mov     [rsp+40h+phkResult], rax; phkResult
0x18001ce2c  mov     r9d, 20019h; samDesired
0x18001ce32  xor     r8d, r8d; ulOptions
0x18001ce35  mov     lpwszUrl, 0FFFFFFFF80000001h; hKey
0x18001ce3c  call    cs:__imp_RegOpenKeyExW
0x18001ce42  mov     ebx, eax
0x18001ce44  test    eax, eax
0x18001ce46  jnz     $Cleanup_10
0x18001ce4c  mov     lpwszUrl, [rbp+hWABRootKey]; hKey
0x18001ce50  lea     rax, [rbp+hSiteKey]
0x18001ce54  mov     r9d, 20019h; samDesired
0x18001ce5a  mov     [rsp+40h+phkResult], rax; phkResult
0x18001ce5f  xor     r8d, r8d; ulOptions
0x18001ce62  mov     lpwszUserName, r14; lpSubKey
0x18001ce65  call    cs:__imp_RegOpenKeyExW
0x18001ce6b  mov     ebx, eax
0x18001ce6d  test    eax, eax
0x18001ce6f  jnz     short $Cleanup_10
0x18001ce71  mov     lpwszUrl, [rbp+hSiteKey]; hkey
0x18001ce75  lea     rax, [rbp+dwLocalUserNameSize]
0x18001ce79  mov     [rsp+40h+pcbData], rax; pcbData
0x18001ce7e  lea     r14d, [rdi+2]
0x18001ce82  mov     [rsp+40h+pvData], rdi; pvData
0x18001ce87  mov     r9d, r14d; dwFlags
0x18001ce8a  xor     r8d, r8d; lpValue
0x18001ce8d  mov     [rsp+40h+phkResult], rdi; pdwType
0x18001ce92  xor     edx, edx; lpSubKey
0x18001ce94  call    cs:__imp_RegGetValueW
0x18001ce9a  mov     ebx, eax
0x18001ce9c  test    eax, eax
0x18001ce9e  jnz     short $Cleanup_10
0x18001cea0  mov     edx, [rbp+dwLocalUserNameSize]; uBytes
0x18001cea3  lea     ecx, [rdi+40h]; uFlags
0x18001cea6  call    cs:__imp_LocalAlloc
0x18001ceac  mov     rdi, rax
0x18001ceaf  test    rax, rax
0x18001ceb2  jnz     short loc_18001CEB9
0x18001ceb4  lea     ebx, [rax+8]
0x18001ceb7  jmp     short $Cleanup_10
0x18001ceb9  mov     lpwszUrl, [rbp+hSiteKey]; hkey
0x18001cebd  lea     rax, [rbp+dwLocalUserNameSize]
0x18001cec1  mov     [rsp+40h+pcbData], rax; pcbData
0x18001cec6  mov     r9d, r14d; dwFlags
0x18001cec9  mov     [rsp+40h+pvData], rdi; pvData
0x18001cece  xor     r8d, r8d; lpValue
0x18001ced1  xor     edx, edx; lpSubKey
0x18001ced3  mov     [rsp+40h+phkResult], 0; pdwType
0x18001cedc  call    cs:__imp_RegGetValueW
0x18001cee2  mov     ebx, eax
0x18001cee4  test    eax, eax
0x18001cee6  jnz     short $Cleanup_10
0x18001cee8  mov     [rsi], rdi
0x18001ceeb  xor     edi, edi
0x18001ceed  mov     lpwszUrl, rdi; hMem
0x18001cef0  call    cs:__imp_LocalFree
0x18001cef6  mov     lpwszUrl, [rbp+hSiteKey]; hKey
0x18001cefa  test    lpwszUrl, lpwszUrl
0x18001cefd  jz      short loc_18001CF05
0x18001ceff  call    cs:__imp_RegCloseKey
0x18001cf05  mov     lpwszUrl, [rbp+hWABRootKey]; hKey
0x18001cf09  test    lpwszUrl, lpwszUrl
0x18001cf0c  jz      short loc_18001CF14
0x18001cf0e  call    cs:__imp_RegCloseKey
0x18001cf14  mov     eax, ebx
0x18001cf16  add     rsp, 40h
0x18001cf1a  pop     r14
0x18001cf1c  pop     rdi
0x18001cf1d  pop     rsi
0x18001cf1e  pop     rbx
0x18001cf1f  pop     rbp
0x18001cf20  retn
```
