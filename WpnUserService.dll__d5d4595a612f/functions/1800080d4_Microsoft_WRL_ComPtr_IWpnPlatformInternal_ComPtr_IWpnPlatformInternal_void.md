# Microsoft::WRL::ComPtr<IWpnPlatformInternal>::~ComPtr<IWpnPlatformInternal>(void)

- ea: `0x1800080d4`
- end: `0x1800080fc`
- name: `??1?$ComPtr@UIWpnPlatformInternal@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800110e2`

## callees

- `0x1800080d4`
- `0x180012010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<IWpnPlatformInternal>::~ComPtr<IWpnPlatformInternal>(_QWORD *a1)
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
0x1800080d4  sub     rsp, 28h
0x1800080d8  mov     rax, rcx
0x1800080db  mov     rcx, [rcx]
0x1800080de  test    rcx, rcx
0x1800080e1  jz      short loc_1800080F7
0x1800080e3  mov     qword ptr [rax], 0
0x1800080ea  mov     rax, [rcx]
0x1800080ed  mov     rax, [rax+10h]
0x1800080f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080f6  nop
0x1800080f7  add     rsp, 28h
0x1800080fb  retn
```
