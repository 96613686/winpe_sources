# ProjectionIterator<ConfigPathToConfigLocationSelector>::~ProjectionIterator<ConfigPathToConfigLocationSelector>(void)

- ea: `0x1800076c0`
- end: `0x1800076f4`
- name: `??1?$ProjectionIterator@VConfigPathToConfigLocationSelector@@@@UEAA@XZ`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007890`

## callees

- `0x1800021a4`
- `0x1800039b0`

## pseudocode

```c
void __fastcall ProjectionIterator<ConfigPathToConfigLocationSelector>::~ProjectionIterator<ConfigPathToConfigLocationSelector>(
        _QWORD *a1)
{
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(a1 + 4);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(a1 + 3);
  ModuleRefCounter::Release();
  *a1 = &SimpleIUnknownImpl<IXPathNodeIterator>::`vftable';
  ModuleRefCounter::Release();
}

```

## disassembly

```asm
0x1800076c0  push    rbx
0x1800076c2  sub     rsp, 20h
0x1800076c6  mov     rbx, rcx
0x1800076c9  add     rcx, 20h ; ' '
0x1800076cd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800076d2  lea     rcx, [rbx+18h]
0x1800076d6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800076db  call    ?Release@ModuleRefCounter@@SAXXZ; ModuleRefCounter::Release(void)
0x1800076e0  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathNodeIterator@@@@6B@; const SimpleIUnknownImpl<IXPathNodeIterator>::`vftable'
0x1800076e7  mov     [rbx], rax
0x1800076ea  add     rsp, 20h
0x1800076ee  pop     rbx
0x1800076ef  jmp     ?Release@ModuleRefCounter@@SAXXZ; ModuleRefCounter::Release(void)
```
