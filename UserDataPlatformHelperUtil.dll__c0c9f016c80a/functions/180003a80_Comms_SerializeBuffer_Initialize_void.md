# Comms::SerializeBuffer::Initialize(void)

- ea: `0x180003a80`
- end: `0x180003ab7`
- name: `?Initialize@SerializeBuffer@Comms@@QEAA_NXZ`
- size: `55`
- prototype: `bool __fastcall(Comms::SerializeBuffer *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002d98`

## pseudocode

```c
bool __fastcall Comms::SerializeBuffer::Initialize(Comms::SerializeBuffer *this)
{
  bool result; // al

  utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve((char *)this + 24, *((_QWORD *)this + 1));
  result = *((_QWORD *)this + 5) - *((_QWORD *)this + 3) >= *((_QWORD *)this + 1);
  *((_BYTE *)this + 48) = result;
  return result;
}

```

## disassembly

```asm
0x180003a80  mov     [rsp+arg_0], rbx
0x180003a85  push    rdi
0x180003a86  sub     rsp, 20h
0x180003a8a  mov     rdx, [rcx+8]
0x180003a8e  mov     rdi, rcx
0x180003a91  add     rcx, 18h
0x180003a95  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x180003a9a  mov     rax, [rdi+28h]
0x180003a9e  sub     rax, [rdi+18h]
0x180003aa2  cmp     rax, [rdi+8]
0x180003aa6  mov     rbx, [rsp+28h+arg_0]
0x180003aab  setnb   al
0x180003aae  mov     [rdi+30h], al
0x180003ab1  add     rsp, 20h
0x180003ab5  pop     rdi
0x180003ab6  retn
```
