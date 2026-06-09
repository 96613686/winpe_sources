# std::shared_ptr<Broker::SystemTimer>::operator=(std::shared_ptr<Broker::SystemTimer> &&)

- ea: `0x180004e18`
- end: `0x180004e55`
- name: `??4?$shared_ptr@VSystemTimer@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `61`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ef50`
- `0x180010e88`
- `0x180011ea8`
- `0x1800120f4`
- `0x180012244`
- `0x180014900`

## callees

- `0x180004e18`
- `0x180005b30`

## pseudocode

```c
_QWORD *__fastcall std::shared_ptr<Broker::SystemTimer>::operator=(_QWORD *a1, __int64 *a2)
{
  __int64 v2; // rax
  __int64 v4; // r8
  std::_Ref_count_base *v5; // rcx

  v2 = *a2;
  v4 = a2[1];
  *a2 = 0;
  a2[1] = 0;
  *a1 = v2;
  v5 = (std::_Ref_count_base *)a1[1];
  a1[1] = v4;
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
  return a1;
}

```

## disassembly

```asm
0x180004e18  push    rbx
0x180004e1a  sub     rsp, 20h
0x180004e1e  mov     rax, [rdx]
0x180004e21  mov     rbx, rcx
0x180004e24  mov     r8, [rdx+8]
0x180004e28  mov     qword ptr [rdx], 0
0x180004e2f  mov     qword ptr [rdx+8], 0
0x180004e37  mov     [rcx], rax
0x180004e3a  mov     rcx, [rcx+8]; this
0x180004e3e  mov     [rbx+8], r8
0x180004e42  test    rcx, rcx
0x180004e45  jz      short loc_180004E4C
0x180004e47  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180004e4c  mov     rax, rbx
0x180004e4f  add     rsp, 20h
0x180004e53  pop     rbx
0x180004e54  retn
```
