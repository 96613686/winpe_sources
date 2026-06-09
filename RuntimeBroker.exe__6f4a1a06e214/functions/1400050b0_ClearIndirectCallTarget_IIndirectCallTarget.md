# ClearIndirectCallTarget(IIndirectCallTarget *)

- ea: `0x1400050b0`
- end: `0x1400050fd`
- name: `?ClearIndirectCallTarget@@YAXPEAUIIndirectCallTarget@@@Z`
- size: `77`
- prototype: `void __fastcall(struct IIndirectCallTarget *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002260`

## callees

- `0x1400050b0`
- `0x14000cdc8`
- `0x140010010`

## string_xrefs

- `0x1400050e7`: `onecore\com\combase\inc\IndirectCallTarget.hpp`

## pseudocode

```c
void __fastcall ClearIndirectCallTarget(struct IIndirectCallTarget *a1)
{
  int v2; // eax
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a1 )
  {
    v2 = (*(__int64 (__fastcall **)(struct IIndirectCallTarget *))(*(_QWORD *)a1 + 40LL))(a1);
    if ( v2 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA,
        (unsigned int)"onecore\\com\\combase\\inc\\IndirectCallTarget.hpp",
        (const char *)(unsigned int)v2,
        v3);
    (*(void (__fastcall **)(struct IIndirectCallTarget *))(*(_QWORD *)a1 + 16LL))(a1);
  }
}

```

## disassembly

```asm
0x1400050b0  test    rcx, rcx
0x1400050b3  jnz     short loc_1400050B6
0x1400050b5  retn
0x1400050b6  push    rbx; int
0x1400050b7  sub     rsp, 20h
0x1400050bb  mov     rax, [rcx]
0x1400050be  mov     rbx, rcx
0x1400050c1  mov     rax, [rax+28h]
0x1400050c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400050ca  test    eax, eax
0x1400050cc  js      short loc_1400050E2
0x1400050ce  mov     rax, [rbx]
0x1400050d1  mov     rcx, rbx
0x1400050d4  mov     rax, [rax+10h]
0x1400050d8  add     rsp, 20h
0x1400050dc  pop     rbx
0x1400050dd  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1400050e2  mov     rcx, [rsp+28h]; this
0x1400050e7  lea     r8, aOnecoreComComb; "onecore\\com\\combase\\inc\\IndirectCal"...
0x1400050ee  mov     r9d, eax; char *
0x1400050f1  mov     edx, 0Ah; void *
0x1400050f6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400050fb  jmp     short loc_1400050CE
```
