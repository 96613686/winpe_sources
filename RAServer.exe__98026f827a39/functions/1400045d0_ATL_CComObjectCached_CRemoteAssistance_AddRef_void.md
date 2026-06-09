# ATL::CComObjectCached<CRemoteAssistance>::AddRef(void)

- ea: `0x1400045d0`
- end: `0x140004601`
- name: `?AddRef@?$CComObjectCached@VCRemoteAssistance@@@ATL@@UEAAKXZ`
- size: `49`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140004610`

## callees

- `0x1400045d0`
- `0x14000a258`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<CRemoteAssistance>::AddRef(__int64 a1)
{
  unsigned int v1; // ebx

  v1 = ATL::SafeIncrementReferenceMultiThread((volatile int *)(a1 + 16));
  if ( v1 == 2 )
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  return v1;
}

```

## disassembly

```asm
0x1400045d0  push    rbx
0x1400045d2  sub     rsp, 20h
0x1400045d6  add     rcx, 10h; volatile int *
0x1400045da  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x1400045df  mov     ebx, eax
0x1400045e1  cmp     eax, 2
0x1400045e4  jnz     short loc_1400045F9
0x1400045e6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400045ed  mov     rdx, [rcx]
0x1400045f0  mov     rax, [rdx+8]
0x1400045f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045f9  mov     eax, ebx
0x1400045fb  add     rsp, 20h
0x1400045ff  pop     rbx
0x140004600  retn
```
