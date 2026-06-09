# ATL::CComPtr<IXMLDOMNodeList>::~CComPtr<IXMLDOMNodeList>(void)

- ea: `0x180002948`
- end: `0x180002966`
- name: `??1?$CComPtr@UIXMLDOMNodeList@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027f7d`
- `0x180027f8f`
- `0x180027fa1`
- `0x180027fb3`
- `0x180028762`
- `0x180028774`
- `0x18002888f`

## callees

- `0x180002948`
- `0x18002a010`

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
0x180002948  sub     rsp, 28h
0x18000294c  mov     rcx, [rcx]
0x18000294f  test    rcx, rcx
0x180002952  jz      short loc_180002961
0x180002954  mov     rax, [rcx]
0x180002957  mov     rax, [rax+10h]
0x18000295b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002960  nop
0x180002961  add     rsp, 28h
0x180002965  retn
```
