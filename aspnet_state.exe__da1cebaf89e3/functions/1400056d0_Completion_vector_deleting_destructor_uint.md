# Completion::`vector deleting destructor'(uint)

- ea: `0x1400056d0`
- end: `0x140005707`
- name: `??_ECompletion@@UEAAPEAXI@Z`
- size: `55`
- prototype: `Completion *__fastcall(Completion *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001390`
- `0x140004fc8`
- `0x1400056d0`

## pseudocode

```c
Completion *__fastcall Completion::`vector deleting destructor'(Completion *this, char a2)
{
  *(_QWORD *)this = &Completion::`vftable';
  if ( (a2 & 1) != 0 )
  {
    if ( (a2 & 4) != 0 )
      __global_delete(this, 0x38u);
    else
      MemFree(this);
  }
  return this;
}

```

## disassembly

```asm
0x1400056d0  push    rbx
0x1400056d2  sub     rsp, 20h
0x1400056d6  lea     rax, ??_7Completion@@6B@; const Completion::`vftable'
0x1400056dd  mov     rbx, rcx
0x1400056e0  mov     [rcx], rax
0x1400056e3  test    dl, 1
0x1400056e6  jz      short loc_1400056FE
0x1400056e8  test    dl, 4
0x1400056eb  jnz     short loc_1400056F4
0x1400056ed  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1400056f2  jmp     short loc_1400056FE
0x1400056f4  mov     edx, 38h ; '8'; unsigned __int64
0x1400056f9  call    ?__global_delete@@YAXPEAX_K@Z; __global_delete(void *,unsigned __int64)
0x1400056fe  mov     rax, rbx
0x140005701  add     rsp, 20h
0x140005705  pop     rbx
0x140005706  retn
```
