# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180009600`
- end: `0x180009631`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180009600`
- `0x18000f488`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(__int64 a1)
{
  unsigned int v1; // ebx

  v1 = ATL::SafeIncrementReferenceMultiThread((volatile int *)(a1 + 8));
  if ( v1 == 2 )
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  return v1;
}

```

## disassembly

```asm
0x180009600  push    rbx
0x180009602  sub     rsp, 20h
0x180009606  add     rcx, 8; volatile int *
0x18000960a  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18000960f  mov     ebx, eax
0x180009611  cmp     eax, 2
0x180009614  jnz     short loc_180009629
0x180009616  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000961d  mov     rdx, [rcx]
0x180009620  mov     rax, [rdx+8]
0x180009624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009629  mov     eax, ebx
0x18000962b  add     rsp, 20h
0x18000962f  pop     rbx
0x180009630  retn
```
