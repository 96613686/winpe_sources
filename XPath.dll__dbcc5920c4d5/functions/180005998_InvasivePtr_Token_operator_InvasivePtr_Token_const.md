# InvasivePtr<Token>::operator=(InvasivePtr<Token> const &)

- ea: `0x180005998`
- end: `0x1800059cc`
- name: `??4?$InvasivePtr@VToken@@@@QEAAAEAV0@AEBV0@@Z`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180007b14`
- `0x180008294`
- `0x18000f138`

## callees

- `0x180005998`
- `0x18000a240`

## pseudocode

```c
_QWORD *__fastcall InvasivePtr<Token>::operator=(_QWORD *a1, __int64 *a2)
{
  __int64 v2; // rbx

  v2 = *a2;
  if ( *a1 != *a2 )
  {
    if ( v2 )
      _InterlockedIncrement((volatile signed __int32 *)(v2 + 24));
    InvasivePtr<Node>::Reset(a1);
    *a1 = v2;
  }
  return a1;
}

```

## disassembly

```asm
0x180005998  mov     [rsp+arg_0], rbx
0x18000599d  push    rdi
0x18000599e  sub     rsp, 20h
0x1800059a2  mov     rbx, [rdx]
0x1800059a5  mov     rdi, rcx
0x1800059a8  cmp     [rcx], rbx
0x1800059ab  jz      short loc_1800059BE
0x1800059ad  test    rbx, rbx
0x1800059b0  jz      short loc_1800059B6
0x1800059b2  lock inc dword ptr [rbx+18h]
0x1800059b6  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x1800059bb  mov     [rdi], rbx
0x1800059be  mov     rbx, [rsp+28h+arg_0]
0x1800059c3  mov     rax, rdi
0x1800059c6  add     rsp, 20h
0x1800059ca  pop     rdi
0x1800059cb  retn
```
