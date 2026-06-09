# std::function<long (void)>::~function<long (void)>(void)

- ea: `0x1400032bc`
- end: `0x1400032ee`
- name: `??1?$function@$$A6AJXZ@std@@QEAA@XZ`
- size: `50`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400093df`
- `0x140009493`
- `0x14000982f`

## callees

- `0x1400032bc`
- `0x14000a010`

## pseudocode

```c
__int64 __fastcall std::function<long (void)>::~function<long (void)>(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 result; // rax

  v3 = *(_QWORD *)(a1 + 56);
  if ( v3 )
  {
    LOBYTE(a2) = v3 != a1;
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 32LL))(v3, a2);
    *(_QWORD *)(a1 + 56) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400032bc  push    rbx
0x1400032be  sub     rsp, 20h
0x1400032c2  mov     rbx, rcx
0x1400032c5  mov     rcx, [rcx+38h]
0x1400032c9  test    rcx, rcx
0x1400032cc  jz      short loc_1400032E8
0x1400032ce  mov     rax, [rcx]
0x1400032d1  cmp     rcx, rbx
0x1400032d4  setnz   dl
0x1400032d7  mov     rax, [rax+20h]
0x1400032db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032e0  mov     qword ptr [rbx+38h], 0
0x1400032e8  add     rsp, 20h
0x1400032ec  pop     rbx
0x1400032ed  retn
```
