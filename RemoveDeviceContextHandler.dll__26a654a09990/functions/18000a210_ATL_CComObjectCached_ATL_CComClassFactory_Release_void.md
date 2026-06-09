# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x18000a210`
- end: `0x18000a29c`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `140`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001be0`
- `0x18000a210`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a267`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a267`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(char *Block)
{
  signed __int32 i; // ecx
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)Block + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)Block + 2, i - 1, i);
        i = *((_DWORD *)Block + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    if ( Block )
    {
      *((_DWORD *)Block + 2) = -1073741823;
      *(_QWORD *)Block = &ATL::CComClassFactory::`vftable';
      if ( Block[56] != (_BYTE)v3 )
      {
        Block[56] = v3;
        DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 16));
      }
      operator delete(Block);
    }
  }
  else if ( i == 2 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *, _QWORD, __int64))(*(_QWORD *)ATL::_pAtlModule + 16LL))(
      ATL::_pAtlModule,
      *(_QWORD *)ATL::_pAtlModule,
      0x7FFFFFFF);
  }
  return v3;
}

```

## disassembly

```asm
0x18000a210  mov     [rsp+arg_0], rbx
0x18000a215  push    rdi
0x18000a216  sub     rsp, 20h
0x18000a21a  mov     rbx, rcx
0x18000a21d  mov     r8d, 7FFFFFFFh
0x18000a223  mov     ecx, [rcx+8]
0x18000a226  jmp     short loc_18000A237
0x18000a228  lea     edx, [rcx-1]
0x18000a22b  mov     eax, ecx
0x18000a22d  lock cmpxchg [rbx+8], edx
0x18000a232  jz      short loc_18000A23C
0x18000a234  mov     ecx, [rbx+8]
0x18000a237  cmp     ecx, r8d
0x18000a23a  jnz     short loc_18000A228
0x18000a23c  lea     edi, [rcx-1]
0x18000a23f  test    edi, edi
0x18000a241  jnz     short loc_18000A277
0x18000a243  test    rbx, rbx
0x18000a246  jz      short loc_18000A28F
0x18000a248  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000a24f  mov     dword ptr [rbx+8], 0C0000001h
0x18000a256  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000a25a  mov     [rbx], rax
0x18000a25d  cmp     [rcx+28h], dil
0x18000a261  jz      short loc_18000A26D
0x18000a263  mov     [rcx+28h], dil
0x18000a267  call    cs:__imp_DeleteCriticalSection
0x18000a26d  mov     rcx, rbx; Block
0x18000a270  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a275  jmp     short loc_18000A28F
0x18000a277  cmp     edi, 1
0x18000a27a  jnz     short loc_18000A28F
0x18000a27c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a283  mov     rdx, [rcx]
0x18000a286  mov     rax, [rdx+10h]
0x18000a28a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a28f  mov     rbx, [rsp+28h+arg_0]
0x18000a294  mov     eax, edi
0x18000a296  add     rsp, 20h
0x18000a29a  pop     rdi
0x18000a29b  retn
```
