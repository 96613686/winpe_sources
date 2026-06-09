# wil::details::ScopeExitFn__lambda_212ad87cdae3078b78d06141a50b79a2___::operator()

- ea: `0x1800609b4`
- end: `0x180060a60`
- name: `wil::details::ScopeExitFn__lambda_212ad87cdae3078b78d06141a50b79a2___::operator()`
- size: `172`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180042d64`
- `0x1800609a8`

## callees

- `0x1800609b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060a55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060a55`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180060a41`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180060a41`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180060a15`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180060a15`

## pseudocode

```c
void __fastcall wil::details::ScopeExitFn__lambda_212ad87cdae3078b78d06141a50b79a2___::operator()(__int64 a1)
{
  int Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  if ( *(_BYTE *)(a1 + 8) )
  {
    *(_BYTE *)(a1 + 8) = 0;
    Data = 1;
    hKey = 0;
    if ( !RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\LogonSoundPlayed",
            0,
            0,
            0,
            2u,
            0,
            &hKey,
            0) )
    {
      RegSetValueExW(hKey, L"LogonUIChecked", 0, 4u, (const BYTE *)&Data, 4u);
      if ( hKey != HKEY_LOCAL_MACHINE )
        RegCloseKey(hKey);
    }
  }
}

```

## disassembly

```asm
0x1800609b4  mov     r11, rsp
0x1800609b7  sub     rsp, 58h
0x1800609bb  cmp     byte ptr [rcx+8], 0
0x1800609bf  jz      loc_180060A5B
0x1800609c5  mov     qword ptr [r11-18h], 0
0x1800609cd  lea     rax, [r11+10h]
0x1800609d1  mov     [r11-20h], rax
0x1800609d5  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800609dc  mov     qword ptr [r11-28h], 0
0x1800609e4  xor     r9d, r9d; lpClass
0x1800609e7  mov     byte ptr [rcx+8], 0
0x1800609eb  xor     r8d, r8d; Reserved
0x1800609ee  mov     [rsp+58h+samDesired], 2; samDesired
0x1800609f6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800609fd  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180060a05  mov     [rsp+58h+Data], 1
0x180060a0d  mov     qword ptr [r11+10h], 0
0x180060a15  call    cs:__imp_RegCreateKeyExW
0x180060a1b  test    eax, eax
0x180060a1d  jnz     short loc_180060A5B
0x180060a1f  mov     rcx, [rsp+58h+hKey]; hKey
0x180060a24  lea     r9d, [rax+4]; dwType
0x180060a28  lea     rax, [rsp+58h+Data]
0x180060a2d  mov     [rsp+58h+samDesired], r9d; cbData
0x180060a32  xor     r8d, r8d; Reserved
0x180060a35  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180060a3a  lea     rdx, aLogonuichecked; "LogonUIChecked"
0x180060a41  call    cs:__imp_RegSetValueExW
0x180060a47  mov     rcx, [rsp+58h+hKey]; hKey
0x180060a4c  cmp     rcx, 0FFFFFFFF80000002h
0x180060a53  jz      short loc_180060A5B
0x180060a55  call    cs:__imp_RegCloseKey
0x180060a5b  add     rsp, 58h
0x180060a5f  retn
```
