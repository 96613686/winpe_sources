# SystemSettings::BatterySaverOneCoreDataModel::CPowerMode::_SetUserConfiguredPowerMode(_GUID const *)

- ea: `0x18003e8b4`
- end: `0x18003e8ef`
- name: `?_SetUserConfiguredPowerMode@CPowerMode@BatterySaverOneCoreDataModel@SystemSettings@@AEAAJPEBU_GUID@@@Z`
- size: `59`
- prototype: `__int64 __fastcall(SystemSettings::BatterySaverOneCoreDataModel::CPowerMode *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18003d200`

## callees

- `0x18003e8b4`

## import_xrefs

- `POWRPROF!PowerSetUserConfiguredDCPowerMode` at `0x18003e8d8`
- `POWRPROF!PowerSetUserConfiguredDCPowerMode` at `0x18003e8d8`
- `POWRPROF!PowerSetUserConfiguredACPowerMode` at `0x18003e8cd`
- `POWRPROF!PowerSetUserConfiguredACPowerMode` at `0x18003e8cd`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatterySaverOneCoreDataModel::CPowerMode::_SetUserConfiguredPowerMode(
        SystemSettings::BatterySaverOneCoreDataModel::CPowerMode *this,
        const struct _GUID *a2)
{
  _BYTE *v2; // rcx
  __int64 result; // rax

  v2 = *(_BYTE **)(*((_QWORD *)this + 11) + 24LL);
  if ( v2 && *v2 )
    result = PowerSetUserConfiguredACPowerMode(a2);
  else
    result = PowerSetUserConfiguredDCPowerMode(a2);
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18003e8b4  sub     rsp, 28h
0x18003e8b8  mov     rax, [rcx+58h]
0x18003e8bc  mov     rcx, [rax+18h]
0x18003e8c0  test    rcx, rcx
0x18003e8c3  jz      short loc_18003E8D5
0x18003e8c5  cmp     byte ptr [rcx], 0
0x18003e8c8  jz      short loc_18003E8D5
0x18003e8ca  mov     rcx, rdx
0x18003e8cd  call    cs:__imp_PowerSetUserConfiguredACPowerMode
0x18003e8d3  jmp     short loc_18003E8DE
0x18003e8d5  mov     rcx, rdx
0x18003e8d8  call    cs:__imp_PowerSetUserConfiguredDCPowerMode
0x18003e8de  test    eax, eax
0x18003e8e0  jle     short loc_18003E8EA
0x18003e8e2  movzx   eax, ax
0x18003e8e5  or      eax, 80070000h
0x18003e8ea  add     rsp, 28h
0x18003e8ee  retn
```
