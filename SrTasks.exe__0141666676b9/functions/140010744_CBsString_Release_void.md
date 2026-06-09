# CBsString::_Release(void)

- ea: `0x140010744`
- end: `0x14001077c`
- name: `?_Release@CBsString@@AEAAXXZ`
- size: `56`
- prototype: `void __fastcall(CBsString *__hidden this)`
- caller_count: `13`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140003320`
- `0x1400039e4`
- `0x140004a70`
- `0x140006018`
- `0x1400066e0`
- `0x1400068d4`
- `0x140006e40`
- `0x14000e0f0`
- `0x14000f24c`
- `0x14000f510`
- `0x14000f7a0`
- `0x14000fa1c`
- `0x14001036c`

## callees

- `0x140010744`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140010760`
- `ole32!CoTaskMemFree` at `0x140010760`

## pseudocode

```c
void __fastcall CBsString::_Release(LPVOID *this)
{
  if ( *this != qword_140013960 )
    CoTaskMemFree(*this);
  *this = qword_140013960;
  this[1] = 0;
}

```

## disassembly

```asm
0x140010744  mov     [rsp+arg_0], rbx
0x140010749  push    rdi
0x14001074a  sub     rsp, 20h
0x14001074e  lea     rdi, qword_140013960
0x140010755  mov     rbx, rcx
0x140010758  cmp     [rcx], rdi
0x14001075b  jz      short loc_140010766
0x14001075d  mov     rcx, [rcx]; pv
0x140010760  call    cs:__imp_CoTaskMemFree
0x140010766  mov     [rbx], rdi
0x140010769  mov     qword ptr [rbx+8], 0
0x140010771  mov     rbx, [rsp+28h+arg_0]
0x140010776  add     rsp, 20h
0x14001077a  pop     rdi
0x14001077b  retn
```
