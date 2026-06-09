# PWGRCore::CPWGRStreamWriter::~CPWGRStreamWriter(void)

- ea: `0x18000a22c`
- end: `0x18000a2ad`
- name: `??1CPWGRStreamWriter@PWGRCore@@UEAA@XZ`
- size: `129`
- prototype: `void __fastcall(PWGRCore::CPWGRStreamWriter *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a390`

## callees

- `0x18000a22c`
- `0x180011010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PWGRCore::CPWGRStreamWriter::~CPWGRStreamWriter(PWGRCore::CPWGRStreamWriter *this)
{
  volatile signed __int32 *v2; // rbx
  __int64 v3; // rcx

  v2 = (volatile signed __int32 *)*((_QWORD *)this + 8);
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  v3 = *((_QWORD *)this + 2);
  if ( v3 )
  {
    *((_QWORD *)this + 2) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  *(_QWORD *)this = &CUnknownBase<IPWGRStreamWriter>::`vftable';
}

```

## disassembly

```asm
0x18000a22c  mov     [rsp+arg_0], rbx
0x18000a231  push    rdi
0x18000a232  sub     rsp, 20h
0x18000a236  mov     rdi, rcx
0x18000a239  mov     rbx, [rcx+40h]
0x18000a23d  test    rbx, rbx
0x18000a240  jz      short loc_18000A27A
0x18000a242  or      eax, 0FFFFFFFFh
0x18000a245  lock xadd [rbx+8], eax
0x18000a24a  cmp     eax, 1
0x18000a24d  jnz     short loc_18000A27A
0x18000a24f  mov     rax, [rbx]
0x18000a252  mov     rcx, rbx
0x18000a255  mov     rax, [rax]
0x18000a258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a25d  or      eax, 0FFFFFFFFh
0x18000a260  lock xadd [rbx+0Ch], eax
0x18000a265  cmp     eax, 1
0x18000a268  jnz     short loc_18000A27A
0x18000a26a  mov     rax, [rbx]
0x18000a26d  mov     rcx, rbx
0x18000a270  mov     rax, [rax+8]
0x18000a274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a279  nop
0x18000a27a  mov     rcx, [rdi+10h]
0x18000a27e  test    rcx, rcx
0x18000a281  jz      short loc_18000A298
0x18000a283  mov     qword ptr [rdi+10h], 0
0x18000a28b  mov     rax, [rcx]
0x18000a28e  mov     rax, [rax+10h]
0x18000a292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a297  nop
0x18000a298  lea     rax, ??_7?$CUnknownBase@UIPWGRStreamWriter@@@@6B@; const CUnknownBase<IPWGRStreamWriter>::`vftable'
0x18000a29f  mov     [rdi], rax
0x18000a2a2  mov     rbx, [rsp+28h+arg_0]
0x18000a2a7  add     rsp, 20h
0x18000a2ab  pop     rdi
0x18000a2ac  retn
```
