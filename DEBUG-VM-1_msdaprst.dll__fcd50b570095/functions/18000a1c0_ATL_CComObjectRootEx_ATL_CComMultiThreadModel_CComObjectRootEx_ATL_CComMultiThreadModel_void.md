# ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>(void)

- ea: `0x18000a1c0`
- end: `0x18000a1e2`
- name: `??0?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `10`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a1e8`
- `0x180013d20`
- `0x180013dec`
- `0x180018f10`
- `0x18001faf0`
- `0x180020dec`
- `0x180020e74`
- `0x180022fa8`
- `0x18002ce20`
- `0x18002db9c`

## import_xrefs

- `MSDART!MPInitializeCriticalSection` at `0x18000a1d3`
- `MSDART!MPInitializeCriticalSection` at `0x18000a1d3`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>(
        _DWORD *a1)
{
  *a1 = 0;
  MPInitializeCriticalSection(a1 + 2);
  return a1;
}

```

## disassembly

```asm
0x18000a1c0  push    rbx
0x18000a1c2  sub     rsp, 20h
0x18000a1c6  mov     rbx, rcx
0x18000a1c9  mov     dword ptr [rcx], 0
0x18000a1cf  add     rcx, 8
0x18000a1d3  call    cs:__imp_MPInitializeCriticalSection
0x18000a1d9  mov     rax, rbx
0x18000a1dc  add     rsp, 20h
0x18000a1e0  pop     rbx
0x18000a1e1  retn
```
