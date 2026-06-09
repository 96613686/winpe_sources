# ATL::CComClassFactory::LockServer(int)

- ea: `0x1800048a0`
- end: `0x1800048c8`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `40`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800048a0`
- `0x18000d010`

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
0x1800048a0  sub     rsp, 28h
0x1800048a4  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800048ab  mov     rax, [rcx]
0x1800048ae  test    edx, edx
0x1800048b0  jz      short loc_1800048B8
0x1800048b2  mov     rax, [rax+8]
0x1800048b6  jmp     short loc_1800048BC
0x1800048b8  mov     rax, [rax+10h]
0x1800048bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048c1  xor     eax, eax
0x1800048c3  add     rsp, 28h
0x1800048c7  retn
```
