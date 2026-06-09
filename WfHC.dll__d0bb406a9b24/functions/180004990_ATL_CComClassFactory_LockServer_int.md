# ATL::CComClassFactory::LockServer(int)

- ea: `0x180004990`
- end: `0x1800049c2`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `50`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004990`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::LockServer(ATL::CComClassFactory *this, int a2)
{
  __int64 v2; // rax

  v2 = *(_QWORD *)ATL::_pAtlModule;
  if ( a2 )
    (*(void (**)(void))(v2 + 8))();
  else
    (*(void (**)(void))(v2 + 16))();
  return 0;
}

```

## disassembly

```asm
0x180004990  sub     rsp, 28h
0x180004994  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000499b  mov     rax, [rcx]
0x18000499e  test    edx, edx
0x1800049a0  jz      short loc_1800049B2
0x1800049a2  mov     rax, [rax+8]
0x1800049a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ab  xor     eax, eax
0x1800049ad  add     rsp, 28h
0x1800049b1  retn
0x1800049b2  mov     rax, [rax+10h]
0x1800049b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049bb  xor     eax, eax
0x1800049bd  add     rsp, 28h
0x1800049c1  retn
```
