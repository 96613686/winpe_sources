# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180003f80`
- end: `0x180003fca`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003f80`
- `0x18000c010`

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
0x180003f80  push    rbx
0x180003f82  sub     rsp, 20h
0x180003f86  mov     ebx, 7FFFFFFFh
0x180003f8b  jmp     short loc_180003F9B
0x180003f8d  lea     edx, [r8+1]
0x180003f91  mov     eax, r8d
0x180003f94  lock cmpxchg [rcx+8], edx
0x180003f99  jz      short loc_180003FA6
0x180003f9b  mov     r8d, [rcx+8]
0x180003f9f  cmp     r8d, ebx
0x180003fa2  jnz     short loc_180003F8D
0x180003fa4  jmp     short loc_180003FC2
0x180003fa6  lea     ebx, [r8+1]
0x180003faa  cmp     ebx, 2
0x180003fad  jnz     short loc_180003FC2
0x180003faf  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003fb6  mov     rax, [rcx]
0x180003fb9  mov     rax, [rax+8]
0x180003fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fc2  mov     eax, ebx
0x180003fc4  add     rsp, 20h
0x180003fc8  pop     rbx
0x180003fc9  retn
```
