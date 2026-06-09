# Comms::SerializeObject(Comms::SerializeBase &,ushort const *)

- ea: `0x180003b50`
- end: `0x180003bc0`
- name: `?SerializeObject@Comms@@YAXAEAVSerializeBase@1@PEBG@Z`
- size: `112`
- prototype: `void __fastcall(Comms *__hidden this, struct Comms::SerializeBase *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003b50`
- `0x18000b010`

## pseudocode

```c
void __fastcall Comms::SerializeObject(Comms *this, struct Comms::SerializeBase *a2, const unsigned __int16 *a3)
{
  __int64 v5; // rax
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF

  v5 = -1;
  do
    ++v5;
  while ( *((_WORD *)a2 + v5) );
  v6 = v5 + 1;
  (*(void (__fastcall **)(Comms *, __int64 *, __int64, unsigned __int64 *))(*(_QWORD *)this + 8LL))(
    this,
    &v6,
    8,
    &unsigned __int64 `RTTI Type Descriptor');
  (*(void (__fastcall **)(Comms *, struct Comms::SerializeBase *, __int64, unsigned __int16 **))(*(_QWORD *)this + 8LL))(
    this,
    a2,
    2 * v6,
    &unsigned short * `RTTI Type Descriptor');
}

```

## disassembly

```asm
0x180003b50  mov     [rsp+arg_8], rbx
0x180003b55  push    rdi
0x180003b56  sub     rsp, 30h
0x180003b5a  mov     rbx, rdx
0x180003b5d  mov     rdi, rcx
0x180003b60  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003b64  inc     rax
0x180003b67  cmp     word ptr [rdx+rax*2], 0
0x180003b6c  jnz     short loc_180003B64
0x180003b6e  inc     rax
0x180003b71  lea     r9, ??_R0_K@8; unsigned __int64 `RTTI Type Descriptor'
0x180003b78  mov     [rsp+38h+arg_0], rax
0x180003b7d  lea     rdx, [rsp+38h+arg_0]
0x180003b82  mov     rax, [rcx]
0x180003b85  mov     r8d, 8
0x180003b8b  mov     rax, [rax+8]
0x180003b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b94  mov     rax, [rdi]
0x180003b97  lea     r9, ??_R0PEAG@8; ushort * `RTTI Type Descriptor'
0x180003b9e  mov     r8, [rsp+38h+arg_0]
0x180003ba3  mov     rdx, rbx
0x180003ba6  add     r8, r8
0x180003ba9  mov     rcx, rdi
0x180003bac  mov     rax, [rax+8]
0x180003bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bb5  mov     rbx, [rsp+38h+arg_8]
0x180003bba  add     rsp, 30h
0x180003bbe  pop     rdi
0x180003bbf  retn
```
