# UpdateTpmRegDword(HKEY__ *,ushort const *,ulong)

- ea: `0x180050a28`
- end: `0x180050ba5`
- name: `?UpdateTpmRegDword@@YA_NPEAUHKEY__@@PEBGK@Z`
- size: `381`
- prototype: `bool __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x1800341ec`

## callees

- `0x180050a28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050af9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050b76`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050af9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050b76`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180050a87`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180050a87`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180050b20`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180050b94`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180050b20`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180050b94`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180050b46`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180050b46`

## string_xrefs

- `0x180050b6c`: `UpdateTimeLast`
- `0x180050b8a`: `UpdateTimeLast`

## pseudocode

```c
char __fastcall UpdateTpmRegDword(HKEY hKey, LPCWSTR lpValueName, int a3)
{
  char v5; // r14
  int ValueW; // eax
  int v7; // ecx
  bool v8; // di
  LSTATUS v10; // eax
  bool v11; // sf
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-10h] BYREF
  int v13; // [rsp+88h] [rbp+38h] BYREF
  int Data; // [rsp+90h] [rbp+40h] BYREF
  DWORD v15; // [rsp+98h] [rbp+48h] BYREF

  Data = a3;
  SystemTimeAsFileTime = 0;
  v13 = 0;
  if ( !lpValueName )
    return 0;
  v15 = 4;
  v5 = 0;
  ValueW = RegGetValueW(hKey, 0, lpValueName, 0x10u, 0, &v13, &v15);
  if ( ValueW > 0 )
    ValueW = (unsigned __int16)ValueW | 0x80070000;
  if ( ValueW < 0 )
  {
    v7 = -1;
    v13 = -1;
  }
  else
  {
    v7 = v13;
  }
  v8 = v7 != -1 && v7 != Data;
  if ( ValueW == -2147024894 || v8 )
  {
    v10 = RegSetValueExW(hKey, lpValueName, 0, 4u, (const BYTE *)&Data, 4u);
    v11 = v10 < 0;
    if ( v10 > 0 )
      v11 = 1;
    if ( v11 )
    {
      if ( v8 )
      {
        RegDeleteValueW(hKey, lpValueName);
        return 1;
      }
    }
    else
    {
      v5 = 1;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      if ( RegSetValueExW(hKey, L"UpdateTimeLast", 0, 0xBu, (const BYTE *)&SystemTimeAsFileTime, 8u) < 0 )
        RegDeleteValueW(hKey, L"UpdateTimeLast");
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180050a28  mov     r11, rsp
0x180050a2b  mov     [r11+18h], r8d
0x180050a2f  push    rbp
0x180050a30  push    rbx
0x180050a31  push    rsi
0x180050a32  push    rdi
0x180050a33  push    r14
0x180050a35  mov     rbp, rsp
0x180050a38  sub     rsp, 50h
0x180050a3c  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180050a44  mov     rsi, rdx
0x180050a47  mov     [rbp+arg_8], 0
0x180050a4e  mov     rbx, rcx
0x180050a51  test    rdx, rdx
0x180050a54  jz      loc_180050B31
0x180050a5a  lea     rax, [rbp+arg_18]
0x180050a5e  mov     [rbp+arg_18], 4
0x180050a65  mov     [r11-48h], rax
0x180050a69  mov     r8, rdx; lpValue
0x180050a6c  lea     rax, [rbp+arg_8]
0x180050a70  mov     r9d, 10h; dwFlags
0x180050a76  mov     [r11-50h], rax
0x180050a7a  xor     edx, edx; lpSubKey
0x180050a7c  mov     qword ptr [r11-58h], 0
0x180050a84  xor     r14b, r14b
0x180050a87  call    cs:__imp_RegGetValueW
0x180050a8e  nop     dword ptr [rax+rax+00h]
0x180050a93  test    eax, eax
0x180050a95  jle     short loc_180050A9F
0x180050a97  movzx   eax, ax
0x180050a9a  or      eax, 80070000h
0x180050a9f  or      edx, 0FFFFFFFFh
0x180050aa2  test    eax, eax
0x180050aa4  js      loc_180050B35
0x180050aaa  mov     ecx, [rbp+arg_8]
0x180050aad  cmp     ecx, edx
0x180050aaf  jnz     short loc_180050ACF
0x180050ab1  xor     dil, dil
0x180050ab4  cmp     eax, 80070002h
0x180050ab9  jz      short loc_180050AD9
0x180050abb  test    dil, dil
0x180050abe  jnz     short loc_180050AD9
0x180050ac0  mov     al, r14b
0x180050ac3  add     rsp, 50h
0x180050ac7  pop     r14
0x180050ac9  pop     rdi
0x180050aca  pop     rsi
0x180050acb  pop     rbx
0x180050acc  pop     rbp
0x180050acd  retn
0x180050acf  cmp     ecx, [rbp+Data]
0x180050ad2  jz      short loc_180050AB1
0x180050ad4  mov     dil, 1
0x180050ad7  jmp     short loc_180050AB4
0x180050ad9  lea     rax, [rbp+Data]
0x180050add  mov     [rsp+50h+cbData], 4; cbData
0x180050ae5  mov     r9d, 4; dwType
0x180050aeb  mov     [rsp+50h+lpData], rax; lpData
0x180050af0  xor     r8d, r8d; Reserved
0x180050af3  mov     rdx, rsi; lpValueName
0x180050af6  mov     rcx, rbx; hKey
0x180050af9  call    cs:__imp_RegSetValueExW
0x180050b00  nop     dword ptr [rax+rax+00h]
0x180050b05  test    eax, eax
0x180050b07  jle     short loc_180050B13
0x180050b09  movzx   eax, ax
0x180050b0c  or      eax, 80070000h
0x180050b11  test    eax, eax
0x180050b13  jns     short loc_180050B3F
0x180050b15  test    dil, dil
0x180050b18  jz      short loc_180050AC0
0x180050b1a  mov     rdx, rsi; lpValueName
0x180050b1d  mov     rcx, rbx; hKey
0x180050b20  call    cs:__imp_RegDeleteValueW
0x180050b27  nop     dword ptr [rax+rax+00h]
0x180050b2c  mov     r14b, 1
0x180050b2f  jmp     short loc_180050AC0
0x180050b31  xor     al, al
0x180050b33  jmp     short loc_180050AC3
0x180050b35  mov     ecx, edx
0x180050b37  mov     [rbp+arg_8], edx
0x180050b3a  jmp     loc_180050AAD
0x180050b3f  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180050b43  mov     r14b, 1
0x180050b46  call    cs:__imp_GetSystemTimeAsFileTime
0x180050b4d  nop     dword ptr [rax+rax+00h]
0x180050b52  lea     rax, [rbp+SystemTimeAsFileTime]
0x180050b56  mov     [rsp+50h+cbData], 8; cbData
0x180050b5e  mov     r9d, 0Bh; dwType
0x180050b64  mov     [rsp+50h+lpData], rax; lpData
0x180050b69  xor     r8d, r8d; Reserved
0x180050b6c  lea     rdx, aUpdatetimelast; "UpdateTimeLast"
0x180050b73  mov     rcx, rbx; hKey
0x180050b76  call    cs:__imp_RegSetValueExW
0x180050b7d  nop     dword ptr [rax+rax+00h]
0x180050b82  test    eax, eax
0x180050b84  jns     loc_180050AC0
0x180050b8a  lea     rdx, aUpdatetimelast; "UpdateTimeLast"
0x180050b91  mov     rcx, rbx; hKey
0x180050b94  call    cs:__imp_RegDeleteValueW
0x180050b9b  nop     dword ptr [rax+rax+00h]
0x180050ba0  jmp     loc_180050AC0
```
