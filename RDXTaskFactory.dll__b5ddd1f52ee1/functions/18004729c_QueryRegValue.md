# QueryRegValue

- ea: `0x18004729c`
- end: `0x18004733e`
- name: `QueryRegValue`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18002d550`

## callees

- `0x18004729c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047318`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047318`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800472d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800472d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004732f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004732f`

## pseudocode

```c
_BOOL8 __fastcall QueryRegValue(__int64 a1, __int64 a2, __int64 a3)
{
  BOOL v3; // ebx
  __int64 Data; // [rsp+50h] [rbp+8h] BYREF
  __int64 cbData; // [rsp+58h] [rbp+10h] BYREF
  __int64 Type; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  Type = a3;
  cbData = a2;
  Data = a1;
  v3 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", 0, 1u, &hKey) )
  {
    LODWORD(Data) = 0;
    LODWORD(cbData) = 4;
    LODWORD(Type) = 0;
    if ( !RegQueryValueExW(hKey, L"Upgrade", 0, (LPDWORD)&Type, (LPBYTE)&Data, (LPDWORD)&cbData) )
      v3 = Type == 4;
    RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x18004729c  mov     r11, rsp
0x18004729f  mov     [r11+18h], r8
0x1800472a3  mov     [r11+10h], rdx
0x1800472a7  mov     [r11+8], rcx
0x1800472ab  push    rbx
0x1800472ac  push    rsi
0x1800472ad  sub     rsp, 38h
0x1800472b1  xor     ebx, ebx
0x1800472b3  lea     rax, [r11+20h]
0x1800472b7  xor     r8d, r8d; ulOptions
0x1800472ba  mov     [r11+20h], rbx
0x1800472be  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x1800472c5  mov     [r11-28h], rax
0x1800472c9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800472d0  lea     esi, [rbx+1]
0x1800472d3  mov     r9d, esi; samDesired
0x1800472d6  call    cs:__imp_RegOpenKeyExW
0x1800472dc  test    eax, eax
0x1800472de  jnz     short loc_180047335
0x1800472e0  mov     rcx, [rsp+48h+hKey]; hKey
0x1800472e5  lea     rax, [rsp+48h+cbData]
0x1800472ea  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800472ef  lea     r9, [rsp+48h+Type]; lpType
0x1800472f4  lea     rax, [rsp+48h+Data]
0x1800472f9  mov     dword ptr [rsp+48h+Data], ebx
0x1800472fd  xor     r8d, r8d; lpReserved
0x180047300  mov     [rsp+48h+lpData], rax; lpData
0x180047305  lea     rdx, aUpgrade; "Upgrade"
0x18004730c  mov     dword ptr [rsp+48h+cbData], 4
0x180047314  mov     dword ptr [rsp+48h+Type], ebx
0x180047318  call    cs:__imp_RegQueryValueExW
0x18004731e  test    eax, eax
0x180047320  jnz     short loc_18004732A
0x180047322  cmp     dword ptr [rsp+48h+Type], 4
0x180047327  cmovz   ebx, esi
0x18004732a  mov     rcx, [rsp+48h+hKey]; hKey
0x18004732f  call    cs:__imp_RegCloseKey
0x180047335  mov     eax, ebx
0x180047337  add     rsp, 38h
0x18004733b  pop     rsi
0x18004733c  pop     rbx
0x18004733d  retn
```
