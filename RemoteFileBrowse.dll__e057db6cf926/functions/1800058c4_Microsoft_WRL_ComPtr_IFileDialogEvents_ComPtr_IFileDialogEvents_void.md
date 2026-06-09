# Microsoft::WRL::ComPtr<IFileDialogEvents>::~ComPtr<IFileDialogEvents>(void)

- ea: `0x1800058c4`
- end: `0x1800058ec`
- name: `??1?$ComPtr@UIFileDialogEvents@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180017b6e`
- `0x180017bf5`
- `0x180017c07`
- `0x180017c19`
- `0x180017c3d`
- `0x180017c85`
- `0x180017ca9`
- `0x180018833`
- `0x180018881`
- `0x18001890b`

## callees

- `0x1800058c4`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<IFileDialogEvents>::~ComPtr<IFileDialogEvents>(_QWORD *a1)
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
0x1800058c4  sub     rsp, 28h
0x1800058c8  mov     rax, rcx
0x1800058cb  mov     rcx, [rcx]
0x1800058ce  test    rcx, rcx
0x1800058d1  jz      short loc_1800058E7
0x1800058d3  mov     qword ptr [rax], 0
0x1800058da  mov     rax, [rcx]
0x1800058dd  mov     rax, [rax+10h]
0x1800058e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058e6  nop
0x1800058e7  add     rsp, 28h
0x1800058eb  retn
```
