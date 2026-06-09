# ATL::CComClassFactory::LockServer(int)

- ea: `0x140006120`
- end: `0x140006148`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `40`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006120`
- `0x140008010`

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
0x140006120  sub     rsp, 28h
0x140006124  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x14000612b  mov     rax, [rcx]
0x14000612e  test    edx, edx
0x140006130  jz      short loc_140006138
0x140006132  mov     rax, [rax+8]
0x140006136  jmp     short loc_14000613C
0x140006138  mov     rax, [rax+10h]
0x14000613c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006141  xor     eax, eax
0x140006143  add     rsp, 28h
0x140006147  retn
```
