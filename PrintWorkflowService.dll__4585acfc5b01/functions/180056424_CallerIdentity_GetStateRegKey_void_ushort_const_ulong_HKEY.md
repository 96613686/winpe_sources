# CallerIdentity::GetStateRegKey(void *,ushort const *,ulong,HKEY__ * *)

- ea: `0x180056424`
- end: `0x1800565b8`
- name: `?GetStateRegKey@CallerIdentity@@YAJPEAXPEBGKPEAPEAUHKEY__@@@Z`
- size: `404`
- prototype: `int(CallerIdentity *__hidden this, void *, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180056254`

## callees

- `0x18000505c`
- `0x180053894`
- `0x1800545a0`
- `0x180056424`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005650b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005650b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005655d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005655d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005657f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056596`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005657f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056596`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18005645b`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x1800564d0`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18005645b`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x1800564d0`

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
  unsigned int v15; // [rsp+90h] [rbp+30h] BYREF
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
      Error = _AllocStringWorker<CTCoAllocPolicy>(v8, v7, 0, v15);
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
0x180056424  mov     [rsp-18h+arg_0], rsi
0x180056429  mov     [rsp-18h+arg_10], r8d
0x18005642e  mov     [rsp-18h+arg_8], rdx
0x180056433  push    rbp
0x180056434  push    rdi
0x180056435  push    r14
0x180056437  mov     rbp, rsp
0x18005643a  sub     rsp, 60h
0x18005643e  mov     r14, r9
0x180056441  mov     qword ptr [r9], 0
0x180056448  lea     r9, [rbp+arg_10]
0x18005644c  mov     [rbp+arg_10], 0
0x180056453  xor     r8d, r8d
0x180056456  xor     edx, edx
0x180056458  mov     rsi, rcx
0x18005645b  call    cs:__imp_GetSystemAppDataKey
0x180056461  test    eax, eax
0x180056463  jz      short loc_18005646F
0x180056465  mov     edi, 8000FFFFh
0x18005646a  jmp     loc_1800565A5
0x18005646f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180056474  mov     edi, eax
0x180056476  cmp     eax, 8007007Ah
0x18005647b  jnz     loc_1800565A5
0x180056481  cmp     [rbp+arg_10], 0
0x180056485  jbe     loc_1800565A5
0x18005648b  xor     ecx, ecx; pv
0x18005648d  mov     [rbp+lpSubKey], 0
0x180056495  call    CoTaskMemFree_0
0x18005649a  mov     r9d, [rbp+arg_10]
0x18005649e  lea     rax, [rbp+lpSubKey]
0x1800564a2  xor     r8d, r8d
0x1800564a5  mov     qword ptr [rsp+60h+samDesired], rax
0x1800564aa  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800564af  mov     edi, eax
0x1800564b1  test    eax, eax
0x1800564b3  js      loc_18005659C
0x1800564b9  mov     r8, [rbp+lpSubKey]
0x1800564bd  lea     r9, [rbp+arg_10]
0x1800564c1  lea     rdx, [rbp+hKey]
0x1800564c5  mov     [rbp+hKey], 0
0x1800564cd  mov     rcx, rsi
0x1800564d0  call    cs:__imp_GetSystemAppDataKey
0x1800564d6  test    eax, eax
0x1800564d8  jnz     short loc_1800564E9
0x1800564da  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800564df  mov     edi, eax
0x1800564e1  test    eax, eax
0x1800564e3  js      loc_180056585
0x1800564e9  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800564ed  lea     rax, [rbp+arg_8]
0x1800564f1  mov     rcx, [rbp+hKey]; hKey
0x1800564f5  mov     r9d, 2001Fh; samDesired
0x1800564fb  xor     r8d, r8d; ulOptions
0x1800564fe  mov     [rsp+60h+phkResult], rax; phkResult
0x180056503  mov     [rbp+arg_8], 0
0x18005650b  call    cs:__imp_RegOpenKeyExW
0x180056511  mov     edi, eax
0x180056513  mov     esi, 80070000h
0x180056518  test    eax, eax
0x18005651a  jle     short loc_180056521
0x18005651c  movzx   edi, ax
0x18005651f  or      edi, esi
0x180056521  test    edi, edi
0x180056523  js      short loc_18005656E
0x180056525  mov     rcx, [rbp+arg_8]; hKey
0x180056529  lea     rdx, aSplashscreen; "SplashScreen"
0x180056530  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x180056539  xor     r9d, r9d; lpClass
0x18005653c  mov     [rsp+60h+var_28], r14; phkResult
0x180056541  xor     r8d, r8d; Reserved
0x180056544  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18005654d  mov     [rsp+60h+samDesired], 20019h; samDesired
0x180056555  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x18005655d  call    cs:__imp_RegCreateKeyExW
0x180056563  mov     edi, eax
0x180056565  test    eax, eax
0x180056567  jle     short loc_18005656E
0x180056569  movzx   edi, ax
0x18005656c  or      edi, esi
0x18005656e  mov     rcx, [rbp+arg_8]; hKey
0x180056572  mov     [rbp+arg_8], 0
0x18005657a  test    rcx, rcx
0x18005657d  jz      short loc_180056585
0x18005657f  call    cs:__imp_RegCloseKey
0x180056585  mov     rcx, [rbp+hKey]; hKey
0x180056589  mov     [rbp+hKey], 0
0x180056591  test    rcx, rcx
0x180056594  jz      short loc_18005659C
0x180056596  call    cs:__imp_RegCloseKey
0x18005659c  mov     rcx, [rbp+lpSubKey]; pv
0x1800565a0  call    CoTaskMemFree_0
0x1800565a5  mov     rsi, [rsp+60h+arg_0]
0x1800565ad  mov     eax, edi
0x1800565af  add     rsp, 60h
0x1800565b3  pop     r14
0x1800565b5  pop     rdi
0x1800565b6  pop     rbp
0x1800565b7  retn
```
