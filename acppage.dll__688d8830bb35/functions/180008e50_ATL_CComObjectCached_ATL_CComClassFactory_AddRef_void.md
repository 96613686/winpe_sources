# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180008e50`
- end: `0x180008e9a`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008e50`
- `0x180017010`

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
0x180008e50  push    rbx
0x180008e52  sub     rsp, 20h
0x180008e56  mov     ebx, 7FFFFFFFh
0x180008e5b  jmp     short loc_180008E6B
0x180008e5d  lea     edx, [r8+1]
0x180008e61  mov     eax, r8d
0x180008e64  lock cmpxchg [rcx+8], edx
0x180008e69  jz      short loc_180008E76
0x180008e6b  mov     r8d, [rcx+8]
0x180008e6f  cmp     r8d, ebx
0x180008e72  jnz     short loc_180008E5D
0x180008e74  jmp     short loc_180008E92
0x180008e76  lea     ebx, [r8+1]
0x180008e7a  cmp     ebx, 2
0x180008e7d  jnz     short loc_180008E92
0x180008e7f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008e86  mov     rax, [rcx]
0x180008e89  mov     rax, [rax+8]
0x180008e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e92  mov     eax, ebx
0x180008e94  add     rsp, 20h
0x180008e98  pop     rbx
0x180008e99  retn
```
