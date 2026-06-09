# BufferWriter::CBufferWriter::IOCompleted(unsigned __int64,ulong,_OVERLAPPED *)

- ea: `0x180015130`
- end: `0x18001518a`
- name: `?IOCompleted@CBufferWriter@BufferWriter@@MEAAX_KKPEAU_OVERLAPPED@@@Z`
- size: `90`
- prototype: `void __fastcall(BufferWriter::CBufferWriter *__hidden this, unsigned __int64, unsigned int, struct _OVERLAPPED *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001048`
- `0x180015130`
- `0x180034010`

## pseudocode

```c
void __fastcall BufferWriter::CBufferWriter::IOCompleted(
        BufferWriter::CBufferWriter *this,
        __int64 a2,
        __int64 a3,
        struct _OVERLAPPED *a4)
{
  PVOID *p_Pointer; // rbx
  void (__fastcall ***v5)(_QWORD, __int64); // rcx

  p_Pointer = &a4[-1].Pointer;
  if ( a4 != (struct _OVERLAPPED *)16 )
  {
    v5 = (void (__fastcall ***)(_QWORD, __int64))*p_Pointer;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)*p_Pointer + 34, 0xFFFFFFFF) == 1 )
    {
      if ( v5 )
        (**v5)(v5, 1);
    }
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)p_Pointer[1] + 16LL))(p_Pointer[1]);
    operator delete(p_Pointer);
  }
}

```

## disassembly

```asm
0x180015130  push    rbx
0x180015132  sub     rsp, 20h
0x180015136  lea     rbx, [r9-10h]
0x18001513a  test    rbx, rbx
0x18001513d  jz      short loc_180015184
0x18001513f  mov     rcx, [rbx]
0x180015142  or      eax, 0FFFFFFFFh
0x180015145  lock xadd [rcx+88h], eax
0x18001514d  cmp     eax, 1
0x180015150  jnz     short loc_180015167
0x180015152  test    rcx, rcx
0x180015155  jz      short loc_180015167
0x180015157  mov     rax, [rcx]
0x18001515a  mov     edx, 1
0x18001515f  mov     rax, [rax]
0x180015162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015167  mov     rcx, [rbx+8]
0x18001516b  mov     rax, [rcx]
0x18001516e  mov     rax, [rax+10h]
0x180015172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015177  mov     edx, 30h ; '0'; unsigned __int64
0x18001517c  mov     rcx, rbx; void *
0x18001517f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015184  add     rsp, 20h
0x180015188  pop     rbx
0x180015189  retn
```
