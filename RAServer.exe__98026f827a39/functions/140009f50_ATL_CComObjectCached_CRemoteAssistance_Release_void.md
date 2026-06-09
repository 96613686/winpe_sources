# ATL::CComObjectCached<CRemoteAssistance>::Release(void)

- ea: `0x140009f50`
- end: `0x140009f97`
- name: `?Release@?$CComObjectCached@VCRemoteAssistance@@@ATL@@UEAAKXZ`
- size: `71`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140009fa0`

## callees

- `0x140003ed8`
- `0x140009f50`
- `0x14000a230`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<CRemoteAssistance>::Release(__int64 a1)
{
  unsigned int v1; // ebx
  void *v2; // r10

  v1 = ATL::SafeDecrementReferenceMultiThread((volatile int *)(a1 + 16));
  if ( v1 )
  {
    if ( v1 == 1 )
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  else if ( v2 )
  {
    ATL::CComObjectCached<CRemoteAssistance>::`scalar deleting destructor'(v2);
  }
  return v1;
}

```

## disassembly

```asm
0x140009f50  push    rbx
0x140009f52  sub     rsp, 20h
0x140009f56  mov     r10, rcx
0x140009f59  add     rcx, 10h; volatile int *
0x140009f5d  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x140009f62  mov     ebx, eax
0x140009f64  test    eax, eax
0x140009f66  jnz     short loc_140009F77
0x140009f68  test    r10, r10
0x140009f6b  jz      short loc_140009F8F
0x140009f6d  mov     rcx, r10
0x140009f70  call    ??_G?$CComObjectCached@VCRemoteAssistance@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<CRemoteAssistance>::`scalar deleting destructor'(uint)
0x140009f75  jmp     short loc_140009F8F
0x140009f77  cmp     ebx, 1
0x140009f7a  jnz     short loc_140009F8F
0x140009f7c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140009f83  mov     rax, [rcx]
0x140009f86  mov     rax, [rax+10h]
0x140009f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009f8f  mov     eax, ebx
0x140009f91  add     rsp, 20h
0x140009f95  pop     rbx
0x140009f96  retn
```
