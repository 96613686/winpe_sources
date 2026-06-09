# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x18000bd80`
- end: `0x18000bdd1`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `81`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000bd80`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(__int64 a1)
{
  signed __int32 v1; // eax
  unsigned __int32 v3; // ebx

  v1 = *(_DWORD *)(a1 + 8);
  if ( v1 == 0x7FFFFFFF )
    return 0x7FFFFFFF;
  while ( 1 )
  {
    v3 = v1 + 1;
    if ( v1 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), v1 + 1, v1) )
      break;
    v1 = *(_DWORD *)(a1 + 8);
    if ( v1 == 0x7FFFFFFF )
      return 0x7FFFFFFF;
  }
  if ( v1 == 1 )
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  return v3;
}

```

## disassembly

```asm
0x18000bd80  push    rbx
0x18000bd82  sub     rsp, 20h
0x18000bd86  mov     eax, [rcx+8]
0x18000bd89  cmp     eax, 7FFFFFFFh
0x18000bd8e  jnz     short loc_18000BDBB
0x18000bd90  mov     eax, 7FFFFFFFh
0x18000bd95  add     rsp, 20h
0x18000bd99  pop     rbx
0x18000bd9a  retn
0x18000bd9b  cmp     ebx, 2
0x18000bd9e  jnz     short loc_18000BDB3
0x18000bda0  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000bda7  mov     rax, [rcx]
0x18000bdaa  mov     rax, [rax+8]
0x18000bdae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdb3  mov     eax, ebx
0x18000bdb5  add     rsp, 20h
0x18000bdb9  pop     rbx
0x18000bdba  retn
0x18000bdbb  lea     ebx, [rax+1]
0x18000bdbe  lock cmpxchg [rcx+8], ebx
0x18000bdc3  jz      short loc_18000BD9B
0x18000bdc5  mov     eax, [rcx+8]
0x18000bdc8  cmp     eax, 7FFFFFFFh
0x18000bdcd  jnz     short loc_18000BDBB
0x18000bdcf  jmp     short loc_18000BD90
```
