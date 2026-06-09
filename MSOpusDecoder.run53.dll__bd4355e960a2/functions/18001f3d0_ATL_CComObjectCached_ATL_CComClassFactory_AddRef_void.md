# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x18001f3d0`
- end: `0x18001f41a`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001f3d0`
- `0x180024010`

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
0x18001f3d0  push    rbx
0x18001f3d2  sub     rsp, 20h
0x18001f3d6  mov     ebx, 7FFFFFFFh
0x18001f3db  jmp     short loc_18001F3EB
0x18001f3dd  lea     edx, [r8+1]
0x18001f3e1  mov     eax, r8d
0x18001f3e4  lock cmpxchg [rcx+8], edx
0x18001f3e9  jz      short loc_18001F3F6
0x18001f3eb  mov     r8d, [rcx+8]
0x18001f3ef  cmp     r8d, ebx
0x18001f3f2  jnz     short loc_18001F3DD
0x18001f3f4  jmp     short loc_18001F412
0x18001f3f6  lea     ebx, [r8+1]
0x18001f3fa  cmp     ebx, 2
0x18001f3fd  jnz     short loc_18001F412
0x18001f3ff  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001f406  mov     rax, [rcx]
0x18001f409  mov     rax, [rax+8]
0x18001f40d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f412  mov     eax, ebx
0x18001f414  add     rsp, 20h
0x18001f418  pop     rbx
0x18001f419  retn
```
