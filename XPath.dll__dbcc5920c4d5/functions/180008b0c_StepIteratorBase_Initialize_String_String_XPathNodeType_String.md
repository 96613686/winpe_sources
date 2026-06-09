# StepIteratorBase::Initialize(String &,String &,XPathNodeType,String &)

- ea: `0x180008b0c`
- end: `0x180008b59`
- name: `?Initialize@StepIteratorBase@@IEAAXAEAVString@@0W4XPathNodeType@@0@Z`
- size: `77`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180007300`
- `0x180007390`
- `0x180007420`
- `0x1800074b0`
- `0x180007540`
- `0x1800075c0`
- `0x180007640`
- `0x1800076d0`
- `0x180007760`
- `0x1800077f0`
- `0x180007880`
- `0x180007910`

## callees

- `0x1800068d8`

## pseudocode

```c
__int64 __fastcall StepIteratorBase::Initialize(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  String::operator=(a1 + 64, a2);
  String::operator=(a1 + 72, a3);
  *(_DWORD *)(a1 + 36) = a4;
  return String::operator=(a1 + 96, a5);
}

```

## disassembly

```asm
0x180008b0c  mov     [rsp+arg_0], rbx
0x180008b11  mov     [rsp+arg_8], rsi
0x180008b16  push    rdi
0x180008b17  sub     rsp, 20h
0x180008b1b  mov     rdi, rcx
0x180008b1e  mov     esi, r9d
0x180008b21  add     rcx, 40h ; '@'
0x180008b25  mov     rbx, r8
0x180008b28  call    ??4String@@QEAAAEAV0@AEBV0@@Z; String::operator=(String const &)
0x180008b2d  lea     rcx, [rdi+48h]
0x180008b31  mov     rdx, rbx
0x180008b34  call    ??4String@@QEAAAEAV0@AEBV0@@Z; String::operator=(String const &)
0x180008b39  mov     rdx, [rsp+28h+arg_20]
0x180008b3e  lea     rcx, [rdi+60h]
0x180008b42  mov     [rdi+24h], esi
0x180008b45  mov     rbx, [rsp+28h+arg_0]
0x180008b4a  mov     rsi, [rsp+28h+arg_8]
0x180008b4f  add     rsp, 20h
0x180008b53  pop     rdi
0x180008b54  jmp     ??4String@@QEAAAEAV0@AEBV0@@Z; String::operator=(String const &)
```
