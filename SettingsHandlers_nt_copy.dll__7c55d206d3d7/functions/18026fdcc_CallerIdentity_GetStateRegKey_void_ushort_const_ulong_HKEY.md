# CallerIdentity::GetStateRegKey(void *,ushort const *,ulong,HKEY__ * *)

- ea: `0x18026fdcc`
- end: `0x18026ff95`
- name: `?GetStateRegKey@CallerIdentity@@YAJPEAXPEBGKPEAPEAUHKEY__@@@Z`
- size: `457`
- prototype: `int(CallerIdentity *__hidden this, void *, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18026fbd4`

## callees

- `0x180048894`
- `0x18004e5f0`
- `0x18026fdcc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026fe43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026ff75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026fe43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026ff75`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18026ff1e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18026ff1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18026ff46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18026ff64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18026ff46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18026ff64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18026fec6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18026fec6`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18026fe03`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18026fe85`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18026fe03`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18026fe85`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18026fdcc  mov     [rsp-18h+arg_0], rsi
0x18026fdd1  mov     [rsp-18h+arg_10], r8d
0x18026fdd6  mov     [rsp-18h+arg_8], rdx
0x18026fddb  push    rbp
0x18026fddc  push    rdi
0x18026fddd  push    r14
0x18026fddf  mov     rbp, rsp
0x18026fde2  sub     rsp, 60h
0x18026fde6  mov     r14, r9
0x18026fde9  mov     rsi, rcx
0x18026fdec  mov     qword ptr [r9], 0
0x18026fdf3  mov     [rbp+arg_10], 0
0x18026fdfa  lea     r9, [rbp+arg_10]
0x18026fdfe  xor     r8d, r8d
0x18026fe01  xor     edx, edx
0x18026fe03  call    cs:__imp_GetSystemAppDataKey
0x18026fe0a  nop     dword ptr [rax+rax+00h]
0x18026fe0f  test    eax, eax
0x18026fe11  jz      short loc_18026FE1D
0x18026fe13  mov     edi, 8000FFFFh
0x18026fe18  jmp     loc_18026FF81
0x18026fe1d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18026fe22  mov     edi, eax
0x18026fe24  cmp     eax, 8007007Ah
0x18026fe29  jnz     loc_18026FF81
0x18026fe2f  cmp     [rbp+arg_10], 0
0x18026fe33  jbe     loc_18026FF81
0x18026fe39  mov     [rbp+lpSubKey], 0
0x18026fe41  xor     ecx, ecx; pv
0x18026fe43  call    cs:__imp_CoTaskMemFree
0x18026fe4a  nop     dword ptr [rax+rax+00h]
0x18026fe4f  mov     r9d, [rbp+arg_10]
0x18026fe53  lea     rax, [rbp+lpSubKey]
0x18026fe57  mov     qword ptr [rsp+60h+samDesired], rax
0x18026fe5c  xor     r8d, r8d
0x18026fe5f  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18026fe64  mov     edi, eax
0x18026fe66  test    eax, eax
0x18026fe68  js      loc_18026FF71
0x18026fe6e  mov     [rbp+hKey], 0
0x18026fe76  lea     r9, [rbp+arg_10]
0x18026fe7a  mov     r8, [rbp+lpSubKey]
0x18026fe7e  lea     rdx, [rbp+hKey]
0x18026fe82  mov     rcx, rsi
0x18026fe85  call    cs:__imp_GetSystemAppDataKey
0x18026fe8c  nop     dword ptr [rax+rax+00h]
0x18026fe91  test    eax, eax
0x18026fe93  jnz     short loc_18026FEA4
0x18026fe95  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18026fe9a  mov     edi, eax
0x18026fe9c  test    eax, eax
0x18026fe9e  js      loc_18026FF53
0x18026fea4  mov     [rbp+arg_8], 0
0x18026feac  lea     rax, [rbp+arg_8]
0x18026feb0  mov     [rsp+60h+phkResult], rax; phkResult
0x18026feb5  mov     r9d, 2001Fh; samDesired
0x18026febb  xor     r8d, r8d; ulOptions
0x18026febe  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18026fec2  mov     rcx, [rbp+hKey]; hKey
0x18026fec6  call    cs:__imp_RegOpenKeyExW
0x18026fecd  nop     dword ptr [rax+rax+00h]
0x18026fed2  mov     edi, eax
0x18026fed4  mov     esi, 80070000h
0x18026fed9  test    eax, eax
0x18026fedb  jle     short loc_18026FEE2
0x18026fedd  movzx   edi, ax
0x18026fee0  or      edi, esi
0x18026fee2  test    edi, edi
0x18026fee4  js      short loc_18026FF35
0x18026fee6  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x18026feef  mov     [rsp+60h+var_28], r14; phkResult
0x18026fef4  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18026fefd  mov     [rsp+60h+samDesired], 20019h; samDesired
0x18026ff05  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x18026ff0d  xor     r9d, r9d; lpClass
0x18026ff10  xor     r8d, r8d; Reserved
0x18026ff13  lea     rdx, aSplashscreen; "SplashScreen"
0x18026ff1a  mov     rcx, [rbp+arg_8]; hKey
0x18026ff1e  call    cs:__imp_RegCreateKeyExW
0x18026ff25  nop     dword ptr [rax+rax+00h]
0x18026ff2a  mov     edi, eax
0x18026ff2c  test    eax, eax
0x18026ff2e  jle     short loc_18026FF35
0x18026ff30  movzx   edi, ax
0x18026ff33  or      edi, esi
0x18026ff35  mov     rcx, [rbp+arg_8]; hKey
0x18026ff39  mov     [rbp+arg_8], 0
0x18026ff41  test    rcx, rcx
0x18026ff44  jz      short loc_18026FF53
0x18026ff46  call    cs:__imp_RegCloseKey
0x18026ff4d  nop     dword ptr [rax+rax+00h]
0x18026ff52  nop
0x18026ff53  mov     rcx, [rbp+hKey]; hKey
0x18026ff57  mov     [rbp+hKey], 0
0x18026ff5f  test    rcx, rcx
0x18026ff62  jz      short loc_18026FF71
0x18026ff64  call    cs:__imp_RegCloseKey
0x18026ff6b  nop     dword ptr [rax+rax+00h]
0x18026ff70  nop
0x18026ff71  mov     rcx, [rbp+lpSubKey]; pv
0x18026ff75  call    cs:__imp_CoTaskMemFree
0x18026ff7c  nop     dword ptr [rax+rax+00h]
0x18026ff81  mov     eax, edi
0x18026ff83  mov     rsi, [rsp+60h+arg_0]
0x18026ff8b  add     rsp, 60h
0x18026ff8f  pop     r14
0x18026ff91  pop     rdi
0x18026ff92  pop     rbp
0x18026ff93  retn
```
