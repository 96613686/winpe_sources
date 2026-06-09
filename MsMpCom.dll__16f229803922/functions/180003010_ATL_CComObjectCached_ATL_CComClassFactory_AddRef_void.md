# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180003010`
- end: `0x18000305a`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003010`
- `0x18000a010`

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
0x180003010  push    rbx
0x180003012  sub     rsp, 20h
0x180003016  mov     ebx, 7FFFFFFFh
0x18000301b  jmp     short loc_18000302B
0x18000301d  lea     edx, [r8+1]
0x180003021  mov     eax, r8d
0x180003024  lock cmpxchg [rcx+8], edx
0x180003029  jz      short loc_180003036
0x18000302b  mov     r8d, [rcx+8]
0x18000302f  cmp     r8d, ebx
0x180003032  jnz     short loc_18000301D
0x180003034  jmp     short loc_180003052
0x180003036  lea     ebx, [r8+1]
0x18000303a  cmp     ebx, 2
0x18000303d  jnz     short loc_180003052
0x18000303f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003046  mov     rax, [rcx]
0x180003049  mov     rax, [rax+8]
0x18000304d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003052  mov     eax, ebx
0x180003054  add     rsp, 20h
0x180003058  pop     rbx
0x180003059  retn
```
