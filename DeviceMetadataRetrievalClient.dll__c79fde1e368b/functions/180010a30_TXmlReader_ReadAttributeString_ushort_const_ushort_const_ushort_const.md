# TXmlReader::ReadAttributeString(ushort const *,ushort const *,ushort const * *)

- ea: `0x180010a30`
- end: `0x180010a7d`
- name: `?ReadAttributeString@TXmlReader@@QEAAJPEBG0PEAPEBG@Z`
- size: `77`
- prototype: `__int64 __fastcall(TXmlReader *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 **)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008d8c`
- `0x18000913c`
- `0x18000a200`

## callees

- `0x180010a30`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall TXmlReader::ReadAttributeString(
        TXmlReader *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 **a4)
{
  __int64 result; // rax

  result = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, const unsigned __int16 *))(**(_QWORD **)this
                                                                                                 + 80LL))(
             *(_QWORD *)this,
             a2,
             &dword_180017E8C);
  if ( !(_DWORD)result )
    return (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 **, _QWORD))(**(_QWORD **)this + 128LL))(
             *(_QWORD *)this,
             a4,
             0);
  return result;
}

```

## disassembly

```asm
0x180010a30  mov     [rsp+arg_0], rbx
0x180010a35  push    rdi
0x180010a36  sub     rsp, 20h
0x180010a3a  mov     rbx, rcx
0x180010a3d  lea     r8, dword_180017E8C
0x180010a44  mov     rcx, [rcx]
0x180010a47  mov     rdi, r9
0x180010a4a  mov     rax, [rcx]
0x180010a4d  mov     rax, [rax+50h]
0x180010a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a56  test    eax, eax
0x180010a58  jnz     short loc_180010A72
0x180010a5a  mov     rcx, [rbx]
0x180010a5d  xor     r8d, r8d
0x180010a60  mov     rdx, rdi
0x180010a63  mov     rax, [rcx]
0x180010a66  mov     rax, [rax+80h]
0x180010a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a72  mov     rbx, [rsp+28h+arg_0]
0x180010a77  add     rsp, 20h
0x180010a7b  pop     rdi
0x180010a7c  retn
```
