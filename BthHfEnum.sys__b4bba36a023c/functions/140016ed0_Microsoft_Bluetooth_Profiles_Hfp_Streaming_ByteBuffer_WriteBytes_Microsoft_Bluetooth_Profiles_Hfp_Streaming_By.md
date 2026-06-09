# Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::WriteBytes(Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader *)

- ea: `0x140016ed0`
- end: `0x140016f1c`
- name: `?WriteBytes@ByteBuffer@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@UEAA_KPEAVByteReader@23456@@Z`
- size: `76`
- prototype: `unsigned __int64 __fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer *__hidden this, struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140017380`
- `0x1400177c8`

## callees

- `0x14001ae00`

## pseudocode

```c
unsigned __int64 __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::WriteBytes(
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer *this,
        struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader *a2)
{
  unsigned __int64 result; // rax
  __int64 v4; // rcx
  unsigned __int64 v5; // rdx

  result = (**(__int64 (__fastcall ***)(struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader *, _QWORD, _QWORD))a2)(
             a2,
             *((_QWORD *)this + 4) + *((_QWORD *)this + 2),
             *((_QWORD *)this + 3) - *((_QWORD *)this + 4));
  v4 = *((_QWORD *)this + 4);
  v5 = *((_QWORD *)this + 3) - v4;
  if ( result < v5 )
    v5 = result;
  *((_QWORD *)this + 4) = v4 + v5;
  return result;
}

```

## disassembly

```asm
0x140016ed0  push    rbx
0x140016ed2  sub     rsp, 20h
0x140016ed6  mov     r9, [rdx]
0x140016ed9  mov     r11, rdx
0x140016edc  mov     r10, [rcx+20h]
0x140016ee0  mov     rbx, rcx
0x140016ee3  mov     r8, [rcx+18h]
0x140016ee7  mov     rdx, [rcx+10h]
0x140016eeb  sub     r8, r10
0x140016eee  mov     rax, [r9]
0x140016ef1  add     rdx, r10
0x140016ef4  mov     rcx, r11
0x140016ef7  call    _guard_dispatch_icall
0x140016efc  mov     rcx, [rbx+20h]
0x140016f00  mov     rdx, [rbx+18h]
0x140016f04  sub     rdx, rcx
0x140016f07  cmp     rax, rdx
0x140016f0a  cmovb   rdx, rax
0x140016f0e  add     rdx, rcx
0x140016f11  mov     [rbx+20h], rdx
0x140016f15  add     rsp, 20h
0x140016f19  pop     rbx
0x140016f1a  retn
```
