# WmiSecurity::~WmiSecurity(void)

- ea: `0x140006894`
- end: `0x1400068b8`
- name: `??1WmiSecurity@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(WmiSecurity *this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140006a18`

## callees

- `0x140006894`
- `0x140006b2c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400068a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400068a5`

## pseudocode

```c
void __fastcall WmiSecurity::~WmiSecurity(WmiSecurity *this, void *a2)
{
  void *v3; // rcx

  v3 = *(void **)this;
  if ( v3 )
    LocalFree(v3);
  WmiSecurity::DestructAbsoluteSD(this, a2);
}

```

## disassembly

```asm
0x140006894  push    rbx
0x140006896  sub     rsp, 20h
0x14000689a  mov     rbx, rcx
0x14000689d  mov     rcx, [rcx]; hMem
0x1400068a0  test    rcx, rcx
0x1400068a3  jz      short loc_1400068AB
0x1400068a5  call    cs:__imp_LocalFree
0x1400068ab  mov     rcx, rbx; this
0x1400068ae  add     rsp, 20h
0x1400068b2  pop     rbx
0x1400068b3  jmp     ?DestructAbsoluteSD@WmiSecurity@@AEAAXPEAX@Z; WmiSecurity::DestructAbsoluteSD(void *)
```
