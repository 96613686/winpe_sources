# CallerIdentity::GetStateRegKey(void *,ushort const *,ulong,HKEY__ * *)

- ea: `0x180054104`
- end: `0x180054298`
- name: `?GetStateRegKey@CallerIdentity@@YAJPEAXPEBGKPEAPEAUHKEY__@@@Z`
- size: `404`
- prototype: `int(CallerIdentity *__hidden this, void *, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18005a350`

## callees

- `0x18002b520`
- `0x18004b914`
- `0x180054104`
- `0x18005d528`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005425f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054276`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005425f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054276`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800541eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800541eb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005423d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005423d`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18005413b`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x1800541b0`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18005413b`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x1800541b0`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetStateRegKey(CallerIdentity *this, HKEY a2, const unsigned __int16 *a3, HKEY *a4)
{
  int Error; // edi
  __int64 v7; // rdx
  __int64 v8; // rcx
  LSTATUS v9; // eax
  LSTATUS Key; // eax
  HKEY v11; // rcx
  HKEY v12; // rcx
  int phkResult; // [rsp+20h] [rbp-40h]
  LPCWSTR lpSubKey[2]; // [rsp+50h] [rbp-10h] BYREF
  HKEY v16; // [rsp+88h] [rbp+28h] BYREF
  unsigned int v17; // [rsp+90h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+38h] BYREF

  v16 = a2;
  *a4 = 0;
  v17 = 0;
  if ( (unsigned int)GetSystemAppDataKey(this, 0, 0, &v17) )
  {
    return (unsigned int)-2147418113;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 && v17 )
    {
      lpSubKey[0] = 0;
      CoTaskMemFree_0(0);
      Error = _AllocStringWorker<CTCoAllocPolicy>(v8, v7, 0, v17, phkResult, lpSubKey);
      if ( Error >= 0 )
      {
        hKey = 0;
        if ( (unsigned int)GetSystemAppDataKey(this, &hKey, lpSubKey[0], &v17)
          || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          v16 = 0;
          v9 = RegOpenKeyExW(hKey, lpSubKey[0], 0, 0x2001Fu, &v16);
          Error = v9;
          if ( v9 > 0 )
            Error = (unsigned __int16)v9 | 0x80070000;
          if ( Error >= 0 )
          {
            Key = RegCreateKeyExW(v16, L"SplashScreen", 0, 0, 0, 0x20019u, 0, a4, 0);
            Error = Key;
            if ( Key > 0 )
              Error = (unsigned __int16)Key | 0x80070000;
          }
          v11 = v16;
          v16 = 0;
          if ( v11 )
            RegCloseKey(v11);
        }
        v12 = hKey;
        hKey = 0;
        if ( v12 )
          RegCloseKey(v12);
      }
      CoTaskMemFree_0((LPVOID)lpSubKey[0]);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180054104  mov     [rsp-18h+arg_0], rsi
0x180054109  mov     [rsp-18h+arg_10], r8d
0x18005410e  mov     [rsp-18h+arg_8], rdx
0x180054113  push    rbp
0x180054114  push    rdi
0x180054115  push    r14
0x180054117  mov     rbp, rsp
0x18005411a  sub     rsp, 60h
0x18005411e  mov     r14, r9
0x180054121  mov     qword ptr [r9], 0
0x180054128  lea     r9, [rbp+arg_10]
0x18005412c  mov     [rbp+arg_10], 0
0x180054133  xor     r8d, r8d
0x180054136  xor     edx, edx
0x180054138  mov     rsi, rcx
0x18005413b  call    cs:__imp_GetSystemAppDataKey
0x180054141  test    eax, eax
0x180054143  jz      short loc_18005414F
0x180054145  mov     edi, 8000FFFFh
0x18005414a  jmp     loc_180054285
0x18005414f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180054154  mov     edi, eax
0x180054156  cmp     eax, 8007007Ah
0x18005415b  jnz     loc_180054285
0x180054161  cmp     [rbp+arg_10], 0
0x180054165  jbe     loc_180054285
0x18005416b  xor     ecx, ecx; pv
0x18005416d  mov     [rbp+lpSubKey], 0
0x180054175  call    CoTaskMemFree_0
0x18005417a  mov     r9d, [rbp+arg_10]
0x18005417e  lea     rax, [rbp+lpSubKey]
0x180054182  xor     r8d, r8d
0x180054185  mov     qword ptr [rsp+60h+samDesired], rax
0x18005418a  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18005418f  mov     edi, eax
0x180054191  test    eax, eax
0x180054193  js      loc_18005427C
0x180054199  mov     r8, [rbp+lpSubKey]
0x18005419d  lea     r9, [rbp+arg_10]
0x1800541a1  lea     rdx, [rbp+hKey]
0x1800541a5  mov     [rbp+hKey], 0
0x1800541ad  mov     rcx, rsi
0x1800541b0  call    cs:__imp_GetSystemAppDataKey
0x1800541b6  test    eax, eax
0x1800541b8  jnz     short loc_1800541C9
0x1800541ba  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800541bf  mov     edi, eax
0x1800541c1  test    eax, eax
0x1800541c3  js      loc_180054265
0x1800541c9  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800541cd  lea     rax, [rbp+arg_8]
0x1800541d1  mov     rcx, [rbp+hKey]; hKey
0x1800541d5  mov     r9d, 2001Fh; samDesired
0x1800541db  xor     r8d, r8d; ulOptions
0x1800541de  mov     [rsp+60h+phkResult], rax; phkResult
0x1800541e3  mov     [rbp+arg_8], 0
0x1800541eb  call    cs:__imp_RegOpenKeyExW
0x1800541f1  mov     edi, eax
0x1800541f3  mov     esi, 80070000h
0x1800541f8  test    eax, eax
0x1800541fa  jle     short loc_180054201
0x1800541fc  movzx   edi, ax
0x1800541ff  or      edi, esi
0x180054201  test    edi, edi
0x180054203  js      short loc_18005424E
0x180054205  mov     rcx, [rbp+arg_8]; hKey
0x180054209  lea     rdx, aSplashscreen; "SplashScreen"
0x180054210  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x180054219  xor     r9d, r9d; lpClass
0x18005421c  mov     [rsp+60h+var_28], r14; phkResult
0x180054221  xor     r8d, r8d; Reserved
0x180054224  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18005422d  mov     [rsp+60h+samDesired], 20019h; samDesired
0x180054235  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x18005423d  call    cs:__imp_RegCreateKeyExW
0x180054243  mov     edi, eax
0x180054245  test    eax, eax
0x180054247  jle     short loc_18005424E
0x180054249  movzx   edi, ax
0x18005424c  or      edi, esi
0x18005424e  mov     rcx, [rbp+arg_8]; hKey
0x180054252  mov     [rbp+arg_8], 0
0x18005425a  test    rcx, rcx
0x18005425d  jz      short loc_180054265
0x18005425f  call    cs:__imp_RegCloseKey
0x180054265  mov     rcx, [rbp+hKey]; hKey
0x180054269  mov     [rbp+hKey], 0
0x180054271  test    rcx, rcx
0x180054274  jz      short loc_18005427C
0x180054276  call    cs:__imp_RegCloseKey
0x18005427c  mov     rcx, [rbp+lpSubKey]; pv
0x180054280  call    CoTaskMemFree_0
0x180054285  mov     rsi, [rsp+60h+arg_0]
0x18005428d  mov     eax, edi
0x18005428f  add     rsp, 60h
0x180054293  pop     r14
0x180054295  pop     rdi
0x180054296  pop     rbp
0x180054297  retn
```
