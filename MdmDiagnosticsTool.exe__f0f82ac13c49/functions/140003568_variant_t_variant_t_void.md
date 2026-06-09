# _variant_t::~_variant_t(void)

- ea: `0x140003568`
- end: `0x140003583`
- name: `??1_variant_t@@QEAA@XZ`
- size: `27`
- prototype: `void __fastcall(VARIANTARG *this)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003ae0`
- `0x1400098b9`
- `0x1400098cb`
- `0x1400098dd`
- `0x1400098ef`

## callees

- `0x140003568`
- `0x140009474`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x14000356c`
- `OLEAUT32!__imp_VariantClear` at `0x14000356c`

## pseudocode

```c
void __fastcall _variant_t::~_variant_t(VARIANTARG *this)
{
  HRESULT v1; // eax

  v1 = VariantClear(this);
  if ( v1 < 0 )
    _com_issue_error(v1);
}

```

## disassembly

```asm
0x140003568  sub     rsp, 28h
0x14000356c  call    cs:__imp_VariantClear
0x140003572  test    eax, eax
0x140003574  jns     short loc_14000357E
0x140003576  mov     ecx, eax; int
0x140003578  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14000357e  add     rsp, 28h
0x140003582  retn
```
