# std::_Ref_count_base::_Decref(void)

- ea: `0x18000798c`
- end: `0x1800079cf`
- name: `?_Decref@_Ref_count_base@std@@QEAAXXZ`
- size: `67`
- prototype: `void __fastcall(std::_Ref_count_base *__hidden this)`
- caller_count: `24`
- callee_count: `2`
- tags: ``

## callers

- `0x180005d70`
- `0x1800062c8`
- `0x180006448`
- `0x1800066cc`
- `0x180006ac0`
- `0x180006bb0`
- `0x1800070f0`
- `0x1800071f0`
- `0x1800072d0`
- `0x180008810`
- `0x180008908`
- `0x18000894c`
- `0x180008990`
- `0x180008c1c`
- `0x180008d9c`
- `0x18000a758`
- `0x18000ab5c`
- `0x18000b278`
- `0x18000b34c`
- `0x18000b7d4`
- `0x18000b990`
- `0x18000bafc`
- `0x18000dfe8`
- `0x18000e0e4`

## callees

- `0x18000798c`
- `0x180010010`

## pseudocode

```c
void __fastcall std::_Ref_count_base::_Decref(std::_Ref_count_base *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(std::_Ref_count_base *))this)(this);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)this + 8LL))(this);
  }
}

```

## disassembly

```asm
0x18000798c  push    rbx
0x18000798e  sub     rsp, 20h
0x180007992  mov     rbx, rcx
0x180007995  or      eax, 0FFFFFFFFh
0x180007998  lock xadd [rcx+8], eax
0x18000799d  cmp     eax, 1
0x1800079a0  jnz     short loc_1800079C9
0x1800079a2  mov     rax, [rcx]
0x1800079a5  mov     rax, [rax]
0x1800079a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079ad  or      eax, 0FFFFFFFFh
0x1800079b0  lock xadd [rbx+0Ch], eax
0x1800079b5  cmp     eax, 1
0x1800079b8  jnz     short loc_1800079C9
0x1800079ba  mov     rax, [rbx]
0x1800079bd  mov     rcx, rbx
0x1800079c0  mov     rax, [rax+8]
0x1800079c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079c9  add     rsp, 20h
0x1800079cd  pop     rbx
0x1800079ce  retn
```
