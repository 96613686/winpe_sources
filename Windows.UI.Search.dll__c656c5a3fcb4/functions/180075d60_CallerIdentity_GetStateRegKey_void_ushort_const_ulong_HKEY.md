# CallerIdentity::GetStateRegKey(void *,ushort const *,ulong,HKEY__ * *)

- ea: `0x180075d60`
- end: `0x180075ef4`
- name: `?GetStateRegKey@CallerIdentity@@YAJPEAXPEBGKPEAPEAUHKEY__@@@Z`
- size: `404`
- prototype: `int(CallerIdentity *__hidden this, void *, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180075b90`

## callees

- `0x1800033ae`
- `0x180010fd0`
- `0x18001f424`
- `0x180075d60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180075e99`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180075e99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075ebb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075ed2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075ebb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075ed2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075e47`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075e47`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x180075d97`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x180075e0c`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x180075d97`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x180075e0c`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetStateRegKey(CallerIdentity *this, HKEY a2, const unsigned __int16 *a3, HKEY *a4)
{
  signed int Error; // edi
  __int64 v7; // rdx
  __int64 v8; // rcx
  LSTATUS v9; // eax
  LSTATUS Key; // eax
  HKEY v11; // rcx
  HKEY v12; // rcx
  HKEY phkResult; // [rsp+88h] [rbp+28h] BYREF
  int v15; // [rsp+90h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+38h] BYREF

  phkResult = a2;
  *a4 = 0;
  v15 = 0;
  if ( (unsigned int)GetSystemAppDataKey(this, 0, 0, &v15) )
  {
    return (unsigned int)-2147418113;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 && v15 )
    {
      CoTaskMemFree_0(0);
      Error = _AllocStringWorker<CTCoAllocPolicy>(v8, v7, 0);
      if ( Error >= 0 )
      {
        hKey = 0;
        if ( (unsigned int)GetSystemAppDataKey(this, &hKey, 0, &v15) || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          phkResult = 0;
          v9 = RegOpenKeyExW(hKey, 0, 0, 0x2001Fu, &phkResult);
          Error = v9;
          if ( v9 > 0 )
            Error = (unsigned __int16)v9 | 0x80070000;
          if ( Error >= 0 )
          {
            Key = RegCreateKeyExW(phkResult, L"SplashScreen", 0, 0, 0, 0x20019u, 0, a4, 0);
            Error = Key;
            if ( Key > 0 )
              Error = (unsigned __int16)Key | 0x80070000;
          }
          v11 = phkResult;
          phkResult = 0;
          if ( v11 )
            RegCloseKey(v11);
        }
        v12 = hKey;
        hKey = 0;
        if ( v12 )
          RegCloseKey(v12);
      }
      CoTaskMemFree_0(0);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180075d60  mov     [rsp-18h+arg_0], rsi
0x180075d65  mov     [rsp-18h+arg_10], r8d
0x180075d6a  mov     [rsp-18h+arg_8], rdx
0x180075d6f  push    rbp
0x180075d70  push    rdi
0x180075d71  push    r14
0x180075d73  mov     rbp, rsp
0x180075d76  sub     rsp, 60h
0x180075d7a  mov     r14, r9
0x180075d7d  mov     qword ptr [r9], 0
0x180075d84  lea     r9, [rbp+arg_10]
0x180075d88  mov     [rbp+arg_10], 0
0x180075d8f  xor     r8d, r8d
0x180075d92  xor     edx, edx
0x180075d94  mov     rsi, rcx
0x180075d97  call    cs:__imp_GetSystemAppDataKey
0x180075d9d  test    eax, eax
0x180075d9f  jz      short loc_180075DAB
0x180075da1  mov     edi, 8000FFFFh
0x180075da6  jmp     loc_180075EE1
0x180075dab  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180075db0  mov     edi, eax
0x180075db2  cmp     eax, 8007007Ah
0x180075db7  jnz     loc_180075EE1
0x180075dbd  cmp     [rbp+arg_10], 0
0x180075dc1  jbe     loc_180075EE1
0x180075dc7  xor     ecx, ecx; pv
0x180075dc9  mov     [rbp+lpSubKey], 0
0x180075dd1  call    CoTaskMemFree_0
0x180075dd6  mov     r9d, [rbp+arg_10]
0x180075dda  lea     rax, [rbp+lpSubKey]
0x180075dde  xor     r8d, r8d
0x180075de1  mov     qword ptr [rsp+60h+samDesired], rax
0x180075de6  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180075deb  mov     edi, eax
0x180075ded  test    eax, eax
0x180075def  js      loc_180075ED8
0x180075df5  mov     r8, [rbp+lpSubKey]
0x180075df9  lea     r9, [rbp+arg_10]
0x180075dfd  lea     rdx, [rbp+hKey]
0x180075e01  mov     [rbp+hKey], 0
0x180075e09  mov     rcx, rsi
0x180075e0c  call    cs:__imp_GetSystemAppDataKey
0x180075e12  test    eax, eax
0x180075e14  jnz     short loc_180075E25
0x180075e16  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180075e1b  mov     edi, eax
0x180075e1d  test    eax, eax
0x180075e1f  js      loc_180075EC1
0x180075e25  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180075e29  lea     rax, [rbp+arg_8]
0x180075e2d  mov     rcx, [rbp+hKey]; hKey
0x180075e31  mov     r9d, 2001Fh; samDesired
0x180075e37  xor     r8d, r8d; ulOptions
0x180075e3a  mov     [rsp+60h+phkResult], rax; phkResult
0x180075e3f  mov     [rbp+arg_8], 0
0x180075e47  call    cs:__imp_RegOpenKeyExW
0x180075e4d  mov     edi, eax
0x180075e4f  mov     esi, 80070000h
0x180075e54  test    eax, eax
0x180075e56  jle     short loc_180075E5D
0x180075e58  movzx   edi, ax
0x180075e5b  or      edi, esi
0x180075e5d  test    edi, edi
0x180075e5f  js      short loc_180075EAA
0x180075e61  mov     rcx, [rbp+arg_8]; hKey
0x180075e65  lea     rdx, aSplashscreen; "SplashScreen"
0x180075e6c  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x180075e75  xor     r9d, r9d; lpClass
0x180075e78  mov     [rsp+60h+var_28], r14; phkResult
0x180075e7d  xor     r8d, r8d; Reserved
0x180075e80  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180075e89  mov     [rsp+60h+samDesired], 20019h; samDesired
0x180075e91  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x180075e99  call    cs:__imp_RegCreateKeyExW
0x180075e9f  mov     edi, eax
0x180075ea1  test    eax, eax
0x180075ea3  jle     short loc_180075EAA
0x180075ea5  movzx   edi, ax
0x180075ea8  or      edi, esi
0x180075eaa  mov     rcx, [rbp+arg_8]; hKey
0x180075eae  mov     [rbp+arg_8], 0
0x180075eb6  test    rcx, rcx
0x180075eb9  jz      short loc_180075EC1
0x180075ebb  call    cs:__imp_RegCloseKey
0x180075ec1  mov     rcx, [rbp+hKey]; hKey
0x180075ec5  mov     [rbp+hKey], 0
0x180075ecd  test    rcx, rcx
0x180075ed0  jz      short loc_180075ED8
0x180075ed2  call    cs:__imp_RegCloseKey
0x180075ed8  mov     rcx, [rbp+lpSubKey]; pv
0x180075edc  call    CoTaskMemFree_0
0x180075ee1  mov     rsi, [rsp+60h+arg_0]
0x180075ee9  mov     eax, edi
0x180075eeb  add     rsp, 60h
0x180075eef  pop     r14
0x180075ef1  pop     rdi
0x180075ef2  pop     rbp
0x180075ef3  retn
```
