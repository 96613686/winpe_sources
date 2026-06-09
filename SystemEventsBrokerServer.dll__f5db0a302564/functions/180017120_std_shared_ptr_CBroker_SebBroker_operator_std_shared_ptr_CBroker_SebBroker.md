# std::shared_ptr<CBroker::SebBroker>::operator=(std::shared_ptr<CBroker::SebBroker> &&)

- ea: `0x180017120`
- end: `0x18001715d`
- name: `??4?$shared_ptr@VSebBroker@CBroker@@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `61`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006e00`
- `0x180018754`
- `0x1800197fc`
- `0x18001ad04`
- `0x18001aee0`
- `0x18001b378`
- `0x18001c100`
- `0x18001c4d8`
- `0x18001df48`
- `0x18001fb20`
- `0x180020bac`

## callees

- `0x1800076a0`
- `0x180017120`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::shared_ptr<CBroker::SebBroker>::operator=(_QWORD *a1, __int64 *a2)
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
0x180017120  push    rbx
0x180017122  sub     rsp, 20h
0x180017126  mov     rax, [rdx]
0x180017129  mov     rbx, rcx
0x18001712c  mov     r8, [rdx+8]
0x180017130  mov     qword ptr [rdx], 0
0x180017137  mov     qword ptr [rdx+8], 0
0x18001713f  mov     [rcx], rax
0x180017142  mov     rcx, [rcx+8]; this
0x180017146  mov     [rbx+8], r8
0x18001714a  test    rcx, rcx
0x18001714d  jz      short loc_180017154
0x18001714f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180017154  mov     rax, rbx
0x180017157  add     rsp, 20h
0x18001715b  pop     rbx
0x18001715c  retn
```
