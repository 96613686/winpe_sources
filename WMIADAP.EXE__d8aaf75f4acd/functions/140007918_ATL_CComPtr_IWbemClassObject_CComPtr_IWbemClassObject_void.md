# ATL::CComPtr<IWbemClassObject>::~CComPtr<IWbemClassObject>(void)

- ea: `0x140007918`
- end: `0x140007936`
- name: `??1?$CComPtr@UIWbemClassObject@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007a20`
- `0x140007e1c`
- `0x1400080fc`
- `0x14000e04c`
- `0x14000e470`
- `0x14000f218`
- `0x14000f298`
- `0x140015478`
- `0x140015bb5`
- `0x140015cca`
- `0x140015e31`
- `0x140015e43`

## callees

- `0x140007918`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IWbemClassObject>::~CComPtr<IWbemClassObject>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x140007918  sub     rsp, 28h
0x14000791c  mov     rcx, [rcx]
0x14000791f  test    rcx, rcx
0x140007922  jz      short loc_140007931
0x140007924  mov     rax, [rcx]
0x140007927  mov     rax, [rax+10h]
0x14000792b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007930  nop
0x140007931  add     rsp, 28h
0x140007935  retn
```
