# CreateCodecMFTInstance(IUnknown *,long *)

- ea: `0x180028030`
- end: `0x18002807e`
- name: `?CreateCodecMFTInstance@@YAPEAVCComBase@@PEAUIUnknown@@PEAJ@Z`
- size: `78`
- prototype: `struct CComBase *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800274ac`
- `0x180028030`
- `0x18002a670`

## pseudocode

```c
struct CComBase *__fastcall CreateCodecMFTInstance(struct IUnknown *a1, int *a2)
{
  CWMVideoDecMediaObject *v4; // rax

  v4 = (CWMVideoDecMediaObject *)operator new(0x758u);
  if ( v4 )
    v4 = CWMVideoDecMediaObject::CWMVideoDecMediaObject(v4, a1, a2, 1);
  return (struct CComBase *)(((unsigned __int64)v4 + 344) & -(__int64)(v4 != 0));
}

```

## disassembly

```asm
0x180028030  mov     [rsp+arg_0], rbx
0x180028035  push    rdi
0x180028036  sub     rsp, 20h
0x18002803a  mov     rdi, rcx
0x18002803d  mov     rbx, rdx
0x180028040  mov     ecx, 758h; Size
0x180028045  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002804a  test    rax, rax
0x18002804d  jz      short loc_180028063
0x18002804f  mov     r9d, 1; int
0x180028055  mov     r8, rbx; int *
0x180028058  mov     rdx, rdi; struct IUnknown *
0x18002805b  mov     rcx, rax; this
0x18002805e  call    ??0CWMVideoDecMediaObject@@QEAA@PEAUIUnknown@@PEAJJ@Z; CWMVideoDecMediaObject::CWMVideoDecMediaObject(IUnknown *,long *,long)
0x180028063  mov     rbx, [rsp+28h+arg_0]
0x180028068  lea     rcx, [rax+158h]
0x18002806f  neg     rax
0x180028072  sbb     rax, rax
0x180028075  and     rax, rcx
0x180028078  add     rsp, 20h
0x18002807c  pop     rdi
0x18002807d  retn
```
