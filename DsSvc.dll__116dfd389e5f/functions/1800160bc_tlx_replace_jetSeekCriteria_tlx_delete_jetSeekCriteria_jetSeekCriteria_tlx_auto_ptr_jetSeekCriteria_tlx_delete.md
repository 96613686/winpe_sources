# tlx::replace<_jetSeekCriteria,&tlx::_delete<_jetSeekCriteria>(_jetSeekCriteria *)>(tlx::auto_ptr<_jetSeekCriteria,&tlx::_delete<_jetSeekCriteria>(_jetSeekCriteria *)> &)

- ea: `0x1800160bc`
- end: `0x1800160e2`
- name: `??$replace@U_jetSeekCriteria@@$1??$_delete@U_jetSeekCriteria@@@tlx@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_jetSeekCriteria@@AEAV?$auto_ptr@U_jetSeekCriteria@@$1??$_delete@U_jetSeekCriteria@@@tlx@@YAXPEAU1@@Z@0@@Z`
- size: `38`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001686c`
- `0x180016dec`
- `0x180017140`
- `0x180017318`
- `0x180017518`

## callees

- `0x18000be3c`
- `0x1800160bc`

## pseudocode

```c
void **__fastcall tlx::replace<_jetSeekCriteria,&void tlx::_delete<_jetSeekCriteria>(_jetSeekCriteria *)>(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
    Common::GlobalHeap::Free(v2);
  *a1 = 0;
  return a1;
}

```

## disassembly

```asm
0x1800160bc  push    rbx
0x1800160be  sub     rsp, 20h
0x1800160c2  mov     rbx, rcx
0x1800160c5  mov     rcx, [rcx]; P
0x1800160c8  test    rcx, rcx
0x1800160cb  jz      short loc_1800160D2
0x1800160cd  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800160d2  mov     qword ptr [rbx], 0
0x1800160d9  mov     rax, rbx
0x1800160dc  add     rsp, 20h
0x1800160e0  pop     rbx
0x1800160e1  retn
```
