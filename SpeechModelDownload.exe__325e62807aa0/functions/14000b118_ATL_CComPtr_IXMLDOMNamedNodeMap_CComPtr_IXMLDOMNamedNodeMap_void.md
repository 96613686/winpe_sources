# ATL::CComPtr<IXMLDOMNamedNodeMap>::~CComPtr<IXMLDOMNamedNodeMap>(void)

- ea: `0x14000b118`
- end: `0x14000b136`
- name: `??1?$CComPtr@UIXMLDOMNamedNodeMap@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001bec3`
- `0x14001bed5`
- `0x14001bf0b`
- `0x14001bf1d`
- `0x14001bf41`
- `0x14001bfad`
- `0x14001bfbf`

## callees

- `0x14000b118`
- `0x14001d010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IXMLDOMNamedNodeMap>::~CComPtr<IXMLDOMNamedNodeMap>(__int64 *a1)
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
0x14000b118  sub     rsp, 28h
0x14000b11c  mov     rcx, [rcx]
0x14000b11f  test    rcx, rcx
0x14000b122  jz      short loc_14000B131
0x14000b124  mov     rax, [rcx]
0x14000b127  mov     rax, [rax+10h]
0x14000b12b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b130  nop
0x14000b131  add     rsp, 28h
0x14000b135  retn
```
