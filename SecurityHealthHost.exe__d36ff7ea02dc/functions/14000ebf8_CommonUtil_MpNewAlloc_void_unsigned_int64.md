# CommonUtil::MpNewAlloc(void * *,unsigned __int64)

- ea: `0x14000ebf8`
- end: `0x14000ec28`
- name: `?MpNewAlloc@CommonUtil@@YAJPEAPEAX_K@Z`
- size: `48`
- prototype: `__int64 __fastcall(CommonUtil *this, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000c110`

## callees

- `0x14000190c`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpNewAlloc(CommonUtil *this, void **a2)
{
  void *v3; // rax

  v3 = operator new((size_t)a2, (const struct std::nothrow_t *)std::nothrow);
  *(_QWORD *)this = v3;
  return v3 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x14000ebf8  push    rbx
0x14000ebfa  sub     rsp, 20h
0x14000ebfe  mov     rax, rdx
0x14000ec01  mov     rbx, rcx
0x14000ec04  mov     rcx, rax; unsigned __int64
0x14000ec07  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000ec0e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000ec13  mov     [rbx], rax
0x14000ec16  neg     rax
0x14000ec19  sbb     eax, eax
0x14000ec1b  not     eax
0x14000ec1d  and     eax, 8007000Eh
0x14000ec22  add     rsp, 20h
0x14000ec26  pop     rbx
0x14000ec27  retn
```
