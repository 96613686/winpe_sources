# ATL::CComClassFactory::LockServer(int)

- ea: `0x180003590`
- end: `0x1800035b1`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `33`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003590`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::LockServer(ATL::CComClassFactory *this, int a2)
{
  __int64 v2; // rax

  v2 = *(_QWORD *)ATL::_pAtlModule;
  if ( a2 )
    (*(void (**)(void))(v2 + 8))();
  else
    (*(void (**)(void))(v2 + 16))();
  return 0;
}

```

## disassembly

```asm
0x180003590  sub     rsp, 28h
0x180003594  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000359b  mov     rax, [rcx]
0x18000359e  test    edx, edx
0x1800035a0  jz      short loc_1800035A7
0x1800035a2  call    qword ptr [rax+8]
0x1800035a5  jmp     short loc_1800035AA
0x1800035a7  call    qword ptr [rax+10h]
0x1800035aa  xor     eax, eax
0x1800035ac  add     rsp, 28h
0x1800035b0  retn
```
