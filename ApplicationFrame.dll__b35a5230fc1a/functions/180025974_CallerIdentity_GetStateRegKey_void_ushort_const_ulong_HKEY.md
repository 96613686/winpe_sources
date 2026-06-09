# CallerIdentity::GetStateRegKey(void *,ushort const *,ulong,HKEY__ * *)

- ea: `0x180025974`
- end: `0x180025a92`
- name: `?GetStateRegKey@CallerIdentity@@YAJPEAXPEBGKPEAPEAUHKEY__@@@Z`
- size: `286`
- prototype: `int(CallerIdentity *__hidden this, void *, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800243a4`

## callees

- `0x180025974`
- `0x180025a98`
- `0x180041ec0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800259df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025a68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800259df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025a68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025a37`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025a37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025a5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025a5d`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x1800259ab`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x180025a17`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x1800259ab`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x180025a17`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CallerIdentity::GetStateRegKey(CallerIdentity *this, HKEY a2, const unsigned __int16 *a3, HKEY *a4)
{
  int Error; // edi
  int v7; // edx
  int v8; // ecx
  LSTATUS v9; // eax
  HKEY v10; // rcx
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF
  int v13; // [rsp+60h] [rbp+30h] BYREF
  LPCWSTR lpSubKey; // [rsp+68h] [rbp+38h]

  hKey = a2;
  *a4 = 0;
  v13 = 0;
  if ( (unsigned int)GetSystemAppDataKey(this, 0, 0, &v13) )
  {
    return (unsigned int)-2147418113;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 && v13 )
    {
      lpSubKey = 0;
      CoTaskMemFree(0);
      Error = _AllocStringWorker<CTCoAllocPolicy>(v8, v7, 0, v13);
      if ( Error >= 0 )
      {
        hKey = 0;
        if ( (unsigned int)GetSystemAppDataKey(this, &hKey, lpSubKey, &v13)
          || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          v9 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x2001Fu, a4);
          Error = v9;
          if ( v9 > 0 )
            Error = (unsigned __int16)v9 | 0x80070000;
        }
        v10 = hKey;
        hKey = 0;
        if ( v10 )
          RegCloseKey(v10);
      }
      CoTaskMemFree((LPVOID)lpSubKey);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180025974  mov     [rsp-18h+arg_0], rsi
0x180025979  mov     [rsp-18h+arg_10], r8d
0x18002597e  mov     [rsp-18h+hKey], rdx
0x180025983  push    rbp
0x180025984  push    rdi
0x180025985  push    r14
0x180025987  mov     rbp, rsp
0x18002598a  sub     rsp, 30h
0x18002598e  mov     r14, r9
0x180025991  mov     rsi, rcx
0x180025994  mov     qword ptr [r9], 0
0x18002599b  mov     [rbp+arg_10], 0
0x1800259a2  lea     r9, [rbp+arg_10]
0x1800259a6  xor     r8d, r8d
0x1800259a9  xor     edx, edx
0x1800259ab  call    cs:__imp_GetSystemAppDataKey
0x1800259b1  test    eax, eax
0x1800259b3  jnz     loc_180025A7E
0x1800259b9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800259be  mov     edi, eax
0x1800259c0  cmp     eax, 8007007Ah
0x1800259c5  jnz     loc_180025A6E
0x1800259cb  cmp     [rbp+arg_10], 0
0x1800259cf  jbe     loc_180025A6E
0x1800259d5  mov     [rbp+lpSubKey], 0
0x1800259dd  xor     ecx, ecx; pv
0x1800259df  call    cs:__imp_CoTaskMemFree
0x1800259e5  mov     r9d, [rbp+arg_10]
0x1800259e9  lea     rax, [rbp+lpSubKey]
0x1800259ed  mov     [rsp+30h+var_8], rax
0x1800259f2  xor     r8d, r8d
0x1800259f5  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800259fa  mov     edi, eax
0x1800259fc  test    eax, eax
0x1800259fe  js      short loc_180025A64
0x180025a00  mov     [rbp+hKey], 0
0x180025a08  lea     r9, [rbp+arg_10]
0x180025a0c  mov     r8, [rbp+lpSubKey]
0x180025a10  lea     rdx, [rbp+hKey]
0x180025a14  mov     rcx, rsi
0x180025a17  call    cs:__imp_GetSystemAppDataKey
0x180025a1d  test    eax, eax
0x180025a1f  jz      short loc_180025A85
0x180025a21  mov     [rsp+30h+phkResult], r14; phkResult
0x180025a26  mov     r9d, 2001Fh; samDesired
0x180025a2c  xor     r8d, r8d; ulOptions
0x180025a2f  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180025a33  mov     rcx, [rbp+hKey]; hKey
0x180025a37  call    cs:__imp_RegOpenKeyExW
0x180025a3d  mov     edi, eax
0x180025a3f  test    eax, eax
0x180025a41  jle     short loc_180025A4C
0x180025a43  movzx   edi, ax
0x180025a46  or      edi, 80070000h
0x180025a4c  mov     rcx, [rbp+hKey]; hKey
0x180025a50  mov     [rbp+hKey], 0
0x180025a58  test    rcx, rcx
0x180025a5b  jz      short loc_180025A64
0x180025a5d  call    cs:__imp_RegCloseKey
0x180025a63  nop
0x180025a64  mov     rcx, [rbp+lpSubKey]; pv
0x180025a68  call    cs:__imp_CoTaskMemFree
0x180025a6e  mov     eax, edi
0x180025a70  mov     rsi, [rsp+30h+arg_0]
0x180025a75  add     rsp, 30h
0x180025a79  pop     r14
0x180025a7b  pop     rdi
0x180025a7c  pop     rbp
0x180025a7d  retn
0x180025a7e  mov     edi, 8000FFFFh
0x180025a83  jmp     short loc_180025A6E
0x180025a85  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180025a8a  mov     edi, eax
0x180025a8c  test    eax, eax
0x180025a8e  js      short loc_180025A4C
0x180025a90  jmp     short loc_180025A21
```
