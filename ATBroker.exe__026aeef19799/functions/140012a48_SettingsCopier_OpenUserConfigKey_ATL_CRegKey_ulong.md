# SettingsCopier::OpenUserConfigKey(ATL::CRegKey &,ulong)

- ea: `0x140012a48`
- end: `0x140012ae1`
- name: `?OpenUserConfigKey@SettingsCopier@@CAJAEAVCRegKey@ATL@@K@Z`
- size: `153`
- prototype: `LSTATUS __fastcall(struct ATL::CRegKey *this, REGSAM)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012640`
- `0x14001271c`

## callees

- `0x14000be54`
- `0x140012a48`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140012a7d`
- `ADVAPI32!RegOpenKeyExW` at `0x140012a7d`
- `ADVAPI32!RegCloseKey` at `0x140012a8f`
- `ADVAPI32!RegCloseKey` at `0x140012a8f`

## string_xrefs

- `0x140012a6c`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig`
- `0x140012ab2`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
LSTATUS __fastcall SettingsCopier::OpenUserConfigKey(struct ATL::CRegKey *this, REGSAM a2)
{
  LSTATUS result; // eax
  unsigned __int16 *v5; // r9
  struct _SECURITY_ATTRIBUTES *v6; // [rsp+30h] [rbp-18h]
  HKEY v7; // [rsp+60h] [rbp+18h] BYREF

  v7 = 0;
  result = RegOpenKeyExW(HKEY_CURRENT_USER, SettingsCopier::_ATConfigKeyString, 0, a2, &v7);
  if ( result )
    return ATL::CRegKey::Create(
             this,
             HKEY_CURRENT_USER,
             SettingsCopier::_ATConfigKeyString,
             v5,
             1u,
             a2,
             v6,
             (unsigned int *)&v7) != 0
         ? 0x80004005
         : 0;
  if ( *(_QWORD *)this )
    result = RegCloseKey(*(HKEY *)this);
  *(_QWORD *)this = v7;
  if ( result )
    return ATL::CRegKey::Create(
             this,
             HKEY_CURRENT_USER,
             SettingsCopier::_ATConfigKeyString,
             v5,
             1u,
             a2,
             v6,
             (unsigned int *)&v7) != 0
         ? 0x80004005
         : 0;
  return result;
}

```

## disassembly

```asm
0x140012a48  mov     r11, rsp
0x140012a4b  mov     [r11+8], rbx
0x140012a4f  push    rdi
0x140012a50  sub     rsp, 40h
0x140012a54  mov     edi, edx
0x140012a56  mov     qword ptr [r11+18h], 0
0x140012a5e  mov     rbx, rcx
0x140012a61  lea     rax, [r11+18h]
0x140012a65  mov     r9d, edx; samDesired
0x140012a68  mov     [r11-28h], rax
0x140012a6c  lea     rdx, ?_ATConfigKeyString@SettingsCopier@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140012a73  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140012a7a  xor     r8d, r8d; ulOptions
0x140012a7d  call    cs:__imp_RegOpenKeyExW
0x140012a83  test    eax, eax
0x140012a85  jnz     short loc_140012AA1
0x140012a87  mov     rcx, [rbx]; hKey
0x140012a8a  test    rcx, rcx
0x140012a8d  jz      short loc_140012A95
0x140012a8f  call    cs:__imp_RegCloseKey
0x140012a95  mov     rcx, [rsp+48h+arg_10]
0x140012a9a  mov     [rbx], rcx
0x140012a9d  test    eax, eax
0x140012a9f  jz      short loc_140012AD6
0x140012aa1  lea     rax, [rsp+48h+arg_10]
0x140012aa6  mov     rdx, 0FFFFFFFF80000001h; HKEY
0x140012aad  mov     [rsp+48h+var_10], rax; unsigned int *
0x140012ab2  lea     r8, ?_ATConfigKeyString@SettingsCopier@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140012ab9  mov     [rsp+48h+var_20], edi; unsigned int
0x140012abd  mov     rcx, rbx; this
0x140012ac0  mov     [rsp+48h+var_28], 1; unsigned int
0x140012ac8  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x140012acd  neg     eax
0x140012acf  sbb     eax, eax
0x140012ad1  and     eax, 80004005h
0x140012ad6  mov     rbx, [rsp+48h+arg_0]
0x140012adb  add     rsp, 40h
0x140012adf  pop     rdi
0x140012ae0  retn
```
