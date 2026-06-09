# Concurrency::task<void>::~task<void>(void)

- ea: `0x140015240`
- end: `0x14001528d`
- name: `??1?$task@X@Concurrency@@QEAA@XZ`
- size: `77`
- prototype: ``
- caller_count: `19`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140032ad0`
- `0x140032b4d`
- `0x140032b5f`
- `0x140032c1e`
- `0x140032c42`
- `0x140032cbb`
- `0x140032ccd`
- `0x140032cf1`
- `0x140032d1d`
- `0x140032d2f`
- `0x140032e31`
- `0x140032ff4`
- `0x140033123`
- `0x140033671`
- `0x14003375f`
- `0x140033847`
- `0x1400339cb`
- `0x140033a0f`
- `0x140033a65`

## callees

- `0x140015240`
- `0x140035010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Concurrency::task<void>::~task<void>(__int64 a1)
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
0x140015240  push    rbx
0x140015242  sub     rsp, 20h
0x140015246  mov     rbx, [rcx+8]
0x14001524a  test    rbx, rbx
0x14001524d  jz      short loc_140015287
0x14001524f  or      eax, 0FFFFFFFFh
0x140015252  lock xadd [rbx+8], eax
0x140015257  cmp     eax, 1
0x14001525a  jnz     short loc_140015287
0x14001525c  mov     rax, [rbx]
0x14001525f  mov     rcx, rbx
0x140015262  mov     rax, [rax]
0x140015265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001526a  or      eax, 0FFFFFFFFh
0x14001526d  lock xadd [rbx+0Ch], eax
0x140015272  cmp     eax, 1
0x140015275  jnz     short loc_140015287
0x140015277  mov     rax, [rbx]
0x14001527a  mov     rcx, rbx
0x14001527d  mov     rax, [rax+8]
0x140015281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015286  nop
0x140015287  add     rsp, 20h
0x14001528b  pop     rbx
0x14001528c  retn
```
