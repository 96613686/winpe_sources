# ATL::CComClassFactory::LockServer(int)

- ea: `0x1800111f0`
- end: `0x180011218`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `40`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800111f0`
- `0x180018010`

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
0x1800111f0  sub     rsp, 28h
0x1800111f4  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800111fb  mov     rax, [rcx]
0x1800111fe  test    edx, edx
0x180011200  jz      short loc_180011208
0x180011202  mov     rax, [rax+8]
0x180011206  jmp     short loc_18001120C
0x180011208  mov     rax, [rax+10h]
0x18001120c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011211  xor     eax, eax
0x180011213  add     rsp, 28h
0x180011217  retn
```
