# CreateResamplerInstance(IUnknown *,long *)

- ea: `0x180009b00`
- end: `0x180009b3f`
- name: `?CreateResamplerInstance@@YAPEAVCComBase@@PEAUIUnknown@@PEAJ@Z`
- size: `63`
- prototype: `struct CComBase *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180009b00`
- `0x180009f08`
- `0x18000abb4`

## pseudocode

```c
struct CComBase *__fastcall CreateResamplerInstance(struct IUnknown *a1, int *a2)
{
  struct CComBase *result; // rax

  result = (struct CComBase *)operator new(0x2F8u, (const struct std::nothrow_t *)&std::nothrow);
  if ( result )
    return CWMResampleMediaObject::CWMResampleMediaObject(result, a1, a2);
  return result;
}

```

## disassembly

```asm
0x180009b00  mov     [rsp+arg_0], rbx
0x180009b05  push    rdi
0x180009b06  sub     rsp, 20h
0x180009b0a  mov     rbx, rdx
0x180009b0d  mov     rdi, rcx
0x180009b10  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009b17  mov     ecx, 2F8h; unsigned __int64
0x180009b1c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009b21  test    rax, rax
0x180009b24  jz      short loc_180009B34
0x180009b26  mov     r8, rbx; int *
0x180009b29  mov     rdx, rdi; struct IUnknown *
0x180009b2c  mov     rcx, rax; this
0x180009b2f  call    ??0CWMResampleMediaObject@@QEAA@PEAUIUnknown@@PEAJ@Z; CWMResampleMediaObject::CWMResampleMediaObject(IUnknown *,long *)
0x180009b34  mov     rbx, [rsp+28h+arg_0]
0x180009b39  add     rsp, 20h
0x180009b3d  pop     rdi
0x180009b3e  retn
```
