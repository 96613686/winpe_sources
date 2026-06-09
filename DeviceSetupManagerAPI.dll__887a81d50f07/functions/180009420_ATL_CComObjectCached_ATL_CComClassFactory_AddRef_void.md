# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180009420`
- end: `0x18000946a`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009420`
- `0x18000f010`

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
0x180009420  push    rbx
0x180009422  sub     rsp, 20h
0x180009426  mov     ebx, 7FFFFFFFh
0x18000942b  jmp     short loc_18000943B
0x18000942d  lea     edx, [r8+1]
0x180009431  mov     eax, r8d
0x180009434  lock cmpxchg [rcx+8], edx
0x180009439  jz      short loc_180009446
0x18000943b  mov     r8d, [rcx+8]
0x18000943f  cmp     r8d, ebx
0x180009442  jnz     short loc_18000942D
0x180009444  jmp     short loc_180009462
0x180009446  lea     ebx, [r8+1]
0x18000944a  cmp     ebx, 2
0x18000944d  jnz     short loc_180009462
0x18000944f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009456  mov     rax, [rcx]
0x180009459  mov     rax, [rax+8]
0x18000945d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009462  mov     eax, ebx
0x180009464  add     rsp, 20h
0x180009468  pop     rbx
0x180009469  retn
```
