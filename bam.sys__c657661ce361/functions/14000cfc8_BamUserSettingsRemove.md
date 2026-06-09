# BamUserSettingsRemove

- ea: `0x14000cfc8`
- end: `0x14000d004`
- name: `BamUserSettingsRemove`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x14000bea0`

## callees

- `0x14000cfc8`
- `0x140013624`

## import_xrefs

- `ntoskrnl!ZwDeleteValueKey` at `0x14000cfe2`
- `ntoskrnl!ZwDeleteValueKey` at `0x14000cfe2`

## pseudocode

```c
__int64 __fastcall BamUserSettingsRemove(void *a1, struct _UNICODE_STRING *a2)
{
  if ( !a1 || !a2 || !a2->Length )
    return 3221225485LL;
  ZwDeleteValueKey(a1, a2);
  return BampUserSettingsUpdateSequenceNumber(a1);
}

```

## disassembly

```asm
0x14000cfc8  push    rbx
0x14000cfca  sub     rsp, 20h
0x14000cfce  xor     eax, eax
0x14000cfd0  mov     rbx, rcx
0x14000cfd3  test    rcx, rcx
0x14000cfd6  jz      short loc_14000CFF8
0x14000cfd8  test    rdx, rdx
0x14000cfdb  jz      short loc_14000CFF8
0x14000cfdd  cmp     [rdx], ax
0x14000cfe0  jz      short loc_14000CFF8
0x14000cfe2  call    cs:__imp_ZwDeleteValueKey
0x14000cfe9  nop     dword ptr [rax+rax+00h]
0x14000cfee  mov     rcx, rbx
0x14000cff1  call    BampUserSettingsUpdateSequenceNumber
0x14000cff6  jmp     short loc_14000CFFD
0x14000cff8  mov     eax, 0C000000Dh
0x14000cffd  add     rsp, 20h
0x14000d001  pop     rbx
0x14000d002  retn
```
