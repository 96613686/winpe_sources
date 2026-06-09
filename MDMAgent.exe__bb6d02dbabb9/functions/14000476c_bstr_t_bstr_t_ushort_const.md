# _bstr_t::_bstr_t(ushort const *)

- ea: `0x14000476c`
- end: `0x1400047f2`
- name: `??0_bstr_t@@QEAA@PEBG@Z`
- size: `134`
- prototype: `_bstr_t *(_bstr_t *__hidden this, const unsigned __int16 *)`
- caller_count: `14`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000829c`
- `0x140009ae8`
- `0x14000a51c`
- `0x14000c314`
- `0x14000d780`
- `0x14000ddd8`
- `0x14000e3a4`
- `0x14000e934`
- `0x14000ee48`
- `0x14000f220`
- `0x14000f69c`
- `0x14000fd3c`
- `0x14001351c`
- `0x1400151d8`

## callees

- `0x14000476c`
- `0x140004d24`
- `0x140008c18`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1400047a5`
- `OLEAUT32!__imp_SysAllocString` at `0x1400047a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_bstr_t *__fastcall _bstr_t::_bstr_t(_bstr_t *this, const unsigned __int16 *a2)
{
  BSTR *v4; // rax
  BSTR *v5; // rbx
  BSTR v6; // rax

  v4 = (BSTR *)_bstr_t::Data_t::operator new((unsigned __int64)this);
  v5 = v4;
  if ( v4 )
  {
    v4[1] = 0;
    *((_DWORD *)v4 + 4) = 1;
    v6 = SysAllocString(a2);
    *v5 = v6;
    if ( !v6 && a2 )
      _com_issue_error(-2147024882);
  }
  else
  {
    v5 = 0;
  }
  *(_QWORD *)this = v5;
  if ( !v5 )
    _com_issue_error(-2147024882);
  return this;
}

```

## disassembly

```asm
0x14000476c  mov     [rsp+arg_0], rbx
0x140004771  mov     [rsp+arg_8], rsi
0x140004776  push    rdi
0x140004777  sub     rsp, 20h
0x14000477b  mov     rsi, rdx
0x14000477e  mov     rdi, rcx
0x140004781  call    ??2Data_t@_bstr_t@@SAPEAX_K@Z; _bstr_t::Data_t::operator new(unsigned __int64)
0x140004786  mov     rbx, rax
0x140004789  mov     [rsp+28h+arg_10], rax
0x14000478e  test    rax, rax
0x140004791  jz      short loc_1400047C9
0x140004793  mov     qword ptr [rax+8], 0
0x14000479b  mov     dword ptr [rax+10h], 1
0x1400047a2  mov     rcx, rsi; psz
0x1400047a5  call    cs:__imp_SysAllocString
0x1400047ac  nop     dword ptr [rax+rax+00h]
0x1400047b1  mov     [rbx], rax
0x1400047b4  test    rax, rax
0x1400047b7  jnz     short loc_1400047CB
0x1400047b9  test    rsi, rsi
0x1400047bc  jz      short loc_1400047CB
0x1400047be  mov     ecx, 8007000Eh; int
0x1400047c3  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400047c9  xor     ebx, ebx
0x1400047cb  mov     [rdi], rbx
0x1400047ce  test    rbx, rbx
0x1400047d1  jnz     short loc_1400047DE
0x1400047d3  mov     ecx, 8007000Eh; int
0x1400047d8  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400047de  mov     rax, rdi
0x1400047e1  mov     rbx, [rsp+28h+arg_0]
0x1400047e6  mov     rsi, [rsp+28h+arg_8]
0x1400047eb  add     rsp, 20h
0x1400047ef  pop     rdi
0x1400047f0  retn
```
