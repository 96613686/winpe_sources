# ATL::CComPtr<IXMLDOMNodeList>::~CComPtr<IXMLDOMNodeList>(void)

- ea: `0x1800030d8`
- end: `0x1800030f6`
- name: `??1?$CComPtr@UIXMLDOMNodeList@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `14`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001388d`
- `0x18001389f`
- `0x1800138b1`
- `0x1800138c3`
- `0x1800138e7`
- `0x1800138f9`
- `0x18001390b`
- `0x18001391d`
- `0x18001392f`
- `0x180013941`
- `0x180013953`
- `0x180013977`
- `0x180013989`
- `0x18001399b`

## callees

- `0x1800030d8`
- `0x180014010`

## pseudocode

```c
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
0x1800030d8  sub     rsp, 28h
0x1800030dc  mov     rcx, [rcx]
0x1800030df  test    rcx, rcx
0x1800030e2  jz      short loc_1800030F1
0x1800030e4  mov     rax, [rcx]
0x1800030e7  mov     rax, [rax+10h]
0x1800030eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030f0  nop
0x1800030f1  add     rsp, 28h
0x1800030f5  retn
```
