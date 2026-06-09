# CopyRegistry

- ea: `0x180002f30`
- end: `0x1800030e0`
- name: `CopyRegistry`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002f30`

## callees

- `0x180002f30`

## import_xrefs

- `ADVAPI32!RegCreateKeyExA` at `0x180003087`
- `ADVAPI32!RegCreateKeyExA` at `0x180003087`
- `ADVAPI32!RegCloseKey` at `0x1800030a5`
- `ADVAPI32!RegCloseKey` at `0x1800030af`
- `ADVAPI32!RegCloseKey` at `0x1800030a5`
- `ADVAPI32!RegCloseKey` at `0x1800030af`
- `ADVAPI32!RegOpenKeyExA` at `0x180003046`
- `ADVAPI32!RegOpenKeyExA` at `0x180003046`
- `ADVAPI32!RegEnumKeyA` at `0x1800030c5`
- `ADVAPI32!RegEnumKeyA` at `0x1800030c5`
- `ADVAPI32!RegSetValueExA` at `0x180002fc4`
- `ADVAPI32!RegSetValueExA` at `0x180002fc4`
- `ADVAPI32!RegEnumValueA` at `0x18000300d`
- `ADVAPI32!RegEnumValueA` at `0x18000300d`
- `ADVAPI32!RegQueryValueExA` at `0x180002f9a`
- `ADVAPI32!RegQueryValueExA` at `0x180002f9a`

## pseudocode

```c
LSTATUS __fastcall CopyRegistry(HKEY a1, HKEY a2, unsigned int a3)
{
  DWORD v4; // edx
  HKEY v6; // rdi
  int i; // ebx
  int v8; // ebx
  DWORD j; // edx
  LSTATUS result; // eax
  DWORD dwType; // [rsp+50h] [rbp-28h] BYREF
  DWORD cchValueName; // [rsp+54h] [rbp-24h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-10h] BYREF
  DWORD v16; // [rsp+C8h] [rbp+50h] BYREF

  dwType = 0;
  v4 = 0;
  phkResult = 0;
  hKey = 0;
  v6 = a1;
  cbData = 0;
  for ( i = 1; ; ++i )
  {
    cchValueName = 256;
    v16 = 0x4000;
    if ( RegEnumValueA(a1, v4, ValueName, &cchValueName, 0, &dwType, &Data, &v16) )
      break;
    if ( a3 || RegQueryValueExA(a2, ValueName, 0, 0, 0, &cbData) )
      RegSetValueExA(a2, ValueName, 0, dwType, &Data, v16);
    v4 = i;
    a1 = v6;
  }
  v8 = 1;
  for ( j = 0; ; j = v8++ )
  {
    result = RegEnumKeyA(v6, j, Name, 0x100u);
    if ( result )
      break;
    if ( !RegOpenKeyExA(v6, Name, 0, 0x20019u, &phkResult) )
    {
      if ( !RegCreateKeyExA(a2, Name, 0, 0, 0, 0x2001Fu, 0, &hKey, 0) )
      {
        CopyRegistry(phkResult, hKey, a3);
        RegCloseKey(hKey);
      }
      RegCloseKey(phkResult);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002f30  push    rbp
0x180002f32  push    rbx
0x180002f33  push    rsi
0x180002f34  push    rdi
0x180002f35  push    r12
0x180002f37  push    r14
0x180002f39  mov     rbp, rsp
0x180002f3c  sub     rsp, 78h
0x180002f40  mov     rsi, rdx
0x180002f43  mov     [rbp+dwType], 0
0x180002f4a  xor     edx, edx
0x180002f4c  mov     [rbp+phkResult], 0
0x180002f54  mov     r14d, r8d
0x180002f57  mov     [rbp+hKey], 0
0x180002f5f  mov     rdi, rcx
0x180002f62  mov     [rbp+cbData], 0
0x180002f69  mov     ebx, 1
0x180002f6e  lea     r12, ValueName
0x180002f75  jmp     short loc_180002FD1
0x180002f77  test    r14d, r14d
0x180002f7a  jnz     short loc_180002FA4
0x180002f7c  lea     rax, [rbp+cbData]
0x180002f80  xor     r9d, r9d; lpType
0x180002f83  mov     [rsp+78h+lpcbData], rax; lpcbData
0x180002f88  xor     r8d, r8d; lpReserved
0x180002f8b  mov     rdx, r12; lpValueName
0x180002f8e  mov     [rsp+78h+lpData], 0; lpData
0x180002f97  mov     rcx, rsi; hKey
0x180002f9a  call    cs:__imp_RegQueryValueExA
0x180002fa0  test    eax, eax
0x180002fa2  jz      short loc_180002FCA
0x180002fa4  mov     eax, [rbp+arg_18]
0x180002fa7  xor     r8d, r8d; Reserved
0x180002faa  mov     r9d, [rbp+dwType]; dwType
0x180002fae  mov     rdx, r12; lpValueName
0x180002fb1  mov     dword ptr [rsp+78h+lpcbData], eax; cbData
0x180002fb5  mov     rcx, rsi; hKey
0x180002fb8  lea     rax, Data
0x180002fbf  mov     [rsp+78h+lpData], rax; lpData
0x180002fc4  call    cs:__imp_RegSetValueExA
0x180002fca  mov     edx, ebx; dwIndex
0x180002fcc  mov     rcx, rdi; hKey
0x180002fcf  inc     ebx
0x180002fd1  lea     rax, [rbp+arg_18]
0x180002fd5  mov     [rbp+cchValueName], 100h
0x180002fdc  mov     [rsp+78h+var_40], rax; lpcbData
0x180002fe1  lea     r9, [rbp+cchValueName]; lpcchValueName
0x180002fe5  lea     rax, Data
0x180002fec  mov     [rbp+arg_18], 4000h
0x180002ff3  mov     [rsp+78h+var_48], rax; lpData
0x180002ff8  mov     r8, r12; lpValueName
0x180002ffb  lea     rax, [rbp+dwType]
0x180002fff  mov     [rsp+78h+lpcbData], rax; lpType
0x180003004  mov     [rsp+78h+lpData], 0; lpReserved
0x18000300d  call    cs:__imp_RegEnumValueA
0x180003013  test    eax, eax
0x180003015  jz      loc_180002F77
0x18000301b  mov     ebx, 1
0x180003020  lea     r12, Name
0x180003027  xor     edx, edx
0x180003029  jmp     loc_1800030B9
0x18000302e  lea     rax, [rbp+phkResult]
0x180003032  mov     r9d, 20019h; samDesired
0x180003038  xor     r8d, r8d; ulOptions
0x18000303b  mov     [rsp+78h+lpData], rax; phkResult
0x180003040  mov     rdx, r12; lpSubKey
0x180003043  mov     rcx, rdi; hKey
0x180003046  call    cs:__imp_RegOpenKeyExA
0x18000304c  test    eax, eax
0x18000304e  jnz     short loc_1800030B5
0x180003050  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x180003059  lea     rax, [rbp+hKey]
0x18000305d  mov     [rsp+78h+var_40], rax; phkResult
0x180003062  xor     r9d, r9d; lpClass
0x180003065  mov     [rsp+78h+var_48], 0; lpSecurityAttributes
0x18000306e  xor     r8d, r8d; Reserved
0x180003071  mov     dword ptr [rsp+78h+lpcbData], 2001Fh; samDesired
0x180003079  mov     rdx, r12; lpSubKey
0x18000307c  mov     rcx, rsi; hKey
0x18000307f  mov     dword ptr [rsp+78h+lpData], 0; dwOptions
0x180003087  call    cs:__imp_RegCreateKeyExA
0x18000308d  test    eax, eax
0x18000308f  jnz     short loc_1800030AB
0x180003091  mov     rdx, [rbp+hKey]
0x180003095  mov     r8d, r14d
0x180003098  mov     rcx, [rbp+phkResult]
0x18000309c  call    CopyRegistry
0x1800030a1  mov     rcx, [rbp+hKey]; hKey
0x1800030a5  call    cs:__imp_RegCloseKey
0x1800030ab  mov     rcx, [rbp+phkResult]; hKey
0x1800030af  call    cs:__imp_RegCloseKey
0x1800030b5  mov     edx, ebx; dwIndex
0x1800030b7  inc     ebx
0x1800030b9  mov     r9d, 100h; cchName
0x1800030bf  mov     r8, r12; lpName
0x1800030c2  mov     rcx, rdi; hKey
0x1800030c5  call    cs:__imp_RegEnumKeyA
0x1800030cb  test    eax, eax
0x1800030cd  jz      loc_18000302E
0x1800030d3  add     rsp, 78h
0x1800030d7  pop     r14
0x1800030d9  pop     r12
0x1800030db  pop     rdi
0x1800030dc  pop     rsi
0x1800030dd  pop     rbx
0x1800030de  pop     rbp
0x1800030df  retn
```
