# SetRegKeyValue32W(HKEY__ *,ushort const *,ushort const *,ulong,uchar const *,ulong)

- ea: `0x180085e68`
- end: `0x180085f0a`
- name: `?SetRegKeyValue32W@@YAJPEAUHKEY__@@PEBG1KPEBEK@Z`
- size: `162`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, BYTE *lpData, DWORD cbData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180020120`

## callees

- `0x180085e68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180085eef`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180085eef`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180085eba`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180085eba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085efc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085efc`

## pseudocode

```c
LSTATUS __fastcall SetRegKeyValue32W(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        BYTE *lpData,
        DWORD cbData)
{
  LSTATUS result; // eax
  LSTATUS v7; // ebx
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF
  DWORD v9; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  v9 = 0;
  result = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Control\\MSDTC\\ASR\\RestoreSession",
             0,
             (LPWSTR)&cchOriginalDestLength,
             0,
             0x20106u,
             0,
             &hKey,
             &v9);
  if ( !result )
  {
    v7 = RegSetValueExW(hKey, L"LastInstance", 0, 1u, lpData, cbData);
    RegCloseKey(hKey);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180085e68  mov     r11, rsp
0x180085e6b  mov     [r11+20h], r9d
0x180085e6f  mov     [r11+18h], r8
0x180085e73  push    rbx
0x180085e74  sub     rsp, 50h
0x180085e78  xor     ebx, ebx
0x180085e7a  lea     rax, [r11+20h]
0x180085e7e  mov     [r11-18h], rax
0x180085e82  lea     r9, cchOriginalDestLength; lpClass
0x180085e89  lea     rax, [r11+18h]
0x180085e8d  mov     [r11+18h], rbx
0x180085e91  mov     [r11-20h], rax
0x180085e95  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\MSD"...
0x180085e9c  mov     [r11-28h], rbx
0x180085ea0  xor     r8d, r8d; Reserved
0x180085ea3  mov     [rsp+58h+samDesired], 20106h; samDesired
0x180085eab  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180085eb2  mov     [rsp+58h+dwOptions], ebx; dwOptions
0x180085eb6  mov     [rsp+58h+arg_18], ebx
0x180085eba  call    cs:__imp_RegCreateKeyExW
0x180085ec0  test    eax, eax
0x180085ec2  jnz     short loc_180085F04
0x180085ec4  mov     eax, [rsp+58h+cbData]
0x180085ecb  lea     r9d, [rbx+1]; dwType
0x180085ecf  mov     rcx, [rsp+58h+hKey]; hKey
0x180085ed4  lea     rdx, aLastinstance; "LastInstance"
0x180085edb  mov     [rsp+58h+samDesired], eax; cbData
0x180085edf  xor     r8d, r8d; Reserved
0x180085ee2  mov     rax, [rsp+58h+lpData]
0x180085eea  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180085eef  call    cs:__imp_RegSetValueExW
0x180085ef5  mov     rcx, [rsp+58h+hKey]; hKey
0x180085efa  mov     ebx, eax
0x180085efc  call    cs:__imp_RegCloseKey
0x180085f02  mov     eax, ebx
0x180085f04  add     rsp, 50h
0x180085f08  pop     rbx
0x180085f09  retn
```
