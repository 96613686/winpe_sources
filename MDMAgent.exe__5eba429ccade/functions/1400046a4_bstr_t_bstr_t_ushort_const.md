# _bstr_t::_bstr_t(ushort const *)

- ea: `0x1400046a4`
- end: `0x140004723`
- name: `??0_bstr_t@@QEAA@PEBG@Z`
- size: `127`
- prototype: `_bstr_t *__fastcall(_bstr_t *this, const unsigned __int16 *)`
- caller_count: `14`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140007f34`
- `0x1400096dc`
- `0x14000a0b8`
- `0x14000bdc4`
- `0x14000d0fc`
- `0x14000d70c`
- `0x14000dca0`
- `0x14000e200`
- `0x14000e6e8`
- `0x14000eaa8`
- `0x14000ef04`
- `0x14000f56c`
- `0x140012bd0`
- `0x14001464c`

## callees

- `0x1400046a4`
- `0x140004c80`
- `0x140008830`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1400046dd`
- `OLEAUT32!__imp_SysAllocString` at `0x1400046dd`

## pseudocode

```c
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
0x1400046a4  mov     [rsp+arg_0], rbx
0x1400046a9  mov     [rsp+arg_8], rsi
0x1400046ae  push    rdi
0x1400046af  sub     rsp, 20h
0x1400046b3  mov     rsi, rdx
0x1400046b6  mov     rdi, rcx
0x1400046b9  call    ??2Data_t@_bstr_t@@SAPEAX_K@Z; _bstr_t::Data_t::operator new(unsigned __int64)
0x1400046be  mov     rbx, rax
0x1400046c1  mov     [rsp+28h+arg_10], rax
0x1400046c6  test    rax, rax
0x1400046c9  jz      short loc_1400046FB
0x1400046cb  mov     qword ptr [rax+8], 0
0x1400046d3  mov     dword ptr [rax+10h], 1
0x1400046da  mov     rcx, rsi; psz
0x1400046dd  call    cs:__imp_SysAllocString
0x1400046e3  mov     [rbx], rax
0x1400046e6  test    rax, rax
0x1400046e9  jnz     short loc_1400046FD
0x1400046eb  test    rsi, rsi
0x1400046ee  jz      short loc_1400046FD
0x1400046f0  mov     ecx, 8007000Eh; int
0x1400046f5  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400046fb  xor     ebx, ebx
0x1400046fd  mov     [rdi], rbx
0x140004700  test    rbx, rbx
0x140004703  jnz     short loc_140004710
0x140004705  mov     ecx, 8007000Eh; int
0x14000470a  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140004710  mov     rax, rdi
0x140004713  mov     rbx, [rsp+28h+arg_0]
0x140004718  mov     rsi, [rsp+28h+arg_8]
0x14000471d  add     rsp, 20h
0x140004721  pop     rdi
0x140004722  retn
```
