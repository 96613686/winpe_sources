# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180004560`
- end: `0x1800045aa`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004560`
- `0x18000b010`

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
        (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
      return v1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180004560  push    rbx
0x180004562  sub     rsp, 20h
0x180004566  mov     ebx, 7FFFFFFFh
0x18000456b  jmp     short loc_18000457B
0x18000456d  lea     edx, [r8+1]
0x180004571  mov     eax, r8d
0x180004574  lock cmpxchg [rcx+8], edx
0x180004579  jz      short loc_180004586
0x18000457b  mov     r8d, [rcx+8]
0x18000457f  cmp     r8d, ebx
0x180004582  jnz     short loc_18000456D
0x180004584  jmp     short loc_1800045A2
0x180004586  lea     ebx, [r8+1]
0x18000458a  cmp     ebx, 2
0x18000458d  jnz     short loc_1800045A2
0x18000458f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004596  mov     rax, [rcx]
0x180004599  mov     rax, [rax+8]
0x18000459d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045a2  mov     eax, ebx
0x1800045a4  add     rsp, 20h
0x1800045a8  pop     rbx
0x1800045a9  retn
```
