# ATL::CComClassFactory::LockServer(int)

- ea: `0x180006f10`
- end: `0x180006f38`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `40`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006f10`
- `0x180013010`

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
0x180006f10  sub     rsp, 28h
0x180006f14  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006f1b  mov     rax, [rcx]
0x180006f1e  test    edx, edx
0x180006f20  jz      short loc_180006F28
0x180006f22  mov     rax, [rax+8]
0x180006f26  jmp     short loc_180006F2C
0x180006f28  mov     rax, [rax+10h]
0x180006f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f31  xor     eax, eax
0x180006f33  add     rsp, 28h
0x180006f37  retn
```
