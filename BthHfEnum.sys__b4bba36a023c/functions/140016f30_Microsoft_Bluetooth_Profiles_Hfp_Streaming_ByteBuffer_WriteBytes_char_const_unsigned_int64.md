# Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::WriteBytes(char const *,unsigned __int64)

- ea: `0x140016f30`
- end: `0x140016f86`
- name: `?WriteBytes@ByteBuffer@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@UEAA_KPEBD_K@Z`
- size: `86`
- prototype: `size_t __fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer *this, const char *, size_t)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001afc0`

## pseudocode

```c
size_t __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::WriteBytes(
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer *this,
        const char *a2,
        size_t a3)
{
  __int64 v3; // r9
  __int64 v5; // rbx
  __int64 v6; // rcx
  size_t v7; // rbx
  __int64 v8; // rcx
  size_t result; // rax
  size_t v10; // rdx

  v3 = *((_QWORD *)this + 4);
  v5 = *((_QWORD *)this + 3);
  v6 = *((_QWORD *)this + 2);
  v7 = v5 - v3;
  if ( a3 < v7 )
    v7 = a3;
  memmove((void *)(v3 + v6), a2, v7);
  v8 = *((_QWORD *)this + 4);
  result = v7;
  v10 = *((_QWORD *)this + 3) - v8;
  if ( v7 < v10 )
    v10 = v7;
  *((_QWORD *)this + 4) = v8 + v10;
  return result;
}

```

## disassembly

```asm
0x140016f30  mov     [rsp+arg_0], rbx
0x140016f35  push    rdi
0x140016f36  sub     rsp, 20h
0x140016f3a  mov     r9, [rcx+20h]
0x140016f3e  mov     rdi, rcx
0x140016f41  mov     rbx, [rcx+18h]
0x140016f45  mov     rcx, [rcx+10h]
0x140016f49  sub     rbx, r9
0x140016f4c  cmp     r8, rbx
0x140016f4f  cmovb   rbx, r8
0x140016f53  add     rcx, r9; void *
0x140016f56  mov     r8, rbx; Size
0x140016f59  call    memmove
0x140016f5e  mov     rcx, [rdi+20h]
0x140016f62  mov     rax, rbx
0x140016f65  mov     rdx, [rdi+18h]
0x140016f69  sub     rdx, rcx
0x140016f6c  cmp     rbx, rdx
0x140016f6f  cmovb   rdx, rbx
0x140016f73  mov     rbx, [rsp+28h+arg_0]
0x140016f78  add     rdx, rcx
0x140016f7b  mov     [rdi+20h], rdx
0x140016f7f  add     rsp, 20h
0x140016f83  pop     rdi
0x140016f84  retn
```
