# ATL::CComPtr<IXMLDOMNodeList>::CComPtr<IXMLDOMNodeList>(ATL::CComPtr<IXMLDOMNodeList> const &)

- ea: `0x140011888`
- end: `0x1400118b6`
- name: `??0?$CComPtr@UIXMLDOMNodeList@@@ATL@@QEAA@AEBV01@@Z`
- size: `46`
- prototype: `__int64 *__fastcall(__int64 *, __int64 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140011974`
- `0x140011c40`
- `0x140011e84`
- `0x140012764`
- `0x140012950`
- `0x140013548`

## callees

- `0x140011888`
- `0x140016010`

## pseudocode

```c
__int64 *__fastcall ATL::CComPtr<IXMLDOMNodeList>::CComPtr<IXMLDOMNodeList>(__int64 *a1, __int64 *a2)
{
  __int64 v3; // rcx

  v3 = *a2;
  *a1 = *a2;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  return a1;
}

```

## disassembly

```asm
0x140011888  mov     [rsp+arg_0], rcx
0x14001188d  push    rbx
0x14001188e  sub     rsp, 20h
0x140011892  mov     rbx, rcx
0x140011895  mov     rcx, [rdx]
0x140011898  mov     [rbx], rcx
0x14001189b  test    rcx, rcx
0x14001189e  jz      short loc_1400118AD
0x1400118a0  mov     rax, [rcx]
0x1400118a3  mov     rax, [rax+8]
0x1400118a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400118ac  nop
0x1400118ad  mov     rax, rbx
0x1400118b0  add     rsp, 20h
0x1400118b4  pop     rbx
0x1400118b5  retn
```
