# ATL::CComObjectRootBase::_Delegate(void *,_GUID const &,void * *,unsigned __int64)

- ea: `0x1800070c0`
- end: `0x1800070e2`
- name: `?_Delegate@CComObjectRootBase@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX_K@Z`
- size: `34`
- prototype: `__int64 __fastcall(void *, const struct _GUID *, void **, unsigned __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800070c0`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectRootBase::_Delegate(char *a1, const struct _GUID *a2, void **a3, __int64 a4)
{
  __int64 (__fastcall ***v4)(_QWORD, const struct _GUID *, void **); // rcx
  __int64 result; // rax

  v4 = *(__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))&a1[a4];
  result = 2147500034LL;
  if ( v4 )
    return (**v4)(v4, a2, a3);
  return result;
}

```

## disassembly

```asm
0x1800070c0  sub     rsp, 28h
0x1800070c4  mov     rcx, [rcx+r9]
0x1800070c8  mov     eax, 80004002h
0x1800070cd  test    rcx, rcx
0x1800070d0  jz      short loc_1800070DD
0x1800070d2  mov     rax, [rcx]
0x1800070d5  mov     rax, [rax]
0x1800070d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070dd  add     rsp, 28h
0x1800070e1  retn
```
