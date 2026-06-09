# ATL::CComObjectCached<ATL::CComClassFactorySingleton<HtmlDocForParsingSiteUnmarshaller>>::Release(void)

- ea: `0x180004730`
- end: `0x1800047db`
- name: `?Release@?$CComObjectCached@V?$CComClassFactorySingleton@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@@ATL@@UEAAKXZ`
- size: `171`
- prototype: `__int64 __fastcall(char *Block, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001160`
- `0x180004730`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800047a6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800047a6`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactorySingleton<HtmlDocForParsingSiteUnmarshaller>>::Release(
        char *Block,
        __int64 a2)
{
  signed __int32 i; // ecx
  unsigned __int32 v4; // edi
  __int64 v5; // rcx

  for ( i = *((_DWORD *)Block + 2); i != 0x7FFFFFFF; i = *((_DWORD *)Block + 2) )
  {
    a2 = (unsigned int)(i - 1);
    if ( i == _InterlockedCompareExchange((volatile signed __int32 *)Block + 2, a2, i) )
      break;
  }
  v4 = i - 1;
  if ( i == 1 )
  {
    if ( Block )
    {
      *((_DWORD *)Block + 2) = -1073741823;
      *(_QWORD *)Block = &ATL::CComClassFactorySingleton<HtmlDocForParsingSiteUnmarshaller>::`vftable';
      v5 = *((_QWORD *)Block + 10);
      if ( v5 )
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v5 + 16LL))(v5, a2, 0x7FFFFFFF);
      *(_QWORD *)Block = &ATL::CComClassFactory::`vftable';
      if ( Block[56] )
      {
        Block[56] = 0;
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
  return v4;
}

```

## disassembly

```asm
0x180004730  mov     [rsp+arg_0], rbx
0x180004735  push    rdi
0x180004736  sub     rsp, 20h
0x18000473a  mov     rbx, rcx
0x18000473d  mov     r8d, 7FFFFFFFh
0x180004743  mov     ecx, [rcx+8]
0x180004746  jmp     short loc_180004757
0x180004748  lea     edx, [rcx-1]
0x18000474b  mov     eax, ecx
0x18000474d  lock cmpxchg [rbx+8], edx
0x180004752  jz      short loc_18000475C
0x180004754  mov     ecx, [rbx+8]
0x180004757  cmp     ecx, r8d
0x18000475a  jnz     short loc_180004748
0x18000475c  lea     edi, [rcx-1]
0x18000475f  test    edi, edi
0x180004761  jnz     short loc_1800047B6
0x180004763  test    rbx, rbx
0x180004766  jz      short loc_1800047CE
0x180004768  lea     rax, ??_7?$CComClassFactorySingleton@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@6B@; const ATL::CComClassFactorySingleton<HtmlDocForParsingSiteUnmarshaller>::`vftable'
0x18000476f  mov     dword ptr [rbx+8], 0C0000001h
0x180004776  mov     [rbx], rax
0x180004779  mov     rcx, [rbx+50h]
0x18000477d  test    rcx, rcx
0x180004780  jz      short loc_18000478E
0x180004782  mov     rax, [rcx]
0x180004785  mov     rax, [rax+10h]
0x180004789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000478e  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180004795  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004799  mov     [rbx], rax
0x18000479c  cmp     byte ptr [rcx+28h], 0
0x1800047a0  jz      short loc_1800047AC
0x1800047a2  mov     byte ptr [rcx+28h], 0
0x1800047a6  call    cs:__imp_DeleteCriticalSection
0x1800047ac  mov     rcx, rbx; Block
0x1800047af  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800047b4  jmp     short loc_1800047CE
0x1800047b6  cmp     edi, 1
0x1800047b9  jnz     short loc_1800047CE
0x1800047bb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800047c2  mov     rdx, [rcx]
0x1800047c5  mov     rax, [rdx+10h]
0x1800047c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047ce  mov     rbx, [rsp+28h+arg_0]
0x1800047d3  mov     eax, edi
0x1800047d5  add     rsp, 20h
0x1800047d9  pop     rdi
0x1800047da  retn
```
