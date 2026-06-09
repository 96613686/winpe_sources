# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x18000b130`
- end: `0x18000b1c1`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `145`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005044`
- `0x18000b130`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b187`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b187`

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
0x18000b130  mov     [rsp+arg_0], rbx
0x18000b135  push    rdi
0x18000b136  sub     rsp, 20h
0x18000b13a  mov     rbx, rcx
0x18000b13d  mov     r8d, 7FFFFFFFh
0x18000b143  mov     ecx, [rcx+8]
0x18000b146  jmp     short loc_18000B157
0x18000b148  lea     edx, [rcx-1]
0x18000b14b  mov     eax, ecx
0x18000b14d  lock cmpxchg [rbx+8], edx
0x18000b152  jz      short loc_18000B15C
0x18000b154  mov     ecx, [rbx+8]
0x18000b157  cmp     ecx, r8d
0x18000b15a  jnz     short loc_18000B148
0x18000b15c  lea     edi, [rcx-1]
0x18000b15f  test    edi, edi
0x18000b161  jnz     short loc_18000B19C
0x18000b163  test    rbx, rbx
0x18000b166  jz      short loc_18000B1B4
0x18000b168  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000b16f  mov     dword ptr [rbx+8], 0C0000001h
0x18000b176  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000b17a  mov     [rbx], rax
0x18000b17d  cmp     [rcx+28h], dil
0x18000b181  jz      short loc_18000B18D
0x18000b183  mov     [rcx+28h], dil
0x18000b187  call    cs:__imp_DeleteCriticalSection
0x18000b18d  mov     edx, 48h ; 'H'
0x18000b192  mov     rcx, rbx; Block
0x18000b195  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b19a  jmp     short loc_18000B1B4
0x18000b19c  cmp     edi, 1
0x18000b19f  jnz     short loc_18000B1B4
0x18000b1a1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b1a8  mov     rdx, [rcx]
0x18000b1ab  mov     rax, [rdx+10h]
0x18000b1af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1b4  mov     rbx, [rsp+28h+arg_0]
0x18000b1b9  mov     eax, edi
0x18000b1bb  add     rsp, 20h
0x18000b1bf  pop     rdi
0x18000b1c0  retn
```
