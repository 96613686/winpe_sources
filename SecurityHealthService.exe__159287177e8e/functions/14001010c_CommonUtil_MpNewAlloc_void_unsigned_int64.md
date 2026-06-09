# CommonUtil::MpNewAlloc(void * *,unsigned __int64)

- ea: `0x14001010c`
- end: `0x14001013c`
- name: `?MpNewAlloc@CommonUtil@@YAJPEAPEAX_K@Z`
- size: `48`
- prototype: `__int64 __fastcall(CommonUtil *this, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140007248`

## callees

- `0x14000162c`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpNewAlloc(CommonUtil *this, void **a2)
{
  void *v3; // rax

  v3 = operator new((size_t)a2, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)this = v3;
  return v3 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x14001010c  push    rbx
0x14001010e  sub     rsp, 20h
0x140010112  mov     rax, rdx
0x140010115  mov     rbx, rcx
0x140010118  mov     rcx, rax; unsigned __int64
0x14001011b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140010122  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140010127  mov     [rbx], rax
0x14001012a  neg     rax
0x14001012d  sbb     eax, eax
0x14001012f  not     eax
0x140010131  and     eax, 8007000Eh
0x140010136  add     rsp, 20h
0x14001013a  pop     rbx
0x14001013b  retn
```
