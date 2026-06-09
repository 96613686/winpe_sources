# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180012010`
- end: `0x1800120a1`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `145`
- prototype: `__int64 __fastcall(char *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002b9c`
- `0x180012010`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012067`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012067`

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
0x180012010  mov     [rsp+arg_0], rbx
0x180012015  push    rdi
0x180012016  sub     rsp, 20h
0x18001201a  mov     rbx, rcx
0x18001201d  mov     r8d, 7FFFFFFFh
0x180012023  mov     ecx, [rcx+8]
0x180012026  jmp     short loc_180012037
0x180012028  lea     edx, [rcx-1]
0x18001202b  mov     eax, ecx
0x18001202d  lock cmpxchg [rbx+8], edx
0x180012032  jz      short loc_18001203C
0x180012034  mov     ecx, [rbx+8]
0x180012037  cmp     ecx, r8d
0x18001203a  jnz     short loc_180012028
0x18001203c  lea     edi, [rcx-1]
0x18001203f  test    edi, edi
0x180012041  jnz     short loc_18001207C
0x180012043  test    rbx, rbx
0x180012046  jz      short loc_180012094
0x180012048  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18001204f  mov     dword ptr [rbx+8], 0C0000001h
0x180012056  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001205a  mov     [rbx], rax
0x18001205d  cmp     [rcx+28h], dil
0x180012061  jz      short loc_18001206D
0x180012063  mov     [rcx+28h], dil
0x180012067  call    cs:__imp_DeleteCriticalSection
0x18001206d  mov     edx, 48h ; 'H'
0x180012072  mov     rcx, rbx; Block
0x180012075  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001207a  jmp     short loc_180012094
0x18001207c  cmp     edi, 1
0x18001207f  jnz     short loc_180012094
0x180012081  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180012088  mov     rdx, [rcx]
0x18001208b  mov     rax, [rdx+10h]
0x18001208f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012094  mov     rbx, [rsp+28h+arg_0]
0x180012099  mov     eax, edi
0x18001209b  add     rsp, 20h
0x18001209f  pop     rdi
0x1800120a0  retn
```
