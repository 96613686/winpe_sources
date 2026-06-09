# ATL::CComPtrBase<IXPathNavigator>::CopyTo(IXPathNavigator * *)

- ea: `0x180007b04`
- end: `0x180007b35`
- name: `?CopyTo@?$CComPtrBase@UIXPathNavigator@@@ATL@@QEAAJPEAPEAUIXPathNavigator@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008b20`
- `0x180008c40`
- `0x180008d50`
- `0x18000ef70`

## callees

- `0x180007b04`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IXPathNavigator>::CopyTo(_QWORD *a1, _QWORD *a2)
{
  __int64 v3; // rcx

  if ( !a2 )
    return 2147500035LL;
  *a2 = *a1;
  v3 = *a1;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  return 0;
}

```

## disassembly

```asm
0x180007b04  sub     rsp, 28h
0x180007b08  test    rdx, rdx
0x180007b0b  jnz     short loc_180007B14
0x180007b0d  mov     eax, 80004003h
0x180007b12  jmp     short loc_180007B30
0x180007b14  mov     rax, [rcx]
0x180007b17  mov     [rdx], rax
0x180007b1a  mov     rcx, [rcx]
0x180007b1d  test    rcx, rcx
0x180007b20  jz      short loc_180007B2E
0x180007b22  mov     rax, [rcx]
0x180007b25  mov     rax, [rax+8]
0x180007b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b2e  xor     eax, eax
0x180007b30  add     rsp, 28h
0x180007b34  retn
```
