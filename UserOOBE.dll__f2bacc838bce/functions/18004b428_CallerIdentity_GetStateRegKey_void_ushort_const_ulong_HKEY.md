# CallerIdentity::GetStateRegKey(void *,ushort const *,ulong,HKEY__ * *)

- ea: `0x18004b428`
- end: `0x18004b5be`
- name: `?GetStateRegKey@CallerIdentity@@YAJPEAXPEBGKPEAPEAUHKEY__@@@Z`
- size: `406`
- prototype: `int(CallerIdentity *__hidden this, void *, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004b254`

## callees

- `0x18001e7b4`
- `0x180022a84`
- `0x18004b428`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b499`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b5a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b499`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b5a5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004b562`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004b562`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b510`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b510`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b584`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b59b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b584`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b59b`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18004b45f`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18004b4d5`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18004b45f`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18004b4d5`

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
      CoTaskMemFree(0);
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
      CoTaskMemFree(0);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18004b428  mov     [rsp-18h+arg_0], rsi
0x18004b42d  mov     [rsp-18h+arg_10], r8d
0x18004b432  mov     [rsp-18h+arg_8], rdx
0x18004b437  push    rbp
0x18004b438  push    rdi
0x18004b439  push    r14
0x18004b43b  mov     rbp, rsp
0x18004b43e  sub     rsp, 60h
0x18004b442  mov     r14, r9
0x18004b445  mov     qword ptr [r9], 0
0x18004b44c  lea     r9, [rbp+arg_10]
0x18004b450  mov     [rbp+arg_10], 0
0x18004b457  xor     r8d, r8d
0x18004b45a  xor     edx, edx
0x18004b45c  mov     rsi, rcx
0x18004b45f  call    cs:__imp_GetSystemAppDataKey
0x18004b465  test    eax, eax
0x18004b467  jz      short loc_18004B473
0x18004b469  mov     edi, 8000FFFFh
0x18004b46e  jmp     loc_18004B5AB
0x18004b473  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004b478  mov     edi, eax
0x18004b47a  cmp     eax, 8007007Ah
0x18004b47f  jnz     loc_18004B5AB
0x18004b485  cmp     [rbp+arg_10], 0
0x18004b489  jbe     loc_18004B5AB
0x18004b48f  xor     ecx, ecx; pv
0x18004b491  mov     [rbp+lpSubKey], 0
0x18004b499  call    cs:__imp_CoTaskMemFree
0x18004b49f  mov     r9d, [rbp+arg_10]
0x18004b4a3  lea     rax, [rbp+lpSubKey]
0x18004b4a7  xor     r8d, r8d
0x18004b4aa  mov     qword ptr [rsp+60h+samDesired], rax
0x18004b4af  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18004b4b4  mov     edi, eax
0x18004b4b6  test    eax, eax
0x18004b4b8  js      loc_18004B5A1
0x18004b4be  mov     r8, [rbp+lpSubKey]
0x18004b4c2  lea     r9, [rbp+arg_10]
0x18004b4c6  lea     rdx, [rbp+hKey]
0x18004b4ca  mov     [rbp+hKey], 0
0x18004b4d2  mov     rcx, rsi
0x18004b4d5  call    cs:__imp_GetSystemAppDataKey
0x18004b4db  test    eax, eax
0x18004b4dd  jnz     short loc_18004B4EE
0x18004b4df  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004b4e4  mov     edi, eax
0x18004b4e6  test    eax, eax
0x18004b4e8  js      loc_18004B58A
0x18004b4ee  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18004b4f2  lea     rax, [rbp+arg_8]
0x18004b4f6  mov     rcx, [rbp+hKey]; hKey
0x18004b4fa  mov     r9d, 2001Fh; samDesired
0x18004b500  xor     r8d, r8d; ulOptions
0x18004b503  mov     [rsp+60h+phkResult], rax; phkResult
0x18004b508  mov     [rbp+arg_8], 0
0x18004b510  call    cs:__imp_RegOpenKeyExW
0x18004b516  mov     edi, eax
0x18004b518  mov     esi, 80070000h
0x18004b51d  test    eax, eax
0x18004b51f  jle     short loc_18004B526
0x18004b521  movzx   edi, ax
0x18004b524  or      edi, esi
0x18004b526  test    edi, edi
0x18004b528  js      short loc_18004B573
0x18004b52a  mov     rcx, [rbp+arg_8]; hKey
0x18004b52e  lea     rdx, aSplashscreen; "SplashScreen"
0x18004b535  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x18004b53e  xor     r9d, r9d; lpClass
0x18004b541  mov     [rsp+60h+var_28], r14; phkResult
0x18004b546  xor     r8d, r8d; Reserved
0x18004b549  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004b552  mov     [rsp+60h+samDesired], 20019h; samDesired
0x18004b55a  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x18004b562  call    cs:__imp_RegCreateKeyExW
0x18004b568  mov     edi, eax
0x18004b56a  test    eax, eax
0x18004b56c  jle     short loc_18004B573
0x18004b56e  movzx   edi, ax
0x18004b571  or      edi, esi
0x18004b573  mov     rcx, [rbp+arg_8]; hKey
0x18004b577  mov     [rbp+arg_8], 0
0x18004b57f  test    rcx, rcx
0x18004b582  jz      short loc_18004B58A
0x18004b584  call    cs:__imp_RegCloseKey
0x18004b58a  mov     rcx, [rbp+hKey]; hKey
0x18004b58e  mov     [rbp+hKey], 0
0x18004b596  test    rcx, rcx
0x18004b599  jz      short loc_18004B5A1
0x18004b59b  call    cs:__imp_RegCloseKey
0x18004b5a1  mov     rcx, [rbp+lpSubKey]; pv
0x18004b5a5  call    cs:__imp_CoTaskMemFree
0x18004b5ab  mov     rsi, [rsp+60h+arg_0]
0x18004b5b3  mov     eax, edi
0x18004b5b5  add     rsp, 60h
0x18004b5b9  pop     r14
0x18004b5bb  pop     rdi
0x18004b5bc  pop     rbp
0x18004b5bd  retn
```
