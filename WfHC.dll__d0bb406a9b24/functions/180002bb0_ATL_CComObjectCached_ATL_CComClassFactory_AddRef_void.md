# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180002bb0`
- end: `0x180002bff`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `79`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002bb0`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(__int64 a1)
{
  signed __int32 v1; // eax
  unsigned __int32 v2; // ebx

  v1 = *(_DWORD *)(a1 + 8);
  if ( v1 == 0x7FFFFFFF )
    return 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = v1 + 1;
    if ( v1 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), v1 + 1, v1) )
      break;
    v1 = *(_DWORD *)(a1 + 8);
    if ( v1 == 0x7FFFFFFF )
      return 0x7FFFFFFF;
  }
  if ( v1 == 1 )
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  return v2;
}

```

## disassembly

```asm
0x180002bb0  push    rbx
0x180002bb2  sub     rsp, 20h
0x180002bb6  mov     eax, [rcx+8]
0x180002bb9  cmp     eax, 7FFFFFFFh
0x180002bbe  jz      short loc_180002BD4
0x180002bc0  lea     ebx, [rax+1]
0x180002bc3  lock cmpxchg [rcx+8], ebx
0x180002bc8  jz      short loc_180002BDF
0x180002bca  mov     eax, [rcx+8]
0x180002bcd  cmp     eax, 7FFFFFFFh
0x180002bd2  jnz     short loc_180002BC0
0x180002bd4  mov     eax, 7FFFFFFFh
0x180002bd9  add     rsp, 20h
0x180002bdd  pop     rbx
0x180002bde  retn
0x180002bdf  cmp     ebx, 2
0x180002be2  jnz     short loc_180002BF7
0x180002be4  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002beb  mov     rdx, [rcx]
0x180002bee  mov     rax, [rdx+8]
0x180002bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bf7  mov     eax, ebx
0x180002bf9  add     rsp, 20h
0x180002bfd  pop     rbx
0x180002bfe  retn
```
