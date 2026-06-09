# CreateMOOBERunningValue(void)

- ea: `0x14000b074`
- end: `0x14000b1a3`
- name: `?CreateMOOBERunningValue@@YA?AW4tagMOOBE_RUNNING_STATE@@XZ`
- size: `303`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001a54c`

## callees

- `0x14000b074`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x14000b11a`
- `ADVAPI32!RegQueryValueExW` at `0x14000b11a`
- `ADVAPI32!RegSetValueExW` at `0x14000b17a`
- `ADVAPI32!RegSetValueExW` at `0x14000b17a`
- `ADVAPI32!RegCreateKeyExW` at `0x14000b0cd`
- `ADVAPI32!RegCreateKeyExW` at `0x14000b0cd`
- `ADVAPI32!RegFlushKey` at `0x14000b189`
- `ADVAPI32!RegFlushKey` at `0x14000b189`
- `ADVAPI32!RegCloseKey` at `0x14000b193`
- `ADVAPI32!RegCloseKey` at `0x14000b193`

## pseudocode

```c
__int64 CreateMOOBERunningValue()
{
  LSTATUS v1; // eax
  unsigned int v2; // ebx
  BYTE v3[8]; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  DWORD Type; // [rsp+80h] [rbp+20h] BYREF
  unsigned int Data; // [rsp+88h] [rbp+28h] BYREF
  DWORD dwDisposition; // [rsp+90h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+38h] BYREF

  hKey = 0;
  dwDisposition = 0;
  if ( RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSAT",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         &dwDisposition) )
  {
    return 1;
  }
  Type = 0;
  Data = 0;
  cbData = 4;
  v1 = RegQueryValueExW(hKey, L"MOOBE", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( v1 == 2 )
  {
    v2 = 0;
    goto LABEL_12;
  }
  if ( v1 || Type != 4 || (v2 = Data) != 0 && Data - 1 > 1 )
  {
    v2 = 1;
    goto LABEL_12;
  }
  if ( Data != 2 )
  {
LABEL_12:
    *(_DWORD *)v3 = 1;
    if ( RegSetValueExW(hKey, L"MOOBE", 0, 4u, v3, 4u) )
      v2 = 1;
  }
  RegFlushKey(hKey);
  RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x14000b074  push    rbp
0x14000b076  push    rbx
0x14000b077  push    rdi
0x14000b078  mov     rbp, rsp
0x14000b07b  sub     rsp, 60h
0x14000b07f  lea     rax, [rbp+dwDisposition]
0x14000b083  mov     [rbp+hKey], 0
0x14000b08b  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x14000b090  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14000b097  lea     rax, [rbp+hKey]
0x14000b09b  mov     [rbp+dwDisposition], 0
0x14000b0a2  mov     [rsp+60h+phkResult], rax; phkResult
0x14000b0a7  xor     r9d, r9d; lpClass
0x14000b0aa  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14000b0b3  xor     r8d, r8d; Reserved
0x14000b0b6  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x14000b0be  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000b0c5  mov     [rsp+60h+dwOptions], 0; dwOptions
0x14000b0cd  call    cs:__imp_RegCreateKeyExW
0x14000b0d3  test    eax, eax
0x14000b0d5  jz      short loc_14000B0E1
0x14000b0d7  mov     eax, 1
0x14000b0dc  jmp     loc_14000B19B
0x14000b0e1  mov     rcx, [rbp+hKey]; hKey
0x14000b0e5  lea     rax, [rbp+cbData]
0x14000b0e9  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x14000b0ee  lea     r9, [rbp+Type]; lpType
0x14000b0f2  lea     rax, [rbp+Data]
0x14000b0f6  mov     [rbp+Type], 0
0x14000b0fd  xor     r8d, r8d; lpReserved
0x14000b100  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x14000b105  lea     rdx, ValueName; "MOOBE"
0x14000b10c  mov     [rbp+Data], 0
0x14000b113  mov     [rbp+cbData], 4
0x14000b11a  call    cs:__imp_RegQueryValueExW
0x14000b120  mov     edi, 1
0x14000b125  cmp     eax, 2
0x14000b128  jnz     short loc_14000B12E
0x14000b12a  xor     ebx, ebx
0x14000b12c  jmp     short loc_14000B152
0x14000b12e  test    eax, eax
0x14000b130  jnz     short loc_14000B150
0x14000b132  cmp     [rbp+Type], 4
0x14000b136  jnz     short loc_14000B150
0x14000b138  mov     ebx, [rbp+Data]
0x14000b13b  mov     eax, ebx
0x14000b13d  test    ebx, ebx
0x14000b13f  jz      short loc_14000B149
0x14000b141  sub     eax, edi
0x14000b143  jz      short loc_14000B149
0x14000b145  cmp     eax, edi
0x14000b147  jnz     short loc_14000B150
0x14000b149  cmp     ebx, 2
0x14000b14c  jz      short loc_14000B185
0x14000b14e  jmp     short loc_14000B152
0x14000b150  mov     ebx, edi
0x14000b152  mov     rcx, [rbp+hKey]; hKey
0x14000b156  lea     rax, [rbp+var_10]
0x14000b15a  mov     [rsp+60h+samDesired], 4; cbData
0x14000b162  lea     rdx, ValueName; "MOOBE"
0x14000b169  mov     r9d, 4; dwType
0x14000b16f  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x14000b174  xor     r8d, r8d; Reserved
0x14000b177  mov     dword ptr [rbp+var_10], edi
0x14000b17a  call    cs:__imp_RegSetValueExW
0x14000b180  test    eax, eax
0x14000b182  cmovnz  ebx, edi
0x14000b185  mov     rcx, [rbp+hKey]; hKey
0x14000b189  call    cs:__imp_RegFlushKey
0x14000b18f  mov     rcx, [rbp+hKey]; hKey
0x14000b193  call    cs:__imp_RegCloseKey
0x14000b199  mov     eax, ebx
0x14000b19b  add     rsp, 60h
0x14000b19f  pop     rdi
0x14000b1a0  pop     rbx
0x14000b1a1  pop     rbp
0x14000b1a2  retn
```
