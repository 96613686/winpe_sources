# ATL::CComClassFactory::LockServer(int)

- ea: `0x180007550`
- end: `0x180007578`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `40`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007550`
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
0x180007550  sub     rsp, 28h
0x180007554  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000755b  mov     rax, [rcx]
0x18000755e  test    edx, edx
0x180007560  jz      short loc_180007568
0x180007562  mov     rax, [rax+8]
0x180007566  jmp     short loc_18000756C
0x180007568  mov     rax, [rax+10h]
0x18000756c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007571  xor     eax, eax
0x180007573  add     rsp, 28h
0x180007577  retn
```
