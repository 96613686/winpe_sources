# ATL::CComPtr<ISpObjectTokenCategory>::~CComPtr<ISpObjectTokenCategory>(void)

- ea: `0x18000db90`
- end: `0x18000dbaf`
- name: `??1?$CComPtr@UISpObjectTokenCategory@@@ATL@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010864`
- `0x180010876`

## callees

- `0x18000db90`
- `0x180011010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComPtr<ISpObjectTokenCategory>::~CComPtr<ISpObjectTokenCategory>(__int64 *a1)
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
0x18000db90  sub     rsp, 28h
0x18000db94  mov     rcx, [rcx]
0x18000db97  test    rcx, rcx
0x18000db9a  jz      short loc_18000DBA9
0x18000db9c  mov     rax, [rcx]
0x18000db9f  mov     rax, [rax+10h]
0x18000dba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dba8  nop
0x18000dba9  add     rsp, 28h
0x18000dbad  retn
```
