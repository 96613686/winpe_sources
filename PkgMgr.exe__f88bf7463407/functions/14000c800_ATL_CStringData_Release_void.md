# ATL::CStringData::Release(void)

- ea: `0x14000c800`
- end: `0x14000c828`
- name: `?Release@CStringData@ATL@@QEAAXXZ`
- size: `40`
- prototype: `void __fastcall(ATL::CStringData *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x14000abb0`
- `0x14000baa4`
- `0x14000bbe4`
- `0x14000cbd0`
- `0x14000dc5c`

## callees

- `0x14000c800`
- `0x14002a010`

## pseudocode

```c
void __fastcall ATL::CStringData::Release(ATL::CStringData *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD, ATL::CStringData *))(**(_QWORD **)this + 8LL))(*(_QWORD *)this, this);
}

```

## disassembly

```asm
0x14000c800  sub     rsp, 28h
0x14000c804  mov     rdx, rcx
0x14000c807  or      eax, 0FFFFFFFFh
0x14000c80a  lock xadd [rcx+10h], eax
0x14000c80f  sub     eax, 1
0x14000c812  jg      short loc_14000C823
0x14000c814  mov     rcx, [rcx]
0x14000c817  mov     rax, [rcx]
0x14000c81a  mov     rax, [rax+8]
0x14000c81e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c823  add     rsp, 28h
0x14000c827  retn
```
