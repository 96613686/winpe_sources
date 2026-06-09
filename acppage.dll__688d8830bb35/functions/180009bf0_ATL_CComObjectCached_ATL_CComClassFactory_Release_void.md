# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180009bf0`
- end: `0x180009c7c`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `140`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001790`
- `0x180009bf0`
- `0x180017010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180009c47`
- `KERNEL32!DeleteCriticalSection` at `0x180009c47`

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
0x180009bf0  mov     [rsp+arg_0], rbx
0x180009bf5  push    rdi
0x180009bf6  sub     rsp, 20h
0x180009bfa  mov     rbx, rcx
0x180009bfd  mov     r8d, 7FFFFFFFh
0x180009c03  mov     ecx, [rcx+8]
0x180009c06  jmp     short loc_180009C17
0x180009c08  lea     edx, [rcx-1]
0x180009c0b  mov     eax, ecx
0x180009c0d  lock cmpxchg [rbx+8], edx
0x180009c12  jz      short loc_180009C1C
0x180009c14  mov     ecx, [rbx+8]
0x180009c17  cmp     ecx, r8d
0x180009c1a  jnz     short loc_180009C08
0x180009c1c  lea     edi, [rcx-1]
0x180009c1f  test    edi, edi
0x180009c21  jnz     short loc_180009C57
0x180009c23  test    rbx, rbx
0x180009c26  jz      short loc_180009C6F
0x180009c28  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180009c2f  mov     dword ptr [rbx+8], 0C0000001h
0x180009c36  lea     rcx, [rbx+10h]; lpCriticalSection
0x180009c3a  mov     [rbx], rax
0x180009c3d  cmp     [rcx+28h], dil
0x180009c41  jz      short loc_180009C4D
0x180009c43  mov     [rcx+28h], dil
0x180009c47  call    cs:__imp_DeleteCriticalSection
0x180009c4d  mov     rcx, rbx; Block
0x180009c50  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009c55  jmp     short loc_180009C6F
0x180009c57  cmp     edi, 1
0x180009c5a  jnz     short loc_180009C6F
0x180009c5c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009c63  mov     rdx, [rcx]
0x180009c66  mov     rax, [rdx+10h]
0x180009c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c6f  mov     rbx, [rsp+28h+arg_0]
0x180009c74  mov     eax, edi
0x180009c76  add     rsp, 20h
0x180009c7a  pop     rdi
0x180009c7b  retn
```
