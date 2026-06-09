# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180007460`
- end: `0x1800074f1`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `145`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001e84`
- `0x180007460`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800074b7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800074b7`

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
0x180007460  mov     [rsp+arg_0], rbx
0x180007465  push    rdi
0x180007466  sub     rsp, 20h
0x18000746a  mov     rbx, rcx
0x18000746d  mov     r8d, 7FFFFFFFh
0x180007473  mov     ecx, [rcx+8]
0x180007476  jmp     short loc_180007487
0x180007478  lea     edx, [rcx-1]
0x18000747b  mov     eax, ecx
0x18000747d  lock cmpxchg [rbx+8], edx
0x180007482  jz      short loc_18000748C
0x180007484  mov     ecx, [rbx+8]
0x180007487  cmp     ecx, r8d
0x18000748a  jnz     short loc_180007478
0x18000748c  lea     edi, [rcx-1]
0x18000748f  test    edi, edi
0x180007491  jnz     short loc_1800074CC
0x180007493  test    rbx, rbx
0x180007496  jz      short loc_1800074E4
0x180007498  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000749f  mov     dword ptr [rbx+8], 0C0000001h
0x1800074a6  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800074aa  mov     [rbx], rax
0x1800074ad  cmp     [rcx+28h], dil
0x1800074b1  jz      short loc_1800074BD
0x1800074b3  mov     [rcx+28h], dil
0x1800074b7  call    cs:__imp_DeleteCriticalSection
0x1800074bd  mov     edx, 48h ; 'H'
0x1800074c2  mov     rcx, rbx; Block
0x1800074c5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800074ca  jmp     short loc_1800074E4
0x1800074cc  cmp     edi, 1
0x1800074cf  jnz     short loc_1800074E4
0x1800074d1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800074d8  mov     rdx, [rcx]
0x1800074db  mov     rax, [rdx+10h]
0x1800074df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074e4  mov     rbx, [rsp+28h+arg_0]
0x1800074e9  mov     eax, edi
0x1800074eb  add     rsp, 20h
0x1800074ef  pop     rdi
0x1800074f0  retn
```
