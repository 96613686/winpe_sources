# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x1800052a0`
- end: `0x1800052ea`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800052a0`
- `0x180007010`

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
0x1800052a0  push    rbx
0x1800052a2  sub     rsp, 20h
0x1800052a6  mov     ebx, 7FFFFFFFh
0x1800052ab  jmp     short loc_1800052BB
0x1800052ad  lea     edx, [r8+1]
0x1800052b1  mov     eax, r8d
0x1800052b4  lock cmpxchg [rcx+8], edx
0x1800052b9  jz      short loc_1800052C6
0x1800052bb  mov     r8d, [rcx+8]
0x1800052bf  cmp     r8d, ebx
0x1800052c2  jnz     short loc_1800052AD
0x1800052c4  jmp     short loc_1800052E2
0x1800052c6  lea     ebx, [r8+1]
0x1800052ca  cmp     ebx, 2
0x1800052cd  jnz     short loc_1800052E2
0x1800052cf  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800052d6  mov     rax, [rcx]
0x1800052d9  mov     rax, [rax+8]
0x1800052dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052e2  mov     eax, ebx
0x1800052e4  add     rsp, 20h
0x1800052e8  pop     rbx
0x1800052e9  retn
```
