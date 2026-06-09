# Mso::Logging::CompositeStructuredTrace::Accept(Mso::Logging::IStructuredTracingVisitor &)

- ea: `0x1400048b0`
- end: `0x1400048fb`
- name: `?Accept@CompositeStructuredTrace@Logging@Mso@@UEBAXAEAUIStructuredTracingVisitor@23@@Z`
- size: `75`
- prototype: `void __fastcall(Mso::Logging::CompositeStructuredTrace *__hidden this, struct Mso::Logging::IStructuredTracingVisitor *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001020`
- `0x1400048b0`

## pseudocode

```c
void __fastcall Mso::Logging::CompositeStructuredTrace::Accept(
        Mso::Logging::CompositeStructuredTrace *this,
        struct Mso::Logging::IStructuredTracingVisitor *a2)
{
  _QWORD *i; // rbx

  for ( i = (_QWORD *)*((_QWORD *)this + 1); i != *((_QWORD **)this + 2); ++i )
    (**(void (__fastcall ***)(_QWORD, struct Mso::Logging::IStructuredTracingVisitor *))*i)(*i, a2);
}

```

## disassembly

```asm
0x1400048b0  mov     [rsp+arg_0], rbx
0x1400048b5  mov     [rsp+arg_8], rsi
0x1400048ba  push    rdi
0x1400048bb  sub     rsp, 20h
0x1400048bf  mov     rbx, [rcx+8]
0x1400048c3  mov     rsi, rdx
0x1400048c6  mov     rdi, rcx
0x1400048c9  cmp     rbx, [rcx+10h]
0x1400048cd  jz      short loc_1400048EB
0x1400048cf  mov     rcx, [rbx]
0x1400048d2  mov     rdx, rsi
0x1400048d5  mov     rax, [rcx]
0x1400048d8  mov     rax, [rax]
0x1400048db  call    cs:__guard_dispatch_icall_fptr
0x1400048e1  add     rbx, 8
0x1400048e5  cmp     rbx, [rdi+10h]
0x1400048e9  jnz     short loc_1400048CF
0x1400048eb  mov     rbx, [rsp+28h+arg_0]
0x1400048f0  mov     rsi, [rsp+28h+arg_8]
0x1400048f5  add     rsp, 20h
0x1400048f9  pop     rdi
0x1400048fa  retn
```
