# ATL::CComPtr<IXMLDOMNodeList>::~CComPtr<IXMLDOMNodeList>(void)

- ea: `0x180014e1c`
- end: `0x180014e3a`
- name: `??1?$CComPtr@UIXMLDOMNodeList@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035f6a`
- `0x180035f7c`
- `0x180035f8e`
- `0x180035fa0`
- `0x180036745`
- `0x180036757`
- `0x180036872`

## callees

- `0x180014e1c`
- `0x180037010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComPtr<IXMLDOMNodeList>::~CComPtr<IXMLDOMNodeList>(__int64 *a1)
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
0x180014e1c  sub     rsp, 28h
0x180014e20  mov     rcx, [rcx]
0x180014e23  test    rcx, rcx
0x180014e26  jz      short loc_180014E35
0x180014e28  mov     rax, [rcx]
0x180014e2b  mov     rax, [rax+10h]
0x180014e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e34  nop
0x180014e35  add     rsp, 28h
0x180014e39  retn
```
