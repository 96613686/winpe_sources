# win_musl::GetDebugOutputFlags(void)

- ea: `0x1800b1b68`
- end: `0x1800b1c24`
- name: `?GetDebugOutputFlags@win_musl@@YAKXZ`
- size: `188`
- prototype: `unsigned int __fastcall(win_musl *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003c7f8`

## callees

- `0x1800b1b68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b1beb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b1beb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b1bbd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b1bbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b1c12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b1c12`

## string_xrefs

- `0x1800b1ba1`: `Software\Microsoft\Windows\CurrentVersion\DocumentServices`

## pseudocode

```c
__int64 __fastcall win_musl::GetDebugOutputFlags(win_musl *this)
{
  DWORD Type; // [rsp+40h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+18h] BYREF
  int Data; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  if ( !_interlockedbittestandset(&dword_180229254, 0x1Eu) )
  {
    hKey = 0;
    Data = 0;
    cbData = 4;
    Type = 0;
    if ( !RegOpenKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\DocumentServices",
            0,
            1u,
            &hKey) )
    {
      if ( !RegQueryValueExW(hKey, L"DebugOutputFlags", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && cbData == 4 )
        dword_180229254 = Data | 0x40000000;
      RegCloseKey(hKey);
    }
  }
  return (unsigned int)dword_180229254;
}

```

## disassembly

```asm
0x1800b1b68  push    rbp
0x1800b1b6a  mov     rbp, rsp
0x1800b1b6d  sub     rsp, 30h
0x1800b1b71  lock bts cs:dword_180229254, 1Eh
0x1800b1b7a  jb      loc_1800B1C18
0x1800b1b80  lea     rax, [rbp+hKey]
0x1800b1b84  mov     [rbp+hKey], 0
0x1800b1b8c  mov     r9d, 1; samDesired
0x1800b1b92  mov     [rsp+30h+phkResult], rax; phkResult
0x1800b1b97  xor     r8d, r8d; ulOptions
0x1800b1b9a  mov     [rbp+Data], 0
0x1800b1ba1  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800b1ba8  mov     [rbp+cbData], 4
0x1800b1baf  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800b1bb6  mov     [rbp+Type], 0
0x1800b1bbd  call    cs:__imp_RegOpenKeyExW
0x1800b1bc3  test    eax, eax
0x1800b1bc5  jnz     short loc_1800B1C18
0x1800b1bc7  mov     rcx, [rbp+hKey]; hKey
0x1800b1bcb  lea     rax, [rbp+cbData]
0x1800b1bcf  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800b1bd4  lea     r9, [rbp+Type]; lpType
0x1800b1bd8  lea     rax, [rbp+Data]
0x1800b1bdc  xor     r8d, r8d; lpReserved
0x1800b1bdf  lea     rdx, ValueName; "DebugOutputFlags"
0x1800b1be6  mov     [rsp+30h+phkResult], rax; lpData
0x1800b1beb  call    cs:__imp_RegQueryValueExW
0x1800b1bf1  test    eax, eax
0x1800b1bf3  jnz     short loc_1800B1C0E
0x1800b1bf5  cmp     [rbp+Type], 4
0x1800b1bf9  jnz     short loc_1800B1C0E
0x1800b1bfb  cmp     [rbp+cbData], 4
0x1800b1bff  jnz     short loc_1800B1C0E
0x1800b1c01  mov     eax, [rbp+Data]
0x1800b1c04  bts     eax, 1Eh
0x1800b1c08  mov     cs:dword_180229254, eax
0x1800b1c0e  mov     rcx, [rbp+hKey]; hKey
0x1800b1c12  call    cs:__imp_RegCloseKey
0x1800b1c18  mov     eax, cs:dword_180229254
0x1800b1c1e  add     rsp, 30h
0x1800b1c22  pop     rbp
0x1800b1c23  retn
```
