# Microsoft::WRL::ComPtr<IApplicationLicenseManager>::~ComPtr<IApplicationLicenseManager>(void)

- ea: `0x180002398`
- end: `0x1800023c0`
- name: `??1?$ComPtr@UIApplicationLicenseManager@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000cbd6`
- `0x18000cbe8`

## callees

- `0x180002398`
- `0x18000d010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<IApplicationLicenseManager>::~ComPtr<IApplicationLicenseManager>(_QWORD *a1)
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
0x180002398  sub     rsp, 28h
0x18000239c  mov     rax, rcx
0x18000239f  mov     rcx, [rcx]
0x1800023a2  test    rcx, rcx
0x1800023a5  jz      short loc_1800023BB
0x1800023a7  mov     qword ptr [rax], 0
0x1800023ae  mov     rax, [rcx]
0x1800023b1  mov     rax, [rax+10h]
0x1800023b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023ba  nop
0x1800023bb  add     rsp, 28h
0x1800023bf  retn
```
