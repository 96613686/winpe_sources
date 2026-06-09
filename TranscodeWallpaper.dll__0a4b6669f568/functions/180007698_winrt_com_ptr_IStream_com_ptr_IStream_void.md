# winrt::com_ptr<IStream>::~com_ptr<IStream>(void)

- ea: `0x180007698`
- end: `0x1800076ac`
- name: `??1?$com_ptr@UIStream@@@winrt@@QEAA@XZ`
- size: `20`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e86b`
- `0x18000e87d`

## callees

- `0x180007698`
- `0x18000ab5c`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<IStream>::~com_ptr<IStream>(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return winrt::com_ptr<IShellItem>::unconditional_release_ref(a1);
  return result;
}

```

## disassembly

```asm
0x180007698  sub     rsp, 28h
0x18000769c  cmp     qword ptr [rcx], 0
0x1800076a0  jz      short loc_1800076A7
0x1800076a2  call    ?unconditional_release_ref@?$com_ptr@UIShellItem@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellItem>::unconditional_release_ref(void)
0x1800076a7  add     rsp, 28h
0x1800076ab  retn
```
