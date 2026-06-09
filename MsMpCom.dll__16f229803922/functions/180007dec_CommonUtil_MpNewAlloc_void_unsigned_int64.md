# CommonUtil::MpNewAlloc(void * *,unsigned __int64)

- ea: `0x180007dec`
- end: `0x180007e1c`
- name: `?MpNewAlloc@CommonUtil@@YAJPEAPEAX_K@Z`
- size: `48`
- prototype: `int(CommonUtil *__hidden this, void **, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007fdc`

## callees

- `0x180002188`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpNewAlloc(CommonUtil *this, void **a2)
{
  void *v3; // rax

  v3 = operator new((unsigned __int64)a2, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)this = v3;
  return v3 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x180007dec  push    rbx
0x180007dee  sub     rsp, 20h
0x180007df2  mov     rax, rdx
0x180007df5  mov     rbx, rcx
0x180007df8  mov     rcx, rax; unsigned __int64
0x180007dfb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007e02  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007e07  mov     [rbx], rax
0x180007e0a  neg     rax
0x180007e0d  sbb     eax, eax
0x180007e0f  not     eax
0x180007e11  and     eax, 8007000Eh
0x180007e16  add     rsp, 20h
0x180007e1a  pop     rbx
0x180007e1b  retn
```
