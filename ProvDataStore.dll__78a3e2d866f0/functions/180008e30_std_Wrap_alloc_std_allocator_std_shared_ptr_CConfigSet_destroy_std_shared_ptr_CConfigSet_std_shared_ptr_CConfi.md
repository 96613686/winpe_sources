# std::_Wrap_alloc<std::allocator<std::shared_ptr<CConfigSet>>>::destroy<std::shared_ptr<CConfigSet>>(std::shared_ptr<CConfigSet> *)

- ea: `0x180008e30`
- end: `0x180008e7d`
- name: `??$destroy@V?$shared_ptr@VCConfigSet@@@std@@@?$_Wrap_alloc@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@std@@@std@@QEAAXPEAV?$shared_ptr@VCConfigSet@@@1@@Z`
- size: `77`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001178f`

## callees

- `0x180008e30`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall std::_Wrap_alloc<std::allocator<std::shared_ptr<CConfigSet>>>::destroy<std::shared_ptr<CConfigSet>>(
        __int64 a1,
        __int64 a2)
{
  volatile signed __int32 *v2; // rbx
  __int64 result; // rax

  v2 = *(volatile signed __int32 **)(a2 + 8);
  if ( v2 )
  {
    result = (unsigned int)_InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      result = (unsigned int)_InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF);
      if ( (_DWORD)result == 1 )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008e30  push    rbx
0x180008e32  sub     rsp, 20h
0x180008e36  mov     rbx, [rdx+8]
0x180008e3a  test    rbx, rbx
0x180008e3d  jz      short loc_180008E77
0x180008e3f  or      eax, 0FFFFFFFFh
0x180008e42  lock xadd [rbx+8], eax
0x180008e47  cmp     eax, 1
0x180008e4a  jnz     short loc_180008E77
0x180008e4c  mov     rax, [rbx]
0x180008e4f  mov     rcx, rbx
0x180008e52  mov     rax, [rax]
0x180008e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e5a  or      eax, 0FFFFFFFFh
0x180008e5d  lock xadd [rbx+0Ch], eax
0x180008e62  cmp     eax, 1
0x180008e65  jnz     short loc_180008E77
0x180008e67  mov     rax, [rbx]
0x180008e6a  mov     rcx, rbx
0x180008e6d  mov     rax, [rax+8]
0x180008e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e76  nop
0x180008e77  add     rsp, 20h
0x180008e7b  pop     rbx
0x180008e7c  retn
```
