# SiCreateTierInternal(_SU_POOL_OBJECT *,_SP_TIER_INFO *)

- ea: `0x140011478`
- end: `0x1400114f0`
- name: `?SiCreateTierInternal@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_TIER_INFO@@@Z`
- size: `120`
- prototype: `int __fastcall(struct _SU_POOL_OBJECT *, struct _SP_TIER_INFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140010b5c`

## callees

- `0x140011478`
- `0x140012104`
- `0x14001232c`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x1400114df`
- `KERNEL32!DeviceIoControl` at `0x1400114df`

## pseudocode

```c
int __fastcall SiCreateTierInternal(struct _SU_POOL_OBJECT *a1, struct _SP_TIER_INFO *a2)
{
  int result; // eax
  DWORD BytesReturned; // [rsp+60h] [rbp+18h] BYREF

  BytesReturned = 0;
  result = SiIsTierTemplateCompatible(a1, a2);
  if ( result )
  {
    result = SiValidateTier(a1, a2);
    if ( result )
      return DeviceIoControl(Spaceport, 0xE7D410u, a2, *((_DWORD *)a2 + 1), 0, 0, &BytesReturned, 0);
  }
  return result;
}

```

## disassembly

```asm
0x140011478  mov     [rsp+arg_0], rbx
0x14001147d  push    rdi
0x14001147e  sub     rsp, 40h
0x140011482  mov     rbx, rdx
0x140011485  mov     [rsp+48h+BytesReturned], 0
0x14001148d  mov     rdi, rcx
0x140011490  call    ?SiIsTierTemplateCompatible@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_TIER_INFO@@@Z; SiIsTierTemplateCompatible(_SU_POOL_OBJECT *,_SP_TIER_INFO *)
0x140011495  test    eax, eax
0x140011497  jz      short loc_1400114E5
0x140011499  mov     rdx, rbx; struct _SP_TIER_INFO *
0x14001149c  mov     rcx, rdi; struct _SU_POOL_OBJECT *
0x14001149f  call    ?SiValidateTier@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_TIER_INFO@@@Z; SiValidateTier(_SU_POOL_OBJECT *,_SP_TIER_INFO *)
0x1400114a4  test    eax, eax
0x1400114a6  jz      short loc_1400114E5
0x1400114a8  mov     r9d, [rbx+4]; nInBufferSize
0x1400114ac  lea     rax, [rsp+48h+BytesReturned]
0x1400114b1  mov     rcx, cs:?Spaceport@@3PEAXEA; hDevice
0x1400114b8  mov     r8, rbx; lpInBuffer
0x1400114bb  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x1400114c4  mov     edx, 0E7D410h; dwIoControlCode
0x1400114c9  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x1400114ce  mov     [rsp+48h+nOutBufferSize], 0; nOutBufferSize
0x1400114d6  mov     [rsp+48h+lpOutBuffer], 0; lpOutBuffer
0x1400114df  call    cs:__imp_DeviceIoControl
0x1400114e5  mov     rbx, [rsp+48h+arg_0]
0x1400114ea  add     rsp, 40h
0x1400114ee  pop     rdi
0x1400114ef  retn
```
