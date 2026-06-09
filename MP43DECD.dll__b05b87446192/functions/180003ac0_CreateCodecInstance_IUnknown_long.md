# CreateCodecInstance(IUnknown *,long *)

- ea: `0x180003ac0`
- end: `0x180003b08`
- name: `?CreateCodecInstance@@YAPEAVCComBase@@PEAUIUnknown@@PEAJ@Z`
- size: `72`
- prototype: `struct CComBase *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000142c`
- `0x1800022e4`
- `0x180003ac0`

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
0x180003ac0  mov     [rsp+arg_0], rbx
0x180003ac5  push    rdi
0x180003ac6  sub     rsp, 20h
0x180003aca  mov     rdi, rcx
0x180003acd  mov     rbx, rdx
0x180003ad0  mov     ecx, 780h; Size
0x180003ad5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003ada  test    rax, rax
0x180003add  jz      short loc_180003AED
0x180003adf  mov     r8, rbx; int *
0x180003ae2  mov     rdx, rdi; struct IUnknown *
0x180003ae5  mov     rcx, rax; this
0x180003ae8  call    ??0CWMVideoDecMediaObject@@QEAA@PEAUIUnknown@@PEAJ@Z; CWMVideoDecMediaObject::CWMVideoDecMediaObject(IUnknown *,long *)
0x180003aed  mov     rbx, [rsp+28h+arg_0]
0x180003af2  lea     rcx, [rax+148h]
0x180003af9  neg     rax
0x180003afc  sbb     rax, rax
0x180003aff  and     rax, rcx
0x180003b02  add     rsp, 20h
0x180003b06  pop     rdi
0x180003b07  retn
```
