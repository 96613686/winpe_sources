# CSpLogger::IsEtwEnabled(void)

- ea: `0x1400099e4`
- end: `0x140009aa5`
- name: `?IsEtwEnabled@CSpLogger@@SA_NXZ`
- size: `193`
- prototype: `bool(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000985c`
- `0x140009aac`
- `0x14001c580`

## callees

- `0x1400099e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140009a6b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140009a6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140009a29`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140009a29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140009a90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140009a90`

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
0x1400099e4  sub     rsp, 38h
0x1400099e8  cmp     cs:?etwStatus@?1??IsEtwEnabled@CSpLogger@@SA_NXZ@4W4EtwStatus@2@A, 0; CSpLogger::EtwStatus `CSpLogger::IsEtwEnabled(void)'::`2'::etwStatus
0x1400099ef  jnz     loc_140009A96
0x1400099f5  lea     rax, [rsp+38h+hKey]
0x1400099fa  mov     cs:?etwStatus@?1??IsEtwEnabled@CSpLogger@@SA_NXZ@4W4EtwStatus@2@A, 2; CSpLogger::EtwStatus `CSpLogger::IsEtwEnabled(void)'::`2'::etwStatus
0x140009a04  mov     r9d, 20019h; samDesired
0x140009a0a  mov     [rsp+38h+phkResult], rax; phkResult
0x140009a0f  xor     r8d, r8d; ulOptions
0x140009a12  mov     [rsp+38h+hKey], 0
0x140009a1b  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Speech_OneCore\\Te"...
0x140009a22  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140009a29  call    cs:__imp_RegOpenKeyExW
0x140009a2f  test    eax, eax
0x140009a31  jnz     short loc_140009A86
0x140009a33  mov     rcx, [rsp+38h+hKey]; hKey
0x140009a38  lea     r9, [rsp+38h+Type]; lpType
0x140009a3d  mov     [rsp+38h+Type], eax
0x140009a41  lea     rdx, ValueName; "ETWEnabled"
0x140009a48  mov     [rsp+38h+Data], eax
0x140009a4c  xor     r8d, r8d; lpReserved
0x140009a4f  lea     rax, [rsp+38h+cbData]
0x140009a54  mov     [rsp+38h+cbData], 4
0x140009a5c  mov     [rsp+38h+lpcbData], rax; lpcbData
0x140009a61  lea     rax, [rsp+38h+Data]
0x140009a66  mov     [rsp+38h+phkResult], rax; lpData
0x140009a6b  call    cs:__imp_RegQueryValueExW
0x140009a71  test    eax, eax
0x140009a73  jnz     short loc_140009A86
0x140009a75  cmp     [rsp+38h+Data], 1
0x140009a7a  jnz     short loc_140009A86
0x140009a7c  mov     cs:?etwStatus@?1??IsEtwEnabled@CSpLogger@@SA_NXZ@4W4EtwStatus@2@A, 1; CSpLogger::EtwStatus `CSpLogger::IsEtwEnabled(void)'::`2'::etwStatus
0x140009a86  mov     rcx, [rsp+38h+hKey]; hKey
0x140009a8b  test    rcx, rcx
0x140009a8e  jz      short loc_140009A96
0x140009a90  call    cs:__imp_RegCloseKey
0x140009a96  cmp     cs:?etwStatus@?1??IsEtwEnabled@CSpLogger@@SA_NXZ@4W4EtwStatus@2@A, 1; CSpLogger::EtwStatus `CSpLogger::IsEtwEnabled(void)'::`2'::etwStatus
0x140009a9d  setz    al
0x140009aa0  add     rsp, 38h
0x140009aa4  retn
```
