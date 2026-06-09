# WwanRegReadData(ushort const *,ulong,ushort const *,ulong *,uchar * *)

- ea: `0x1800a31bc`
- end: `0x1800a338f`
- name: `?WwanRegReadData@@YAKPEBGK0PEAKPEAPEAE@Z`
- size: `467`
- prototype: `unsigned int __usercall@<eax>(LPCWSTR lpSubKey@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, unsigned int *@<r9>, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18009ca38`
- `0x18009d2e8`

## callees

- `0x180012300`
- `0x180016c50`
- `0x180074758`
- `0x180074cec`
- `0x1800a31bc`
- `0x1800b6a40`
- `0x1800b6ac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a32cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a32cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a335e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a335e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a3227`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a3227`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a325f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a3301`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a325f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a3301`

## string_xrefs

- `0x1800a3236`: `RegOpenKeyEx failed, dwError (0x%8x)`
- `0x1800a31d2`: `WwanRegReadData`

## pseudocode

```c
__int64 __fastcall WwanRegReadData(
        LPCWSTR lpSubKey,
        DWORD a2,
        const unsigned __int16 *a3,
        unsigned int *a4,
        unsigned __int8 **a5)
{
  unsigned int v7; // eax
  unsigned int v9; // eax
  DWORD v10; // ecx
  BYTE *v11; // rdi
  unsigned int v12; // eax
  DWORD Type; // [rsp+30h] [rbp-28h] BYREF
  DWORD lpcbData; // [rsp+34h] [rbp-24h] BYREF
  DWORD v16; // [rsp+38h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+40h] BYREF

  cbData = a2;
  WwanLog::Enter("WwanRegReadData");
  hKey = 0;
  Type = 0;
  v16 = 0;
  cbData = 0;
  lpcbData = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 1u, &hKey);
  LODWORD(lpSubKey) = v7;
  if ( v7 )
  {
    WwanLog::Error("WwanRegReadData", 0, L"RegOpenKeyEx failed, dwError (0x%8x)", v7);
    goto LABEL_17;
  }
  v9 = RegQueryValueExW(hKey, a3, 0, &Type, 0, &cbData);
  LODWORD(lpSubKey) = v9;
  if ( v9 )
  {
    WwanLog::Error("WwanRegReadData", 0, L"RegQueryValueExW failed, dwError (0x%8x)", v9);
    goto LABEL_17;
  }
  if ( Type != 3 )
  {
    LODWORD(lpSubKey) = 13;
    WwanLog::Error("WwanRegReadData", 0, L"data type mismatch, dwError (0x%8x)", 13);
    goto LABEL_17;
  }
  v10 = cbData;
  v11 = 0;
  if ( cbData )
  {
    v11 = (BYTE *)WwanMemAlloc(cbData);
    if ( !v11 )
    {
      lpSubKey = (LPCWSTR)GetLastError();
      WwanLog::Error("WwanRegReadData", 0, L"WwanMemAlloc failed, dwError (0x%8x)", lpSubKey);
      goto LABEL_17;
    }
    lpcbData = cbData;
    v12 = RegQueryValueExW(hKey, a3, 0, &v16, v11, &lpcbData);
    LODWORD(lpSubKey) = v12;
    if ( v12 )
    {
      WwanLog::Error("WwanRegReadData", 0, L"RegQueryValueExW failed, dwError (0x%8x)", v12);
LABEL_15:
      WwanMemFree(v11);
      goto LABEL_17;
    }
    if ( Type != 3 || (v10 = cbData, lpcbData > cbData) )
    {
      LODWORD(lpSubKey) = 13;
      WwanLog::Error("WwanRegReadData", 0, L"data type mismatch, dwError (0x%8x)", 13);
      goto LABEL_15;
    }
  }
  *a5 = v11;
  *a4 = v10;
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  WwanLog::Verbose("WwanRegReadData", 0, L"dwError (0x%8x)", (unsigned int)lpSubKey);
  WwanLog::Exit("WwanRegReadData");
  return (unsigned int)lpSubKey;
}

```

## disassembly

```asm
0x1800a31bc  mov     [rsp-30h+cbData], edx
0x1800a31c0  push    rbp
0x1800a31c1  push    rbx
0x1800a31c2  push    rsi
0x1800a31c3  push    rdi
0x1800a31c4  push    r12
0x1800a31c6  push    r14
0x1800a31c8  mov     rbp, rsp
0x1800a31cb  sub     rsp, 58h
0x1800a31cf  mov     rbx, rcx
0x1800a31d2  lea     r12, aWwanregreaddat; "WwanRegReadData"
0x1800a31d9  mov     rcx, r12; char *
0x1800a31dc  mov     r14, r9
0x1800a31df  mov     rsi, r8
0x1800a31e2  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x1800a31e7  lea     rax, [rbp+hKey]
0x1800a31eb  mov     [rbp+hKey], 0
0x1800a31f3  mov     r9d, 1; samDesired
0x1800a31f9  mov     [rsp+58h+phkResult], rax; phkResult
0x1800a31fe  xor     r8d, r8d; ulOptions
0x1800a3201  mov     [rbp+Type], 0
0x1800a3208  mov     rdx, rbx; lpSubKey
0x1800a320b  mov     [rbp+var_20], 0
0x1800a3212  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a3219  mov     [rbp+cbData], 0
0x1800a3220  mov     [rbp+var_24], 0
0x1800a3227  call    cs:__imp_RegOpenKeyExW
0x1800a322d  mov     ebx, eax
0x1800a322f  test    eax, eax
0x1800a3231  jz      short loc_1800A323F
0x1800a3233  mov     r9d, eax
0x1800a3236  lea     r8, aRegopenkeyexFa_0; "RegOpenKeyEx failed, dwError (0x%8x)"
0x1800a323d  jmp     short loc_1800A328F
0x1800a323f  mov     rcx, [rbp+hKey]; hKey
0x1800a3243  lea     rax, [rbp+cbData]
0x1800a3247  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800a324c  lea     r9, [rbp+Type]; lpType
0x1800a3250  xor     r8d, r8d; lpReserved
0x1800a3253  mov     [rsp+58h+phkResult], 0; lpData
0x1800a325c  mov     rdx, rsi; lpValueName
0x1800a325f  call    cs:__imp_RegQueryValueExW
0x1800a3265  mov     ebx, eax
0x1800a3267  test    eax, eax
0x1800a3269  jz      short loc_1800A3277
0x1800a326b  mov     r9d, eax
0x1800a326e  lea     r8, aRegqueryvaluee_11; "RegQueryValueExW failed, dwError (0x%8x"...
0x1800a3275  jmp     short loc_1800A328F
0x1800a3277  mov     edx, [rbp+Type]
0x1800a327a  cmp     edx, 3
0x1800a327d  jz      short loc_1800A329E
0x1800a327f  mov     r9d, 0Dh
0x1800a3285  lea     r8, aDataTypeMismat; "data type mismatch, dwError (0x%8x)"
0x1800a328c  mov     ebx, r9d
0x1800a328f  xor     edx, edx; struct _GUID *
0x1800a3291  mov     rcx, r12; char *
0x1800a3294  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a3299  jmp     loc_1800A3355
0x1800a329e  mov     ecx, [rbp+cbData]
0x1800a32a1  xor     edi, edi
0x1800a32a3  test    ecx, ecx
0x1800a32a5  jz      loc_1800A334B
0x1800a32ab  lea     eax, [rdx-1]
0x1800a32ae  cmp     eax, 1
0x1800a32b1  jbe     short loc_1800A32B8
0x1800a32b3  cmp     edx, 7
0x1800a32b6  jnz     short loc_1800A32BE
0x1800a32b8  add     ecx, 4; Size
0x1800a32bb  mov     [rbp+cbData], ecx
0x1800a32be  call    WwanMemAlloc
0x1800a32c3  mov     rdi, rax
0x1800a32c6  test    rax, rax
0x1800a32c9  jnz     short loc_1800A32DF
0x1800a32cb  call    cs:__imp_GetLastError
0x1800a32d1  mov     ebx, eax
0x1800a32d3  lea     r8, aWwanmemallocFa; "WwanMemAlloc failed, dwError (0x%8x)"
0x1800a32da  mov     r9d, eax
0x1800a32dd  jmp     short loc_1800A328F
0x1800a32df  mov     eax, [rbp+cbData]
0x1800a32e2  lea     r9, [rbp+var_20]; lpType
0x1800a32e6  mov     rcx, [rbp+hKey]; hKey
0x1800a32ea  xor     r8d, r8d; lpReserved
0x1800a32ed  mov     [rbp+var_24], eax
0x1800a32f0  mov     rdx, rsi; lpValueName
0x1800a32f3  lea     rax, [rbp+var_24]
0x1800a32f7  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800a32fc  mov     [rsp+58h+phkResult], rdi; lpData
0x1800a3301  call    cs:__imp_RegQueryValueExW
0x1800a3307  mov     ebx, eax
0x1800a3309  test    eax, eax
0x1800a330b  jz      short loc_1800A3319
0x1800a330d  lea     r8, aRegqueryvaluee_11; "RegQueryValueExW failed, dwError (0x%8x"...
0x1800a3314  mov     r9d, eax
0x1800a3317  jmp     short loc_1800A3337
0x1800a3319  cmp     [rbp+Type], 3
0x1800a331d  jnz     short loc_1800A3327
0x1800a331f  mov     ecx, [rbp+cbData]
0x1800a3322  cmp     [rbp+var_24], ecx
0x1800a3325  jbe     short loc_1800A334B
0x1800a3327  mov     r9d, 0Dh
0x1800a332d  lea     r8, aDataTypeMismat; "data type mismatch, dwError (0x%8x)"
0x1800a3334  mov     ebx, r9d
0x1800a3337  xor     edx, edx; struct _GUID *
0x1800a3339  mov     rcx, r12; char *
0x1800a333c  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a3341  mov     rcx, rdi
0x1800a3344  call    WwanMemFree
0x1800a3349  jmp     short loc_1800A3355
0x1800a334b  mov     rax, [rbp+arg_20]
0x1800a334f  mov     [rax], rdi
0x1800a3352  mov     [r14], ecx
0x1800a3355  mov     rcx, [rbp+hKey]; hKey
0x1800a3359  test    rcx, rcx
0x1800a335c  jz      short loc_1800A3364
0x1800a335e  call    cs:__imp_RegCloseKey
0x1800a3364  mov     r9d, ebx
0x1800a3367  lea     r8, aDwerror0x8x; "dwError (0x%8x)"
0x1800a336e  xor     edx, edx; struct _GUID *
0x1800a3370  mov     rcx, r12; char *
0x1800a3373  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800a3378  mov     rcx, r12; char *
0x1800a337b  call    ?Exit@WwanLog@@SAXPEBD@Z; WwanLog::Exit(char const *)
0x1800a3380  mov     eax, ebx
0x1800a3382  add     rsp, 58h
0x1800a3386  pop     r14
0x1800a3388  pop     r12
0x1800a338a  pop     rdi
0x1800a338b  pop     rsi
0x1800a338c  pop     rbx
0x1800a338d  pop     rbp
0x1800a338e  retn
```
