# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180016670`
- end: `0x180016701`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `145`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001900`
- `0x180016670`
- `0x180035010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800166c7`
- `KERNEL32!DeleteCriticalSection` at `0x1800166c7`

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
0x180016670  mov     [rsp+arg_0], rbx
0x180016675  push    rdi
0x180016676  sub     rsp, 20h
0x18001667a  mov     rbx, rcx
0x18001667d  mov     r8d, 7FFFFFFFh
0x180016683  mov     ecx, [rcx+8]
0x180016686  jmp     short loc_180016697
0x180016688  lea     edx, [rcx-1]
0x18001668b  mov     eax, ecx
0x18001668d  lock cmpxchg [rbx+8], edx
0x180016692  jz      short loc_18001669C
0x180016694  mov     ecx, [rbx+8]
0x180016697  cmp     ecx, r8d
0x18001669a  jnz     short loc_180016688
0x18001669c  lea     edi, [rcx-1]
0x18001669f  test    edi, edi
0x1800166a1  jnz     short loc_1800166DC
0x1800166a3  test    rbx, rbx
0x1800166a6  jz      short loc_1800166F4
0x1800166a8  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1800166af  mov     dword ptr [rbx+8], 0C0000001h
0x1800166b6  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800166ba  mov     [rbx], rax
0x1800166bd  cmp     [rcx+28h], dil
0x1800166c1  jz      short loc_1800166CD
0x1800166c3  mov     [rcx+28h], dil
0x1800166c7  call    cs:__imp_DeleteCriticalSection
0x1800166cd  mov     edx, 48h ; 'H'
0x1800166d2  mov     rcx, rbx; Block
0x1800166d5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800166da  jmp     short loc_1800166F4
0x1800166dc  cmp     edi, 1
0x1800166df  jnz     short loc_1800166F4
0x1800166e1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800166e8  mov     rdx, [rcx]
0x1800166eb  mov     rax, [rdx+10h]
0x1800166ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166f4  mov     rbx, [rsp+28h+arg_0]
0x1800166f9  mov     eax, edi
0x1800166fb  add     rsp, 20h
0x1800166ff  pop     rdi
0x180016700  retn
```
