# ATL::CComClassFactory::LockServer(int)

- ea: `0x180004ec0`
- end: `0x180004ee8`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `40`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004ec0`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::LockServer(ATL::CComClassFactory *this, int a2)
{
  __int64 v2; // rax
  void (*v3)(void); // rax

  v2 = *(_QWORD *)ATL::_pAtlModule;
  if ( a2 )
    v3 = *(void (**)(void))(v2 + 8);
  else
    v3 = *(void (**)(void))(v2 + 16);
  v3();
  return 0;
}

```

## disassembly

```asm
0x180004ec0  sub     rsp, 28h
0x180004ec4  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004ecb  mov     rax, [rcx]
0x180004ece  test    edx, edx
0x180004ed0  jz      short loc_180004ED8
0x180004ed2  mov     rax, [rax+8]
0x180004ed6  jmp     short loc_180004EDC
0x180004ed8  mov     rax, [rax+10h]
0x180004edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ee1  xor     eax, eax
0x180004ee3  add     rsp, 28h
0x180004ee7  retn
```
