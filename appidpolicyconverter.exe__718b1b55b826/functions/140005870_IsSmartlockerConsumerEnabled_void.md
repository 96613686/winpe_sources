# IsSmartlockerConsumerEnabled(void)

- ea: `0x140005870`
- end: `0x140005967`
- name: `?IsSmartlockerConsumerEnabled@@YA_NXZ`
- size: `247`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000458c`

## callees

- `0x140005870`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400058b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400058b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400058fc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000593d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400058fc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000593d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400058c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005958`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400058c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005958`

## string_xrefs

- `0x1400058a8`: `System\CurrentControlSet\Control\AppID\Configuration\SMARTLOCKER`

## pseudocode

```c
bool IsSmartlockerConsumerEnabled(void)
{
  bool v0; // bl
  BYTE v2[8]; // [rsp+30h] [rbp-18h] BYREF
  HKEY *p_hKey; // [rsp+38h] [rbp-10h]
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  DWORD Type; // [rsp+68h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+28h] BYREF
  __int64 Data; // [rsp+78h] [rbp+30h] BYREF

  v0 = 0;
  hKey = 0;
  p_hKey = &hKey;
  Data = 0;
  *(_QWORD *)v2 = 0;
  cbData = 0;
  Type = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\AppID\\Configuration\\SMARTLOCKER",
         0,
         0x20019u,
         &hKey) )
  {
    RegCloseKey(hKey);
    return 0;
  }
  else
  {
    cbData = 8;
    if ( RegQueryValueExW(hKey, L"DISABLED", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 11 || !Data )
    {
      cbData = 8;
      if ( !RegQueryValueExW(hKey, L"ENABLED", 0, &Type, v2, &cbData) && Type == 11 )
        v0 = *(_QWORD *)v2 != 0;
    }
    RegCloseKey(hKey);
    return v0;
  }
}

```

## disassembly

```asm
0x140005870  push    rbp
0x140005872  push    rbx
0x140005873  mov     rbp, rsp
0x140005876  sub     rsp, 48h
0x14000587a  xor     ebx, ebx
0x14000587c  mov     [rbp+hKey], rbx
0x140005880  lea     rax, [rbp+hKey]
0x140005884  mov     [rbp+var_10], rax
0x140005888  mov     [rbp+Data], rbx
0x14000588c  mov     qword ptr [rbp+var_18], rbx
0x140005890  mov     [rbp+cbData], ebx
0x140005893  mov     [rbp+Type], ebx
0x140005896  lea     rax, [rbp+hKey]
0x14000589a  mov     [rsp+48h+phkResult], rax; phkResult
0x14000589f  mov     r9d, 20019h; samDesired
0x1400058a5  xor     r8d, r8d; ulOptions
0x1400058a8  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\App"...
0x1400058af  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400058b6  call    cs:__imp_RegOpenKeyExW
0x1400058bc  test    eax, eax
0x1400058be  jz      short loc_1400058D1
0x1400058c0  mov     rcx, [rbp+hKey]; hKey
0x1400058c4  call    cs:__imp_RegCloseKey
0x1400058ca  xor     al, al
0x1400058cc  jmp     loc_140005960
0x1400058d1  mov     [rbp+cbData], 8
0x1400058d8  lea     rax, [rbp+cbData]
0x1400058dc  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1400058e1  lea     rax, [rbp+Data]
0x1400058e5  mov     [rsp+48h+phkResult], rax; lpData
0x1400058ea  lea     r9, [rbp+Type]; lpType
0x1400058ee  xor     r8d, r8d; lpReserved
0x1400058f1  lea     rdx, aDisabled; "DISABLED"
0x1400058f8  mov     rcx, [rbp+hKey]; hKey
0x1400058fc  call    cs:__imp_RegQueryValueExW
0x140005902  test    eax, eax
0x140005904  jnz     short loc_140005912
0x140005906  cmp     [rbp+Type], 0Bh
0x14000590a  jnz     short loc_140005912
0x14000590c  cmp     [rbp+Data], rbx
0x140005910  jnz     short loc_140005954
0x140005912  mov     [rbp+cbData], 8
0x140005919  lea     rax, [rbp+cbData]
0x14000591d  mov     [rsp+48h+lpcbData], rax; lpcbData
0x140005922  lea     rax, [rbp+var_18]
0x140005926  mov     [rsp+48h+phkResult], rax; lpData
0x14000592b  lea     r9, [rbp+Type]; lpType
0x14000592f  xor     r8d, r8d; lpReserved
0x140005932  lea     rdx, Value; "ENABLED"
0x140005939  mov     rcx, [rbp+hKey]; hKey
0x14000593d  call    cs:__imp_RegQueryValueExW
0x140005943  test    eax, eax
0x140005945  jnz     short loc_140005954
0x140005947  cmp     [rbp+Type], 0Bh
0x14000594b  jnz     short loc_140005954
0x14000594d  cmp     qword ptr [rbp+var_18], rbx
0x140005951  setnz   bl
0x140005954  mov     rcx, [rbp+hKey]; hKey
0x140005958  call    cs:__imp_RegCloseKey
0x14000595e  mov     al, bl
0x140005960  add     rsp, 48h
0x140005964  pop     rbx
0x140005965  pop     rbp
0x140005966  retn
```
