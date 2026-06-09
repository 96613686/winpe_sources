# wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)

- ea: `0x18000ad18`
- end: `0x18000ad72`
- name: `?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z`
- size: `90`
- prototype: `bool __fastcall(void **this, const void *, unsigned __int64)`
- caller_count: `16`
- callee_count: `3`
- tags: ``

## callers

- `0x180004d14`
- `0x180004e44`
- `0x180004f74`
- `0x1800050a4`
- `0x1800051d4`
- `0x180005304`
- `0x180005434`
- `0x180005564`
- `0x180005694`
- `0x1800057c4`
- `0x1800058f4`
- `0x180005a24`
- `0x180007ccc`
- `0x180007d50`
- `0x180009cf0`
- `0x180009e68`

## callees

- `0x18000ac28`
- `0x18000ad18`
- `0x18000b43c`

## pseudocode

```c
bool __fastcall wil::details_abi::heap_buffer::push_back(void **this, const void *a2, unsigned __int64 a3)
{
  bool result; // al

  result = wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)this, a3);
  if ( result )
  {
    memcpy_s(this[1], ((_BYTE *)this[2] - (_BYTE *)this[1]) & -(__int64)(this[1] < this[2]), a2, a3);
    this[1] = (char *)this[1] + a3;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000ad18  mov     [rsp+arg_0], rbx
0x18000ad1d  mov     [rsp+arg_8], rsi
0x18000ad22  push    rdi
0x18000ad23  sub     rsp, 20h
0x18000ad27  mov     rsi, rdx
0x18000ad2a  mov     rdi, r8
0x18000ad2d  mov     rdx, r8; unsigned __int64
0x18000ad30  mov     rbx, rcx
0x18000ad33  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000ad38  test    al, al
0x18000ad3a  jz      short loc_18000AD62
0x18000ad3c  mov     rcx, [rbx+8]; Destination
0x18000ad40  mov     r9, rdi; SourceSize
0x18000ad43  mov     rax, [rbx+10h]
0x18000ad47  mov     r8, rsi; Source
0x18000ad4a  sub     rax, rcx
0x18000ad4d  cmp     rcx, [rbx+10h]
0x18000ad51  sbb     rdx, rdx
0x18000ad54  and     rdx, rax; DestinationSize
0x18000ad57  call    memcpy_s
0x18000ad5c  add     [rbx+8], rdi
0x18000ad60  mov     al, 1
0x18000ad62  mov     rbx, [rsp+28h+arg_0]
0x18000ad67  mov     rsi, [rsp+28h+arg_8]
0x18000ad6c  add     rsp, 20h
0x18000ad70  pop     rdi
0x18000ad71  retn
```
