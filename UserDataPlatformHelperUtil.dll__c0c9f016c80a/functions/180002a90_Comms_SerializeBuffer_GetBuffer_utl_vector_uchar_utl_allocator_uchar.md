# Comms::SerializeBuffer::GetBuffer(utl::vector<uchar,utl::allocator<uchar>> &)

- ea: `0x180002a90`
- end: `0x180002aca`
- name: `?GetBuffer@SerializeBuffer@Comms@@QEAAXAEAV?$vector@EV?$allocator@E@utl@@@utl@@@Z`
- size: `58`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall Comms::SerializeBuffer::GetBuffer(_QWORD *a1, _QWORD *a2)
{
  __int64 v3; // r8
  __int64 v4; // rax
  __int64 v5; // r8
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 result; // rax

  v3 = a1[3];
  a1[3] = *a2;
  v4 = a2[1];
  *a2 = v3;
  v5 = a1[4];
  a1[4] = v4;
  v6 = a2[2];
  a2[1] = v5;
  v7 = a1[5];
  a1[5] = v6;
  a2[2] = v7;
  result = a1[3];
  a1[4] = result;
  return result;
}

```

## disassembly

```asm
0x180002a90  mov     rax, [rdx]
0x180002a93  mov     r9, rcx
0x180002a96  mov     r8, [rcx+18h]
0x180002a9a  mov     [rcx+18h], rax
0x180002a9e  mov     rax, [rdx+8]
0x180002aa2  mov     [rdx], r8
0x180002aa5  mov     r8, [rcx+20h]
0x180002aa9  mov     [rcx+20h], rax
0x180002aad  mov     rax, [rdx+10h]
0x180002ab1  mov     [rdx+8], r8
0x180002ab5  mov     rcx, [rcx+28h]
0x180002ab9  mov     [r9+28h], rax
0x180002abd  mov     [rdx+10h], rcx
0x180002ac1  mov     rax, [r9+18h]
0x180002ac5  mov     [r9+20h], rax
0x180002ac9  retn
```
