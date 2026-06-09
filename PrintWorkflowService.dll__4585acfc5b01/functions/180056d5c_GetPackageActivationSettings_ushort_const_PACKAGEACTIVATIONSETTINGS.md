# GetPackageActivationSettings(ushort const *,PACKAGEACTIVATIONSETTINGS *)

- ea: `0x180056d5c`
- end: `0x180056e05`
- name: `?GetPackageActivationSettings@@YAJPEBGPEAW4PACKAGEACTIVATIONSETTINGS@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(LPCWSTR lpValue, enum PACKAGEACTIVATIONSETTINGS *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180055604`

## callees

- `0x180056d5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180056d85`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180056d85`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180056ddd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180056ddd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056df2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056df2`

## pseudocode

```c
__int64 __fastcall GetPackageActivationSettings(LPCWSTR lpValue, enum PACKAGEACTIVATIONSETTINGS *a2)
{
  LSTATUS v4; // eax
  bool v5; // sf
  int pvData; // [rsp+58h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp+18h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+20h] BYREF

  *(_DWORD *)a2 = 0;
  phkResult = 0;
  v4 = RegOpenCurrentUser(0x20019u, &phkResult);
  v5 = v4 < 0;
  if ( v4 > 0 )
    v5 = 1;
  if ( !v5 )
  {
    pvData = 0;
    pcbData = 4;
    if ( !RegGetValueW(
            phkResult,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced\\PackageActivate",
            lpValue,
            0x18u,
            0,
            &pvData,
            &pcbData) )
      *(_DWORD *)a2 = pvData;
    RegCloseKey(phkResult);
  }
  return 0;
}

```

## disassembly

```asm
0x180056d5c  mov     [rsp+arg_0], rbx
0x180056d61  push    rdi
0x180056d62  sub     rsp, 40h
0x180056d66  mov     rbx, rdx
0x180056d69  mov     dword ptr [rdx], 0
0x180056d6f  mov     rdi, rcx
0x180056d72  mov     [rsp+48h+phkResult], 0
0x180056d7b  lea     rdx, [rsp+48h+phkResult]; phkResult
0x180056d80  mov     ecx, 20019h; samDesired
0x180056d85  call    cs:__imp_RegOpenCurrentUser
0x180056d8b  test    eax, eax
0x180056d8d  jle     short loc_180056D99
0x180056d8f  movzx   eax, ax
0x180056d92  or      eax, 80070000h
0x180056d97  test    eax, eax
0x180056d99  js      short loc_180056DF8
0x180056d9b  mov     rcx, [rsp+48h+phkResult]; hkey
0x180056da0  lea     rax, [rsp+48h+arg_10]
0x180056da5  mov     [rsp+48h+pcbData], rax; pcbData
0x180056daa  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180056db1  lea     rax, [rsp+48h+arg_8]
0x180056db6  mov     [rsp+48h+arg_8], 0
0x180056dbe  mov     [rsp+48h+pvData], rax; pvData
0x180056dc3  mov     r9d, 18h; dwFlags
0x180056dc9  mov     r8, rdi; lpValue
0x180056dcc  mov     [rsp+48h+pdwType], 0; pdwType
0x180056dd5  mov     [rsp+48h+arg_10], 4
0x180056ddd  call    cs:__imp_RegGetValueW
0x180056de3  test    eax, eax
0x180056de5  jnz     short loc_180056DED
0x180056de7  mov     eax, [rsp+48h+arg_8]
0x180056deb  mov     [rbx], eax
0x180056ded  mov     rcx, [rsp+48h+phkResult]; hKey
0x180056df2  call    cs:__imp_RegCloseKey
0x180056df8  mov     rbx, [rsp+48h+arg_0]
0x180056dfd  xor     eax, eax
0x180056dff  add     rsp, 40h
0x180056e03  pop     rdi
0x180056e04  retn
```
