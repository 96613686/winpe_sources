# ATL::CComPtr<IXMLDOMNodeList>::~CComPtr<IXMLDOMNodeList>(void)

- ea: `0x1800159fc`
- end: `0x180015a1b`
- name: `??1?$CComPtr@UIXMLDOMNodeList@@@ATL@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003771c`
- `0x18003772e`
- `0x180037740`
- `0x180037752`
- `0x180037f00`
- `0x180037f12`
- `0x18003802e`

## callees

- `0x1800159fc`
- `0x180039010`

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
0x1800159fc  sub     rsp, 28h
0x180015a00  mov     rcx, [rcx]
0x180015a03  test    rcx, rcx
0x180015a06  jz      short loc_180015A15
0x180015a08  mov     rax, [rcx]
0x180015a0b  mov     rax, [rax+10h]
0x180015a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a14  nop
0x180015a15  add     rsp, 28h
0x180015a19  retn
```
