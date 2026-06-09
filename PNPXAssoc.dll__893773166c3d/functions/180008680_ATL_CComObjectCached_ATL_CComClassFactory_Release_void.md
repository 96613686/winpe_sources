# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180008680`
- end: `0x18000870c`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `140`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800019b0`
- `0x180008680`
- `0x180014010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800086d7`
- `KERNEL32!DeleteCriticalSection` at `0x1800086d7`

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
0x180008680  mov     [rsp+arg_0], rbx
0x180008685  push    rdi
0x180008686  sub     rsp, 20h
0x18000868a  mov     rbx, rcx
0x18000868d  mov     r8d, 7FFFFFFFh
0x180008693  mov     ecx, [rcx+8]
0x180008696  jmp     short loc_1800086A7
0x180008698  lea     edx, [rcx-1]
0x18000869b  mov     eax, ecx
0x18000869d  lock cmpxchg [rbx+8], edx
0x1800086a2  jz      short loc_1800086AC
0x1800086a4  mov     ecx, [rbx+8]
0x1800086a7  cmp     ecx, r8d
0x1800086aa  jnz     short loc_180008698
0x1800086ac  lea     edi, [rcx-1]
0x1800086af  test    edi, edi
0x1800086b1  jnz     short loc_1800086E7
0x1800086b3  test    rbx, rbx
0x1800086b6  jz      short loc_1800086FF
0x1800086b8  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1800086bf  mov     dword ptr [rbx+8], 0C0000001h
0x1800086c6  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800086ca  mov     [rbx], rax
0x1800086cd  cmp     [rcx+28h], dil
0x1800086d1  jz      short loc_1800086DD
0x1800086d3  mov     [rcx+28h], dil
0x1800086d7  call    cs:__imp_DeleteCriticalSection
0x1800086dd  mov     rcx, rbx; Block
0x1800086e0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800086e5  jmp     short loc_1800086FF
0x1800086e7  cmp     edi, 1
0x1800086ea  jnz     short loc_1800086FF
0x1800086ec  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800086f3  mov     rdx, [rcx]
0x1800086f6  mov     rax, [rdx+10h]
0x1800086fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086ff  mov     rbx, [rsp+28h+arg_0]
0x180008704  mov     eax, edi
0x180008706  add     rsp, 20h
0x18000870a  pop     rdi
0x18000870b  retn
```
