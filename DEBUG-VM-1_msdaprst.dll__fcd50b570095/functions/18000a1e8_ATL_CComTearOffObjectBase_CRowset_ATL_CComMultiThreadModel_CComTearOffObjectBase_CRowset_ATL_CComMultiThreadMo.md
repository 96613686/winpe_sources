# ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)

- ea: `0x18000a1e8`
- end: `0x18000a207`
- name: `??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ad40`
- `0x18000ae20`
- `0x18000af00`
- `0x18000afe0`
- `0x18000b0c0`
- `0x18000b1b0`
- `0x18000b290`
- `0x18000b3a0`
- `0x18000b490`
- `0x18000b570`
- `0x18000b650`

## callees

- `0x18000a1c0`

## pseudocode

```c
__int64 __fastcall ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(
        __int64 a1)
{
  __int64 result; // rax

  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>();
  result = a1;
  *(_QWORD *)(a1 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x18000a1e8  push    rbx
0x18000a1ea  sub     rsp, 20h
0x18000a1ee  mov     rbx, rcx
0x18000a1f1  call    ??0?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>(void)
0x18000a1f6  mov     rax, rbx
0x18000a1f9  mov     qword ptr [rbx+10h], 0
0x18000a201  add     rsp, 20h
0x18000a205  pop     rbx
0x18000a206  retn
```
