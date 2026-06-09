# BampUserSettingsUpdateSequenceNumber

- ea: `0x140013624`
- end: `0x140013662`
- name: `BampUserSettingsUpdateSequenceNumber`
- size: `62`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, installer_update`

## callers

- `0x14000cfc8`
- `0x140015608`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x140013650`
- `ntoskrnl!ZwSetValueKey` at `0x140013650`

## pseudocode

```c
NTSTATUS __fastcall BampUserSettingsUpdateSequenceNumber(void *a1)
{
  _InterlockedIncrement((_DWORD *)&BampUserSettingsContext + 2);
  return ZwSetValueKey(a1, &BampUserSettingsSequenceValueName, 0, 4u, &BampUserSettingsContext + 1, 4u);
}

```

## disassembly

```asm
0x140013624  sub     rsp, 38h
0x140013628  lock inc dword ptr cs:BampUserSettingsContext+8
0x14001362f  mov     r9d, 4; Type
0x140013635  lea     rax, BampUserSettingsContext+8
0x14001363c  mov     [rsp+38h+DataSize], r9d; DataSize
0x140013641  lea     rdx, BampUserSettingsSequenceValueName; ValueName
0x140013648  xor     r8d, r8d; TitleIndex
0x14001364b  mov     [rsp+38h+Data], rax; Data
0x140013650  call    cs:__imp_ZwSetValueKey
0x140013657  nop     dword ptr [rax+rax+00h]
0x14001365c  add     rsp, 38h
0x140013660  retn
```
