# CW32System::GetSurrogateFontName(ushort *,ulong)

- ea: `0x18004ab60`
- end: `0x18004ac02`
- name: `?GetSurrogateFontName@CW32System@@CA_NPEAGK@Z`
- size: `162`
- prototype: `bool __fastcall(LPBYTE lpData, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004a158`

## callees

- `0x18004ab60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ab9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ab9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004abe4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004abe4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004abd5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004abd5`

## pseudocode

```c
bool __fastcall CW32System::GetSurrogateFontName(LPBYTE lpData, DWORD a2)
{
  bool v3; // bl
  DWORD Type; // [rsp+48h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  Type = a2;
  hKey = 0;
  v3 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\LanguagePack\\SurrogateFallback",
          0,
          1u,
          &hKey) )
  {
    Type = 0;
    cbData = 64;
    if ( !RegQueryValueExW(hKey, L"Plane2", 0, &Type, lpData, &cbData) )
      v3 = Type == 1;
    RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x18004ab60  mov     rax, rsp
0x18004ab63  mov     [rax+8], rbx
0x18004ab67  mov     [rax+10h], edx
0x18004ab6a  push    rdi
0x18004ab6b  sub     rsp, 30h
0x18004ab6f  mov     qword ptr [rax+20h], 0
0x18004ab77  lea     rax, [rax+20h]
0x18004ab7b  mov     rdi, rcx
0x18004ab7e  mov     [rsp+38h+phkResult], rax; phkResult
0x18004ab83  mov     r9d, 1; samDesired
0x18004ab89  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18004ab90  xor     r8d, r8d; ulOptions
0x18004ab93  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004ab9a  xor     bl, bl
0x18004ab9c  call    cs:__imp_RegOpenKeyExW
0x18004aba2  test    eax, eax
0x18004aba4  jnz     short loc_18004ABEA
0x18004aba6  mov     rcx, [rsp+38h+hKey]; hKey
0x18004abab  lea     r9, [rsp+38h+Type]; lpType
0x18004abb0  mov     [rsp+38h+Type], eax
0x18004abb4  lea     rdx, ValueName; "Plane2"
0x18004abbb  lea     rax, [rsp+38h+cbData]
0x18004abc0  mov     [rsp+38h+cbData], 40h ; '@'
0x18004abc8  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18004abcd  xor     r8d, r8d; lpReserved
0x18004abd0  mov     [rsp+38h+phkResult], rdi; lpData
0x18004abd5  call    cs:__imp_RegQueryValueExW
0x18004abdb  test    eax, eax
0x18004abdd  jz      short loc_18004ABF7
0x18004abdf  mov     rcx, [rsp+38h+hKey]; hKey
0x18004abe4  call    cs:__imp_RegCloseKey
0x18004abea  mov     al, bl
0x18004abec  mov     rbx, [rsp+38h+arg_0]
0x18004abf1  add     rsp, 30h
0x18004abf5  pop     rdi
0x18004abf6  retn
0x18004abf7  cmp     [rsp+38h+Type], 1
0x18004abfc  jnz     short loc_18004ABDF
0x18004abfe  mov     bl, 1
0x18004ac00  jmp     short loc_18004ABDF
```
