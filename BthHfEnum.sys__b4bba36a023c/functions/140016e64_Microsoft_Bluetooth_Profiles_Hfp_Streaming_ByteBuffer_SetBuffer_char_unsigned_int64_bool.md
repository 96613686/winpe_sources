# Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::SetBuffer(char *,unsigned __int64,bool)

- ea: `0x140016e64`
- end: `0x140016ec6`
- name: `?SetBuffer@ByteBuffer@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@QEAAXPEAD_K_N@Z`
- size: `98`
- prototype: `void __fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer *this, char *, __int64)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140017004`
- `0x140017208`
- `0x14001728c`
- `0x140017310`
- `0x140017344`
- `0x140017380`
- `0x1400177c8`
- `0x14002ef90`

## callees

- `0x140016e64`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140016e8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016e8d`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::SetBuffer(
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer *this,
        char *a2,
        __int64 a3)
{
  void *v6; // rcx

  if ( *((_BYTE *)this + 48) )
  {
    v6 = (void *)*((_QWORD *)this + 2);
    if ( v6 )
      ExFreePoolWithTag(v6, 0);
  }
  *((_QWORD *)this + 2) = a2;
  *((_QWORD *)this + 3) = a3;
  *((_BYTE *)this + 48) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
}

```

## disassembly

```asm
0x140016e64  mov     [rsp+arg_0], rbx
0x140016e69  mov     [rsp+arg_8], rsi
0x140016e6e  push    rdi
0x140016e6f  sub     rsp, 20h
0x140016e73  cmp     byte ptr [rcx+30h], 0
0x140016e77  mov     rdi, r8
0x140016e7a  mov     rsi, rdx
0x140016e7d  mov     rbx, rcx
0x140016e80  jz      short loc_140016E99
0x140016e82  mov     rcx, [rcx+10h]; P
0x140016e86  test    rcx, rcx
0x140016e89  jz      short loc_140016E99
0x140016e8b  xor     edx, edx; Tag
0x140016e8d  call    cs:__imp_ExFreePoolWithTag
0x140016e94  nop     dword ptr [rax+rax+00h]
0x140016e99  mov     [rbx+10h], rsi
0x140016e9d  mov     rsi, [rsp+28h+arg_8]
0x140016ea2  mov     [rbx+18h], rdi
0x140016ea6  mov     byte ptr [rbx+30h], 0
0x140016eaa  mov     qword ptr [rbx+20h], 0
0x140016eb2  mov     qword ptr [rbx+28h], 0
0x140016eba  mov     rbx, [rsp+28h+arg_0]
0x140016ebf  add     rsp, 20h
0x140016ec3  pop     rdi
0x140016ec4  retn
```
