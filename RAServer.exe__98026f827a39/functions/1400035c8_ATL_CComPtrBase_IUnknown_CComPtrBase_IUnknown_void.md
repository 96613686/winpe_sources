# ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)

- ea: `0x1400035c8`
- end: `0x1400035e6`
- name: `??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `20`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400033dc`
- `0x1400035bc`
- `0x1400069fc`
- `0x1400074dc`
- `0x14000ceb4`
- `0x14000d1f8`
- `0x14000d38c`
- `0x14000ded0`
- `0x140011404`
- `0x140011530`
- `0x140011920`
- `0x140011d10`
- `0x140011fc0`
- `0x140012890`
- `0x140012b98`
- `0x140012c00`
- `0x140012fe0`
- `0x140013250`
- `0x140013760`
- `0x140014a90`

## callees

- `0x1400035c8`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(__int64 *a1)
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
0x1400035c8  sub     rsp, 28h
0x1400035cc  mov     rcx, [rcx]
0x1400035cf  test    rcx, rcx
0x1400035d2  jz      short loc_1400035E1
0x1400035d4  mov     rax, [rcx]
0x1400035d7  mov     rax, [rax+10h]
0x1400035db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400035e0  nop
0x1400035e1  add     rsp, 28h
0x1400035e5  retn
```
