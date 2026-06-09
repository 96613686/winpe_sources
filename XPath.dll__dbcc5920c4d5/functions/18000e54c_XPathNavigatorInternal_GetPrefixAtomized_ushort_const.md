# XPathNavigatorInternal::GetPrefixAtomized(ushort const * *)

- ea: `0x18000e54c`
- end: `0x18000e58b`
- name: `?GetPrefixAtomized@XPathNavigatorInternal@@QEAAJPEAPEBG@Z`
- size: `63`
- prototype: `__int64 __fastcall(XPathNavigatorInternal *__hidden this, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ba20`
- `0x18000cdd0`

## callees

- `0x18000e498`
- `0x18000e54c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathNavigatorInternal::GetPrefixAtomized(XPathNavigatorInternal *this, const unsigned __int16 **a2)
{
  __int64 result; // rax

  result = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 56LL))(*(_QWORD *)this);
  if ( (int)result >= 0 && !*a2 )
    return XPathNavigatorInternal::GetEmptyStringAtomized(this, a2);
  return result;
}

```

## disassembly

```asm
0x18000e54c  mov     [rsp+arg_0], rbx
0x18000e551  push    rdi
0x18000e552  sub     rsp, 20h
0x18000e556  mov     rdi, rcx
0x18000e559  mov     rbx, rdx
0x18000e55c  mov     rcx, [rcx]
0x18000e55f  mov     rax, [rcx]
0x18000e562  mov     rax, [rax+38h]
0x18000e566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e56b  test    eax, eax
0x18000e56d  js      short loc_18000E580
0x18000e56f  cmp     qword ptr [rbx], 0
0x18000e573  jnz     short loc_18000E580
0x18000e575  mov     rdx, rbx; unsigned __int16 **
0x18000e578  mov     rcx, rdi; this
0x18000e57b  call    ?GetEmptyStringAtomized@XPathNavigatorInternal@@AEAAJPEAPEBG@Z; XPathNavigatorInternal::GetEmptyStringAtomized(ushort const * *)
0x18000e580  mov     rbx, [rsp+28h+arg_0]
0x18000e585  add     rsp, 20h
0x18000e589  pop     rdi
0x18000e58a  retn
```
