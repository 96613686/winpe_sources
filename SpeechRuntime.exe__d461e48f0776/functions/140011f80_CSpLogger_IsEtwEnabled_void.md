# CSpLogger::IsEtwEnabled(void)

- ea: `0x140011f80`
- end: `0x140012041`
- name: `?IsEtwEnabled@CSpLogger@@SA_NXZ`
- size: `193`
- prototype: `bool(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140011e08`
- `0x140012048`
- `0x1400120b8`

## callees

- `0x140011f80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011fc5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011fc5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001202c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001202c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140012007`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140012007`

## pseudocode

```c
bool CSpLogger::IsEtwEnabled(void)
{
  int Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  if ( !`CSpLogger::IsEtwEnabled'::`2'::etwStatus )
  {
    `CSpLogger::IsEtwEnabled'::`2'::etwStatus = 2;
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Speech_OneCore\\Test", 0, 0x20019u, &hKey) )
    {
      Type = 0;
      Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"ETWEnabled", 0, &Type, (LPBYTE)&Data, &cbData) && Data == 1 )
        `CSpLogger::IsEtwEnabled'::`2'::etwStatus = 1;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return `CSpLogger::IsEtwEnabled'::`2'::etwStatus == 1;
}

```

## disassembly

```asm
0x140011f80  sub     rsp, 38h
0x140011f84  cmp     cs:?etwStatus@?1??IsEtwEnabled@CSpLogger@@SA_NXZ@4W4EtwStatus@2@A, 0; CSpLogger::EtwStatus `CSpLogger::IsEtwEnabled(void)'::`2'::etwStatus
0x140011f8b  jnz     loc_140012032
0x140011f91  lea     rax, [rsp+38h+hKey]
0x140011f96  mov     cs:?etwStatus@?1??IsEtwEnabled@CSpLogger@@SA_NXZ@4W4EtwStatus@2@A, 2; CSpLogger::EtwStatus `CSpLogger::IsEtwEnabled(void)'::`2'::etwStatus
0x140011fa0  mov     r9d, 20019h; samDesired
0x140011fa6  mov     [rsp+38h+phkResult], rax; phkResult
0x140011fab  xor     r8d, r8d; ulOptions
0x140011fae  mov     [rsp+38h+hKey], 0
0x140011fb7  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Speech_OneCore\\Te"...
0x140011fbe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140011fc5  call    cs:__imp_RegOpenKeyExW
0x140011fcb  test    eax, eax
0x140011fcd  jnz     short loc_140012022
0x140011fcf  mov     rcx, [rsp+38h+hKey]; hKey
0x140011fd4  lea     r9, [rsp+38h+Type]; lpType
0x140011fd9  mov     [rsp+38h+Type], eax
0x140011fdd  lea     rdx, ValueName; "ETWEnabled"
0x140011fe4  mov     [rsp+38h+Data], eax
0x140011fe8  xor     r8d, r8d; lpReserved
0x140011feb  lea     rax, [rsp+38h+cbData]
0x140011ff0  mov     [rsp+38h+cbData], 4
0x140011ff8  mov     [rsp+38h+lpcbData], rax; lpcbData
0x140011ffd  lea     rax, [rsp+38h+Data]
0x140012002  mov     [rsp+38h+phkResult], rax; lpData
0x140012007  call    cs:__imp_RegQueryValueExW
0x14001200d  test    eax, eax
0x14001200f  jnz     short loc_140012022
0x140012011  cmp     [rsp+38h+Data], 1
0x140012016  jnz     short loc_140012022
0x140012018  mov     cs:?etwStatus@?1??IsEtwEnabled@CSpLogger@@SA_NXZ@4W4EtwStatus@2@A, 1; CSpLogger::EtwStatus `CSpLogger::IsEtwEnabled(void)'::`2'::etwStatus
0x140012022  mov     rcx, [rsp+38h+hKey]; hKey
0x140012027  test    rcx, rcx
0x14001202a  jz      short loc_140012032
0x14001202c  call    cs:__imp_RegCloseKey
0x140012032  cmp     cs:?etwStatus@?1??IsEtwEnabled@CSpLogger@@SA_NXZ@4W4EtwStatus@2@A, 1; CSpLogger::EtwStatus `CSpLogger::IsEtwEnabled(void)'::`2'::etwStatus
0x140012039  setz    al
0x14001203c  add     rsp, 38h
0x140012040  retn
```
