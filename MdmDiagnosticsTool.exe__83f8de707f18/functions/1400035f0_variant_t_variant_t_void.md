# _variant_t::~_variant_t(void)

- ea: `0x1400035f0`
- end: `0x140003612`
- name: `??1_variant_t@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(_variant_t *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003c44`
- `0x140009eee`
- `0x140009f00`
- `0x140009f12`
- `0x140009f24`

## callees

- `0x1400035f0`
- `0x140009aa4`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1400035f4`
- `OLEAUT32!__imp_VariantClear` at `0x1400035f4`

## pseudocode

```c
void __fastcall _variant_t::~_variant_t(VARIANTARG *this)
{
  HRESULT v1; // eax
  struct IErrorInfo *v2; // rdx

  v1 = VariantClear(this);
  if ( v1 < 0 )
    _com_issue_error(v1, v2);
}

```

## disassembly

```asm
0x1400035f0  sub     rsp, 28h
0x1400035f4  call    cs:__imp_VariantClear
0x1400035fb  nop     dword ptr [rax+rax+00h]
0x140003600  test    eax, eax
0x140003602  jns     short loc_14000360C
0x140003604  mov     ecx, eax; int
0x140003606  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14000360c  add     rsp, 28h
0x140003610  retn
```
