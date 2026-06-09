# InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(XPathNodeIteratorBase *)

- ea: `0x1800059d4`
- end: `0x180005a08`
- name: `??$?4VXPathNodeIteratorBase@@@?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAAAEAV0@PEAVXPathNodeIteratorBase@@@Z`
- size: `52`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x180005a3c`
- `0x180005b60`
- `0x180005c7c`
- `0x180007110`
- `0x1800071b4`
- `0x180007258`
- `0x180008cb4`
- `0x180009d84`
- `0x18000a094`
- `0x18000c7cc`
- `0x18000ca88`
- `0x18000cb64`

## callees

- `0x1800054e0`
- `0x1800059d4`

## pseudocode

```c
_QWORD *__fastcall InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(_QWORD *a1, __int64 a2)
{
  if ( *a1 != a2 )
  {
    if ( a2 )
      _InterlockedIncrement((volatile signed __int32 *)(a2 + 16));
    InvasivePtr<UnionExpressionIterator>::Reset(a1);
    *a1 = a2;
  }
  return a1;
}

```

## disassembly

```asm
0x1800059d4  mov     [rsp+arg_0], rbx
0x1800059d9  push    rdi
0x1800059da  sub     rsp, 20h
0x1800059de  mov     rbx, rdx
0x1800059e1  mov     rdi, rcx
0x1800059e4  cmp     [rcx], rdx
0x1800059e7  jz      short loc_1800059FA
0x1800059e9  test    rdx, rdx
0x1800059ec  jz      short loc_1800059F2
0x1800059ee  lock inc dword ptr [rdx+10h]
0x1800059f2  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x1800059f7  mov     [rdi], rbx
0x1800059fa  mov     rbx, [rsp+28h+arg_0]
0x1800059ff  mov     rax, rdi
0x180005a02  add     rsp, 20h
0x180005a06  pop     rdi
0x180005a07  retn
```
