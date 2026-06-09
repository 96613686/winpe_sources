# Common::RegistryKey::EnumKey(ulong,ulong *,ushort *,_FILETIME *)

- ea: `0x18000faac`
- end: `0x18000faf6`
- name: `?EnumKey@RegistryKey@Common@@QEAAJKPEAKPEAGPEAU_FILETIME@@@Z`
- size: `74`
- prototype: `int(Common::RegistryKey *__hidden this, unsigned int, unsigned int *, unsigned __int16 *, struct _FILETIME *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c244`
- `0x18000c2e8`

## callees

- `0x18000faac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000fadf`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000fadf`

## pseudocode

```c
LSTATUS __fastcall Common::RegistryKey::EnumKey(HKEY *this, DWORD a2, unsigned int *a3, unsigned __int16 *a4)
{
  LSTATUS result; // eax

  result = RegEnumKeyExW(*this, a2, a4, a3, 0, 0, 0, 0);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000faac  mov     r11, rsp
0x18000faaf  sub     rsp, 48h
0x18000fab3  mov     rcx, [rcx]; hKey
0x18000fab6  mov     rax, r9
0x18000fab9  mov     qword ptr [r11-10h], 0
0x18000fac1  mov     r9, r8; lpcchName
0x18000fac4  mov     qword ptr [r11-18h], 0
0x18000facc  mov     r8, rax; lpName
0x18000facf  mov     qword ptr [r11-20h], 0
0x18000fad7  mov     qword ptr [r11-28h], 0
0x18000fadf  call    cs:__imp_RegEnumKeyExW
0x18000fae5  test    eax, eax
0x18000fae7  jle     short loc_18000FAF1
0x18000fae9  movzx   eax, ax
0x18000faec  or      eax, 80070000h
0x18000faf1  add     rsp, 48h
0x18000faf5  retn
```
