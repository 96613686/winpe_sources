# CTpThrottlingSamplingStore::GetThrottlingState(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int,int *)

- ea: `0x1800a2f38`
- end: `0x1800a317a`
- name: `?GetThrottlingState@CTpThrottlingSamplingStore@@CAJPEB_W0000HPEAH@Z`
- size: `578`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, LPCWSTR lpValueName, int, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a2ea4`
- `0x1800a3180`

## callees

- `0x1800a2f38`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a303f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a303f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a30a6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a30a6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a313f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a313f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a307a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a30db`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a307a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a30db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a2ff8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3152`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3161`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a2ff8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3152`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3161`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a2fe6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a2fe6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a310b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a310b`

## string_xrefs

- `0x1800a3135`: `AccessTime`

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
0x1800a2f38  push    rbp
0x1800a2f3a  push    rbx
0x1800a2f3b  push    rsi
0x1800a2f3c  push    rdi
0x1800a2f3d  push    r12
0x1800a2f3f  push    r13
0x1800a2f41  push    r14
0x1800a2f43  push    r15
0x1800a2f45  mov     rbp, rsp
0x1800a2f48  sub     rsp, 78h
0x1800a2f4c  mov     r12, [rbp+arg_30]
0x1800a2f50  lea     rax, aSoftwareMicros_30; "SOFTWARE\\Microsoft\\TelemetryClient\\T"...
0x1800a2f57  xor     r13d, r13d
0x1800a2f5a  mov     [rbp+cbData], 8
0x1800a2f61  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r13
0x1800a2f65  mov     [rbp+arg_10], r13
0x1800a2f69  mov     [rbp+hKey], r13
0x1800a2f6d  mov     [rbp+Type], r13d
0x1800a2f71  mov     qword ptr [rbp+Data], r13
0x1800a2f75  mov     [rbp+lpSubKey], rax
0x1800a2f79  mov     [rbp+var_30], rcx
0x1800a2f7d  mov     [rbp+var_28], rdx
0x1800a2f81  mov     [rbp+var_20], r8
0x1800a2f85  mov     [rbp+var_18], r9
0x1800a2f89  test    r12, r12
0x1800a2f8c  jnz     short loc_1800A2F98
0x1800a2f8e  mov     esi, 80070057h
0x1800a2f93  jmp     loc_1800A3167
0x1800a2f98  neg     [rbp+arg_28]
0x1800a2f9b  mov     esi, r13d
0x1800a2f9e  mov     r15d, r13d
0x1800a2fa1  mov     [r12], r13d
0x1800a2fa5  sbb     rdi, rdi
0x1800a2fa8  mov     r14d, r13d
0x1800a2fab  neg     rdi
0x1800a2fae  add     rdi, 0FFFFFFFF80000001h
0x1800a2fb5  mov     rbx, rdi
0x1800a2fb8  cmp     r14d, 5
0x1800a2fbc  jnb     short loc_1800A3032
0x1800a2fbe  mov     eax, r14d
0x1800a2fc1  mov     rdx, [rbp+rax*8+lpSubKey]; lpSubKey
0x1800a2fc6  test    rdx, rdx
0x1800a2fc9  jz      short loc_1800A3032
0x1800a2fcb  cmp     [rdx], r13w
0x1800a2fcf  jz      short loc_1800A3032
0x1800a2fd1  lea     rax, [rbp+hKey]
0x1800a2fd5  mov     r9d, 103h; samDesired
0x1800a2fdb  xor     r8d, r8d; ulOptions
0x1800a2fde  mov     [rsp+78h+phkResult], rax; phkResult
0x1800a2fe3  mov     rcx, rbx; hKey
0x1800a2fe6  call    cs:__imp_RegOpenKeyExW
0x1800a2fec  test    eax, eax
0x1800a2fee  jnz     short loc_1800A3018
0x1800a2ff0  cmp     rdi, rbx
0x1800a2ff3  jz      short loc_1800A2FFE
0x1800a2ff5  mov     rcx, rbx; hKey
0x1800a2ff8  call    cs:__imp_RegCloseKey
0x1800a2ffe  mov     rbx, [rbp+hKey]
0x1800a3002  cmp     r14d, 4
0x1800a3006  mov     eax, 1
0x1800a300b  mov     [rbp+hKey], r13
0x1800a300f  cmovz   r15d, eax
0x1800a3013  add     r14d, eax
0x1800a3016  jmp     short loc_1800A2FB8
0x1800a3018  mov     [rbp+hKey], r13
0x1800a301c  cmp     eax, 2
0x1800a301f  jz      short loc_1800A3032
0x1800a3021  test    eax, eax
0x1800a3023  jg      short loc_1800A3029
0x1800a3025  mov     esi, eax
0x1800a3027  jmp     short loc_1800A3032
0x1800a3029  movzx   esi, ax
0x1800a302c  or      esi, 80070000h
0x1800a3032  cmp     rdi, rbx
0x1800a3035  jz      loc_1800A3145
0x1800a303b  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800a303f  call    cs:__imp_GetSystemTimeAsFileTime
0x1800a3045  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800a3049  mov     [rbp+arg_10], rax
0x1800a304d  test    r15d, r15d
0x1800a3050  jz      short loc_1800A30B1
0x1800a3052  mov     r14, [rbp+lpValueName]
0x1800a3056  test    r14, r14
0x1800a3059  jz      short loc_1800A30B1
0x1800a305b  lea     rax, [rbp+cbData]
0x1800a305f  xor     r8d, r8d; lpReserved
0x1800a3062  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800a3067  lea     r9, [rbp+Type]; lpType
0x1800a306b  lea     rax, [rbp+Data]
0x1800a306f  mov     rdx, r14; lpValueName
0x1800a3072  mov     rcx, rbx; hKey
0x1800a3075  mov     [rsp+78h+phkResult], rax; lpData
0x1800a307a  call    cs:__imp_RegQueryValueExW
0x1800a3080  test    eax, eax
0x1800a3082  jnz     short loc_1800A30B1
0x1800a3084  cmp     [rbp+Type], 0Bh
0x1800a3088  jnz     short loc_1800A30B1
0x1800a308a  cmp     [rbp+cbData], 8
0x1800a308e  jnz     short loc_1800A30B1
0x1800a3090  mov     rax, qword ptr [rbp+Data]
0x1800a3094  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a3098  jz      short loc_1800A3113
0x1800a309a  cmp     [rbp+arg_10], rax
0x1800a309e  jb      short loc_1800A3113
0x1800a30a0  mov     rdx, r14; lpValueName
0x1800a30a3  mov     rcx, rbx; hKey
0x1800a30a6  call    cs:__imp_RegDeleteValueW
0x1800a30ac  jmp     loc_1800A3145
0x1800a30b1  lea     rax, [rbp+cbData]
0x1800a30b5  mov     [rbp+cbData], 8
0x1800a30bc  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800a30c1  lea     r9, [rbp+Type]; lpType
0x1800a30c5  lea     rax, [rbp+Data]
0x1800a30c9  xor     r8d, r8d; lpReserved
0x1800a30cc  lea     rdx, aThrottleexpiry; "ThrottleExpiryTime"
0x1800a30d3  mov     [rsp+78h+phkResult], rax; lpData
0x1800a30d8  mov     rcx, rbx; hKey
0x1800a30db  call    cs:__imp_RegQueryValueExW
0x1800a30e1  test    eax, eax
0x1800a30e3  jnz     short loc_1800A3145
0x1800a30e5  cmp     [rbp+Type], 0Bh
0x1800a30e9  jnz     short loc_1800A3145
0x1800a30eb  cmp     [rbp+cbData], 8
0x1800a30ef  jnz     short loc_1800A3145
0x1800a30f1  mov     rax, qword ptr [rbp+Data]
0x1800a30f5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a30f9  jz      short loc_1800A3113
0x1800a30fb  cmp     [rbp+arg_10], rax
0x1800a30ff  jb      short loc_1800A3113
0x1800a3101  lea     rdx, Src; lpSubKey
0x1800a3108  mov     rcx, rbx; hKey
0x1800a310b  call    cs:__imp_RegDeleteTreeW
0x1800a3111  jmp     short loc_1800A3145
0x1800a3113  lea     rax, [rbp+arg_10]
0x1800a3117  mov     dword ptr [rsp+78h+lpcbData], 8; cbData
0x1800a311f  mov     r9d, 0Bh; dwType
0x1800a3125  mov     [rsp+78h+phkResult], rax; lpData
0x1800a312a  xor     r8d, r8d; Reserved
0x1800a312d  mov     dword ptr [r12], 1
0x1800a3135  lea     rdx, aAccesstime; "AccessTime"
0x1800a313c  mov     rcx, rbx; hKey
0x1800a313f  call    cs:__imp_RegSetValueExW
0x1800a3145  test    rbx, rbx
0x1800a3148  jz      short loc_1800A3158
0x1800a314a  cmp     rdi, rbx
0x1800a314d  jz      short loc_1800A3158
0x1800a314f  mov     rcx, rbx; hKey
0x1800a3152  call    cs:__imp_RegCloseKey
0x1800a3158  mov     rcx, [rbp+hKey]; hKey
0x1800a315c  test    rcx, rcx
0x1800a315f  jz      short loc_1800A3167
0x1800a3161  call    cs:__imp_RegCloseKey
0x1800a3167  mov     eax, esi
0x1800a3169  add     rsp, 78h
0x1800a316d  pop     r15
0x1800a316f  pop     r14
0x1800a3171  pop     r13
0x1800a3173  pop     r12
0x1800a3175  pop     rdi
0x1800a3176  pop     rsi
0x1800a3177  pop     rbx
0x1800a3178  pop     rbp
0x1800a3179  retn
```
