# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180007600`
- end: `0x180007691`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `145`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002024`
- `0x180007600`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007657`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007657`

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
0x180007600  mov     [rsp+arg_0], rbx
0x180007605  push    rdi
0x180007606  sub     rsp, 20h
0x18000760a  mov     rbx, rcx
0x18000760d  mov     r8d, 7FFFFFFFh
0x180007613  mov     ecx, [rcx+8]
0x180007616  jmp     short loc_180007627
0x180007618  lea     edx, [rcx-1]
0x18000761b  mov     eax, ecx
0x18000761d  lock cmpxchg [rbx+8], edx
0x180007622  jz      short loc_18000762C
0x180007624  mov     ecx, [rbx+8]
0x180007627  cmp     ecx, r8d
0x18000762a  jnz     short loc_180007618
0x18000762c  lea     edi, [rcx-1]
0x18000762f  test    edi, edi
0x180007631  jnz     short loc_18000766C
0x180007633  test    rbx, rbx
0x180007636  jz      short loc_180007684
0x180007638  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000763f  mov     dword ptr [rbx+8], 0C0000001h
0x180007646  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000764a  mov     [rbx], rax
0x18000764d  cmp     [rcx+28h], dil
0x180007651  jz      short loc_18000765D
0x180007653  mov     [rcx+28h], dil
0x180007657  call    cs:__imp_DeleteCriticalSection
0x18000765d  mov     edx, 48h ; 'H'
0x180007662  mov     rcx, rbx; Block
0x180007665  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000766a  jmp     short loc_180007684
0x18000766c  cmp     edi, 1
0x18000766f  jnz     short loc_180007684
0x180007671  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007678  mov     rdx, [rcx]
0x18000767b  mov     rax, [rdx+10h]
0x18000767f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007684  mov     rbx, [rsp+28h+arg_0]
0x180007689  mov     eax, edi
0x18000768b  add     rsp, 20h
0x18000768f  pop     rdi
0x180007690  retn
```
