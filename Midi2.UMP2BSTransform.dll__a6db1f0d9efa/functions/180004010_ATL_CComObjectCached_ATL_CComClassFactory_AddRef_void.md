# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180004010`
- end: `0x18000405a`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004010`
- `0x18000f010`

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
0x180004010  push    rbx
0x180004012  sub     rsp, 20h
0x180004016  mov     ebx, 7FFFFFFFh
0x18000401b  jmp     short loc_18000402B
0x18000401d  lea     edx, [r8+1]
0x180004021  mov     eax, r8d
0x180004024  lock cmpxchg [rcx+8], edx
0x180004029  jz      short loc_180004036
0x18000402b  mov     r8d, [rcx+8]
0x18000402f  cmp     r8d, ebx
0x180004032  jnz     short loc_18000401D
0x180004034  jmp     short loc_180004052
0x180004036  lea     ebx, [r8+1]
0x18000403a  cmp     ebx, 2
0x18000403d  jnz     short loc_180004052
0x18000403f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004046  mov     rax, [rcx]
0x180004049  mov     rax, [rax+8]
0x18000404d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004052  mov     eax, ebx
0x180004054  add     rsp, 20h
0x180004058  pop     rbx
0x180004059  retn
```
