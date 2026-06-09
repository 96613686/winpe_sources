# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180004120`
- end: `0x18000416a`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004120`
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
0x180004120  push    rbx
0x180004122  sub     rsp, 20h
0x180004126  mov     ebx, 7FFFFFFFh
0x18000412b  jmp     short loc_18000413B
0x18000412d  lea     edx, [r8+1]
0x180004131  mov     eax, r8d
0x180004134  lock cmpxchg [rcx+8], edx
0x180004139  jz      short loc_180004146
0x18000413b  mov     r8d, [rcx+8]
0x18000413f  cmp     r8d, ebx
0x180004142  jnz     short loc_18000412D
0x180004144  jmp     short loc_180004162
0x180004146  lea     ebx, [r8+1]
0x18000414a  cmp     ebx, 2
0x18000414d  jnz     short loc_180004162
0x18000414f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004156  mov     rax, [rcx]
0x180004159  mov     rax, [rax+8]
0x18000415d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004162  mov     eax, ebx
0x180004164  add     rsp, 20h
0x180004168  pop     rbx
0x180004169  retn
```
