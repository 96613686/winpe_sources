# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180005830`
- end: `0x18000587a`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005830`
- `0x180013010`

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
0x180005830  push    rbx
0x180005832  sub     rsp, 20h
0x180005836  mov     ebx, 7FFFFFFFh
0x18000583b  jmp     short loc_18000584B
0x18000583d  lea     edx, [r8+1]
0x180005841  mov     eax, r8d
0x180005844  lock cmpxchg [rcx+8], edx
0x180005849  jz      short loc_180005856
0x18000584b  mov     r8d, [rcx+8]
0x18000584f  cmp     r8d, ebx
0x180005852  jnz     short loc_18000583D
0x180005854  jmp     short loc_180005872
0x180005856  lea     ebx, [r8+1]
0x18000585a  cmp     ebx, 2
0x18000585d  jnz     short loc_180005872
0x18000585f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005866  mov     rax, [rcx]
0x180005869  mov     rax, [rax+8]
0x18000586d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005872  mov     eax, ebx
0x180005874  add     rsp, 20h
0x180005878  pop     rbx
0x180005879  retn
```
