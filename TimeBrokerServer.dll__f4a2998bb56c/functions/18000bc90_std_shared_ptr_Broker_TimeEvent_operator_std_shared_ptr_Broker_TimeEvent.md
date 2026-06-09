# std::shared_ptr<Broker::TimeEvent>::operator=(std::shared_ptr<Broker::TimeEvent> &&)

- ea: `0x18000bc90`
- end: `0x18000bd1d`
- name: `??4?$shared_ptr@VTimeEvent@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `141`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001579c`

## callees

- `0x18000bc90`
- `0x18001c010`

## pseudocode

```c
_QWORD *__fastcall std::shared_ptr<Broker::TimeEvent>::operator=(_QWORD *a1, __int64 *a2)
{
  __int64 v2; // rax
  __int64 v4; // r8
  volatile signed __int32 *v5; // rbx

  v2 = *a2;
  v4 = a2[1];
  *a2 = 0;
  a2[1] = 0;
  *a1 = v2;
  v5 = (volatile signed __int32 *)a1[1];
  a1[1] = v4;
  if ( !v5 )
    return a1;
  if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
    if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
  }
  return a1;
}

```

## disassembly

```asm
0x18000bc90  mov     [rsp+arg_8], rbx
0x18000bc95  push    rdi
0x18000bc96  sub     rsp, 20h
0x18000bc9a  mov     rax, [rdx]
0x18000bc9d  mov     rdi, rcx
0x18000bca0  mov     r8, [rdx+8]
0x18000bca4  xor     ecx, ecx
0x18000bca6  mov     [rdx], rcx
0x18000bca9  mov     [rdx+8], rcx
0x18000bcad  mov     [rdi], rax
0x18000bcb0  mov     rbx, [rdi+8]
0x18000bcb4  mov     [rdi+8], r8
0x18000bcb8  test    rbx, rbx
0x18000bcbb  jz      short loc_18000BD0F
0x18000bcbd  mov     [rsp+28h+arg_0], rsi
0x18000bcc2  mov     esi, 0FFFFFFFFh
0x18000bcc7  mov     eax, esi
0x18000bcc9  lock xadd [rbx+8], eax
0x18000bcce  cmp     eax, 1
0x18000bcd1  jz      short loc_18000BCE6
0x18000bcd3  mov     rsi, [rsp+28h+arg_0]
0x18000bcd8  mov     rax, rdi
0x18000bcdb  mov     rbx, [rsp+28h+arg_8]
0x18000bce0  add     rsp, 20h
0x18000bce4  pop     rdi
0x18000bce5  retn
0x18000bce6  mov     rax, [rbx]
0x18000bce9  mov     rcx, rbx
0x18000bcec  mov     rax, [rax]
0x18000bcef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcf4  lock xadd [rbx+0Ch], esi
0x18000bcf9  cmp     esi, 1
0x18000bcfc  jnz     short loc_18000BCD3
0x18000bcfe  mov     rax, [rbx]
0x18000bd01  mov     rcx, rbx
0x18000bd04  mov     rax, [rax+8]
0x18000bd08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd0d  jmp     short loc_18000BCD3
0x18000bd0f  mov     rbx, [rsp+28h+arg_8]
0x18000bd14  mov     rax, rdi
0x18000bd17  add     rsp, 20h
0x18000bd1b  pop     rdi
0x18000bd1c  retn
```
