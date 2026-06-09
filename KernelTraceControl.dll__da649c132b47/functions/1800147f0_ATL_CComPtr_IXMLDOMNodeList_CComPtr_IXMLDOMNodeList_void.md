# ATL::CComPtr<IXMLDOMNodeList>::~CComPtr<IXMLDOMNodeList>(void)

- ea: `0x1800147f0`
- end: `0x18001480e`
- name: `??1?$CComPtr@UIXMLDOMNodeList@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800289da`
- `0x1800289e6`
- `0x1800289f2`
- `0x1800289fe`
- `0x180028a0a`
- `0x180028ce3`
- `0x18002955a`
- `0x180029566`
- `0x1800295b1`
- `0x1800295bd`

## callees

- `0x1800147f0`
- `0x180027910`

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
0x1800147f0  sub     rsp, 28h
0x1800147f4  mov     rcx, [rcx]
0x1800147f7  test    rcx, rcx
0x1800147fa  jz      short loc_180014809
0x1800147fc  mov     rax, [rcx]
0x1800147ff  mov     rax, [rax+10h]
0x180014803  call    cs:__guard_dispatch_icall_fptr
0x180014809  add     rsp, 28h
0x18001480d  retn
```
