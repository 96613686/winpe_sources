# RegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)

- ea: `0x18000a18c`
- end: `0x18000a20d`
- name: `?RegSetDWORD@@YAKPEAUHKEY__@@PEBG1K@Z`
- size: `129`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180004390`
- `0x180004900`
- `0x18000b760`
- `0x180011c20`

## callees

- `0x18000a18c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a1c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a1c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a1fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a1fa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a1ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a1ed`

## pseudocode

```c
__int64 __fastcall RegSetDWORD(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, int a4)
{
  unsigned int v5; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+58h] [rbp+20h] BYREF

  Data = a4;
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20006u, &hKey);
  if ( !v5 )
  {
    v5 = RegSetValueExW(hKey, a3, 0, 4u, (const BYTE *)&Data, 4u);
    RegCloseKey(hKey);
  }
  return v5;
}

```

## disassembly

```asm
0x18000a18c  mov     r11, rsp
0x18000a18f  mov     [r11+10h], rbx
0x18000a193  mov     [r11+20h], r9d
0x18000a197  mov     [r11+8], rcx
0x18000a19b  push    rdi
0x18000a19c  sub     rsp, 30h
0x18000a1a0  mov     rdi, r8
0x18000a1a3  mov     qword ptr [r11+8], 0
0x18000a1ab  lea     rax, [r11+8]
0x18000a1af  xor     r8d, r8d; ulOptions
0x18000a1b2  mov     r9d, 20006h; samDesired
0x18000a1b8  mov     [r11-18h], rax
0x18000a1bc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a1c3  call    cs:__imp_RegOpenKeyExW
0x18000a1c9  mov     ebx, eax
0x18000a1cb  test    eax, eax
0x18000a1cd  jnz     short loc_18000A200
0x18000a1cf  mov     rcx, [rsp+38h+hKey]; hKey
0x18000a1d4  lea     r9d, [rax+4]; dwType
0x18000a1d8  lea     rax, [rsp+38h+Data]
0x18000a1dd  mov     [rsp+38h+cbData], r9d; cbData
0x18000a1e2  xor     r8d, r8d; Reserved
0x18000a1e5  mov     [rsp+38h+lpData], rax; lpData
0x18000a1ea  mov     rdx, rdi; lpValueName
0x18000a1ed  call    cs:__imp_RegSetValueExW
0x18000a1f3  mov     rcx, [rsp+38h+hKey]; hKey
0x18000a1f8  mov     ebx, eax
0x18000a1fa  call    cs:__imp_RegCloseKey
0x18000a200  mov     eax, ebx
0x18000a202  mov     rbx, [rsp+38h+arg_8]
0x18000a207  add     rsp, 30h
0x18000a20b  pop     rdi
0x18000a20c  retn
```
