# Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::ReadBytes(Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteWriter *)

- ea: `0x140016df0`
- end: `0x140016e3c`
- name: `?ReadBytes@ByteBuffer@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@UEAA_KPEAVByteWriter@23456@@Z`
- size: `76`
- prototype: `unsigned __int64 __fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer *__hidden this, struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteWriter *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140017208`
- `0x14001728c`

## callees

- `0x14001ae00`

## pseudocode

```c
unsigned __int64 __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::ReadBytes(
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer *this,
        struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteWriter *a2)
{
  unsigned __int64 result; // rax
  __int64 v4; // rcx
  unsigned __int64 v5; // rdx

  result = (**(__int64 (__fastcall ***)(struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteWriter *, _QWORD, _QWORD))a2)(
             a2,
             *((_QWORD *)this + 4) + *((_QWORD *)this + 1),
             *((_QWORD *)this + 2) - *((_QWORD *)this + 4));
  v4 = *((_QWORD *)this + 4);
  v5 = *((_QWORD *)this + 2) - v4;
  if ( result < v5 )
    v5 = result;
  *((_QWORD *)this + 4) = v4 + v5;
  return result;
}

```

## disassembly

```asm
0x140016df0  push    rbx
0x140016df2  sub     rsp, 20h
0x140016df6  mov     r9, [rdx]
0x140016df9  mov     r11, rdx
0x140016dfc  mov     r10, [rcx+20h]
0x140016e00  mov     rbx, rcx
0x140016e03  mov     r8, [rcx+10h]
0x140016e07  mov     rdx, [rcx+8]
0x140016e0b  sub     r8, r10
0x140016e0e  mov     rax, [r9]
0x140016e11  add     rdx, r10
0x140016e14  mov     rcx, r11
0x140016e17  call    _guard_dispatch_icall
0x140016e1c  mov     rcx, [rbx+20h]
0x140016e20  mov     rdx, [rbx+10h]
0x140016e24  sub     rdx, rcx
0x140016e27  cmp     rax, rdx
0x140016e2a  cmovb   rdx, rax
0x140016e2e  add     rdx, rcx
0x140016e31  mov     [rbx+20h], rdx
0x140016e35  add     rsp, 20h
0x140016e39  pop     rbx
0x140016e3a  retn
```
