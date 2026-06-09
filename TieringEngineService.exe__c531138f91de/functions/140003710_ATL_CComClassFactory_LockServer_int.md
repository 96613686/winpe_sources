# ATL::CComClassFactory::LockServer(int)

- ea: `0x140003710`
- end: `0x140003738`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `40`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140003710`
- `0x140041010`

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
0x140003710  sub     rsp, 28h
0x140003714  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x14000371b  mov     rax, [rcx]
0x14000371e  test    edx, edx
0x140003720  jz      short loc_140003728
0x140003722  mov     rax, [rax+8]
0x140003726  jmp     short loc_14000372C
0x140003728  mov     rax, [rax+10h]
0x14000372c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003731  xor     eax, eax
0x140003733  add     rsp, 28h
0x140003737  retn
```
