# Comms::SerializeBuffer::`vector deleting destructor'(uint)

- ea: `0x180003890`
- end: `0x1800038df`
- name: `??_ESerializeBuffer@Comms@@UEAAPEAXI@Z`
- size: `79`
- prototype: `Comms::SerializeBuffer *__fastcall(Comms::SerializeBuffer *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001160`
- `0x180001178`
- `0x180003890`

## pseudocode

```c
Comms::SerializeBuffer *__fastcall Comms::SerializeBuffer::`vector deleting destructor'(
        Comms::SerializeBuffer *this,
        char a2)
{
  void *v4; // rcx

  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 != (void *)-1LL )
  {
    *((_QWORD *)this + 4) = v4;
    operator delete(v4);
  }
  *(_QWORD *)this = &Comms::SerializeBase::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003890  mov     [rsp+arg_0], rbx
0x180003895  push    rdi
0x180003896  sub     rsp, 20h
0x18000389a  mov     rbx, rcx
0x18000389d  mov     edi, edx
0x18000389f  mov     rcx, [rcx+18h]; Block
0x1800038a3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800038a7  jz      short loc_1800038B9
0x1800038a9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800038b0  mov     [rbx+20h], rcx
0x1800038b4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800038b9  lea     rax, ??_7SerializeBase@Comms@@6B@; const Comms::SerializeBase::`vftable'
0x1800038c0  mov     [rbx], rax
0x1800038c3  test    dil, 1
0x1800038c7  jz      short loc_1800038D1
0x1800038c9  mov     rcx, rbx; Block
0x1800038cc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800038d1  mov     rax, rbx
0x1800038d4  mov     rbx, [rsp+28h+arg_0]
0x1800038d9  add     rsp, 20h
0x1800038dd  pop     rdi
0x1800038de  retn
```
