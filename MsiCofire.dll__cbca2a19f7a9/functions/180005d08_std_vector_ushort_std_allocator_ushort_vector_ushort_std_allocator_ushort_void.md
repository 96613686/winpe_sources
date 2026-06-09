# std::vector<ushort *,std::allocator<ushort *>>::~vector<ushort *,std::allocator<ushort *>>(void)

- ea: `0x180005d08`
- end: `0x180005d3c`
- name: `??1?$vector@PEAGV?$allocator@PEAG@std@@@std@@QEAA@XZ`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180007482`
- `0x1800074db`

## callees

- `0x180005d08`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005d19`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005d19`

## pseudocode

```c
void __fastcall std::vector<unsigned short *>::~vector<unsigned short *>(__int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    operator delete(v2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x180005d08  push    rbx
0x180005d0a  sub     rsp, 20h
0x180005d0e  mov     rbx, rcx
0x180005d11  mov     rcx, [rcx]
0x180005d14  test    rcx, rcx
0x180005d17  jz      short loc_180005D36
0x180005d19  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005d1f  mov     qword ptr [rbx], 0
0x180005d26  mov     qword ptr [rbx+8], 0
0x180005d2e  mov     qword ptr [rbx+10h], 0
0x180005d36  add     rsp, 20h
0x180005d3a  pop     rbx
0x180005d3b  retn
```
