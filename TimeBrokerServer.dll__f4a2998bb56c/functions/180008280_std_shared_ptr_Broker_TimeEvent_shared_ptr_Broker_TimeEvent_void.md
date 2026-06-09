# std::shared_ptr<Broker::TimeEvent>::~shared_ptr<Broker::TimeEvent>(void)

- ea: `0x180008280`
- end: `0x1800082d9`
- name: `??1?$shared_ptr@VTimeEvent@Broker@@@std@@QEAA@XZ`
- size: `89`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `20`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000215c`
- `0x1800061e0`
- `0x180019e7e`
- `0x180019eb0`
- `0x180019ed4`
- `0x18001a018`
- `0x18001a580`
- `0x18001a5a0`
- `0x18001a5c0`
- `0x18001a690`
- `0x18001a860`
- `0x18001a880`
- `0x18001a940`
- `0x18001a972`
- `0x18001acdd`
- `0x18001b5a5`
- `0x18001b9d0`
- `0x18001ba10`
- `0x18001ba90`
- `0x18001bd00`

## callees

- `0x180008280`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall std::shared_ptr<Broker::TimeEvent>::~shared_ptr<Broker::TimeEvent>(__int64 a1)
{
  volatile signed __int32 *v1; // rbx
  __int64 result; // rax

  v1 = *(volatile signed __int32 **)(a1 + 8);
  if ( v1 )
  {
    result = (unsigned int)_InterlockedExchangeAdd(v1 + 2, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      result = (**(__int64 (__fastcall ***)(volatile signed __int32 *))v1)(v1);
      if ( _InterlockedExchangeAdd(v1 + 3, 0xFFFFFFFF) == 1 )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v1 + 8LL))(v1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008280  push    rbx
0x180008282  sub     rsp, 20h
0x180008286  mov     rbx, [rcx+8]
0x18000828a  test    rbx, rbx
0x18000828d  jz      short loc_1800082AA
0x18000828f  mov     [rsp+28h+arg_0], rdi
0x180008294  mov     edi, 0FFFFFFFFh
0x180008299  mov     eax, edi
0x18000829b  lock xadd [rbx+8], eax
0x1800082a0  cmp     eax, 1
0x1800082a3  jz      short loc_1800082B0
0x1800082a5  mov     rdi, [rsp+28h+arg_0]
0x1800082aa  add     rsp, 20h
0x1800082ae  pop     rbx
0x1800082af  retn
0x1800082b0  mov     rax, [rbx]
0x1800082b3  mov     rcx, rbx
0x1800082b6  mov     rax, [rax]
0x1800082b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082be  lock xadd [rbx+0Ch], edi
0x1800082c3  cmp     edi, 1
0x1800082c6  jnz     short loc_1800082A5
0x1800082c8  mov     rax, [rbx]
0x1800082cb  mov     rcx, rbx
0x1800082ce  mov     rax, [rax+8]
0x1800082d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082d7  jmp     short loc_1800082A5
```
