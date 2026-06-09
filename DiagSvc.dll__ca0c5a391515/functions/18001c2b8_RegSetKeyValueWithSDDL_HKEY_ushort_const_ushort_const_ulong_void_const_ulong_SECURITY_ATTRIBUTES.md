# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x18001c2b8`
- end: `0x18001c376`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, DWORD, BYTE *lpData, DWORD cbData)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001c104`
- `0x18001c264`

## callees

- `0x18001c2b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001c316`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001c316`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c348`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c348`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c35e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c35e`

## string_xrefs

- `0x18001c2dc`: `SYSTEM\CurrentControlSet\Services\diagsvc\Settings`

## pseudocode

```c
__int64 __fastcall _RegSetKeyValueWithSDDL(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        BYTE *lpData,
        DWORD cbData)
{
  unsigned int v8; // ebx
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  v8 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\diagsvc\\Settings",
         0,
         0,
         0,
         2u,
         0,
         &hKey,
         0);
  if ( !v8 )
  {
    v8 = RegSetValueExW(hKey, a3, 0, a4, lpData, cbData);
    if ( hKey != HKEY_LOCAL_MACHINE )
      RegCloseKey(hKey);
  }
  return v8;
}

```

## disassembly

```asm
0x18001c2b8  mov     r11, rsp
0x18001c2bb  mov     [r11+8], rbx
0x18001c2bf  mov     [r11+18h], rsi
0x18001c2c3  mov     [r11+10h], rdx
0x18001c2c7  push    rdi
0x18001c2c8  sub     rsp, 50h
0x18001c2cc  mov     qword ptr [r11-18h], 0
0x18001c2d4  lea     rax, [r11+10h]
0x18001c2d8  mov     [r11-20h], rax
0x18001c2dc  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\di"...
0x18001c2e3  mov     qword ptr [r11-28h], 0
0x18001c2eb  mov     edi, r9d
0x18001c2ee  mov     rsi, r8
0x18001c2f1  mov     [rsp+58h+samDesired], 2; samDesired
0x18001c2f9  xor     r9d, r9d; lpClass
0x18001c2fc  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18001c304  xor     r8d, r8d; Reserved
0x18001c307  mov     qword ptr [r11+10h], 0
0x18001c30f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c316  call    cs:__imp_RegCreateKeyExW
0x18001c31c  mov     ebx, eax
0x18001c31e  test    eax, eax
0x18001c320  jnz     short loc_18001C364
0x18001c322  mov     eax, [rsp+58h+cbData]
0x18001c329  mov     r9d, edi; dwType
0x18001c32c  mov     rcx, [rsp+58h+hKey]; hKey
0x18001c331  xor     r8d, r8d; Reserved
0x18001c334  mov     [rsp+58h+samDesired], eax; cbData
0x18001c338  mov     rdx, rsi; lpValueName
0x18001c33b  mov     rax, [rsp+58h+lpData]
0x18001c343  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18001c348  call    cs:__imp_RegSetValueExW
0x18001c34e  mov     rcx, [rsp+58h+hKey]; hKey
0x18001c353  mov     ebx, eax
0x18001c355  cmp     rcx, 0FFFFFFFF80000002h
0x18001c35c  jz      short loc_18001C364
0x18001c35e  call    cs:__imp_RegCloseKey
0x18001c364  mov     rsi, [rsp+58h+arg_10]
0x18001c369  mov     eax, ebx
0x18001c36b  mov     rbx, [rsp+58h+arg_0]
0x18001c370  add     rsp, 50h
0x18001c374  pop     rdi
0x18001c375  retn
```
