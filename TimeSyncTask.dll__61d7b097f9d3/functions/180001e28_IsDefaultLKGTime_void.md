# IsDefaultLKGTime(void)

- ea: `0x180001e28`
- end: `0x180001fcd`
- name: `?IsDefaultLKGTime@@YAHXZ`
- size: `421`
- prototype: `_BOOL8(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180002ba0`

## callees

- `0x180001460`
- `0x180001d2a`
- `0x180001e28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001f2c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001f2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f19`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180001f74`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180001f74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001f24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001fa4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001f24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001fa4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001ef7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001ef7`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180001eb5`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180001eb5`

## string_xrefs

- `0x180001ea7`: `System\CurrentControlSet\Services\W32Time\Config`
- `0x180001eae`: `W32TimeConfig`

## pseudocode

```c
_BOOL8 IsDefaultLKGTime(void)
{
  BOOL v0; // edi
  LSTATUS v1; // r12d
  HKEY *v2; // rsi
  HKEY v3; // r15
  HKEY v4; // r14
  DWORD LastError; // ebx
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pdwType; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 pvData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY *p_hkey; // [rsp+58h] [rbp-A8h]
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  char v13; // [rsp+68h] [rbp-98h]
  WCHAR SubKey; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v15[526]; // [rsp+72h] [rbp-8Eh] BYREF

  pcbData = 0;
  SubKey = 0;
  pdwType = 0;
  pvData = 0;
  hkey = 0;
  memset_0(v15, 0, 0x206u);
  v0 = 1;
  if ( !(unsigned int)GetPersistedRegistryLocationW(
                        L"W32TimeConfig",
                        L"System\\CurrentControlSet\\Services\\W32Time\\Config",
                        &SubKey,
                        520,
                        0) )
  {
    phkResult = 0;
    p_hkey = &hkey;
    v13 = 1;
    v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, &SubKey, 0, 1u, &phkResult);
    if ( v13 )
    {
      v2 = p_hkey;
      v3 = phkResult;
      v4 = *p_hkey;
      if ( *p_hkey )
      {
        LastError = GetLastError();
        RegCloseKey(v4);
        SetLastError(LastError);
      }
      *v2 = v3;
    }
    if ( !v1 )
    {
      pcbData = 8;
      if ( !RegGetValueW(hkey, 0, L"LastKnownGoodTime", 0xFFFFu, &pdwType, &pvData, &pcbData) && pdwType == 11 )
        v0 = pvData <= 0x1D0CBED024C8000LL;
    }
  }
  if ( hkey )
    RegCloseKey(hkey);
  return v0;
}

```

## disassembly

```asm
0x180001e28  push    rbp
0x180001e2a  push    rbx
0x180001e2b  push    rsi
0x180001e2c  push    rdi
0x180001e2d  push    r12
0x180001e2f  push    r14
0x180001e31  push    r15
0x180001e33  lea     rbp, [rsp-190h]
0x180001e3b  sub     rsp, 290h
0x180001e42  mov     rax, cs:__security_cookie
0x180001e49  xor     rax, rsp
0x180001e4c  mov     [rbp+1C0h+var_40], rax
0x180001e53  xor     eax, eax
0x180001e55  mov     [rsp+2C0h+var_280], 0
0x180001e5d  xor     edx, edx; Val
0x180001e5f  mov     [rsp+2C0h+SubKey], ax
0x180001e64  mov     r8d, 206h; Size
0x180001e6a  mov     [rsp+2C0h+pdwType], 0
0x180001e72  lea     rcx, [rsp+2C0h+var_24E]; void *
0x180001e77  mov     [rsp+2C0h+var_270], 0
0x180001e80  mov     [rsp+2C0h+hkey], 0
0x180001e89  call    memset_0
0x180001e8e  mov     r9d, 208h
0x180001e94  mov     [rsp+2C0h+phkResult], 0
0x180001e9d  lea     r8, [rsp+2C0h+SubKey]
0x180001ea2  mov     edi, 1
0x180001ea7  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x180001eae  lea     rcx, aW32timeconfig; "W32TimeConfig"
0x180001eb5  call    cs:__imp_GetPersistedRegistryLocationW
0x180001ebb  test    eax, eax
0x180001ebd  jnz     loc_180001F9A
0x180001ec3  lea     rax, [rsp+2C0h+hkey]
0x180001ec8  mov     [rsp+2C0h+var_260], 0
0x180001ed1  mov     [rsp+2C0h+var_268], rax
0x180001ed6  lea     rdx, [rsp+2C0h+SubKey]; lpSubKey
0x180001edb  lea     rax, [rsp+2C0h+var_260]
0x180001ee0  mov     [rsp+2C0h+var_258], dil
0x180001ee5  mov     r9d, edi; samDesired
0x180001ee8  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180001eed  xor     r8d, r8d; ulOptions
0x180001ef0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001ef7  call    cs:__imp_RegOpenKeyExW
0x180001efd  cmp     [rsp+2C0h+var_258], 0
0x180001f02  mov     r12d, eax
0x180001f05  jz      short loc_180001F35
0x180001f07  mov     rsi, [rsp+2C0h+var_268]
0x180001f0c  mov     r15, [rsp+2C0h+var_260]
0x180001f11  mov     r14, [rsi]
0x180001f14  test    r14, r14
0x180001f17  jz      short loc_180001F32
0x180001f19  call    cs:__imp_GetLastError
0x180001f1f  mov     rcx, r14; hKey
0x180001f22  mov     ebx, eax
0x180001f24  call    cs:__imp_RegCloseKey
0x180001f2a  mov     ecx, ebx; dwErrCode
0x180001f2c  call    cs:__imp_SetLastError
0x180001f32  mov     [rsi], r15
0x180001f35  test    r12d, r12d
0x180001f38  jnz     short loc_180001F9A
0x180001f3a  mov     rcx, [rsp+2C0h+hkey]; hkey
0x180001f3f  lea     rax, [rsp+2C0h+var_280]
0x180001f44  mov     [rsp+2C0h+pcbData], rax; pcbData
0x180001f49  lea     r8, Value; "LastKnownGoodTime"
0x180001f50  lea     rax, [rsp+2C0h+var_270]
0x180001f55  mov     [rsp+2C0h+var_280], 8
0x180001f5d  mov     [rsp+2C0h+pvData], rax; pvData
0x180001f62  mov     r9d, 0FFFFh; dwFlags
0x180001f68  lea     rax, [rsp+2C0h+pdwType]
0x180001f6d  xor     edx, edx; lpSubKey
0x180001f6f  mov     [rsp+2C0h+phkResult], rax; pdwType
0x180001f74  call    cs:__imp_RegGetValueW
0x180001f7a  test    eax, eax
0x180001f7c  jnz     short loc_180001F9A
0x180001f7e  cmp     [rsp+2C0h+pdwType], 0Bh
0x180001f83  jnz     short loc_180001F9A
0x180001f85  xor     edi, edi
0x180001f87  mov     rax, 1D0CBED024C8000h
0x180001f91  cmp     [rsp+2C0h+var_270], rax
0x180001f96  setbe   dil
0x180001f9a  mov     rcx, [rsp+2C0h+hkey]; hKey
0x180001f9f  test    rcx, rcx
0x180001fa2  jz      short loc_180001FAA
0x180001fa4  call    cs:__imp_RegCloseKey
0x180001faa  mov     eax, edi
0x180001fac  mov     rcx, [rbp+1C0h+var_40]
0x180001fb3  xor     rcx, rsp; StackCookie
0x180001fb6  call    __security_check_cookie
0x180001fbb  add     rsp, 290h
0x180001fc2  pop     r15
0x180001fc4  pop     r14
0x180001fc6  pop     r12
0x180001fc8  pop     rdi
0x180001fc9  pop     rsi
0x180001fca  pop     rbx
0x180001fcb  pop     rbp
0x180001fcc  retn
```
