# _dynamic_atexit_destructor_for___Module__

- ea: `0x18000c160`
- end: `0x18000c18f`
- name: `_dynamic_atexit_destructor_for___Module__`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800064c0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000c16b`
- `KERNEL32!DeleteCriticalSection` at `0x18000c16b`

## pseudocode

```c
void dynamic_atexit_destructor_for___Module__()
{
  unsigned int v0; // edx

  DeleteCriticalSection(&stru_1800128F0);
  _Module = &ATL::CComModule::`vftable';
  ATL::CAtlModule::Term((ATL::CAtlModule *)&_Module, v0);
}

```

## disassembly

```asm
0x18000c160  sub     rsp, 28h
0x18000c164  lea     rcx, stru_1800128F0; lpCriticalSection
0x18000c16b  call    cs:__imp_DeleteCriticalSection
0x18000c171  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x18000c178  lea     rcx, ?_Module@@3VCBrwCapModule@@A; this
0x18000c17f  mov     cs:?_Module@@3VCBrwCapModule@@A, rax; CBrwCapModule _Module
0x18000c186  add     rsp, 28h
0x18000c18a  jmp     ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
```
