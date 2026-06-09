# ATL::CComVariant::~CComVariant(void)

- ea: `0x14000e264`
- end: `0x14000e283`
- name: `??1CComVariant@ATL@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(VARIANTARG *this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140015d4b`
- `0x140015d5d`
- `0x140015dbe`
- `0x140015dd0`

## callees

- `0x14000e264`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x14000e277`
- `OLEAUT32!__imp_VariantClear` at `0x14000e277`

## pseudocode

```c
void __fastcall ATL::CComVariant::~CComVariant(VARIANTARG *this)
{
  if ( this->vt == 4095 )
    this->vt = 8;
  VariantClear(this);
}

```

## disassembly

```asm
0x14000e264  sub     rsp, 28h
0x14000e268  mov     eax, 0FFFh
0x14000e26d  cmp     [rcx], ax
0x14000e270  jnz     short loc_14000E277
0x14000e272  mov     word ptr [rcx], 8
0x14000e277  call    cs:__imp_VariantClear
0x14000e27d  nop
0x14000e27e  add     rsp, 28h
0x14000e282  retn
```
