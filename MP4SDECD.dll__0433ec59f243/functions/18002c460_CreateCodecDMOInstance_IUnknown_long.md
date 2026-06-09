# CreateCodecDMOInstance(IUnknown *,long *)

- ea: `0x18002c460`
- end: `0x18002c4ab`
- name: `?CreateCodecDMOInstance@@YAPEAVCComBase@@PEAUIUnknown@@PEAJ@Z`
- size: `75`
- prototype: `struct CComBase *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800274ac`
- `0x18002a670`
- `0x18002c460`

## pseudocode

```c
struct CComBase *__fastcall CreateCodecDMOInstance(struct IUnknown *a1, int *a2)
{
  CWMVideoDecMediaObject *v4; // rax

  v4 = (CWMVideoDecMediaObject *)operator new(0x758u);
  if ( v4 )
    v4 = CWMVideoDecMediaObject::CWMVideoDecMediaObject(v4, a1, a2, 0);
  return (struct CComBase *)(((unsigned __int64)v4 + 344) & -(__int64)(v4 != 0));
}

```

## disassembly

```asm
0x18002c460  mov     [rsp+arg_0], rbx
0x18002c465  push    rdi
0x18002c466  sub     rsp, 20h
0x18002c46a  mov     rdi, rcx
0x18002c46d  mov     rbx, rdx
0x18002c470  mov     ecx, 758h; Size
0x18002c475  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c47a  test    rax, rax
0x18002c47d  jz      short loc_18002C490
0x18002c47f  xor     r9d, r9d; int
0x18002c482  mov     r8, rbx; int *
0x18002c485  mov     rdx, rdi; struct IUnknown *
0x18002c488  mov     rcx, rax; this
0x18002c48b  call    ??0CWMVideoDecMediaObject@@QEAA@PEAUIUnknown@@PEAJJ@Z; CWMVideoDecMediaObject::CWMVideoDecMediaObject(IUnknown *,long *,long)
0x18002c490  mov     rbx, [rsp+28h+arg_0]
0x18002c495  lea     rcx, [rax+158h]
0x18002c49c  neg     rax
0x18002c49f  sbb     rax, rax
0x18002c4a2  and     rax, rcx
0x18002c4a5  add     rsp, 20h
0x18002c4a9  pop     rdi
0x18002c4aa  retn
```
