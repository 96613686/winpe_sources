# ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)

- ea: `0x1800030fc`
- end: `0x18000311a`
- name: `??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011f90`
- `0x1800125a4`
- `0x180012db0`
- `0x180012fe0`
- `0x1800130e0`
- `0x1800131e4`

## callees

- `0x1800030fc`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(__int64 *a1)
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
0x1800030fc  sub     rsp, 28h
0x180003100  mov     rcx, [rcx]
0x180003103  test    rcx, rcx
0x180003106  jz      short loc_180003115
0x180003108  mov     rax, [rcx]
0x18000310b  mov     rax, [rax+10h]
0x18000310f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003114  nop
0x180003115  add     rsp, 28h
0x180003119  retn
```
