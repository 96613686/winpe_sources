# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x1800046d0`
- end: `0x18000471a`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800046d0`
- `0x180015010`

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
0x1800046d0  push    rbx
0x1800046d2  sub     rsp, 20h
0x1800046d6  mov     ebx, 7FFFFFFFh
0x1800046db  jmp     short loc_1800046EB
0x1800046dd  lea     edx, [r8+1]
0x1800046e1  mov     eax, r8d
0x1800046e4  lock cmpxchg [rcx+8], edx
0x1800046e9  jz      short loc_1800046F6
0x1800046eb  mov     r8d, [rcx+8]
0x1800046ef  cmp     r8d, ebx
0x1800046f2  jnz     short loc_1800046DD
0x1800046f4  jmp     short loc_180004712
0x1800046f6  lea     ebx, [r8+1]
0x1800046fa  cmp     ebx, 2
0x1800046fd  jnz     short loc_180004712
0x1800046ff  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004706  mov     rax, [rcx]
0x180004709  mov     rax, [rax+8]
0x18000470d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004712  mov     eax, ebx
0x180004714  add     rsp, 20h
0x180004718  pop     rbx
0x180004719  retn
```
