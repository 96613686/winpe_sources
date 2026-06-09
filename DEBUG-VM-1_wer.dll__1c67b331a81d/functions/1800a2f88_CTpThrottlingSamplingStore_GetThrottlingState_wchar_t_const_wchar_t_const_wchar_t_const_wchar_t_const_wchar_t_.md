# CTpThrottlingSamplingStore::GetThrottlingState(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int,int *)

- ea: `0x1800a2f88`
- end: `0x1800a31ca`
- name: `?GetThrottlingState@CTpThrottlingSamplingStore@@CAJPEB_W0000HPEAH@Z`
- size: `578`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, LPCWSTR lpValueName, int, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a2ef4`
- `0x1800a31d0`

## callees

- `0x1800a2f88`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a308f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a308f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a30f6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a30f6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a318f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a318f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a30ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a312b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a30ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a312b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3048`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a31a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a31b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3048`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a31a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a31b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a3036`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a3036`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a315b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a315b`

## string_xrefs

- `0x1800a3185`: `AccessTime`

## pseudocode

```c
__int64 __fastcall CTpThrottlingSamplingStore::GetThrottlingState(
        const wchar_t *a1,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        LPCWSTR lpValueName,
        int a6,
        int *a7)
{
  int *v7; // r12
  unsigned int v8; // esi
  bool v9; // cf
  int v10; // r15d
  unsigned int v11; // r14d
  HKEY v12; // rdi
  HKEY v13; // rbx
  LPCWSTR v14; // rdx
  LSTATUS v15; // eax
  const WCHAR *v16; // r14
  BYTE Data[8]; // [rsp+30h] [rbp-48h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-40h] BYREF
  LPCWSTR lpSubKey[7]; // [rsp+40h] [rbp-38h]
  DWORD cbData; // [rsp+C0h] [rbp+48h] BYREF
  DWORD Type; // [rsp+C8h] [rbp+50h] BYREF
  struct _FILETIME v23; // [rsp+D0h] [rbp+58h] BYREF
  HKEY hKey; // [rsp+D8h] [rbp+60h] BYREF

  v7 = a7;
  cbData = 8;
  SystemTimeAsFileTime = 0;
  v23 = 0;
  hKey = 0;
  Type = 0;
  *(_QWORD *)Data = 0;
  lpSubKey[0] = L"SOFTWARE\\Microsoft\\TelemetryClient\\ThrottleStore";
  lpSubKey[1] = a1;
  lpSubKey[2] = a2;
  lpSubKey[3] = a3;
  lpSubKey[4] = a4;
  if ( !a7 )
    return (unsigned int)-2147024809;
  v9 = a6 != 0;
  a6 = -a6;
  v8 = 0;
  v10 = 0;
  *a7 = 0;
  v11 = 0;
  v12 = (HKEY)(v9 - 0x7FFFFFFFLL);
  v13 = v12;
  while ( v11 < 5 )
  {
    v14 = lpSubKey[v11];
    if ( !v14 || !*v14 )
      break;
    v15 = RegOpenKeyExW(v13, v14, 0, 0x103u, &hKey);
    if ( v15 )
    {
      hKey = 0;
      if ( v15 != 2 )
      {
        if ( v15 > 0 )
          v8 = (unsigned __int16)v15 | 0x80070000;
        else
          v8 = v15;
      }
      break;
    }
    if ( v12 != v13 )
      RegCloseKey(v13);
    v13 = hKey;
    hKey = 0;
    if ( v11 == 4 )
      v10 = 1;
    ++v11;
  }
  if ( v12 != v13 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v23 = SystemTimeAsFileTime;
    if ( v10
      && (v16 = lpValueName) != 0
      && !RegQueryValueExW(v13, lpValueName, 0, &Type, Data, &cbData)
      && Type == 11
      && cbData == 8 )
    {
      if ( *(_QWORD *)Data != -1 && *(unsigned __int64 *)&v23 >= *(_QWORD *)Data )
      {
        RegDeleteValueW(v13, v16);
        goto LABEL_33;
      }
    }
    else
    {
      cbData = 8;
      if ( RegQueryValueExW(v13, L"ThrottleExpiryTime", 0, &Type, Data, &cbData) || Type != 11 || cbData != 8 )
        goto LABEL_33;
      if ( *(_QWORD *)Data != -1 && *(unsigned __int64 *)&v23 >= *(_QWORD *)Data )
      {
        RegDeleteTreeW(v13, (LPCWSTR)&Src);
        goto LABEL_33;
      }
    }
    *v7 = 1;
    RegSetValueExW(v13, L"AccessTime", 0, 0xBu, (const BYTE *)&v23, 8u);
  }
LABEL_33:
  if ( v13 && v12 != v13 )
    RegCloseKey(v13);
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x1800a2f88  push    rbp
0x1800a2f8a  push    rbx
0x1800a2f8b  push    rsi
0x1800a2f8c  push    rdi
0x1800a2f8d  push    r12
0x1800a2f8f  push    r13
0x1800a2f91  push    r14
0x1800a2f93  push    r15
0x1800a2f95  mov     rbp, rsp
0x1800a2f98  sub     rsp, 78h
0x1800a2f9c  mov     r12, [rbp+arg_30]
0x1800a2fa0  lea     rax, aSoftwareMicros_30; "SOFTWARE\\Microsoft\\TelemetryClient\\T"...
0x1800a2fa7  xor     r13d, r13d
0x1800a2faa  mov     [rbp+cbData], 8
0x1800a2fb1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r13
0x1800a2fb5  mov     [rbp+arg_10], r13
0x1800a2fb9  mov     [rbp+hKey], r13
0x1800a2fbd  mov     [rbp+Type], r13d
0x1800a2fc1  mov     qword ptr [rbp+Data], r13
0x1800a2fc5  mov     [rbp+lpSubKey], rax
0x1800a2fc9  mov     [rbp+var_30], rcx
0x1800a2fcd  mov     [rbp+var_28], rdx
0x1800a2fd1  mov     [rbp+var_20], r8
0x1800a2fd5  mov     [rbp+var_18], r9
0x1800a2fd9  test    r12, r12
0x1800a2fdc  jnz     short loc_1800A2FE8
0x1800a2fde  mov     esi, 80070057h
0x1800a2fe3  jmp     loc_1800A31B7
0x1800a2fe8  neg     [rbp+arg_28]
0x1800a2feb  mov     esi, r13d
0x1800a2fee  mov     r15d, r13d
0x1800a2ff1  mov     [r12], r13d
0x1800a2ff5  sbb     rdi, rdi
0x1800a2ff8  mov     r14d, r13d
0x1800a2ffb  neg     rdi
0x1800a2ffe  add     rdi, 0FFFFFFFF80000001h
0x1800a3005  mov     rbx, rdi
0x1800a3008  cmp     r14d, 5
0x1800a300c  jnb     short loc_1800A3082
0x1800a300e  mov     eax, r14d
0x1800a3011  mov     rdx, [rbp+rax*8+lpSubKey]; lpSubKey
0x1800a3016  test    rdx, rdx
0x1800a3019  jz      short loc_1800A3082
0x1800a301b  cmp     [rdx], r13w
0x1800a301f  jz      short loc_1800A3082
0x1800a3021  lea     rax, [rbp+hKey]
0x1800a3025  mov     r9d, 103h; samDesired
0x1800a302b  xor     r8d, r8d; ulOptions
0x1800a302e  mov     [rsp+78h+phkResult], rax; phkResult
0x1800a3033  mov     rcx, rbx; hKey
0x1800a3036  call    cs:__imp_RegOpenKeyExW
0x1800a303c  test    eax, eax
0x1800a303e  jnz     short loc_1800A3068
0x1800a3040  cmp     rdi, rbx
0x1800a3043  jz      short loc_1800A304E
0x1800a3045  mov     rcx, rbx; hKey
0x1800a3048  call    cs:__imp_RegCloseKey
0x1800a304e  mov     rbx, [rbp+hKey]
0x1800a3052  cmp     r14d, 4
0x1800a3056  mov     eax, 1
0x1800a305b  mov     [rbp+hKey], r13
0x1800a305f  cmovz   r15d, eax
0x1800a3063  add     r14d, eax
0x1800a3066  jmp     short loc_1800A3008
0x1800a3068  mov     [rbp+hKey], r13
0x1800a306c  cmp     eax, 2
0x1800a306f  jz      short loc_1800A3082
0x1800a3071  test    eax, eax
0x1800a3073  jg      short loc_1800A3079
0x1800a3075  mov     esi, eax
0x1800a3077  jmp     short loc_1800A3082
0x1800a3079  movzx   esi, ax
0x1800a307c  or      esi, 80070000h
0x1800a3082  cmp     rdi, rbx
0x1800a3085  jz      loc_1800A3195
0x1800a308b  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800a308f  call    cs:__imp_GetSystemTimeAsFileTime
0x1800a3095  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800a3099  mov     [rbp+arg_10], rax
0x1800a309d  test    r15d, r15d
0x1800a30a0  jz      short loc_1800A3101
0x1800a30a2  mov     r14, [rbp+lpValueName]
0x1800a30a6  test    r14, r14
0x1800a30a9  jz      short loc_1800A3101
0x1800a30ab  lea     rax, [rbp+cbData]
0x1800a30af  xor     r8d, r8d; lpReserved
0x1800a30b2  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800a30b7  lea     r9, [rbp+Type]; lpType
0x1800a30bb  lea     rax, [rbp+Data]
0x1800a30bf  mov     rdx, r14; lpValueName
0x1800a30c2  mov     rcx, rbx; hKey
0x1800a30c5  mov     [rsp+78h+phkResult], rax; lpData
0x1800a30ca  call    cs:__imp_RegQueryValueExW
0x1800a30d0  test    eax, eax
0x1800a30d2  jnz     short loc_1800A3101
0x1800a30d4  cmp     [rbp+Type], 0Bh
0x1800a30d8  jnz     short loc_1800A3101
0x1800a30da  cmp     [rbp+cbData], 8
0x1800a30de  jnz     short loc_1800A3101
0x1800a30e0  mov     rax, qword ptr [rbp+Data]
0x1800a30e4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a30e8  jz      short loc_1800A3163
0x1800a30ea  cmp     [rbp+arg_10], rax
0x1800a30ee  jb      short loc_1800A3163
0x1800a30f0  mov     rdx, r14; lpValueName
0x1800a30f3  mov     rcx, rbx; hKey
0x1800a30f6  call    cs:__imp_RegDeleteValueW
0x1800a30fc  jmp     loc_1800A3195
0x1800a3101  lea     rax, [rbp+cbData]
0x1800a3105  mov     [rbp+cbData], 8
0x1800a310c  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800a3111  lea     r9, [rbp+Type]; lpType
0x1800a3115  lea     rax, [rbp+Data]
0x1800a3119  xor     r8d, r8d; lpReserved
0x1800a311c  lea     rdx, aThrottleexpiry; "ThrottleExpiryTime"
0x1800a3123  mov     [rsp+78h+phkResult], rax; lpData
0x1800a3128  mov     rcx, rbx; hKey
0x1800a312b  call    cs:__imp_RegQueryValueExW
0x1800a3131  test    eax, eax
0x1800a3133  jnz     short loc_1800A3195
0x1800a3135  cmp     [rbp+Type], 0Bh
0x1800a3139  jnz     short loc_1800A3195
0x1800a313b  cmp     [rbp+cbData], 8
0x1800a313f  jnz     short loc_1800A3195
0x1800a3141  mov     rax, qword ptr [rbp+Data]
0x1800a3145  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a3149  jz      short loc_1800A3163
0x1800a314b  cmp     [rbp+arg_10], rax
0x1800a314f  jb      short loc_1800A3163
0x1800a3151  lea     rdx, Src; lpSubKey
0x1800a3158  mov     rcx, rbx; hKey
0x1800a315b  call    cs:__imp_RegDeleteTreeW
0x1800a3161  jmp     short loc_1800A3195
0x1800a3163  lea     rax, [rbp+arg_10]
0x1800a3167  mov     dword ptr [rsp+78h+lpcbData], 8; cbData
0x1800a316f  mov     r9d, 0Bh; dwType
0x1800a3175  mov     [rsp+78h+phkResult], rax; lpData
0x1800a317a  xor     r8d, r8d; Reserved
0x1800a317d  mov     dword ptr [r12], 1
0x1800a3185  lea     rdx, aAccesstime; "AccessTime"
0x1800a318c  mov     rcx, rbx; hKey
0x1800a318f  call    cs:__imp_RegSetValueExW
0x1800a3195  test    rbx, rbx
0x1800a3198  jz      short loc_1800A31A8
0x1800a319a  cmp     rdi, rbx
0x1800a319d  jz      short loc_1800A31A8
0x1800a319f  mov     rcx, rbx; hKey
0x1800a31a2  call    cs:__imp_RegCloseKey
0x1800a31a8  mov     rcx, [rbp+hKey]; hKey
0x1800a31ac  test    rcx, rcx
0x1800a31af  jz      short loc_1800A31B7
0x1800a31b1  call    cs:__imp_RegCloseKey
0x1800a31b7  mov     eax, esi
0x1800a31b9  add     rsp, 78h
0x1800a31bd  pop     r15
0x1800a31bf  pop     r14
0x1800a31c1  pop     r13
0x1800a31c3  pop     r12
0x1800a31c5  pop     rdi
0x1800a31c6  pop     rsi
0x1800a31c7  pop     rbx
0x1800a31c8  pop     rbp
0x1800a31c9  retn
```
