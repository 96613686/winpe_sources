# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x1800066f0`
- end: `0x18000673a`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800066f0`
- `0x18000e010`

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
0x1800066f0  push    rbx
0x1800066f2  sub     rsp, 20h
0x1800066f6  mov     ebx, 7FFFFFFFh
0x1800066fb  jmp     short loc_18000670B
0x1800066fd  lea     edx, [r8+1]
0x180006701  mov     eax, r8d
0x180006704  lock cmpxchg [rcx+8], edx
0x180006709  jz      short loc_180006716
0x18000670b  mov     r8d, [rcx+8]
0x18000670f  cmp     r8d, ebx
0x180006712  jnz     short loc_1800066FD
0x180006714  jmp     short loc_180006732
0x180006716  lea     ebx, [r8+1]
0x18000671a  cmp     ebx, 2
0x18000671d  jnz     short loc_180006732
0x18000671f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006726  mov     rax, [rcx]
0x180006729  mov     rax, [rax+8]
0x18000672d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006732  mov     eax, ebx
0x180006734  add     rsp, 20h
0x180006738  pop     rbx
0x180006739  retn
```
