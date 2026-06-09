# Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::~ByteBuffer(void)

- ea: `0x140016cac`
- end: `0x140016ce8`
- name: `??1ByteBuffer@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@UEAA@XZ`
- size: `60`
- prototype: `void __fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140015db0`
- `0x140016f8c`
- `0x140016fc8`
- `0x140017910`
- `0x140017b00`
- `0x14002eb38`

## callees

- `0x140016cac`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140016cd6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016cd6`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::~ByteBuffer(
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer *this)
{
  bool v1; // zf
  void *v2; // rcx

  v1 = *((_BYTE *)this + 48) == 0;
  *(_QWORD *)this = &Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::`vftable'{for `Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteWriter'};
  *((_QWORD *)this + 1) = &Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::`vftable'{for `Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader'};
  if ( !v1 )
  {
    v2 = (void *)*((_QWORD *)this + 2);
    if ( v2 )
      ExFreePoolWithTag(v2, 0);
  }
}

```

## disassembly

```asm
0x140016cac  sub     rsp, 28h
0x140016cb0  cmp     byte ptr [rcx+30h], 0
0x140016cb4  lea     rax, ??_7ByteBuffer@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@6BByteWriter@12345@@; const Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::`vftable'{for `Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteWriter'}
0x140016cbb  mov     [rcx], rax
0x140016cbe  lea     rax, ??_7ByteBuffer@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@6BByteReader@12345@@; const Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::`vftable'{for `Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader'}
0x140016cc5  mov     [rcx+8], rax
0x140016cc9  jz      short loc_140016CE2
0x140016ccb  mov     rcx, [rcx+10h]; P
0x140016ccf  test    rcx, rcx
0x140016cd2  jz      short loc_140016CE2
0x140016cd4  xor     edx, edx; Tag
0x140016cd6  call    cs:__imp_ExFreePoolWithTag
0x140016cdd  nop     dword ptr [rax+rax+00h]
0x140016ce2  add     rsp, 28h
0x140016ce6  retn
```
