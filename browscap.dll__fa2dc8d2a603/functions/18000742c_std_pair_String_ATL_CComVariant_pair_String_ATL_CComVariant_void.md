# std::pair<String,ATL::CComVariant>::~pair<String,ATL::CComVariant>(void)

- ea: `0x18000742c`
- end: `0x18000744c`
- name: `??1?$pair@VString@@VCComVariant@ATL@@@std@@QEAA@XZ`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000bd7f`

## callees

- `0x180002498`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180007439`
- `OLEAUT32!__imp_VariantClear` at `0x180007439`

## pseudocode

```c
__int64 __fastcall std::pair<String,ATL::CComVariant>::~pair<String,ATL::CComVariant>(__int64 a1)
{
  VariantClear((VARIANTARG *)(a1 + 16));
  return TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(a1);
}

```

## disassembly

```asm
0x18000742c  push    rbx
0x18000742e  sub     rsp, 20h
0x180007432  mov     rbx, rcx
0x180007435  add     rcx, 10h; pvarg
0x180007439  call    cs:__imp_VariantClear
0x18000743f  mov     rcx, rbx
0x180007442  add     rsp, 20h
0x180007446  pop     rbx
0x180007447  jmp     ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
```
