# ATL::CComClassFactory::LockServer(int)

- ea: `0x180004830`
- end: `0x180004858`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `40`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004830`
- `0x18000a010`

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
0x180004830  sub     rsp, 28h
0x180004834  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000483b  mov     rax, [rcx]
0x18000483e  test    edx, edx
0x180004840  jz      short loc_180004848
0x180004842  mov     rax, [rax+8]
0x180004846  jmp     short loc_18000484C
0x180004848  mov     rax, [rax+10h]
0x18000484c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004851  xor     eax, eax
0x180004853  add     rsp, 28h
0x180004857  retn
```
