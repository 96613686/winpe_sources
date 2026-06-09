# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x180010798`
- end: `0x1800107b8`
- name: `_ATL::CComCriticalSection::Init_::_1_::filt$0`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
_BOOL8 __fastcall ATL::CComCriticalSection::Init_::_1_::filt_0(_DWORD **a1)
{
  return **a1 == -1073741801;
}

```

## disassembly

```asm
0x180010798  push    rbp
0x18001079a  sub     rsp, 20h
0x18001079e  mov     rbp, rdx
0x1800107a1  mov     rax, [rcx]
0x1800107a4  xor     ecx, ecx
0x1800107a6  cmp     dword ptr [rax], 0C0000017h
0x1800107ac  setz    cl
0x1800107af  mov     eax, ecx
0x1800107b1  add     rsp, 20h
0x1800107b5  pop     rbp
0x1800107b6  retn
```
