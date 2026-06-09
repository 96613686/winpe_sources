# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180011d50`
- end: `0x180011ddc`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `140`
- prototype: `__int64 __fastcall(char *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001520`
- `0x180011d50`
- `0x180014010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180011da7`
- `KERNEL32!DeleteCriticalSection` at `0x180011da7`

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
0x180011d50  mov     [rsp+arg_0], rbx
0x180011d55  push    rdi
0x180011d56  sub     rsp, 20h
0x180011d5a  mov     rbx, rcx
0x180011d5d  mov     r8d, 7FFFFFFFh
0x180011d63  mov     ecx, [rcx+8]
0x180011d66  jmp     short loc_180011D77
0x180011d68  lea     edx, [rcx-1]
0x180011d6b  mov     eax, ecx
0x180011d6d  lock cmpxchg [rbx+8], edx
0x180011d72  jz      short loc_180011D7C
0x180011d74  mov     ecx, [rbx+8]
0x180011d77  cmp     ecx, r8d
0x180011d7a  jnz     short loc_180011D68
0x180011d7c  lea     edi, [rcx-1]
0x180011d7f  test    edi, edi
0x180011d81  jnz     short loc_180011DB7
0x180011d83  test    rbx, rbx
0x180011d86  jz      short loc_180011DCF
0x180011d88  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180011d8f  mov     dword ptr [rbx+8], 0C0000001h
0x180011d96  lea     rcx, [rbx+10h]; lpCriticalSection
0x180011d9a  mov     [rbx], rax
0x180011d9d  cmp     [rcx+28h], dil
0x180011da1  jz      short loc_180011DAD
0x180011da3  mov     [rcx+28h], dil
0x180011da7  call    cs:__imp_DeleteCriticalSection
0x180011dad  mov     rcx, rbx; Block
0x180011db0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011db5  jmp     short loc_180011DCF
0x180011db7  cmp     edi, 1
0x180011dba  jnz     short loc_180011DCF
0x180011dbc  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011dc3  mov     rdx, [rcx]
0x180011dc6  mov     rax, [rdx+10h]
0x180011dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dcf  mov     rbx, [rsp+28h+arg_0]
0x180011dd4  mov     eax, edi
0x180011dd6  add     rsp, 20h
0x180011dda  pop     rdi
0x180011ddb  retn
```
