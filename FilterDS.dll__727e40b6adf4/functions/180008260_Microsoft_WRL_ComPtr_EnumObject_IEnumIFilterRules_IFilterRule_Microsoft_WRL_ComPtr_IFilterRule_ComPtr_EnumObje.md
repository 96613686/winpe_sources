# Microsoft::WRL::ComPtr<EnumObject<IEnumIFilterRules,IFilterRule *,Microsoft::WRL::ComPtr<IFilterRule>>>::~ComPtr<EnumObject<IEnumIFilterRules,IFilterRule *,Microsoft::WRL::ComPtr<IFilterRule>>>(void)

- ea: `0x180008260`
- end: `0x180008288`
- name: `??1?$ComPtr@V?$EnumObject@UIEnumIFilterRules@@PEAUIFilterRule@@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002201f`
- `0x18002210e`
- `0x1800221d8`
- `0x1800221ea`
- `0x180022775`
- `0x1800227ab`
- `0x180022a7d`
- `0x180022ae3`
- `0x180022f95`
- `0x180022fa7`
- `0x18002344c`
- `0x1800236b6`
- `0x180023854`

## callees

- `0x180008260`
- `0x180024010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<EnumObject<IEnumIFilterRules,IFilterRule *,Microsoft::WRL::ComPtr<IFilterRule>>>::~ComPtr<EnumObject<IEnumIFilterRules,IFilterRule *,Microsoft::WRL::ComPtr<IFilterRule>>>(
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
0x180008260  sub     rsp, 28h
0x180008264  mov     rax, rcx
0x180008267  mov     rcx, [rcx]
0x18000826a  test    rcx, rcx
0x18000826d  jz      short loc_180008283
0x18000826f  mov     qword ptr [rax], 0
0x180008276  mov     rax, [rcx]
0x180008279  mov     rax, [rax+10h]
0x18000827d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008282  nop
0x180008283  add     rsp, 28h
0x180008287  retn
```
