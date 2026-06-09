# CThread::Release(void)

- ea: `0x180006d18`
- end: `0x180006d55`
- name: `?Release@CThread@@AEBAJXZ`
- size: `61`
- prototype: `__int64 __fastcall(CThread *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006c3c`

## callees

- `0x1800019e0`
- `0x180006a60`
- `0x180006d18`

## pseudocode

```c
__int64 __fastcall CThread::Release(CThread *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this);
  if ( !v2 && this )
  {
    CThread::~CThread(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x180006d18  mov     [rsp+arg_0], rbx
0x180006d1d  push    rdi
0x180006d1e  sub     rsp, 20h
0x180006d22  mov     rbx, rcx
0x180006d25  or      edi, 0FFFFFFFFh
0x180006d28  lock xadd [rcx], edi
0x180006d2c  sub     edi, 1
0x180006d2f  jnz     short loc_180006D48
0x180006d31  test    rcx, rcx
0x180006d34  jz      short loc_180006D48
0x180006d36  call    ??1CThread@@AEAA@XZ; CThread::~CThread(void)
0x180006d3b  mov     edx, 80h; unsigned __int64
0x180006d40  mov     rcx, rbx; void *
0x180006d43  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006d48  mov     rbx, [rsp+28h+arg_0]
0x180006d4d  mov     eax, edi
0x180006d4f  add     rsp, 20h
0x180006d53  pop     rdi
0x180006d54  retn
```
