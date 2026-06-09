# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180021d50`
- end: `0x180021de1`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `145`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001914`
- `0x180021d50`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021da7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021da7`

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
    (*(void (__fastcall **)(ATL::CAtlModule *, _QWORD, __int64))(*(_QWORD *)ATL::_pAtlModule + 16LL))(
      ATL::_pAtlModule,
      *(_QWORD *)ATL::_pAtlModule,
      0x7FFFFFFF);
  }
  return v3;
}

```

## disassembly

```asm
0x180021d50  mov     [rsp+arg_0], rbx
0x180021d55  push    rdi
0x180021d56  sub     rsp, 20h
0x180021d5a  mov     rbx, rcx
0x180021d5d  mov     r8d, 7FFFFFFFh
0x180021d63  mov     ecx, [rcx+8]
0x180021d66  jmp     short loc_180021D77
0x180021d68  lea     edx, [rcx-1]
0x180021d6b  mov     eax, ecx
0x180021d6d  lock cmpxchg [rbx+8], edx
0x180021d72  jz      short loc_180021D7C
0x180021d74  mov     ecx, [rbx+8]
0x180021d77  cmp     ecx, r8d
0x180021d7a  jnz     short loc_180021D68
0x180021d7c  lea     edi, [rcx-1]
0x180021d7f  test    edi, edi
0x180021d81  jnz     short loc_180021DBC
0x180021d83  test    rbx, rbx
0x180021d86  jz      short loc_180021DD4
0x180021d88  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180021d8f  mov     dword ptr [rbx+8], 0C0000001h
0x180021d96  lea     rcx, [rbx+10h]; lpCriticalSection
0x180021d9a  mov     [rbx], rax
0x180021d9d  cmp     [rcx+28h], dil
0x180021da1  jz      short loc_180021DAD
0x180021da3  mov     [rcx+28h], dil
0x180021da7  call    cs:__imp_DeleteCriticalSection
0x180021dad  mov     edx, 48h ; 'H'
0x180021db2  mov     rcx, rbx; Block
0x180021db5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021dba  jmp     short loc_180021DD4
0x180021dbc  cmp     edi, 1
0x180021dbf  jnz     short loc_180021DD4
0x180021dc1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180021dc8  mov     rdx, [rcx]
0x180021dcb  mov     rax, [rdx+10h]
0x180021dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021dd4  mov     rbx, [rsp+28h+arg_0]
0x180021dd9  mov     eax, edi
0x180021ddb  add     rsp, 20h
0x180021ddf  pop     rdi
0x180021de0  retn
```
