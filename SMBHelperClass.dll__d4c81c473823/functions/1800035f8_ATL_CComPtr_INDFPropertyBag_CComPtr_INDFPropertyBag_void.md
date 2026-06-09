# ATL::CComPtr<INDFPropertyBag>::~CComPtr<INDFPropertyBag>(void)

- ea: `0x1800035f8`
- end: `0x180003616`
- name: `??1?$CComPtr@UINDFPropertyBag@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001010c`

## callees

- `0x1800035f8`
- `0x180012010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComPtr<INDFPropertyBag>::~CComPtr<INDFPropertyBag>(__int64 *a1)
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
0x1800035f8  sub     rsp, 28h
0x1800035fc  mov     rcx, [rcx]
0x1800035ff  test    rcx, rcx
0x180003602  jz      short loc_180003611
0x180003604  mov     rax, [rcx]
0x180003607  mov     rax, [rax+10h]
0x18000360b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003610  nop
0x180003611  add     rsp, 28h
0x180003615  retn
```
