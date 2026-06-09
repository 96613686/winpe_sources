# handle_thread::Close(void)

- ea: `0x180006af0`
- end: `0x180006b38`
- name: `?Close@handle_thread@@QEAAXXZ`
- size: `72`
- prototype: `void __fastcall(handle_thread *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180005e08`
- `0x180006150`
- `0x180006b8c`

## callees

- `0x1800019e0`
- `0x180006a60`
- `0x180006af0`

## pseudocode

```c
void __fastcall handle_thread::Close(CThread **this)
{
  CThread *v1; // rbx

  v1 = *this;
  if ( *this )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v1, 0xFFFFFFFF) == 1 )
    {
      CThread::~CThread(v1);
      operator delete(v1);
    }
    *this = 0;
  }
}

```

## disassembly

```asm
0x180006af0  mov     [rsp+arg_8], rbx
0x180006af5  push    rdi
0x180006af6  sub     rsp, 20h
0x180006afa  mov     rbx, [rcx]
0x180006afd  mov     rdi, rcx
0x180006b00  test    rbx, rbx
0x180006b03  jz      short loc_180006B2D
0x180006b05  or      eax, 0FFFFFFFFh
0x180006b08  lock xadd [rbx], eax
0x180006b0c  cmp     eax, 1
0x180006b0f  jnz     short loc_180006B26
0x180006b11  mov     rcx, rbx; this
0x180006b14  call    ??1CThread@@AEAA@XZ; CThread::~CThread(void)
0x180006b19  mov     edx, 80h; unsigned __int64
0x180006b1e  mov     rcx, rbx; void *
0x180006b21  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006b26  mov     qword ptr [rdi], 0
0x180006b2d  mov     rbx, [rsp+28h+arg_8]
0x180006b32  add     rsp, 20h
0x180006b36  pop     rdi
0x180006b37  retn
```
