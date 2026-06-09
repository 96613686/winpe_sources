# _variant_t::_variant_t(ushort const *)

- ea: `0x1400091e0`
- end: `0x14000922c`
- name: `??0_variant_t@@QEAA@PEBG@Z`
- size: `76`
- prototype: `_variant_t *(_variant_t *__hidden this, const unsigned __int16 *)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000a51c`
- `0x14000d780`
- `0x14000ddd8`
- `0x14000e3a4`
- `0x14000e934`
- `0x14000ee48`
- `0x14000f69c`
- `0x14000fd3c`
- `0x14001351c`
- `0x1400151d8`

## callees

- `0x140008c18`
- `0x1400091e0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1400091f3`
- `OLEAUT32!__imp_SysAllocString` at `0x1400091f3`

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
0x1400091e0  mov     [rsp+arg_0], rbx
0x1400091e5  push    rdi
0x1400091e6  sub     rsp, 20h
0x1400091ea  mov     rbx, rcx
0x1400091ed  mov     rdi, rdx
0x1400091f0  mov     rcx, rdx; psz
0x1400091f3  call    cs:__imp_SysAllocString
0x1400091fa  nop     dword ptr [rax+rax+00h]
0x1400091ff  test    rax, rax
0x140009202  jnz     short loc_140009214
0x140009204  test    rdi, rdi
0x140009207  jz      short loc_140009214
0x140009209  mov     ecx, 8007000Eh; int
0x14000920e  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140009214  mov     [rbx+8], rax
0x140009218  mov     rax, rbx
0x14000921b  mov     word ptr [rbx], 8
0x140009220  mov     rbx, [rsp+28h+arg_0]
0x140009225  add     rsp, 20h
0x140009229  pop     rdi
0x14000922a  retn
```
