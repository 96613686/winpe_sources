# Microsoft::WRL::ComPtr<ILocaleMapConfiguration>::~ComPtr<ILocaleMapConfiguration>(void)

- ea: `0x180006c14`
- end: `0x180006c3c`
- name: `??1?$ComPtr@UILocaleMapConfiguration@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ee0e`
- `0x18000ee44`
- `0x18000f060`
- `0x18000f072`

## callees

- `0x180006c14`
- `0x180010010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<ILocaleMapConfiguration>::~ComPtr<ILocaleMapConfiguration>(_QWORD *a1)
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
0x180006c14  sub     rsp, 28h
0x180006c18  mov     rax, rcx
0x180006c1b  mov     rcx, [rcx]
0x180006c1e  test    rcx, rcx
0x180006c21  jz      short loc_180006C37
0x180006c23  mov     qword ptr [rax], 0
0x180006c2a  mov     rax, [rcx]
0x180006c2d  mov     rax, [rax+10h]
0x180006c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c36  nop
0x180006c37  add     rsp, 28h
0x180006c3b  retn
```
