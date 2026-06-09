# Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(void)

- ea: `0x140003790`
- end: `0x1400037b8`
- name: `??1?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `8`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000e1a3`
- `0x14000e1b5`
- `0x14000e97d`
- `0x14000e9a1`
- `0x14000e9b3`
- `0x14000e9c5`
- `0x14000e9d7`
- `0x14000ee82`

## callees

- `0x140003790`
- `0x140010010`

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
0x140003790  sub     rsp, 28h
0x140003794  mov     rax, rcx
0x140003797  mov     rcx, [rcx]
0x14000379a  test    rcx, rcx
0x14000379d  jz      short loc_1400037B3
0x14000379f  mov     qword ptr [rax], 0
0x1400037a6  mov     rax, [rcx]
0x1400037a9  mov     rax, [rax+10h]
0x1400037ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037b2  nop
0x1400037b3  add     rsp, 28h
0x1400037b7  retn
```
