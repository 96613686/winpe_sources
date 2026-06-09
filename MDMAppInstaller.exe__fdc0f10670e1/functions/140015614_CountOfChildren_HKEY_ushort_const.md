# CountOfChildren(HKEY__ *,ushort const *)

- ea: `0x140015614`
- end: `0x1400156d7`
- name: `?CountOfChildren@@YAHPEAUHKEY__@@PEBG@Z`
- size: `195`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140015a38`

## callees

- `0x14000740c`
- `0x140015614`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140015647`
- `ADVAPI32!RegOpenKeyExW` at `0x140015647`
- `ADVAPI32!RegCloseKey` at `0x1400156b8`
- `ADVAPI32!RegCloseKey` at `0x1400156b8`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1400156aa`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1400156aa`

## string_xrefs

- `0x1400156c2`: `Failed to RegOpenKeyEx (%1!x!)`

## pseudocode

```c
__int64 __fastcall CountOfChildren(HKEY a1, const unsigned __int16 *a2)
{
  unsigned int v2; // eax
  DWORD cSubKeys; // [rsp+70h] [rbp+8h] BYREF
  int v5; // [rsp+74h] [rbp+Ch]
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF

  v5 = HIDWORD(a1);
  cSubKeys = 0;
  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, &hKey);
  if ( v2 )
  {
    LogError(L"Failed to RegOpenKeyEx (%1!x!)", v2);
  }
  else
  {
    RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    RegCloseKey(hKey);
  }
  return cSubKeys;
}

```

## disassembly

```asm
0x140015614  mov     rax, rsp
0x140015617  mov     [rax+8], rcx
0x14001561b  sub     rsp, 68h
0x14001561f  mov     dword ptr [rax+8], 0
0x140015626  mov     r9d, 20019h; samDesired
0x14001562c  mov     qword ptr [rax+18h], 0
0x140015634  lea     rax, [rax+18h]
0x140015638  xor     r8d, r8d; ulOptions
0x14001563b  mov     [rsp+68h+phkResult], rax; phkResult
0x140015640  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140015647  call    cs:__imp_RegOpenKeyExW
0x14001564d  test    eax, eax
0x14001564f  jnz     short loc_1400156C0
0x140015651  mov     rcx, [rsp+68h+hKey]; hKey
0x140015659  lea     rax, [rsp+68h+cSubKeys]
0x14001565e  mov     [rsp+68h+lpftLastWriteTime], 0; lpftLastWriteTime
0x140015667  xor     r9d, r9d; lpReserved
0x14001566a  mov     [rsp+68h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x140015673  xor     r8d, r8d; lpcchClass
0x140015676  mov     [rsp+68h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x14001567f  xor     edx, edx; lpClass
0x140015681  mov     [rsp+68h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x14001568a  mov     [rsp+68h+lpcValues], 0; lpcValues
0x140015693  mov     [rsp+68h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x14001569c  mov     [rsp+68h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x1400156a5  mov     [rsp+68h+phkResult], rax; lpcSubKeys
0x1400156aa  call    cs:__imp_RegQueryInfoKeyW
0x1400156b0  mov     rcx, [rsp+68h+hKey]; hKey
0x1400156b8  call    cs:__imp_RegCloseKey
0x1400156be  jmp     short loc_1400156CE
0x1400156c0  mov     edx, eax
0x1400156c2  lea     rcx, aFailedToRegope; "Failed to RegOpenKeyEx (%1!x!)"
0x1400156c9  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x1400156ce  mov     eax, [rsp+68h+cSubKeys]
0x1400156d2  add     rsp, 68h
0x1400156d6  retn
```
