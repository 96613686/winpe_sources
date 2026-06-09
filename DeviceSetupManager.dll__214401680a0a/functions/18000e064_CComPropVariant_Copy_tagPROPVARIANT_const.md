# CComPropVariant::Copy(tagPROPVARIANT const &)

- ea: `0x18000e064`
- end: `0x18000e091`
- name: `?Copy@CComPropVariant@@QEAAJAEBUtagPROPVARIANT@@@Z`
- size: `45`
- prototype: `HRESULT __fastcall(PROPVARIANT *this, const PROPVARIANT *)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180014198`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000e074`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000e074`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000e08a`

## pseudocode

```c
HRESULT __fastcall CComPropVariant::Copy(PROPVARIANT *this, const PROPVARIANT *a2)
{
  PropVariantClear(this);
  return PropVariantCopy(this, a2);
}

```

## disassembly

```asm
0x18000e064  mov     [rsp+arg_0], rbx
0x18000e069  push    rdi
0x18000e06a  sub     rsp, 20h
0x18000e06e  mov     rbx, rdx
0x18000e071  mov     rdi, rcx
0x18000e074  call    cs:__imp_PropVariantClear
0x18000e07a  mov     rdx, rbx
0x18000e07d  mov     rcx, rdi
0x18000e080  mov     rbx, [rsp+28h+arg_0]
0x18000e085  add     rsp, 20h
0x18000e089  pop     rdi
0x18000e08a  jmp     cs:__imp_PropVariantCopy
```
