# CPimcContext::ShutdownSharedMemoryCommunications(void)

- ea: `0x180006b10`
- end: `0x180006ba1`
- name: `?ShutdownSharedMemoryCommunications@CPimcContext@@QEAAXXZ`
- size: `145`
- prototype: `void __fastcall(CPimcContext *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006a28`
- `0x180009f28`

## callees

- `0x180001360`
- `0x180006b10`
- `0x18000ce0c`

## import_xrefs

- `KERNEL32!UnmapViewOfFile` at `0x180006b22`
- `KERNEL32!UnmapViewOfFile` at `0x180006b36`
- `KERNEL32!UnmapViewOfFile` at `0x180006b22`
- `KERNEL32!UnmapViewOfFile` at `0x180006b36`

## pseudocode

```c
void __fastcall CPimcContext::ShutdownSharedMemoryCommunications(CPimcContext *this)
{
  const void *v2; // rcx
  const void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  v2 = (const void *)*((_QWORD *)this + 11);
  if ( v2 )
  {
    UnmapViewOfFile(v2);
    *((_QWORD *)this + 11) = 0;
  }
  v3 = (const void *)*((_QWORD *)this + 12);
  if ( v3 )
  {
    UnmapViewOfFile(v3);
    *((_QWORD *)this + 12) = 0;
  }
  SafeCloseHandle((void **)this + 7);
  SafeCloseHandle((void **)this + 8);
  SafeCloseHandle((void **)this + 9);
  SafeCloseHandle((void **)this + 10);
  v4 = (void *)*((_QWORD *)this + 15);
  if ( v4 )
  {
    operator delete(v4);
    *((_QWORD *)this + 15) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 17);
  if ( v5 )
  {
    operator delete(v5);
    *((_QWORD *)this + 17) = 0;
  }
}

```

## disassembly

```asm
0x180006b10  push    rbx
0x180006b12  sub     rsp, 20h
0x180006b16  mov     rbx, rcx
0x180006b19  mov     rcx, [rcx+58h]; lpBaseAddress
0x180006b1d  test    rcx, rcx
0x180006b20  jz      short loc_180006B2D
0x180006b22  call    cs:__imp_UnmapViewOfFile
0x180006b28  and     qword ptr [rbx+58h], 0
0x180006b2d  mov     rcx, [rbx+60h]; lpBaseAddress
0x180006b31  test    rcx, rcx
0x180006b34  jz      short loc_180006B41
0x180006b36  call    cs:__imp_UnmapViewOfFile
0x180006b3c  and     qword ptr [rbx+60h], 0
0x180006b41  lea     rcx, [rbx+38h]; void **
0x180006b45  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x180006b4a  lea     rcx, [rbx+40h]; void **
0x180006b4e  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x180006b53  lea     rcx, [rbx+48h]; void **
0x180006b57  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x180006b5c  lea     rcx, [rbx+50h]; void **
0x180006b60  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x180006b65  mov     rcx, [rbx+78h]; Block
0x180006b69  test    rcx, rcx
0x180006b6c  jz      short loc_180006B7D
0x180006b6e  mov     edx, 8
0x180006b73  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006b78  and     qword ptr [rbx+78h], 0
0x180006b7d  mov     rcx, [rbx+88h]; Block
0x180006b84  test    rcx, rcx
0x180006b87  jz      short loc_180006B9B
0x180006b89  mov     edx, 1
0x180006b8e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006b93  and     qword ptr [rbx+88h], 0
0x180006b9b  add     rsp, 20h
0x180006b9f  pop     rbx
0x180006ba0  retn
```
