# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180008d10`
- end: `0x180008da1`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `145`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800033f4`
- `0x180008d10`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008d67`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008d67`

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
0x180008d10  mov     [rsp+arg_0], rbx
0x180008d15  push    rdi
0x180008d16  sub     rsp, 20h
0x180008d1a  mov     rbx, rcx
0x180008d1d  mov     r8d, 7FFFFFFFh
0x180008d23  mov     ecx, [rcx+8]
0x180008d26  jmp     short loc_180008D37
0x180008d28  lea     edx, [rcx-1]
0x180008d2b  mov     eax, ecx
0x180008d2d  lock cmpxchg [rbx+8], edx
0x180008d32  jz      short loc_180008D3C
0x180008d34  mov     ecx, [rbx+8]
0x180008d37  cmp     ecx, r8d
0x180008d3a  jnz     short loc_180008D28
0x180008d3c  lea     edi, [rcx-1]
0x180008d3f  test    edi, edi
0x180008d41  jnz     short loc_180008D7C
0x180008d43  test    rbx, rbx
0x180008d46  jz      short loc_180008D94
0x180008d48  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180008d4f  mov     dword ptr [rbx+8], 0C0000001h
0x180008d56  lea     rcx, [rbx+10h]; lpCriticalSection
0x180008d5a  mov     [rbx], rax
0x180008d5d  cmp     [rcx+28h], dil
0x180008d61  jz      short loc_180008D6D
0x180008d63  mov     [rcx+28h], dil
0x180008d67  call    cs:__imp_DeleteCriticalSection
0x180008d6d  mov     edx, 48h ; 'H'
0x180008d72  mov     rcx, rbx; Block
0x180008d75  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008d7a  jmp     short loc_180008D94
0x180008d7c  cmp     edi, 1
0x180008d7f  jnz     short loc_180008D94
0x180008d81  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008d88  mov     rdx, [rcx]
0x180008d8b  mov     rax, [rdx+10h]
0x180008d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d94  mov     rbx, [rsp+28h+arg_0]
0x180008d99  mov     eax, edi
0x180008d9b  add     rsp, 20h
0x180008d9f  pop     rdi
0x180008da0  retn
```
