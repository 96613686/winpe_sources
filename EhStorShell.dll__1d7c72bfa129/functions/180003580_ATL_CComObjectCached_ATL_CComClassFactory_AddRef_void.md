# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180003580`
- end: `0x1800035b1`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `49`
- prototype: `unsigned int __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003580`
- `0x18000912c`
- `0x18000c010`

## pseudocode

```c
unsigned int __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(__int64 a1)
{
  unsigned int result; // eax

  result = ATL::SafeIncrementReferenceMultiThread((volatile int *)(a1 + 8));
  if ( result == 2 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    return 2;
  }
  return result;
}

```

## disassembly

```asm
0x180003580  push    rbx
0x180003582  sub     rsp, 20h
0x180003586  add     rcx, 8; volatile int *
0x18000358a  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18000358f  mov     ebx, eax
0x180003591  cmp     eax, 2
0x180003594  jnz     short loc_1800035AB
0x180003596  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000359d  mov     rax, [rcx]
0x1800035a0  mov     rax, [rax+8]
0x1800035a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035a9  mov     eax, ebx
0x1800035ab  add     rsp, 20h
0x1800035af  pop     rbx
0x1800035b0  retn
```
