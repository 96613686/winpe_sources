# Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::ReadBytes(char *,unsigned __int64)

- ea: `0x140016d80`
- end: `0x140016ddc`
- name: `?ReadBytes@ByteBuffer@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@UEAA_KPEAD_K@Z`
- size: `92`
- prototype: `size_t __fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer *this, char *, size_t)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001afc0`

## pseudocode

```c
size_t __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::ReadBytes(
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer *this,
        char *a2,
        size_t a3)
{
  __int64 v3; // r9
  size_t v5; // rbx
  __int64 v6; // rcx
  size_t result; // rax
  size_t v8; // rdx

  v3 = *((_QWORD *)this + 4);
  v5 = *((_QWORD *)this + 2) - v3;
  if ( a3 < v5 )
    v5 = a3;
  memmove(a2, (const void *)(v3 + *((_QWORD *)this + 1)), v5);
  v6 = *((_QWORD *)this + 4);
  result = v5;
  v8 = *((_QWORD *)this + 2) - v6;
  if ( v5 < v8 )
    v8 = v5;
  *((_QWORD *)this + 4) = v6 + v8;
  return result;
}

```

## disassembly

```asm
0x140016d80  mov     [rsp+arg_0], rbx
0x140016d85  push    rdi
0x140016d86  sub     rsp, 20h
0x140016d8a  mov     r9, [rcx+20h]
0x140016d8e  mov     r10, rdx
0x140016d91  mov     rbx, [rcx+10h]
0x140016d95  mov     rdi, rcx
0x140016d98  mov     rdx, [rcx+8]
0x140016d9c  sub     rbx, r9
0x140016d9f  cmp     r8, rbx
0x140016da2  mov     rcx, r10; void *
0x140016da5  cmovb   rbx, r8
0x140016da9  add     rdx, r9; Src
0x140016dac  mov     r8, rbx; Size
0x140016daf  call    memmove
0x140016db4  mov     rcx, [rdi+20h]
0x140016db8  mov     rax, rbx
0x140016dbb  mov     rdx, [rdi+10h]
0x140016dbf  sub     rdx, rcx
0x140016dc2  cmp     rbx, rdx
0x140016dc5  cmovb   rdx, rbx
0x140016dc9  mov     rbx, [rsp+28h+arg_0]
0x140016dce  add     rdx, rcx
0x140016dd1  mov     [rdi+20h], rdx
0x140016dd5  add     rsp, 20h
0x140016dd9  pop     rdi
0x140016dda  retn
```
