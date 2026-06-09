# GetExecPid(void)

- ea: `0x140005498`
- end: `0x14000555a`
- name: `?GetExecPid@@YAKXZ`
- size: `194`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140005ad0`

## callees

- `0x140005498`
- `0x140005938`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005517`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005517`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000550c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000550c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400054ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400054ce`

## string_xrefs

- `0x1400054e6`: `ProcessID`

## pseudocode

```c
__int64 GetExecPid(void)
{
  LSTATUS v0; // eax
  unsigned int Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  Data = 0;
  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WBEM\\CIMOM", 0, 0x20019u, &hKey);
  if ( v0 )
  {
    if ( v0 == -1
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10);
    }
  }
  else
  {
    Type = 0;
    cbData = 4;
    RegQueryValueExW(hKey, L"ProcessID", 0, &Type, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey);
  }
  return Data;
}

```

## disassembly

```asm
0x140005498  sub     rsp, 38h
0x14000549c  lea     rax, [rsp+38h+hKey]
0x1400054a1  mov     [rsp+38h+Data], 0
0x1400054a9  mov     r9d, 20019h; samDesired
0x1400054af  mov     [rsp+38h+phkResult], rax; phkResult
0x1400054b4  xor     r8d, r8d; ulOptions
0x1400054b7  mov     [rsp+38h+hKey], 0
0x1400054c0  lea     rdx, SubKey; "Software\\Microsoft\\WBEM\\CIMOM"
0x1400054c7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400054ce  call    cs:__imp_RegOpenKeyExW
0x1400054d4  test    eax, eax
0x1400054d6  jnz     short loc_14000551F
0x1400054d8  mov     rcx, [rsp+38h+hKey]; hKey
0x1400054dd  lea     r9, [rsp+38h+Type]; lpType
0x1400054e2  mov     [rsp+38h+Type], eax
0x1400054e6  lea     rdx, ValueName; "ProcessID"
0x1400054ed  lea     rax, [rsp+38h+cbData]
0x1400054f2  mov     [rsp+38h+cbData], 4
0x1400054fa  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1400054ff  xor     r8d, r8d; lpReserved
0x140005502  lea     rax, [rsp+38h+Data]
0x140005507  mov     [rsp+38h+phkResult], rax; lpData
0x14000550c  call    cs:__imp_RegQueryValueExW
0x140005512  mov     rcx, [rsp+38h+hKey]; hKey
0x140005517  call    cs:__imp_RegCloseKey
0x14000551d  jmp     short loc_140005551
0x14000551f  cmp     eax, 0FFFFFFFFh
0x140005522  jnz     short loc_140005551
0x140005524  mov     rcx, cs:WPP_GLOBAL_Control
0x14000552b  lea     rax, WPP_GLOBAL_Control
0x140005532  cmp     rcx, rax
0x140005535  jz      short loc_140005551
0x140005537  test    byte ptr [rcx+1Ch], 8
0x14000553b  jz      short loc_140005551
0x14000553d  cmp     byte ptr [rcx+19h], 0
0x140005541  jnz     short loc_140005551
0x140005543  mov     rcx, [rcx+10h]
0x140005547  mov     edx, 0Ah
0x14000554c  call    WPP_SF_
0x140005551  mov     eax, [rsp+38h+Data]
0x140005555  add     rsp, 38h
0x140005559  retn
```
