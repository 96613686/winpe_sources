# CBindingList::Delete(CBinding *)

- ea: `0x1800248b0`
- end: `0x18002491a`
- name: `?Delete@CBindingList@@AEAAXPEAVCBinding@@@Z`
- size: `106`
- prototype: `void __fastcall(CBindingList *this, struct CBinding *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180024748`
- `0x1800247a8`
- `0x180024920`

## callees

- `0x1800016f4`
- `0x18001b1a0`
- `0x180024700`
- `0x1800248b0`

## pseudocode

```c
void __fastcall CBindingList::Delete(CBindingList *this, struct CBinding *a2)
{
  if ( a2 )
  {
    if ( gDebug )
      _DebugMsg(2, 0xC83u, *(_QWORD *)a2);
    *(_QWORD *)(*((_QWORD *)a2 + 6) + 8LL) = *((_QWORD *)a2 + 7);
    **((_QWORD **)a2 + 7) = *((_QWORD *)a2 + 6);
    CBinding::~CBinding(a2);
    operator delete(a2);
    --*((_DWORD *)this + 18);
  }
}

```

## disassembly

```asm
0x1800248b0  test    rdx, rdx
0x1800248b3  jz      short locret_180024919
0x1800248b5  mov     [rsp+arg_0], rbx
0x1800248ba  push    rdi
0x1800248bb  sub     rsp, 20h
0x1800248bf  cmp     cs:?gDebug@@3KA, 0; ulong gDebug
0x1800248c6  mov     rbx, rdx
0x1800248c9  mov     rdi, rcx
0x1800248cc  jz      short loc_1800248E0
0x1800248ce  mov     r8, [rdx]
0x1800248d1  mov     ecx, 2; unsigned int
0x1800248d6  mov     edx, 0C83h; unsigned int
0x1800248db  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800248e0  mov     rcx, [rbx+30h]
0x1800248e4  mov     rax, [rbx+38h]
0x1800248e8  mov     [rcx+8], rax
0x1800248ec  mov     rcx, [rbx+38h]
0x1800248f0  mov     rax, [rbx+30h]
0x1800248f4  mov     [rcx], rax
0x1800248f7  mov     rcx, rbx; this
0x1800248fa  call    ??1CBinding@@QEAA@XZ; CBinding::~CBinding(void)
0x1800248ff  mov     edx, 40h ; '@'; unsigned __int64
0x180024904  mov     rcx, rbx; void *
0x180024907  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002490c  dec     dword ptr [rdi+48h]
0x18002490f  mov     rbx, [rsp+28h+arg_0]
0x180024914  add     rsp, 20h
0x180024918  pop     rdi
0x180024919  retn
```
