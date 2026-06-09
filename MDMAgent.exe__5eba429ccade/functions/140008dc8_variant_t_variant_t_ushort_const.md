# _variant_t::_variant_t(ushort const *)

- ea: `0x140008dc8`
- end: `0x140008e0d`
- name: `??0_variant_t@@QEAA@PEBG@Z`
- size: `69`
- prototype: `_variant_t *__fastcall(_variant_t *this, const unsigned __int16 *)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000a0b8`
- `0x14000d0fc`
- `0x14000d70c`
- `0x14000dca0`
- `0x14000e200`
- `0x14000e6e8`
- `0x14000ef04`
- `0x14000f56c`
- `0x140012bd0`
- `0x14001464c`

## callees

- `0x140008830`
- `0x140008dc8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140008ddb`
- `OLEAUT32!__imp_SysAllocString` at `0x140008ddb`

## pseudocode

```c
_variant_t *__fastcall _variant_t::_variant_t(_variant_t *this, const unsigned __int16 *a2)
{
  BSTR v4; // rax
  _variant_t *result; // rax

  v4 = SysAllocString(a2);
  if ( !v4 && a2 )
    _com_issue_error(-2147024882);
  *((_QWORD *)this + 1) = v4;
  result = this;
  *(_WORD *)this = 8;
  return result;
}

```

## disassembly

```asm
0x140008dc8  mov     [rsp+arg_0], rbx
0x140008dcd  push    rdi
0x140008dce  sub     rsp, 20h
0x140008dd2  mov     rbx, rcx
0x140008dd5  mov     rdi, rdx
0x140008dd8  mov     rcx, rdx; psz
0x140008ddb  call    cs:__imp_SysAllocString
0x140008de1  test    rax, rax
0x140008de4  jnz     short loc_140008DF6
0x140008de6  test    rdi, rdi
0x140008de9  jz      short loc_140008DF6
0x140008deb  mov     ecx, 8007000Eh; int
0x140008df0  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140008df6  mov     [rbx+8], rax
0x140008dfa  mov     rax, rbx
0x140008dfd  mov     word ptr [rbx], 8
0x140008e02  mov     rbx, [rsp+28h+arg_0]
0x140008e07  add     rsp, 20h
0x140008e0b  pop     rdi
0x140008e0c  retn
```
