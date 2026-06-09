# ATL::CComClassFactory::LockServer(int)

- ea: `0x1800096e0`
- end: `0x180009708`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `40`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800096e0`
- `0x180017010`

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
0x1800096e0  sub     rsp, 28h
0x1800096e4  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800096eb  mov     rax, [rcx]
0x1800096ee  test    edx, edx
0x1800096f0  jz      short loc_1800096F8
0x1800096f2  mov     rax, [rax+8]
0x1800096f6  jmp     short loc_1800096FC
0x1800096f8  mov     rax, [rax+10h]
0x1800096fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009701  xor     eax, eax
0x180009703  add     rsp, 28h
0x180009707  retn
```
