# CommonUtil::MpNewBuffer<uchar>(uchar * *,unsigned __int64)

- ea: `0x140021e54`
- end: `0x140021e84`
- name: `??$MpNewBuffer@E@CommonUtil@@YAJPEAPEAE_K@Z`
- size: `48`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000355c`
- `0x140022568`
- `0x14002476c`

## callees

- `0x140006170`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpNewBuffer<unsigned char>(_QWORD *a1, unsigned __int64 a2)
{
  void *v3; // rax

  v3 = operator new[](a2, (const struct std::nothrow_t *)&std::nothrow);
  *a1 = v3;
  return v3 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x140021e54  push    rbx
0x140021e56  sub     rsp, 20h
0x140021e5a  mov     rax, rdx
0x140021e5d  mov     rbx, rcx
0x140021e60  mov     rcx, rax; unsigned __int64
0x140021e63  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140021e6a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140021e6f  mov     [rbx], rax
0x140021e72  neg     rax
0x140021e75  sbb     eax, eax
0x140021e77  not     eax
0x140021e79  and     eax, 8007000Eh
0x140021e7e  add     rsp, 20h
0x140021e82  pop     rbx
0x140021e83  retn
```
