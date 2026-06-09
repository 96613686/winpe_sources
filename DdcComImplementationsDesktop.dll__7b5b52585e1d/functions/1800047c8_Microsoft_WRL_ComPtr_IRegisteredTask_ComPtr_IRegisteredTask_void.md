# Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(void)

- ea: `0x1800047c8`
- end: `0x1800047f0`
- name: `??1?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `12`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bd9f`
- `0x18000bdb1`
- `0x18000bdc3`
- `0x18000bdd5`
- `0x18000bde7`
- `0x18000bdf9`
- `0x18000be0b`
- `0x18000be1d`
- `0x18000be2f`
- `0x18000be41`
- `0x18000be53`
- `0x18000be65`

## callees

- `0x1800047c8`
- `0x18000c010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(_QWORD *a1)
{
  _QWORD *result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x1800047c8  sub     rsp, 28h
0x1800047cc  mov     rax, rcx
0x1800047cf  mov     rcx, [rcx]
0x1800047d2  test    rcx, rcx
0x1800047d5  jz      short loc_1800047EB
0x1800047d7  mov     qword ptr [rax], 0
0x1800047de  mov     rax, [rcx]
0x1800047e1  mov     rax, [rax+10h]
0x1800047e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047ea  nop
0x1800047eb  add     rsp, 28h
0x1800047ef  retn
```
