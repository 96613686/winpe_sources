# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x18001c900`
- end: `0x18001c9c0`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, __int64, BYTE *lpData, DWORD cbData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ba64`

## callees

- `0x18001c900`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c9a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c9a8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001c956`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001c956`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c992`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c992`

## string_xrefs

- `0x18001c919`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsAI\SettingsLastConfiguration`
- `0x18001c939`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsAI\SettingsLastConfiguration`

## pseudocode

```c
__int64 __fastcall _RegSetKeyValueWithSDDL(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        BYTE *lpData,
        DWORD cbData)
{
  HKEY v7; // rcx
  unsigned int v8; // edi
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  v7 = HKEY_LOCAL_MACHINE;
  hKey = 0;
  if ( aSoftwareMicros_1[0] )
  {
    v8 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsAI\\SettingsLastConfiguration",
           0,
           0,
           0,
           2u,
           0,
           &hKey,
           0);
    if ( v8 )
      return v8;
    v7 = hKey;
  }
  else
  {
    hKey = HKEY_LOCAL_MACHINE;
  }
  v8 = RegSetValueExW(v7, a3, 0, 1u, lpData, cbData);
  if ( hKey != HKEY_LOCAL_MACHINE )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x18001c900  mov     r11, rsp
0x18001c903  mov     [r11+8], rbp
0x18001c907  mov     [r11+18h], rsi
0x18001c90b  mov     [r11+10h], rdx
0x18001c90f  push    rdi
0x18001c910  sub     rsp, 50h
0x18001c914  xor     ebp, ebp
0x18001c916  mov     rsi, r8
0x18001c919  cmp     word ptr cs:aSoftwareMicros_1, bp; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001c920  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c927  mov     [r11+10h], rbp
0x18001c92b  jz      short loc_18001C969
0x18001c92d  mov     [r11-18h], rbp
0x18001c931  lea     rax, [r11+10h]
0x18001c935  mov     [r11-20h], rax
0x18001c939  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001c940  mov     [r11-28h], rbp
0x18001c944  xor     r9d, r9d; lpClass
0x18001c947  mov     [rsp+58h+samDesired], 2; samDesired
0x18001c94f  xor     r8d, r8d; Reserved
0x18001c952  mov     [rsp+58h+dwOptions], ebp; dwOptions
0x18001c956  call    cs:__imp_RegCreateKeyExW
0x18001c95c  mov     edi, eax
0x18001c95e  test    eax, eax
0x18001c960  jnz     short loc_18001C9AE
0x18001c962  mov     rcx, [rsp+58h+hKey]
0x18001c967  jmp     short loc_18001C96E
0x18001c969  mov     [rsp+58h+hKey], rcx
0x18001c96e  mov     eax, [rsp+58h+cbData]
0x18001c975  mov     r9d, 1; dwType
0x18001c97b  mov     [rsp+58h+samDesired], eax; cbData
0x18001c97f  xor     r8d, r8d; Reserved
0x18001c982  mov     rax, [rsp+58h+lpData]
0x18001c98a  mov     rdx, rsi; lpValueName
0x18001c98d  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18001c992  call    cs:__imp_RegSetValueExW
0x18001c998  mov     rcx, [rsp+58h+hKey]; hKey
0x18001c99d  mov     edi, eax
0x18001c99f  cmp     rcx, 0FFFFFFFF80000002h
0x18001c9a6  jz      short loc_18001C9AE
0x18001c9a8  call    cs:__imp_RegCloseKey
0x18001c9ae  mov     rbp, [rsp+58h+arg_0]
0x18001c9b3  mov     eax, edi
0x18001c9b5  mov     rsi, [rsp+58h+arg_10]
0x18001c9ba  add     rsp, 50h
0x18001c9be  pop     rdi
0x18001c9bf  retn
```
