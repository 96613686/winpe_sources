# ATL::CComClassFactory::LockServer(int)

- ea: `0x180002f70`
- end: `0x180002f99`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `41`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002f70`
- `0x18000e4a0`

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
0x180002f70  sub     rsp, 28h
0x180002f74  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002f7b  mov     rax, [rcx]
0x180002f7e  test    edx, edx
0x180002f80  jz      short loc_180002F88
0x180002f82  mov     rax, [rax+8]
0x180002f86  jmp     short loc_180002F8C
0x180002f88  mov     rax, [rax+10h]
0x180002f8c  call    cs:__guard_dispatch_icall_fptr
0x180002f92  xor     eax, eax
0x180002f94  add     rsp, 28h
0x180002f98  retn
```
