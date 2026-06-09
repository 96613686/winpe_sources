# Microsoft::WRL::ComPtr<IGlobalOptions>::~ComPtr<IGlobalOptions>(void)

- ea: `0x180003c3c`
- end: `0x180003c64`
- name: `??1?$ComPtr@UIGlobalOptions@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c96a`

## callees

- `0x180003c3c`
- `0x18000e010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<IGlobalOptions>::~ComPtr<IGlobalOptions>(_QWORD *a1)
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
0x180003c3c  sub     rsp, 28h
0x180003c40  mov     rax, rcx
0x180003c43  mov     rcx, [rcx]
0x180003c46  test    rcx, rcx
0x180003c49  jz      short loc_180003C5F
0x180003c4b  mov     qword ptr [rax], 0
0x180003c52  mov     rax, [rcx]
0x180003c55  mov     rax, [rax+10h]
0x180003c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c5e  nop
0x180003c5f  add     rsp, 28h
0x180003c63  retn
```
