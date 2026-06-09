# win_musl::GetDebugOutputFlags(void)

- ea: `0x180092138`
- end: `0x1800921f5`
- name: `?GetDebugOutputFlags@win_musl@@YAKXZ`
- size: `189`
- prototype: `unsigned int __fastcall(win_musl *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015af4`

## callees

- `0x180092138`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800921ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800921ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180092195`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180092195`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800921c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800921c3`

## string_xrefs

- `0x180092179`: `Software\Microsoft\Windows\CurrentVersion\DocumentServices`

## pseudocode

```c
__int64 __fastcall win_musl::GetDebugOutputFlags(win_musl *this)
{
  DWORD Type; // [rsp+40h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+18h] BYREF
  int Data; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  if ( !_interlockedbittestandset(&dword_1801C5038, 0x1Eu) )
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
        dword_1801C5038 = Data | 0x40000000;
      RegCloseKey(hKey);
    }
  }
  return (unsigned int)dword_1801C5038;
}

```

## disassembly

```asm
0x180092138  push    rbp
0x18009213a  mov     rbp, rsp
0x18009213d  sub     rsp, 30h
0x180092141  lock bts cs:dword_1801C5038, 1Eh
0x18009214a  jnb     short loc_180092158
0x18009214c  mov     eax, cs:dword_1801C5038
0x180092152  add     rsp, 30h
0x180092156  pop     rbp
0x180092157  retn
0x180092158  lea     rax, [rbp+hKey]
0x18009215c  mov     [rbp+hKey], 0
0x180092164  mov     r9d, 1; samDesired
0x18009216a  mov     [rsp+30h+phkResult], rax; phkResult
0x18009216f  xor     r8d, r8d; ulOptions
0x180092172  mov     [rbp+Data], 0
0x180092179  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180092180  mov     [rbp+cbData], 4
0x180092187  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18009218e  mov     [rbp+Type], 0
0x180092195  call    cs:__imp_RegOpenKeyExW
0x18009219b  test    eax, eax
0x18009219d  jnz     short loc_18009214C
0x18009219f  mov     rcx, [rbp+hKey]; hKey
0x1800921a3  lea     rax, [rbp+cbData]
0x1800921a7  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800921ac  lea     r9, [rbp+Type]; lpType
0x1800921b0  lea     rax, [rbp+Data]
0x1800921b4  xor     r8d, r8d; lpReserved
0x1800921b7  lea     rdx, ValueName; "DebugOutputFlags"
0x1800921be  mov     [rsp+30h+phkResult], rax; lpData
0x1800921c3  call    cs:__imp_RegQueryValueExW
0x1800921c9  test    eax, eax
0x1800921cb  jnz     short loc_1800921E6
0x1800921cd  cmp     [rbp+Type], 4
0x1800921d1  jnz     short loc_1800921E6
0x1800921d3  cmp     [rbp+cbData], 4
0x1800921d7  jnz     short loc_1800921E6
0x1800921d9  mov     eax, [rbp+Data]
0x1800921dc  bts     eax, 1Eh
0x1800921e0  mov     cs:dword_1801C5038, eax
0x1800921e6  mov     rcx, [rbp+hKey]; hKey
0x1800921ea  call    cs:__imp_RegCloseKey
0x1800921f0  jmp     loc_18009214C
```
