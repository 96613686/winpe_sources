# ATL::CComClassFactory::LockServer(int)

- ea: `0x1800116a0`
- end: `0x1800116c8`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `40`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800116a0`
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
0x1800116a0  sub     rsp, 28h
0x1800116a4  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800116ab  mov     rax, [rcx]
0x1800116ae  test    edx, edx
0x1800116b0  jz      short loc_1800116B8
0x1800116b2  mov     rax, [rax+8]
0x1800116b6  jmp     short loc_1800116BC
0x1800116b8  mov     rax, [rax+10h]
0x1800116bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116c1  xor     eax, eax
0x1800116c3  add     rsp, 28h
0x1800116c7  retn
```
