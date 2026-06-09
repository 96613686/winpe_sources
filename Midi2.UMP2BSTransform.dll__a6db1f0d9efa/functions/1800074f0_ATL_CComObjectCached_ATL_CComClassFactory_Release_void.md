# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x1800074f0`
- end: `0x180007581`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `145`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001f14`
- `0x1800074f0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007547`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007547`

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
0x1800074f0  mov     [rsp+arg_0], rbx
0x1800074f5  push    rdi
0x1800074f6  sub     rsp, 20h
0x1800074fa  mov     rbx, rcx
0x1800074fd  mov     r8d, 7FFFFFFFh
0x180007503  mov     ecx, [rcx+8]
0x180007506  jmp     short loc_180007517
0x180007508  lea     edx, [rcx-1]
0x18000750b  mov     eax, ecx
0x18000750d  lock cmpxchg [rbx+8], edx
0x180007512  jz      short loc_18000751C
0x180007514  mov     ecx, [rbx+8]
0x180007517  cmp     ecx, r8d
0x18000751a  jnz     short loc_180007508
0x18000751c  lea     edi, [rcx-1]
0x18000751f  test    edi, edi
0x180007521  jnz     short loc_18000755C
0x180007523  test    rbx, rbx
0x180007526  jz      short loc_180007574
0x180007528  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000752f  mov     dword ptr [rbx+8], 0C0000001h
0x180007536  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000753a  mov     [rbx], rax
0x18000753d  cmp     [rcx+28h], dil
0x180007541  jz      short loc_18000754D
0x180007543  mov     [rcx+28h], dil
0x180007547  call    cs:__imp_DeleteCriticalSection
0x18000754d  mov     edx, 48h ; 'H'
0x180007552  mov     rcx, rbx; Block
0x180007555  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000755a  jmp     short loc_180007574
0x18000755c  cmp     edi, 1
0x18000755f  jnz     short loc_180007574
0x180007561  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007568  mov     rdx, [rcx]
0x18000756b  mov     rax, [rdx+10h]
0x18000756f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007574  mov     rbx, [rsp+28h+arg_0]
0x180007579  mov     eax, edi
0x18000757b  add     rsp, 20h
0x18000757f  pop     rdi
0x180007580  retn
```
