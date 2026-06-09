# WmiSecurity::`scalar deleting destructor'(uint)

- ea: `0x140006a18`
- end: `0x140006a38`
- name: `??_GWmiSecurity@@QEAAPEAXI@Z`
- size: `32`
- prototype: `WmiSecurity *__fastcall(WmiSecurity *this, void *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000661c`
- `0x140006820`
- `0x1400068c0`

## callees

- `0x140006894`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140006a29`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140006a29`

## pseudocode

```c
WmiSecurity *__fastcall WmiSecurity::`scalar deleting destructor'(WmiSecurity *this, void *a2)
{
  WmiSecurity::~WmiSecurity(this, a2);
  CWin32DefaultArena::WbemMemFree(this);
  return this;
}

```

## disassembly

```asm
0x140006a18  push    rbx
0x140006a1a  sub     rsp, 20h
0x140006a1e  mov     rbx, rcx
0x140006a21  call    ??1WmiSecurity@@QEAA@XZ; WmiSecurity::~WmiSecurity(void)
0x140006a26  mov     rcx, rbx
0x140006a29  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140006a2f  mov     rax, rbx
0x140006a32  add     rsp, 20h
0x140006a36  pop     rbx
0x140006a37  retn
```
