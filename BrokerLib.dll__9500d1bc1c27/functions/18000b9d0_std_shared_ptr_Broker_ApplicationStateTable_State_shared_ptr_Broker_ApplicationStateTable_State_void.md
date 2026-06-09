# std::shared_ptr<Broker::ApplicationStateTable::State>::~shared_ptr<Broker::ApplicationStateTable::State>(void)

- ea: `0x18000b9d0`
- end: `0x18000ba27`
- name: `??1?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@QEAA@XZ`
- size: `87`
- prototype: ``
- caller_count: `24`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b578`
- `0x18001af62`
- `0x18001b090`
- `0x18001b1f0`
- `0x18001b222`
- `0x18001b260`
- `0x18001b340`
- `0x18001b400`
- `0x18001b420`
- `0x18001b7f5`
- `0x18001b830`
- `0x18001b9c0`
- `0x18001be3f`
- `0x18001be58`
- `0x18001be71`
- `0x18001bf24`
- `0x18001d082`
- `0x18001d3bb`
- `0x18001d6de`
- `0x18001d6f0`
- `0x18001d77f`
- `0x18001dc1d`
- `0x18001dc2f`
- `0x18001dd24`

## callees

- `0x18000b9d0`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall std::shared_ptr<Broker::ApplicationStateTable::State>::~shared_ptr<Broker::ApplicationStateTable::State>(
        __int64 a1)
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
0x18000b9d0  push    rbx
0x18000b9d2  sub     rsp, 20h
0x18000b9d6  mov     rbx, [rcx+8]
0x18000b9da  test    rbx, rbx
0x18000b9dd  jz      short loc_18000BA21
0x18000b9df  mov     [rsp+28h+arg_0], rdi
0x18000b9e4  mov     edi, 0FFFFFFFFh
0x18000b9e9  mov     eax, edi
0x18000b9eb  lock xadd [rbx+8], eax
0x18000b9f0  cmp     eax, 1
0x18000b9f3  jnz     short loc_18000BA1C
0x18000b9f5  mov     rax, [rbx]
0x18000b9f8  mov     rcx, rbx
0x18000b9fb  mov     rax, [rax]
0x18000b9fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba03  lock xadd [rbx+0Ch], edi
0x18000ba08  cmp     edi, 1
0x18000ba0b  jnz     short loc_18000BA1C
0x18000ba0d  mov     rax, [rbx]
0x18000ba10  mov     rcx, rbx
0x18000ba13  mov     rax, [rax+8]
0x18000ba17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba1c  mov     rdi, [rsp+28h+arg_0]
0x18000ba21  add     rsp, 20h
0x18000ba25  pop     rbx
0x18000ba26  retn
```
