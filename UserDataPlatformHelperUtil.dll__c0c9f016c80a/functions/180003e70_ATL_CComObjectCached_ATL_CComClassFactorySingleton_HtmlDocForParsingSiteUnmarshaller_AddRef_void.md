# ATL::CComObjectCached<ATL::CComClassFactorySingleton<HtmlDocForParsingSiteUnmarshaller>>::AddRef(void)

- ea: `0x180003e70`
- end: `0x180003eba`
- name: `?AddRef@?$CComObjectCached@V?$CComClassFactorySingleton@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003e70`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactorySingleton<HtmlDocForParsingSiteUnmarshaller>>::AddRef(
        __int64 a1)
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
0x180003e70  push    rbx
0x180003e72  sub     rsp, 20h
0x180003e76  mov     ebx, 7FFFFFFFh
0x180003e7b  jmp     short loc_180003E8B
0x180003e7d  lea     edx, [r8+1]
0x180003e81  mov     eax, r8d
0x180003e84  lock cmpxchg [rcx+8], edx
0x180003e89  jz      short loc_180003E96
0x180003e8b  mov     r8d, [rcx+8]
0x180003e8f  cmp     r8d, ebx
0x180003e92  jnz     short loc_180003E7D
0x180003e94  jmp     short loc_180003EB2
0x180003e96  lea     ebx, [r8+1]
0x180003e9a  cmp     ebx, 2
0x180003e9d  jnz     short loc_180003EB2
0x180003e9f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003ea6  mov     rax, [rcx]
0x180003ea9  mov     rax, [rax+8]
0x180003ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eb2  mov     eax, ebx
0x180003eb4  add     rsp, 20h
0x180003eb8  pop     rbx
0x180003eb9  retn
```
