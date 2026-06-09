# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x18000d250`
- end: `0x18000d29a`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000d250`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(__int64 a1)
{
  unsigned int v1; // ebx
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 8);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), v2 + 1, v2) )
    {
      v1 = v2 + 1;
      if ( v2 == 1 )
        (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
      return v1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18000d250  push    rbx
0x18000d252  sub     rsp, 20h
0x18000d256  mov     ebx, 7FFFFFFFh
0x18000d25b  jmp     short loc_18000D26B
0x18000d25d  lea     edx, [r8+1]
0x18000d261  mov     eax, r8d
0x18000d264  lock cmpxchg [rcx+8], edx
0x18000d269  jz      short loc_18000D276
0x18000d26b  mov     r8d, [rcx+8]
0x18000d26f  cmp     r8d, ebx
0x18000d272  jnz     short loc_18000D25D
0x18000d274  jmp     short loc_18000D292
0x18000d276  lea     ebx, [r8+1]
0x18000d27a  cmp     ebx, 2
0x18000d27d  jnz     short loc_18000D292
0x18000d27f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000d286  mov     rax, [rcx]
0x18000d289  mov     rax, [rax+8]
0x18000d28d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d292  mov     eax, ebx
0x18000d294  add     rsp, 20h
0x18000d298  pop     rbx
0x18000d299  retn
```
