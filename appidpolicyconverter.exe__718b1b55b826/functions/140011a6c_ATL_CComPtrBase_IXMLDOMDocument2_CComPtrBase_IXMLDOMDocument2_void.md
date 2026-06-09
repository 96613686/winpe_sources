# ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)

- ea: `0x140011a6c`
- end: `0x140011a8a`
- name: `??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `24`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400118bc`
- `0x140011a54`
- `0x140011aa8`
- `0x140011c40`
- `0x140011fa0`
- `0x140012138`
- `0x140012278`
- `0x140012764`
- `0x140012950`
- `0x140012e1c`
- `0x1400130ec`
- `0x140013548`
- `0x140014f51`
- `0x140014f63`
- `0x140014f8b`
- `0x140014fc9`
- `0x140015041`
- `0x1400150a7`
- `0x140015113`
- `0x140015125`
- `0x140015137`
- `0x1400151ab`
- `0x1400152d9`
- `0x140015387`

## callees

- `0x140011a6c`
- `0x140016010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(__int64 *a1)
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
0x140011a6c  sub     rsp, 28h
0x140011a70  mov     rcx, [rcx]
0x140011a73  test    rcx, rcx
0x140011a76  jz      short loc_140011A85
0x140011a78  mov     rax, [rcx]
0x140011a7b  mov     rax, [rax+10h]
0x140011a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011a84  nop
0x140011a85  add     rsp, 28h
0x140011a89  retn
```
