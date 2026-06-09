# std::shared_ptr<Broker::TimeEvent>::operator=(std::shared_ptr<Broker::TimeEvent> const &)

- ea: `0x180004dd4`
- end: `0x180004e0f`
- name: `??4?$shared_ptr@VTimeEvent@Broker@@@std@@QEAAAEAV01@AEBV01@@Z`
- size: `59`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800050d0`
- `0x180011d00`
- `0x180014568`
- `0x180015b10`
- `0x180015cb0`
- `0x180015f3c`

## callees

- `0x180004dd4`
- `0x180005b30`

## pseudocode

```c
_QWORD *__fastcall std::shared_ptr<Broker::TimeEvent>::operator=(_QWORD *a1, _QWORD *a2)
{
  __int64 v2; // rax
  __int64 v4; // r8
  std::_Ref_count_base *v5; // rcx

  v2 = a2[1];
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  v4 = a2[1];
  *a1 = *a2;
  v5 = (std::_Ref_count_base *)a1[1];
  a1[1] = v4;
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
  return a1;
}

```

## disassembly

```asm
0x180004dd4  push    rbx
0x180004dd6  sub     rsp, 20h
0x180004dda  mov     rax, [rdx+8]
0x180004dde  mov     rbx, rcx
0x180004de1  test    rax, rax
0x180004de4  jz      short loc_180004DEA
0x180004de6  lock inc dword ptr [rax+8]
0x180004dea  mov     rax, [rdx]
0x180004ded  mov     r8, [rdx+8]
0x180004df1  mov     [rcx], rax
0x180004df4  mov     rcx, [rcx+8]; this
0x180004df8  mov     [rbx+8], r8
0x180004dfc  test    rcx, rcx
0x180004dff  jz      short loc_180004E06
0x180004e01  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180004e06  mov     rax, rbx
0x180004e09  add     rsp, 20h
0x180004e0d  pop     rbx
0x180004e0e  retn
```
