# ATL::CComPtrBase<IUnknown>::Release(void)

- ea: `0x18000e958`
- end: `0x18000e980`
- name: `?Release@?$CComPtrBase@UIUnknown@@@ATL@@QEAAXXZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012b10`
- `0x180013430`

## callees

- `0x18000e958`
- `0x18001b010`

## pseudocode

```c
_QWORD *__fastcall ATL::CComPtrBase<IUnknown>::Release(_QWORD *a1)
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
0x18000e958  sub     rsp, 28h
0x18000e95c  mov     rax, rcx
0x18000e95f  mov     rcx, [rcx]
0x18000e962  test    rcx, rcx
0x18000e965  jz      short loc_18000E97B
0x18000e967  mov     qword ptr [rax], 0
0x18000e96e  mov     rax, [rcx]
0x18000e971  mov     rax, [rax+10h]
0x18000e975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e97a  nop
0x18000e97b  add     rsp, 28h
0x18000e97f  retn
```
