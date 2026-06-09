# IsInLSAProcess

- ea: `0x18004eb84`
- end: `0x18004eca8`
- name: `IsInLSAProcess`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002c3d4`

## callees

- `0x18002bf08`
- `0x18004eb84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ec07`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ec07`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ec67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ec67`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004ec3f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004ec3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004ec4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004ec4f`

## pseudocode

```c
_BOOL8 IsInLSAProcess()
{
  int v0; // ebx
  int v1; // eax
  char TrustedEnvironment; // cl
  int Data; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  DWORD Type; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  v0 = dword_1800A4AD0;
  hKey = 0;
  Data = 0;
  Type = 0;
  cbData = 4;
  if ( dword_1800A4AD0 == -1 )
  {
    v1 = g_TrustedEnvironment;
    if ( g_TrustedEnvironment )
    {
      TrustedEnvironment = g_TrustedEnvironment;
    }
    else
    {
      TrustedEnvironment = GetTrustedEnvironment();
      v1 = g_TrustedEnvironment;
    }
    if ( (TrustedEnvironment & 0x18) != 0 )
      goto LABEL_15;
    if ( !v1 )
      LOBYTE(v1) = GetTrustedEnvironment();
    if ( (v1 & 4) != 0 )
    {
LABEL_15:
      v0 = 0;
    }
    else
    {
      v0 = 0;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlset\\Control\\Lsa", 0, 1u, &hKey) )
      {
        if ( !RegQueryValueExW(hKey, L"LsaPid", 0, &Type, (LPBYTE)&Data, &cbData) )
          v0 = Data == GetCurrentProcessId();
        RegCloseKey(hKey);
      }
    }
    dword_1800A4AD0 = v0;
  }
  return v0 == 1;
}

```

## disassembly

```asm
0x18004eb84  mov     rax, rsp
0x18004eb87  push    rbx
0x18004eb88  push    rsi
0x18004eb89  sub     rsp, 38h
0x18004eb8d  mov     ebx, cs:dword_1800A4AD0
0x18004eb93  mov     esi, 1
0x18004eb98  mov     qword ptr [rax+20h], 0
0x18004eba0  mov     dword ptr [rax+8], 0
0x18004eba7  mov     dword ptr [rax+18h], 0
0x18004ebae  mov     dword ptr [rax+10h], 4
0x18004ebb5  cmp     ebx, 0FFFFFFFFh
0x18004ebb8  jnz     loc_18004EC79
0x18004ebbe  mov     eax, cs:g_TrustedEnvironment
0x18004ebc4  test    eax, eax
0x18004ebc6  jz      loc_18004EC88
0x18004ebcc  mov     ecx, eax
0x18004ebce  test    cl, 18h
0x18004ebd1  jnz     loc_18004ECA4
0x18004ebd7  test    eax, eax
0x18004ebd9  jz      loc_18004EC9A
0x18004ebdf  test    al, 4
0x18004ebe1  jnz     loc_18004ECA4
0x18004ebe7  lea     rax, [rsp+48h+hKey]
0x18004ebec  mov     r9d, esi; samDesired
0x18004ebef  xor     r8d, r8d; ulOptions
0x18004ebf2  mov     [rsp+48h+phkResult], rax; phkResult
0x18004ebf7  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlset\\Control\\Lsa"
0x18004ebfe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004ec05  xor     ebx, ebx
0x18004ec07  call    cs:__imp_RegOpenKeyExW
0x18004ec0e  nop     dword ptr [rax+rax+00h]
0x18004ec13  test    eax, eax
0x18004ec15  jnz     short loc_18004EC73
0x18004ec17  mov     rcx, [rsp+48h+hKey]; hKey
0x18004ec1c  lea     rax, [rsp+48h+cbData]
0x18004ec21  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18004ec26  lea     r9, [rsp+48h+Type]; lpType
0x18004ec2b  lea     rax, [rsp+48h+Data]
0x18004ec30  xor     r8d, r8d; lpReserved
0x18004ec33  lea     rdx, aLsapid; "LsaPid"
0x18004ec3a  mov     [rsp+48h+phkResult], rax; lpData
0x18004ec3f  call    cs:__imp_RegQueryValueExW
0x18004ec46  nop     dword ptr [rax+rax+00h]
0x18004ec4b  test    eax, eax
0x18004ec4d  jnz     short loc_18004EC62
0x18004ec4f  call    cs:__imp_GetCurrentProcessId
0x18004ec56  nop     dword ptr [rax+rax+00h]
0x18004ec5b  cmp     [rsp+48h+Data], eax
0x18004ec5f  cmovz   ebx, esi
0x18004ec62  mov     rcx, [rsp+48h+hKey]; hKey
0x18004ec67  call    cs:__imp_RegCloseKey
0x18004ec6e  nop     dword ptr [rax+rax+00h]
0x18004ec73  mov     cs:dword_1800A4AD0, ebx
0x18004ec79  xor     eax, eax
0x18004ec7b  cmp     ebx, esi
0x18004ec7d  setz    al
0x18004ec80  add     rsp, 38h
0x18004ec84  pop     rsi
0x18004ec85  pop     rbx
0x18004ec86  retn
0x18004ec88  call    GetTrustedEnvironment
0x18004ec8d  mov     ecx, eax
0x18004ec8f  mov     eax, cs:g_TrustedEnvironment
0x18004ec95  jmp     loc_18004EBCE
0x18004ec9a  call    GetTrustedEnvironment
0x18004ec9f  jmp     loc_18004EBDF
0x18004eca4  xor     ebx, ebx
0x18004eca6  jmp     short loc_18004EC73
```
