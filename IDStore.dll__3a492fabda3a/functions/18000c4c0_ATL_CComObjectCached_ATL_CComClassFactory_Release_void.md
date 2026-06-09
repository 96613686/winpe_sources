# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x18000c4c0`
- end: `0x18000c521`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `97`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000c4c0`
- `0x18000c528`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(_DWORD *a1)
{
  signed __int32 i; // ebx
  unsigned __int32 v2; // ebx

  for ( i = a1[2]; i != 0x7FFFFFFF; i = a1[2] )
  {
    if ( i == _InterlockedCompareExchange(a1 + 2, i - 1, i) )
      break;
  }
  v2 = i - 1;
  if ( v2 )
  {
    if ( v2 == 1 )
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    return v2;
  }
  if ( !a1 )
    return v2;
  ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(a1);
  return 0;
}

```

## disassembly

```asm
0x18000c4c0  push    rbx
0x18000c4c2  sub     rsp, 20h
0x18000c4c6  mov     ebx, [rcx+8]
0x18000c4c9  cmp     ebx, 7FFFFFFFh
0x18000c4cf  jnz     short loc_18000C508
0x18000c4d1  sub     ebx, 1
0x18000c4d4  jz      short loc_18000C4F6
0x18000c4d6  cmp     ebx, 1
0x18000c4d9  jnz     short loc_18000C4EE
0x18000c4db  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c4e2  mov     rax, [rcx]
0x18000c4e5  mov     rax, [rax+10h]
0x18000c4e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4ee  mov     eax, ebx
0x18000c4f0  add     rsp, 20h
0x18000c4f4  pop     rbx
0x18000c4f5  retn
0x18000c4f6  test    rcx, rcx
0x18000c4f9  jz      short loc_18000C4EE
0x18000c4fb  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x18000c500  mov     eax, ebx
0x18000c502  add     rsp, 20h
0x18000c506  pop     rbx
0x18000c507  retn
0x18000c508  lea     edx, [rbx-1]
0x18000c50b  mov     eax, ebx
0x18000c50d  lock cmpxchg [rcx+8], edx
0x18000c512  jz      short loc_18000C4D1
0x18000c514  mov     ebx, [rcx+8]
0x18000c517  cmp     ebx, 7FFFFFFFh
0x18000c51d  jnz     short loc_18000C508
0x18000c51f  jmp     short loc_18000C4D1
```
