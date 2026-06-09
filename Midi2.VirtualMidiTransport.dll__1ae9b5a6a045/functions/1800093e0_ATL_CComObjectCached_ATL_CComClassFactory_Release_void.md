# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x1800093e0`
- end: `0x180009471`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `145`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003914`
- `0x1800093e0`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009437`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009437`

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
0x1800093e0  mov     [rsp+arg_0], rbx
0x1800093e5  push    rdi
0x1800093e6  sub     rsp, 20h
0x1800093ea  mov     rbx, rcx
0x1800093ed  mov     r8d, 7FFFFFFFh
0x1800093f3  mov     ecx, [rcx+8]
0x1800093f6  jmp     short loc_180009407
0x1800093f8  lea     edx, [rcx-1]
0x1800093fb  mov     eax, ecx
0x1800093fd  lock cmpxchg [rbx+8], edx
0x180009402  jz      short loc_18000940C
0x180009404  mov     ecx, [rbx+8]
0x180009407  cmp     ecx, r8d
0x18000940a  jnz     short loc_1800093F8
0x18000940c  lea     edi, [rcx-1]
0x18000940f  test    edi, edi
0x180009411  jnz     short loc_18000944C
0x180009413  test    rbx, rbx
0x180009416  jz      short loc_180009464
0x180009418  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000941f  mov     dword ptr [rbx+8], 0C0000001h
0x180009426  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000942a  mov     [rbx], rax
0x18000942d  cmp     [rcx+28h], dil
0x180009431  jz      short loc_18000943D
0x180009433  mov     [rcx+28h], dil
0x180009437  call    cs:__imp_DeleteCriticalSection
0x18000943d  mov     edx, 48h ; 'H'
0x180009442  mov     rcx, rbx; Block
0x180009445  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000944a  jmp     short loc_180009464
0x18000944c  cmp     edi, 1
0x18000944f  jnz     short loc_180009464
0x180009451  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009458  mov     rdx, [rcx]
0x18000945b  mov     rax, [rdx+10h]
0x18000945f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009464  mov     rbx, [rsp+28h+arg_0]
0x180009469  mov     eax, edi
0x18000946b  add     rsp, 20h
0x18000946f  pop     rdi
0x180009470  retn
```
