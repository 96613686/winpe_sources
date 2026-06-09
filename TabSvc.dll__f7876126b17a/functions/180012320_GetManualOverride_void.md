# GetManualOverride(void)

- ea: `0x180012320`
- end: `0x1800123c5`
- name: `?GetManualOverride@@YAKXZ`
- size: `165`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012060`
- `0x180015660`

## callees

- `0x180012320`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800123a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800123a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001238b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001238b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012350`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012350`

## pseudocode

```c
__int64 GetManualOverride(void)
{
  unsigned int v0; // ebx
  unsigned int v1; // ecx
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF
  unsigned int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v0 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\TabletPC", 0, 0x20019u, &hKey) )
  {
    Type = 0;
    Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"AutoStart", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && cbData == 4 )
      v0 = Data;
    RegCloseKey(hKey);
    v1 = 0;
    if ( (v0 & 3) != 3 )
      return v0;
    return v1;
  }
  return v0;
}

```

## disassembly

```asm
0x180012320  push    rbp
0x180012322  push    rbx
0x180012323  mov     rbp, rsp
0x180012326  sub     rsp, 38h
0x18001232a  lea     rax, [rbp+hKey]
0x18001232e  xor     ebx, ebx
0x180012330  mov     r9d, 20019h; samDesired
0x180012336  mov     [rbp+hKey], rbx
0x18001233a  xor     r8d, r8d; ulOptions
0x18001233d  mov     [rsp+38h+phkResult], rax; phkResult
0x180012342  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\TabletPC"
0x180012349  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012350  call    cs:__imp_RegOpenKeyExW
0x180012356  test    eax, eax
0x180012358  jnz     short loc_1800123BC
0x18001235a  mov     rcx, [rbp+hKey]; hKey
0x18001235e  lea     rax, [rbp+cbData]
0x180012362  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180012367  lea     r9, [rbp+Type]; lpType
0x18001236b  lea     rax, [rbp+Data]
0x18001236f  mov     [rbp+Type], ebx
0x180012372  xor     r8d, r8d; lpReserved
0x180012375  mov     [rsp+38h+phkResult], rax; lpData
0x18001237a  lea     rdx, ValueName; "AutoStart"
0x180012381  mov     [rbp+Data], ebx
0x180012384  mov     [rbp+cbData], 4
0x18001238b  call    cs:__imp_RegQueryValueExW
0x180012391  test    eax, eax
0x180012393  jnz     short loc_1800123A3
0x180012395  cmp     [rbp+Type], 4
0x180012399  jnz     short loc_1800123A3
0x18001239b  cmp     [rbp+cbData], 4
0x18001239f  cmovz   ebx, [rbp+Data]
0x1800123a3  mov     rcx, [rbp+hKey]; hKey
0x1800123a7  call    cs:__imp_RegCloseKey
0x1800123ad  mov     edx, ebx
0x1800123af  xor     ecx, ecx
0x1800123b1  and     edx, 3
0x1800123b4  cmp     dl, 3
0x1800123b7  cmovnz  ecx, ebx
0x1800123ba  mov     ebx, ecx
0x1800123bc  mov     eax, ebx
0x1800123be  add     rsp, 38h
0x1800123c2  pop     rbx
0x1800123c3  pop     rbp
0x1800123c4  retn
```
