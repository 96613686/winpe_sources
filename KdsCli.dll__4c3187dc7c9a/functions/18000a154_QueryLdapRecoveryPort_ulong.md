# QueryLdapRecoveryPort(ulong *)

- ea: `0x18000a154`
- end: `0x18000a265`
- name: `?QueryLdapRecoveryPort@@YAJPEAK@Z`
- size: `273`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009408`

## callees

- `0x18000a154`
- `0x18001a450`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a255`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a255`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a206`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a206`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a1a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a1a5`

## string_xrefs

- `0x18000a1b7`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`
- `0x18000a226`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`

## pseudocode

```c
__int64 __fastcall QueryLdapRecoveryPort(unsigned int *a1)
{
  int v2; // ebx
  unsigned int v3; // r9d
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  DWORD Type; // [rsp+58h] [rbp+28h] BYREF
  unsigned int Data; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  *a1 = 0;
  Data = 0;
  Type = 0;
  cbData = 0;
  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\KdsClient", 0, 1u, &hKey);
  if ( v2 )
  {
    v3 = 2067;
  }
  else
  {
    cbData = 4;
    v2 = RegQueryValueExW(hKey, L"LdapRecoveryPort", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v2 )
    {
      if ( Type == 4 )
      {
        v2 = 0;
        *a1 = Data;
      }
      else
      {
        v2 = -2147024809;
        SidKeyDebugTraceError(
          0x80070057,
          "hr",
          "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx",
          0x82Cu);
      }
      goto LABEL_10;
    }
    v3 = 2083;
  }
  SidKeyDebugTraceError(v2, "dwReturn", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", v3);
  if ( v2 > 0 )
    v2 = (unsigned __int16)v2 | 0x80070000;
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000a154  push    rbp
0x18000a156  push    rbx
0x18000a157  push    rdi
0x18000a158  mov     rbp, rsp
0x18000a15b  sub     rsp, 30h
0x18000a15f  mov     rdi, rcx
0x18000a162  mov     dword ptr [rcx], 0
0x18000a168  lea     rax, [rbp+hKey]
0x18000a16c  mov     [rbp+Data], 0
0x18000a173  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a17a  mov     [rsp+30h+phkResult], rax; phkResult
0x18000a17f  mov     r9d, 1; samDesired
0x18000a185  mov     [rbp+Type], 0
0x18000a18c  xor     r8d, r8d; ulOptions
0x18000a18f  mov     [rbp+cbData], 0
0x18000a196  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Kds"...
0x18000a19d  mov     [rbp+hKey], 0
0x18000a1a5  call    cs:__imp_RegOpenKeyExW
0x18000a1ab  mov     ebx, eax
0x18000a1ad  test    eax, eax
0x18000a1af  jz      short loc_18000A1DB
0x18000a1b1  mov     r9d, 813h; unsigned int
0x18000a1b7  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000a1be  mov     ecx, ebx; unsigned int
0x18000a1c0  lea     rdx, aDwreturn; "dwReturn"
0x18000a1c7  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000a1cc  test    ebx, ebx
0x18000a1ce  jle     short loc_18000A24C
0x18000a1d0  movzx   ebx, bx
0x18000a1d3  or      ebx, 80070000h
0x18000a1d9  jmp     short loc_18000A24C
0x18000a1db  mov     rcx, [rbp+hKey]; hKey
0x18000a1df  lea     rax, [rbp+cbData]
0x18000a1e3  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000a1e8  lea     r9, [rbp+Type]; lpType
0x18000a1ec  lea     rax, [rbp+Data]
0x18000a1f0  mov     [rbp+cbData], 4
0x18000a1f7  xor     r8d, r8d; lpReserved
0x18000a1fa  mov     [rsp+30h+phkResult], rax; lpData
0x18000a1ff  lea     rdx, ValueName; "LdapRecoveryPort"
0x18000a206  call    cs:__imp_RegQueryValueExW
0x18000a20c  mov     ebx, eax
0x18000a20e  test    eax, eax
0x18000a210  jz      short loc_18000A21A
0x18000a212  mov     r9d, 823h
0x18000a218  jmp     short loc_18000A1B7
0x18000a21a  cmp     [rbp+Type], 4
0x18000a21e  jz      short loc_18000A245
0x18000a220  mov     r9d, 82Ch; unsigned int
0x18000a226  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000a22d  lea     rdx, aHr; "hr"
0x18000a234  mov     ecx, 80070057h; unsigned int
0x18000a239  mov     ebx, 80070057h
0x18000a23e  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000a243  jmp     short loc_18000A24C
0x18000a245  mov     eax, [rbp+Data]
0x18000a248  xor     ebx, ebx
0x18000a24a  mov     [rdi], eax
0x18000a24c  mov     rcx, [rbp+hKey]; hKey
0x18000a250  test    rcx, rcx
0x18000a253  jz      short loc_18000A25B
0x18000a255  call    cs:__imp_RegCloseKey
0x18000a25b  mov     eax, ebx
0x18000a25d  add     rsp, 30h
0x18000a261  pop     rdi
0x18000a262  pop     rbx
0x18000a263  pop     rbp
0x18000a264  retn
```
