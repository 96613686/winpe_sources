# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x18000a5b0`
- end: `0x18000a641`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `145`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004434`
- `0x18000a5b0`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a607`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a607`

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
0x18000a5b0  mov     [rsp+arg_0], rbx
0x18000a5b5  push    rdi
0x18000a5b6  sub     rsp, 20h
0x18000a5ba  mov     rbx, rcx
0x18000a5bd  mov     r8d, 7FFFFFFFh
0x18000a5c3  mov     ecx, [rcx+8]
0x18000a5c6  jmp     short loc_18000A5D7
0x18000a5c8  lea     edx, [rcx-1]
0x18000a5cb  mov     eax, ecx
0x18000a5cd  lock cmpxchg [rbx+8], edx
0x18000a5d2  jz      short loc_18000A5DC
0x18000a5d4  mov     ecx, [rbx+8]
0x18000a5d7  cmp     ecx, r8d
0x18000a5da  jnz     short loc_18000A5C8
0x18000a5dc  lea     edi, [rcx-1]
0x18000a5df  test    edi, edi
0x18000a5e1  jnz     short loc_18000A61C
0x18000a5e3  test    rbx, rbx
0x18000a5e6  jz      short loc_18000A634
0x18000a5e8  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000a5ef  mov     dword ptr [rbx+8], 0C0000001h
0x18000a5f6  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000a5fa  mov     [rbx], rax
0x18000a5fd  cmp     [rcx+28h], dil
0x18000a601  jz      short loc_18000A60D
0x18000a603  mov     [rcx+28h], dil
0x18000a607  call    cs:__imp_DeleteCriticalSection
0x18000a60d  mov     edx, 48h ; 'H'
0x18000a612  mov     rcx, rbx; Block
0x18000a615  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a61a  jmp     short loc_18000A634
0x18000a61c  cmp     edi, 1
0x18000a61f  jnz     short loc_18000A634
0x18000a621  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a628  mov     rdx, [rcx]
0x18000a62b  mov     rax, [rdx+10h]
0x18000a62f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a634  mov     rbx, [rsp+28h+arg_0]
0x18000a639  mov     eax, edi
0x18000a63b  add     rsp, 20h
0x18000a63f  pop     rdi
0x18000a640  retn
```
