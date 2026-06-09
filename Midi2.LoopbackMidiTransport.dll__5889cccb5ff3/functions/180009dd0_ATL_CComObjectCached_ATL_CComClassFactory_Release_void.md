# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180009dd0`
- end: `0x180009e61`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `145`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800041a4`
- `0x180009dd0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009e27`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009e27`

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
0x180009dd0  mov     [rsp+arg_0], rbx
0x180009dd5  push    rdi
0x180009dd6  sub     rsp, 20h
0x180009dda  mov     rbx, rcx
0x180009ddd  mov     r8d, 7FFFFFFFh
0x180009de3  mov     ecx, [rcx+8]
0x180009de6  jmp     short loc_180009DF7
0x180009de8  lea     edx, [rcx-1]
0x180009deb  mov     eax, ecx
0x180009ded  lock cmpxchg [rbx+8], edx
0x180009df2  jz      short loc_180009DFC
0x180009df4  mov     ecx, [rbx+8]
0x180009df7  cmp     ecx, r8d
0x180009dfa  jnz     short loc_180009DE8
0x180009dfc  lea     edi, [rcx-1]
0x180009dff  test    edi, edi
0x180009e01  jnz     short loc_180009E3C
0x180009e03  test    rbx, rbx
0x180009e06  jz      short loc_180009E54
0x180009e08  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180009e0f  mov     dword ptr [rbx+8], 0C0000001h
0x180009e16  lea     rcx, [rbx+10h]; lpCriticalSection
0x180009e1a  mov     [rbx], rax
0x180009e1d  cmp     [rcx+28h], dil
0x180009e21  jz      short loc_180009E2D
0x180009e23  mov     [rcx+28h], dil
0x180009e27  call    cs:__imp_DeleteCriticalSection
0x180009e2d  mov     edx, 48h ; 'H'
0x180009e32  mov     rcx, rbx; Block
0x180009e35  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009e3a  jmp     short loc_180009E54
0x180009e3c  cmp     edi, 1
0x180009e3f  jnz     short loc_180009E54
0x180009e41  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009e48  mov     rdx, [rcx]
0x180009e4b  mov     rax, [rdx+10h]
0x180009e4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e54  mov     rbx, [rsp+28h+arg_0]
0x180009e59  mov     eax, edi
0x180009e5b  add     rsp, 20h
0x180009e5f  pop     rdi
0x180009e60  retn
```
