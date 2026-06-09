# CNonClusterTmInstance::GetRegistryValue(char const *,char const *,ulong *,uchar *,ulong *)

- ea: `0x180052bf0`
- end: `0x180052d3c`
- name: `?GetRegistryValue@CNonClusterTmInstance@@UEAAJPEBD0PEAKPEAE1@Z`
- size: `332`
- prototype: `int(CNonClusterTmInstance *__hidden this, const char *, const char *, unsigned int *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180052bf0`
- `0x1800709bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180052caf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180052cc7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180052cf0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180052caf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180052cc7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180052cf0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180052d21`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180052d21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052c54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052c63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052c72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052c54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052c63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052c72`

## pseudocode

```c
__int64 __fastcall CNonClusterTmInstance::GetRegistryValue(
        CNonClusterTmInstance *this,
        const char *a2,
        const char *a3,
        unsigned int *a4,
        unsigned __int8 *lpData,
        unsigned int *lpcbData)
{
  const unsigned __int16 *v6; // rcx
  int Value; // eax
  unsigned int v11; // ebx
  bool v12; // cc
  HKEY v14; // rcx
  HKEY v15; // [rsp+30h] [rbp-10h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+20h] BYREF

  v6 = (const unsigned __int16 *)*((_QWORD *)this + 5);
  v15 = 0;
  hKey = 0;
  phkResult = 0;
  Value = RegConnectHostnameW(v6, HKEY_LOCAL_MACHINE, &v15);
  v11 = Value;
  v12 = Value <= 0;
  if ( Value )
  {
LABEL_2:
    if ( v12 )
      goto LABEL_4;
    goto LABEL_3;
  }
  if ( a2 )
  {
    Value = RegOpenKeyExA(v15, "Software\\Microsoft\\MSDTC", 0, 0x20100u, &hKey);
    v11 = Value;
    v12 = Value <= 0;
    if ( Value )
      goto LABEL_2;
    Value = RegOpenKeyExA(hKey, a2, 0, 0x101u, &phkResult);
    v11 = Value;
    v12 = Value <= 0;
    if ( Value )
      goto LABEL_2;
    v14 = phkResult;
  }
  else
  {
    Value = RegOpenKeyExA(v15, "Software\\Microsoft\\MSDTC", 0, 0x101u, &hKey);
    v11 = Value;
    v12 = Value <= 0;
    if ( Value )
      goto LABEL_2;
    v14 = hKey;
  }
  v11 = 0;
  Value = RegQueryValueExA(v14, a3, 0, a4, lpData, lpcbData);
  if ( Value )
  {
    if ( Value > 0 )
    {
LABEL_3:
      v11 = (unsigned __int16)Value | 0x80070000;
      goto LABEL_4;
    }
    v11 = Value;
  }
LABEL_4:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v15 )
    RegCloseKey(v15);
  return v11;
}

```

## disassembly

```asm
0x180052bf0  mov     [rsp-18h+arg_8], rbx
0x180052bf5  mov     [rsp-18h+arg_10], rsi
0x180052bfa  push    rbp
0x180052bfb  push    rdi
0x180052bfc  push    r14
0x180052bfe  mov     rbp, rsp
0x180052c01  sub     rsp, 40h
0x180052c05  mov     rcx, [rcx+28h]; unsigned __int16 *
0x180052c09  mov     r14, r8
0x180052c0c  mov     rdi, rdx
0x180052c0f  mov     [rbp+var_10], 0
0x180052c17  lea     r8, [rbp+var_10]; HKEY *
0x180052c1b  mov     [rbp+hKey], 0
0x180052c23  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180052c2a  mov     [rbp+var_8], 0
0x180052c32  mov     rsi, r9
0x180052c35  call    ?RegConnectHostnameW@@YAJPEBGPEAUHKEY__@@PEAPEAU1@@Z; RegConnectHostnameW(ushort const *,HKEY__ *,HKEY__ * *)
0x180052c3a  mov     ebx, eax
0x180052c3c  test    eax, eax
0x180052c3e  jz      short loc_180052C8D
0x180052c40  jle     short loc_180052C4B
0x180052c42  movzx   ebx, ax
0x180052c45  or      ebx, 80070000h
0x180052c4b  mov     rcx, [rbp+hKey]; hKey
0x180052c4f  test    rcx, rcx
0x180052c52  jz      short loc_180052C5A
0x180052c54  call    cs:__imp_RegCloseKey
0x180052c5a  mov     rcx, [rbp+var_8]; hKey
0x180052c5e  test    rcx, rcx
0x180052c61  jz      short loc_180052C69
0x180052c63  call    cs:__imp_RegCloseKey
0x180052c69  mov     rcx, [rbp+var_10]; hKey
0x180052c6d  test    rcx, rcx
0x180052c70  jz      short loc_180052C78
0x180052c72  call    cs:__imp_RegCloseKey
0x180052c78  mov     rsi, [rsp+40h+arg_10]
0x180052c7d  mov     eax, ebx
0x180052c7f  mov     rbx, [rsp+40h+arg_8]
0x180052c84  add     rsp, 40h
0x180052c88  pop     r14
0x180052c8a  pop     rdi
0x180052c8b  pop     rbp
0x180052c8c  retn
0x180052c8d  mov     rcx, [rbp+var_10]; hKey
0x180052c91  lea     rax, [rbp+hKey]
0x180052c95  xor     r8d, r8d; ulOptions
0x180052c98  mov     [rsp+40h+phkResult], rax; phkResult
0x180052c9d  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\MSDTC"
0x180052ca4  test    rdi, rdi
0x180052ca7  jnz     short loc_180052CC1
0x180052ca9  mov     r9d, 101h; samDesired
0x180052caf  call    cs:__imp_RegOpenKeyExA
0x180052cb5  mov     ebx, eax
0x180052cb7  test    eax, eax
0x180052cb9  jnz     short loc_180052C40
0x180052cbb  mov     rcx, [rbp+hKey]
0x180052cbf  jmp     short loc_180052D04
0x180052cc1  mov     r9d, 20100h; samDesired
0x180052cc7  call    cs:__imp_RegOpenKeyExA
0x180052ccd  mov     ebx, eax
0x180052ccf  test    eax, eax
0x180052cd1  jnz     loc_180052C40
0x180052cd7  mov     rcx, [rbp+hKey]; hKey
0x180052cdb  lea     rax, [rbp+var_8]
0x180052cdf  mov     r9d, 101h; samDesired
0x180052ce5  mov     [rsp+40h+phkResult], rax; phkResult
0x180052cea  xor     r8d, r8d; ulOptions
0x180052ced  mov     rdx, rdi; lpSubKey
0x180052cf0  call    cs:__imp_RegOpenKeyExA
0x180052cf6  mov     ebx, eax
0x180052cf8  test    eax, eax
0x180052cfa  jnz     loc_180052C40
0x180052d00  mov     rcx, [rbp+var_8]; hKey
0x180052d04  mov     rax, [rbp+arg_28]
0x180052d08  mov     r9, rsi; lpType
0x180052d0b  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180052d10  xor     r8d, r8d; lpReserved
0x180052d13  mov     rax, [rbp+lpData]
0x180052d17  mov     rdx, r14; lpValueName
0x180052d1a  mov     [rsp+40h+phkResult], rax; lpData
0x180052d1f  xor     ebx, ebx
0x180052d21  call    cs:__imp_RegQueryValueExA
0x180052d27  test    eax, eax
0x180052d29  jz      loc_180052C4B
0x180052d2f  jg      loc_180052C42
0x180052d35  mov     ebx, eax
0x180052d37  jmp     loc_180052C4B
```
