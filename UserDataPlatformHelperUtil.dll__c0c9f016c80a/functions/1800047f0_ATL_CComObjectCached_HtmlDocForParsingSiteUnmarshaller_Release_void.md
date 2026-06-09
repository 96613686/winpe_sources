# ATL::CComObjectCached<HtmlDocForParsingSiteUnmarshaller>::Release(void)

- ea: `0x1800047f0`
- end: `0x18000485a`
- name: `?Release@?$CComObjectCached@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@UEAAKXZ`
- size: `106`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001160`
- `0x1800047f0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<HtmlDocForParsingSiteUnmarshaller>::Release(volatile signed __int32 *a1)
{
  __int64 v1; // r8
  unsigned int v2; // ebx

  do
    v1 = *((unsigned int *)a1 + 2);
  while ( (_DWORD)v1 != 0x7FFFFFFF && (_DWORD)v1 != _InterlockedCompareExchange(a1 + 2, v1 - 1, v1) );
  v2 = v1 - 1;
  if ( (_DWORD)v1 == 1 )
  {
    if ( a1 )
    {
      *((_DWORD *)a1 + 2) = -1073741823;
      *(_QWORD *)a1 = &ATL::CComObjectCached<HtmlDocForParsingSiteUnmarshaller>::`vftable';
      operator delete((void *)a1);
    }
  }
  else if ( (_DWORD)v1 == 2 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *, _QWORD, __int64, __int64))(*(_QWORD *)ATL::_pAtlModule + 16LL))(
      ATL::_pAtlModule,
      *(_QWORD *)ATL::_pAtlModule,
      v1,
      0x7FFFFFFF);
  }
  return v2;
}

```

## disassembly

```asm
0x1800047f0  push    rbx
0x1800047f2  sub     rsp, 20h
0x1800047f6  mov     r9d, 7FFFFFFFh
0x1800047fc  jmp     short loc_18000480C
0x1800047fe  lea     edx, [r8-1]
0x180004802  mov     eax, r8d
0x180004805  lock cmpxchg [rcx+8], edx
0x18000480a  jz      short loc_180004815
0x18000480c  mov     r8d, [rcx+8]
0x180004810  cmp     r8d, r9d
0x180004813  jnz     short loc_1800047FE
0x180004815  lea     ebx, [r8-1]
0x180004819  test    ebx, ebx
0x18000481b  jnz     short loc_18000483A
0x18000481d  test    rcx, rcx
0x180004820  jz      short loc_180004852
0x180004822  lea     rax, ??_7?$CComObjectCached@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@6B@; const ATL::CComObjectCached<HtmlDocForParsingSiteUnmarshaller>::`vftable'
0x180004829  mov     dword ptr [rcx+8], 0C0000001h
0x180004830  mov     [rcx], rax
0x180004833  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004838  jmp     short loc_180004852
0x18000483a  cmp     ebx, 1
0x18000483d  jnz     short loc_180004852
0x18000483f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004846  mov     rdx, [rcx]
0x180004849  mov     rax, [rdx+10h]
0x18000484d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004852  mov     eax, ebx
0x180004854  add     rsp, 20h
0x180004858  pop     rbx
0x180004859  retn
```
