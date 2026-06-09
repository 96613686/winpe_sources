# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x18000ef10`
- end: `0x18000ef57`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `71`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180008cfc`
- `0x18000ef10`
- `0x18000f460`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(__int64 a1)
{
  unsigned int v1; // ebx
  void *v2; // r10

  v1 = ATL::SafeDecrementReferenceMultiThread((volatile int *)(a1 + 8));
  if ( v1 )
  {
    if ( v1 == 1 )
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  else if ( v2 )
  {
    ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(v2);
  }
  return v1;
}

```

## disassembly

```asm
0x18000ef10  push    rbx
0x18000ef12  sub     rsp, 20h
0x18000ef16  mov     r10, rcx
0x18000ef19  add     rcx, 8; volatile int *
0x18000ef1d  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000ef22  mov     ebx, eax
0x18000ef24  test    eax, eax
0x18000ef26  jnz     short loc_18000EF37
0x18000ef28  test    r10, r10
0x18000ef2b  jz      short loc_18000EF4F
0x18000ef2d  mov     rcx, r10; Block
0x18000ef30  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x18000ef35  jmp     short loc_18000EF4F
0x18000ef37  cmp     ebx, 1
0x18000ef3a  jnz     short loc_18000EF4F
0x18000ef3c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000ef43  mov     rax, [rcx]
0x18000ef46  mov     rax, [rax+10h]
0x18000ef4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef4f  mov     eax, ebx
0x18000ef51  add     rsp, 20h
0x18000ef55  pop     rbx
0x18000ef56  retn
```
