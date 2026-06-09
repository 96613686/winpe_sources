# VfsPreNetworkQueryOpen

- ea: `0x14000ad00`
- end: `0x14000ad38`
- name: `VfsPreNetworkQueryOpen`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000ad00`
- `0x14000f124`

## pseudocode

```c
__int64 __fastcall VfsPreNetworkQueryOpen(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 32);
  if ( (unsigned __int8)VfsDecodeFileObject(v2, 0, 0) )
    return 3;
  else
    return *(_QWORD *)(v2 + 24) != 0 ? 1 : 3;
}

```

## disassembly

```asm
0x14000ad00  push    rbx
0x14000ad02  sub     rsp, 20h
0x14000ad06  mov     rbx, [rdx+20h]
0x14000ad0a  xor     r8d, r8d
0x14000ad0d  mov     rcx, rbx
0x14000ad10  xor     edx, edx
0x14000ad12  call    VfsDecodeFileObject
0x14000ad17  test    al, al
0x14000ad19  jnz     short loc_14000AD2C
0x14000ad1b  mov     rax, [rbx+18h]
0x14000ad1f  neg     rax
0x14000ad22  sbb     eax, eax
0x14000ad24  and     eax, 0FFFFFFFEh
0x14000ad27  add     eax, 3
0x14000ad2a  jmp     short loc_14000AD31
0x14000ad2c  mov     eax, 3
0x14000ad31  add     rsp, 20h
0x14000ad35  pop     rbx
0x14000ad36  retn
```
