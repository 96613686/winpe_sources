# std::shared_ptr<CConfigSet>::~shared_ptr<CConfigSet>(void)

- ea: `0x180008ebc`
- end: `0x180008f09`
- name: `??1?$shared_ptr@VCConfigSet@@@std@@QEAA@XZ`
- size: `77`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180011759`
- `0x18001176b`
- `0x18001177d`
- `0x180011aae`
- `0x180011ac0`
- `0x180011c85`

## callees

- `0x180008ebc`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall std::shared_ptr<CConfigSet>::~shared_ptr<CConfigSet>(__int64 a1)
{
  volatile signed __int32 *v1; // rbx
  __int64 result; // rax

  v1 = *(volatile signed __int32 **)(a1 + 8);
  if ( v1 )
  {
    result = (unsigned int)_InterlockedExchangeAdd(v1 + 2, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v1)(v1);
      result = (unsigned int)_InterlockedExchangeAdd(v1 + 3, 0xFFFFFFFF);
      if ( (_DWORD)result == 1 )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v1 + 8LL))(v1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008ebc  push    rbx
0x180008ebe  sub     rsp, 20h
0x180008ec2  mov     rbx, [rcx+8]
0x180008ec6  test    rbx, rbx
0x180008ec9  jz      short loc_180008F03
0x180008ecb  or      eax, 0FFFFFFFFh
0x180008ece  lock xadd [rbx+8], eax
0x180008ed3  cmp     eax, 1
0x180008ed6  jnz     short loc_180008F03
0x180008ed8  mov     rax, [rbx]
0x180008edb  mov     rcx, rbx
0x180008ede  mov     rax, [rax]
0x180008ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ee6  or      eax, 0FFFFFFFFh
0x180008ee9  lock xadd [rbx+0Ch], eax
0x180008eee  cmp     eax, 1
0x180008ef1  jnz     short loc_180008F03
0x180008ef3  mov     rax, [rbx]
0x180008ef6  mov     rcx, rbx
0x180008ef9  mov     rax, [rax+8]
0x180008efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f02  nop
0x180008f03  add     rsp, 20h
0x180008f07  pop     rbx
0x180008f08  retn
```
