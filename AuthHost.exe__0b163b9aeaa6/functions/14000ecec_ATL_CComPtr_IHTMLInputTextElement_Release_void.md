# ATL::CComPtr<IHTMLInputTextElement>::Release(void)

- ea: `0x14000ecec`
- end: `0x14000ed13`
- name: `?Release@?$CComPtr@UIHTMLInputTextElement@@@ATL@@QEAAXXZ`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000ed48`

## callees

- `0x14000ecec`
- `0x140014010`

## pseudocode

```c
_QWORD *__fastcall ATL::CComPtr<IHTMLInputTextElement>::Release(_QWORD *a1)
{
  _QWORD *result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x14000ecec  sub     rsp, 28h
0x14000ecf0  mov     rax, rcx
0x14000ecf3  mov     rcx, [rcx]
0x14000ecf6  test    rcx, rcx
0x14000ecf9  jz      short loc_14000ED0E
0x14000ecfb  mov     qword ptr [rax], 0
0x14000ed02  mov     rax, [rcx]
0x14000ed05  mov     rax, [rax+10h]
0x14000ed09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ed0e  add     rsp, 28h
0x14000ed12  retn
```
