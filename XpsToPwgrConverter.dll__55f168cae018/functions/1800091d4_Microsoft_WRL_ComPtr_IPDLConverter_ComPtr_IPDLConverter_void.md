# Microsoft::WRL::ComPtr<IPDLConverter>::~ComPtr<IPDLConverter>(void)

- ea: `0x1800091d4`
- end: `0x1800091fc`
- name: `??1?$ComPtr@UIPDLConverter@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000fe08`
- `0x18000fe9a`
- `0x18000feac`
- `0x18000ff24`
- `0x180010655`
- `0x1800106bb`
- `0x1800106f3`

## callees

- `0x1800091d4`
- `0x180011010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<IPDLConverter>::~ComPtr<IPDLConverter>(_QWORD *a1)
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
0x1800091d4  sub     rsp, 28h
0x1800091d8  mov     rax, rcx
0x1800091db  mov     rcx, [rcx]
0x1800091de  test    rcx, rcx
0x1800091e1  jz      short loc_1800091F7
0x1800091e3  mov     qword ptr [rax], 0
0x1800091ea  mov     rax, [rcx]
0x1800091ed  mov     rax, [rax+10h]
0x1800091f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091f6  nop
0x1800091f7  add     rsp, 28h
0x1800091fb  retn
```
