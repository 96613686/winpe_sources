# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180007bc0`
- end: `0x180007c51`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `145`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002494`
- `0x180007bc0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007c17`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007c17`

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
0x180007bc0  mov     [rsp+arg_0], rbx
0x180007bc5  push    rdi
0x180007bc6  sub     rsp, 20h
0x180007bca  mov     rbx, rcx
0x180007bcd  mov     r8d, 7FFFFFFFh
0x180007bd3  mov     ecx, [rcx+8]
0x180007bd6  jmp     short loc_180007BE7
0x180007bd8  lea     edx, [rcx-1]
0x180007bdb  mov     eax, ecx
0x180007bdd  lock cmpxchg [rbx+8], edx
0x180007be2  jz      short loc_180007BEC
0x180007be4  mov     ecx, [rbx+8]
0x180007be7  cmp     ecx, r8d
0x180007bea  jnz     short loc_180007BD8
0x180007bec  lea     edi, [rcx-1]
0x180007bef  test    edi, edi
0x180007bf1  jnz     short loc_180007C2C
0x180007bf3  test    rbx, rbx
0x180007bf6  jz      short loc_180007C44
0x180007bf8  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180007bff  mov     dword ptr [rbx+8], 0C0000001h
0x180007c06  lea     rcx, [rbx+10h]; lpCriticalSection
0x180007c0a  mov     [rbx], rax
0x180007c0d  cmp     [rcx+28h], dil
0x180007c11  jz      short loc_180007C1D
0x180007c13  mov     [rcx+28h], dil
0x180007c17  call    cs:__imp_DeleteCriticalSection
0x180007c1d  mov     edx, 48h ; 'H'
0x180007c22  mov     rcx, rbx; Block
0x180007c25  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007c2a  jmp     short loc_180007C44
0x180007c2c  cmp     edi, 1
0x180007c2f  jnz     short loc_180007C44
0x180007c31  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007c38  mov     rdx, [rcx]
0x180007c3b  mov     rax, [rdx+10h]
0x180007c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c44  mov     rbx, [rsp+28h+arg_0]
0x180007c49  mov     eax, edi
0x180007c4b  add     rsp, 20h
0x180007c4f  pop     rdi
0x180007c50  retn
```
