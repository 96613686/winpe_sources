# Comms::SerializeObject(Comms::SerializeBase &,char const *)

- ea: `0x180003ad0`
- end: `0x180003b3c`
- name: `?SerializeObject@Comms@@YAXAEAVSerializeBase@1@PEBD@Z`
- size: `108`
- prototype: `void __fastcall(Comms *__hidden this, struct Comms::SerializeBase *, const char *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003ad0`
- `0x18000b010`

## pseudocode

```c
void __fastcall Comms::SerializeObject(Comms *this, struct Comms::SerializeBase *a2, const char *a3)
{
  __int64 v5; // rax
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF

  v5 = -1;
  do
    ++v5;
  while ( *((_BYTE *)a2 + v5) );
  v6 = v5 + 1;
  (*(void (__fastcall **)(Comms *, __int64 *, __int64, unsigned __int64 *))(*(_QWORD *)this + 8LL))(
    this,
    &v6,
    8,
    &unsigned __int64 `RTTI Type Descriptor');
  (*(void (__fastcall **)(Comms *, struct Comms::SerializeBase *, __int64, char **))(*(_QWORD *)this + 8LL))(
    this,
    a2,
    v6,
    &char * `RTTI Type Descriptor');
}

```

## disassembly

```asm
0x180003ad0  mov     [rsp+arg_8], rbx
0x180003ad5  push    rdi
0x180003ad6  sub     rsp, 30h
0x180003ada  mov     rbx, rdx
0x180003add  mov     rdi, rcx
0x180003ae0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003ae4  inc     rax
0x180003ae7  cmp     byte ptr [rdx+rax], 0
0x180003aeb  jnz     short loc_180003AE4
0x180003aed  inc     rax
0x180003af0  lea     r9, ??_R0_K@8; unsigned __int64 `RTTI Type Descriptor'
0x180003af7  mov     [rsp+38h+arg_0], rax
0x180003afc  lea     rdx, [rsp+38h+arg_0]
0x180003b01  mov     rax, [rcx]
0x180003b04  mov     r8d, 8
0x180003b0a  mov     rax, [rax+8]
0x180003b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b13  mov     rax, [rdi]
0x180003b16  lea     r9, ??_R0PEAD@8; char * `RTTI Type Descriptor'
0x180003b1d  mov     r8, [rsp+38h+arg_0]
0x180003b22  mov     rdx, rbx
0x180003b25  mov     rcx, rdi
0x180003b28  mov     rax, [rax+8]
0x180003b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b31  mov     rbx, [rsp+38h+arg_8]
0x180003b36  add     rsp, 30h
0x180003b3a  pop     rdi
0x180003b3b  retn
```
