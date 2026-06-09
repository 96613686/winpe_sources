# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180011450`
- end: `0x18001149a`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180011450`
- `0x180014010`

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
0x180011450  push    rbx
0x180011452  sub     rsp, 20h
0x180011456  mov     ebx, 7FFFFFFFh
0x18001145b  jmp     short loc_18001146B
0x18001145d  lea     edx, [r8+1]
0x180011461  mov     eax, r8d
0x180011464  lock cmpxchg [rcx+8], edx
0x180011469  jz      short loc_180011476
0x18001146b  mov     r8d, [rcx+8]
0x18001146f  cmp     r8d, ebx
0x180011472  jnz     short loc_18001145D
0x180011474  jmp     short loc_180011492
0x180011476  lea     ebx, [r8+1]
0x18001147a  cmp     ebx, 2
0x18001147d  jnz     short loc_180011492
0x18001147f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011486  mov     rax, [rcx]
0x180011489  mov     rax, [rax+8]
0x18001148d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011492  mov     eax, ebx
0x180011494  add     rsp, 20h
0x180011498  pop     rbx
0x180011499  retn
```
