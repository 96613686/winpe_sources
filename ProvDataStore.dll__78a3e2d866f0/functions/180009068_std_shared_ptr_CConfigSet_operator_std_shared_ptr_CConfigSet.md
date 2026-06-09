# std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)

- ea: `0x180009068`
- end: `0x1800090f1`
- name: `??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `137`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `12`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008368`
- `0x1800085e4`
- `0x18000a6e0`
- `0x18000a9f0`
- `0x18000b31c`
- `0x18000b6d8`
- `0x18000b8f8`
- `0x18000c6ec`
- `0x18000c8dc`
- `0x18000db4c`
- `0x18000e184`
- `0x18000f704`

## callees

- `0x180009068`
- `0x180012010`

## pseudocode

```c
_QWORD *__fastcall std::shared_ptr<CConfigSet>::operator=(_QWORD *a1, __int64 *a2)
{
  __int64 v3; // rax
  __int64 v4; // rcx
  volatile signed __int32 *v5; // rbx
  char v7; // [rsp+20h] [rbp-18h] BYREF

  if ( &v7 == (char *)a2 )
  {
    v4 = 0;
    v3 = 0;
  }
  else
  {
    v3 = a2[1];
    a2[1] = 0;
    v4 = *a2;
    *a2 = 0;
  }
  v5 = (volatile signed __int32 *)a1[1];
  a1[1] = v3;
  *a1 = v4;
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180009068  mov     [rsp+arg_0], rbx
0x18000906d  push    rdi
0x18000906e  sub     rsp, 30h
0x180009072  mov     rdi, rcx
0x180009075  lea     rax, [rsp+38h+var_18]
0x18000907a  cmp     rax, rdx
0x18000907d  jz      short loc_180009097
0x18000907f  mov     rax, [rdx+8]
0x180009083  mov     qword ptr [rdx+8], 0
0x18000908b  mov     rcx, [rdx]
0x18000908e  mov     qword ptr [rdx], 0
0x180009095  jmp     short loc_18000909B
0x180009097  xor     ecx, ecx
0x180009099  xor     eax, eax
0x18000909b  mov     rbx, [rdi+8]
0x18000909f  mov     [rdi+8], rax
0x1800090a3  mov     [rdi], rcx
0x1800090a6  test    rbx, rbx
0x1800090a9  jz      short loc_1800090E3
0x1800090ab  or      eax, 0FFFFFFFFh
0x1800090ae  lock xadd [rbx+8], eax
0x1800090b3  cmp     eax, 1
0x1800090b6  jnz     short loc_1800090E3
0x1800090b8  mov     rax, [rbx]
0x1800090bb  mov     rcx, rbx
0x1800090be  mov     rax, [rax]
0x1800090c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090c6  or      eax, 0FFFFFFFFh
0x1800090c9  lock xadd [rbx+0Ch], eax
0x1800090ce  cmp     eax, 1
0x1800090d1  jnz     short loc_1800090E3
0x1800090d3  mov     rax, [rbx]
0x1800090d6  mov     rcx, rbx
0x1800090d9  mov     rax, [rax+8]
0x1800090dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090e2  nop
0x1800090e3  mov     rax, rdi
0x1800090e6  mov     rbx, [rsp+38h+arg_0]
0x1800090eb  add     rsp, 30h
0x1800090ef  pop     rdi
0x1800090f0  retn
```
