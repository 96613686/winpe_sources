# CreateCodecInstance(IUnknown *,long *)

- ea: `0x180003b80`
- end: `0x180003bc8`
- name: `?CreateCodecInstance@@YAPEAVCComBase@@PEAUIUnknown@@PEAJ@Z`
- size: `72`
- prototype: `struct CComBase *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000145c`
- `0x1800023a0`
- `0x180003b80`

## pseudocode

```c
struct CComBase *__fastcall CreateCodecInstance(struct IUnknown *a1, int *a2)
{
  CWMVideoDecMediaObject *v4; // rax

  v4 = (CWMVideoDecMediaObject *)operator new(0x780u);
  if ( v4 )
    v4 = CWMVideoDecMediaObject::CWMVideoDecMediaObject(v4, a1, a2);
  return (struct CComBase *)(((unsigned __int64)v4 + 328) & -(__int64)(v4 != 0));
}

```

## disassembly

```asm
0x180003b80  mov     [rsp+arg_0], rbx
0x180003b85  push    rdi
0x180003b86  sub     rsp, 20h
0x180003b8a  mov     rdi, rcx
0x180003b8d  mov     rbx, rdx
0x180003b90  mov     ecx, 780h; Size
0x180003b95  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003b9a  test    rax, rax
0x180003b9d  jz      short loc_180003BAD
0x180003b9f  mov     r8, rbx; int *
0x180003ba2  mov     rdx, rdi; struct IUnknown *
0x180003ba5  mov     rcx, rax; this
0x180003ba8  call    ??0CWMVideoDecMediaObject@@QEAA@PEAUIUnknown@@PEAJ@Z; CWMVideoDecMediaObject::CWMVideoDecMediaObject(IUnknown *,long *)
0x180003bad  mov     rbx, [rsp+28h+arg_0]
0x180003bb2  lea     rcx, [rax+148h]
0x180003bb9  neg     rax
0x180003bbc  sbb     rax, rax
0x180003bbf  and     rax, rcx
0x180003bc2  add     rsp, 20h
0x180003bc6  pop     rdi
0x180003bc7  retn
```
