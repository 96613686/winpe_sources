# std::function<long (thread_inside_functions &)>::~function<long (thread_inside_functions &)>(void)

- ea: `0x1800069b0`
- end: `0x1800069e2`
- name: `??1?$function@$$A6AJAEAVthread_inside_functions@@@Z@std@@QEAA@XZ`
- size: `50`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000a42d`
- `0x18000a481`
- `0x18000a4c8`

## callees

- `0x1800069b0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall std::function<long (thread_inside_functions &)>::~function<long (thread_inside_functions &)>(
        __int64 a1,
        __int64 a2)
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
0x1800069b0  push    rbx
0x1800069b2  sub     rsp, 20h
0x1800069b6  mov     rbx, rcx
0x1800069b9  mov     rcx, [rcx+38h]
0x1800069bd  test    rcx, rcx
0x1800069c0  jz      short loc_1800069DC
0x1800069c2  mov     rax, [rcx]
0x1800069c5  cmp     rcx, rbx
0x1800069c8  setnz   dl
0x1800069cb  mov     rax, [rax+20h]
0x1800069cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069d4  mov     qword ptr [rbx+38h], 0
0x1800069dc  add     rsp, 20h
0x1800069e0  pop     rbx
0x1800069e1  retn
```
