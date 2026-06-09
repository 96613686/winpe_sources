# RegGetDword

- ea: `0x180012f30`
- end: `0x180012fff`
- name: `RegGetDword`
- size: `207`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000f418`

## callees

- `0x180012f30`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180012fe3`
- `KERNEL32!SetLastError` at `0x180012ff0`
- `KERNEL32!SetLastError` at `0x180012fe3`
- `KERNEL32!SetLastError` at `0x180012ff0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012fdb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012fdb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012fbb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012fbb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012f88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012f88`

## string_xrefs

- `0x180012f81`: `Microsoft\PolicyManager\current\device\update`

## pseudocode

```c
__int64 __fastcall RegGetDword(HKEY a1, __int64 a2, __int64 a3)
{
  DWORD v3; // ecx
  LSTATUS v4; // eax
  LSTATUS v5; // ebx
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF
  int v9; // [rsp+5Ch] [rbp+24h]
  unsigned int Data; // [rsp+60h] [rbp+28h] BYREF
  int v11; // [rsp+64h] [rbp+2Ch]
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v11 = HIDWORD(a3);
  v9 = HIDWORD(a2);
  hKey = 0;
  Data = 0;
  cbData = 4;
  Type = 0;
  if ( a1 )
  {
    v4 = RegOpenKeyExW(a1, L"Microsoft\\PolicyManager\\current\\device\\update", 0, 0x20019u, &hKey);
    if ( v4 || !hKey )
    {
      v3 = v4;
      goto LABEL_11;
    }
    v5 = RegQueryValueExW(hKey, L"QuickMachineRecoveryEnrolled", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v5 )
    {
      if ( cbData == 4 )
      {
LABEL_9:
        RegCloseKey(hKey);
        SetLastError(v5);
        return Data;
      }
      v5 = 13;
    }
    Data = 0;
    goto LABEL_9;
  }
  v3 = 87;
LABEL_11:
  SetLastError(v3);
  return 0;
}

```

## disassembly

```asm
0x180012f30  mov     qword ptr [rsp-10h+Data], r8
0x180012f35  mov     qword ptr [rsp-10h+cbData], rdx
0x180012f3a  push    rbp
0x180012f3b  push    rbx
0x180012f3c  mov     rbp, rsp
0x180012f3f  sub     rsp, 38h
0x180012f43  mov     [rbp+hKey], 0
0x180012f4b  mov     [rbp+Data], 0
0x180012f52  mov     [rbp+cbData], 4
0x180012f59  mov     [rbp+Type], 0
0x180012f60  test    rcx, rcx
0x180012f63  jnz     short loc_180012F6F
0x180012f65  mov     ecx, 57h ; 'W'; hKey
0x180012f6a  jmp     loc_180012FF0
0x180012f6f  lea     rax, [rbp+hKey]
0x180012f73  mov     r9d, 20019h; samDesired
0x180012f79  xor     r8d, r8d; ulOptions
0x180012f7c  mov     [rsp+38h+phkResult], rax; phkResult
0x180012f81  lea     rdx, aMicrosoftPolic_0; "Microsoft\\PolicyManager\\current\\devi"...
0x180012f88  call    cs:__imp_RegOpenKeyExW
0x180012f8e  test    eax, eax
0x180012f90  jnz     short loc_180012FEE
0x180012f92  mov     rcx, [rbp+hKey]; hKey
0x180012f96  test    rcx, rcx
0x180012f99  jz      short loc_180012FEE
0x180012f9b  lea     rax, [rbp+cbData]
0x180012f9f  xor     r8d, r8d; lpReserved
0x180012fa2  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180012fa7  lea     r9, [rbp+Type]; lpType
0x180012fab  lea     rax, [rbp+Data]
0x180012faf  lea     rdx, aQuickmachinere; "QuickMachineRecoveryEnrolled"
0x180012fb6  mov     [rsp+38h+phkResult], rax; lpData
0x180012fbb  call    cs:__imp_RegQueryValueExW
0x180012fc1  mov     ebx, eax
0x180012fc3  test    eax, eax
0x180012fc5  jnz     short loc_180012FD0
0x180012fc7  cmp     [rbp+cbData], 4
0x180012fcb  jz      short loc_180012FD7
0x180012fcd  lea     ebx, [rax+0Dh]
0x180012fd0  mov     [rbp+Data], 0
0x180012fd7  mov     rcx, [rbp+hKey]; hKey
0x180012fdb  call    cs:__imp_RegCloseKey
0x180012fe1  mov     ecx, ebx; dwErrCode
0x180012fe3  call    cs:__imp_SetLastError
0x180012fe9  mov     eax, [rbp+Data]
0x180012fec  jmp     short loc_180012FF8
0x180012fee  mov     ecx, eax; dwErrCode
0x180012ff0  call    cs:__imp_SetLastError
0x180012ff6  xor     eax, eax
0x180012ff8  add     rsp, 38h
0x180012ffc  pop     rbx
0x180012ffd  pop     rbp
0x180012ffe  retn
```
