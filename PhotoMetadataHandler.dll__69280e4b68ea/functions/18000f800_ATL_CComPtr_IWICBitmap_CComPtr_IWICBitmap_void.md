# ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)

- ea: `0x18000f800`
- end: `0x18000f81f`
- name: `??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `24`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800277d0`
- `0x180027aa2`
- `0x180027abb`
- `0x180027b10`
- `0x180027b30`
- `0x180027ba0`
- `0x180027bc0`
- `0x180027c20`
- `0x180027c40`
- `0x180027c60`
- `0x180027cd2`
- `0x180027ce4`
- `0x180027ecd`
- `0x180027f97`
- `0x180027fa9`
- `0x180027fbb`
- `0x180027fcd`
- `0x180027fdf`
- `0x180027ff1`
- `0x180028003`
- `0x180028015`
- `0x180028027`
- `0x180028311`
- `0x18002838f`

## callees

- `0x18000f800`
- `0x180029010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(__int64 *a1)
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
0x18000f800  sub     rsp, 28h
0x18000f804  mov     rcx, [rcx]
0x18000f807  test    rcx, rcx
0x18000f80a  jz      short loc_18000F819
0x18000f80c  mov     rax, [rcx]
0x18000f80f  mov     rax, [rax+10h]
0x18000f813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f818  nop
0x18000f819  add     rsp, 28h
0x18000f81d  retn
```
