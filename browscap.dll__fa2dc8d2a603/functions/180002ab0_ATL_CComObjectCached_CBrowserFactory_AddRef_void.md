# ATL::CComObjectCached<CBrowserFactory>::AddRef(void)

- ea: `0x180002ab0`
- end: `0x180002afa`
- name: `?AddRef@?$CComObjectCached@VCBrowserFactory@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002ab0`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<CBrowserFactory>::AddRef(__int64 a1)
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
0x180002ab0  push    rbx
0x180002ab2  sub     rsp, 20h
0x180002ab6  mov     ebx, 7FFFFFFFh
0x180002abb  jmp     short loc_180002ACB
0x180002abd  lea     edx, [r8+1]
0x180002ac1  mov     eax, r8d
0x180002ac4  lock cmpxchg [rcx+8], edx
0x180002ac9  jz      short loc_180002AD6
0x180002acb  mov     r8d, [rcx+8]
0x180002acf  cmp     r8d, ebx
0x180002ad2  jnz     short loc_180002ABD
0x180002ad4  jmp     short loc_180002AF2
0x180002ad6  lea     ebx, [r8+1]
0x180002ada  cmp     ebx, 2
0x180002add  jnz     short loc_180002AF2
0x180002adf  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002ae6  mov     rax, [rcx]
0x180002ae9  mov     rax, [rax+8]
0x180002aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002af2  mov     eax, ebx
0x180002af4  add     rsp, 20h
0x180002af8  pop     rbx
0x180002af9  retn
```
