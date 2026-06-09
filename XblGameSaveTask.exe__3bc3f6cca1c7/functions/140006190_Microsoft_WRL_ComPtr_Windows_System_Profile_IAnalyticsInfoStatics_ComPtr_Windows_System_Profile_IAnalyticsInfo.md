# Microsoft::WRL::ComPtr<Windows::System::Profile::IAnalyticsInfoStatics>::~ComPtr<Windows::System::Profile::IAnalyticsInfoStatics>(void)

- ea: `0x140006190`
- end: `0x1400061b8`
- name: `??1?$ComPtr@UIAnalyticsInfoStatics@Profile@System@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000662a`
- `0x14000663c`

## callees

- `0x140006190`
- `0x140007010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<Windows::System::Profile::IAnalyticsInfoStatics>::~ComPtr<Windows::System::Profile::IAnalyticsInfoStatics>(
        _QWORD *a1)
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
0x140006190  sub     rsp, 28h
0x140006194  mov     rax, rcx
0x140006197  mov     rcx, [rcx]
0x14000619a  test    rcx, rcx
0x14000619d  jz      short loc_1400061B3
0x14000619f  mov     qword ptr [rax], 0
0x1400061a6  mov     rax, [rcx]
0x1400061a9  mov     rax, [rax+10h]
0x1400061ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400061b2  nop
0x1400061b3  add     rsp, 28h
0x1400061b7  retn
```
