# XPathNavigatorInternal::GetLocalNameAtomized(ushort const * *)

- ea: `0x18000e504`
- end: `0x18000e543`
- name: `?GetLocalNameAtomized@XPathNavigatorInternal@@QEAAJPEAPEBG@Z`
- size: `63`
- prototype: `__int64 __fastcall(XPathNavigatorInternal *__hidden this, const unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b970`
- `0x18000ba20`
- `0x18000cdd0`

## callees

- `0x18000e498`
- `0x18000e504`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathNavigatorInternal::GetLocalNameAtomized(
        XPathNavigatorInternal *this,
        const unsigned __int16 **a2)
{
  __int64 result; // rax

  result = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 64LL))(*(_QWORD *)this);
  if ( (int)result >= 0 && !*a2 )
    return XPathNavigatorInternal::GetEmptyStringAtomized(this, a2);
  return result;
}

```

## disassembly

```asm
0x18000e504  mov     [rsp+arg_0], rbx
0x18000e509  push    rdi
0x18000e50a  sub     rsp, 20h
0x18000e50e  mov     rdi, rcx
0x18000e511  mov     rbx, rdx
0x18000e514  mov     rcx, [rcx]
0x18000e517  mov     rax, [rcx]
0x18000e51a  mov     rax, [rax+40h]
0x18000e51e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e523  test    eax, eax
0x18000e525  js      short loc_18000E538
0x18000e527  cmp     qword ptr [rbx], 0
0x18000e52b  jnz     short loc_18000E538
0x18000e52d  mov     rdx, rbx; unsigned __int16 **
0x18000e530  mov     rcx, rdi; this
0x18000e533  call    ?GetEmptyStringAtomized@XPathNavigatorInternal@@AEAAJPEAPEBG@Z; XPathNavigatorInternal::GetEmptyStringAtomized(ushort const * *)
0x18000e538  mov     rbx, [rsp+28h+arg_0]
0x18000e53d  add     rsp, 20h
0x18000e541  pop     rdi
0x18000e542  retn
```
