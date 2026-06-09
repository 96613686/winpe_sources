# ATL::CComPtr<ICatRegister>::~CComPtr<ICatRegister>(void)

- ea: `0x1800025ec`
- end: `0x180002610`
- name: `??1?$CComPtr@UICatRegister@@@ATL@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e6aa`

## callees

- `0x1800025ec`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<ICatRegister>::~CComPtr<ICatRegister>(__int64 *a1)
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
0x1800025ec  mov     [rsp+arg_0], rcx
0x1800025f1  sub     rsp, 28h
0x1800025f5  mov     rcx, [rcx]
0x1800025f8  test    rcx, rcx
0x1800025fb  jz      short loc_18000260B
0x1800025fd  mov     rax, [rcx]
0x180002600  mov     rax, [rax+10h]
0x180002604  call    cs:__guard_dispatch_icall_fptr
0x18000260a  nop
0x18000260b  add     rsp, 28h
0x18000260f  retn
```
