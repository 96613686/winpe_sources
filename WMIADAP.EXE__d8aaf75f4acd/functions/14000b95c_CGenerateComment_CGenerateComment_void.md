# CGenerateComment::~CGenerateComment(void)

- ea: `0x14000b95c`
- end: `0x14000b97a`
- name: `??1CGenerateComment@@UEAA@XZ`
- size: `30`
- prototype: `void __fastcall(BSTR *this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400159cf`
- `0x140015ac4`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000b96e`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b96e`

## pseudocode

```c
void __fastcall CGenerateComment::~CGenerateComment(BSTR *this)
{
  *this = (BSTR)&CGenerateComment::`vftable';
  SysFreeString(this[1]);
}

```

## disassembly

```asm
0x14000b95c  sub     rsp, 28h
0x14000b960  lea     rax, ??_7CGenerateComment@@6B@; const CGenerateComment::`vftable'
0x14000b967  mov     [rcx], rax
0x14000b96a  mov     rcx, [rcx+8]; bstrString
0x14000b96e  call    cs:__imp_SysFreeString
0x14000b974  nop
0x14000b975  add     rsp, 28h
0x14000b979  retn
```
