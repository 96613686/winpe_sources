# Microsoft::WRL::ComPtr<IUnknown>::~ComPtr<IUnknown>(void)

- ea: `0x18000f06c`
- end: `0x18000f093`
- name: `??1?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEAA@XZ`
- size: `39`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f018`

## callees

- `0x18000f06c`
- `0x18001c010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<IUnknown>::~ComPtr<IUnknown>(_QWORD *a1)
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
0x18000f06c  sub     rsp, 28h
0x18000f070  mov     rax, rcx
0x18000f073  mov     rcx, [rcx]
0x18000f076  test    rcx, rcx
0x18000f079  jz      short loc_18000F08E
0x18000f07b  mov     qword ptr [rax], 0
0x18000f082  mov     rax, [rcx]
0x18000f085  mov     rax, [rax+10h]
0x18000f089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f08e  add     rsp, 28h
0x18000f092  retn
```
