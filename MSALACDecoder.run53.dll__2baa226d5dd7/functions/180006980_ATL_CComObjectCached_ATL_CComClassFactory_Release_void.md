# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180006980`
- end: `0x180006a11`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `145`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001574`
- `0x180006980`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800069d7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800069d7`

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
0x180006980  mov     [rsp+arg_0], rbx
0x180006985  push    rdi
0x180006986  sub     rsp, 20h
0x18000698a  mov     rbx, rcx
0x18000698d  mov     r8d, 7FFFFFFFh
0x180006993  mov     ecx, [rcx+8]
0x180006996  jmp     short loc_1800069A7
0x180006998  lea     edx, [rcx-1]
0x18000699b  mov     eax, ecx
0x18000699d  lock cmpxchg [rbx+8], edx
0x1800069a2  jz      short loc_1800069AC
0x1800069a4  mov     ecx, [rbx+8]
0x1800069a7  cmp     ecx, r8d
0x1800069aa  jnz     short loc_180006998
0x1800069ac  lea     edi, [rcx-1]
0x1800069af  test    edi, edi
0x1800069b1  jnz     short loc_1800069EC
0x1800069b3  test    rbx, rbx
0x1800069b6  jz      short loc_180006A04
0x1800069b8  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1800069bf  mov     dword ptr [rbx+8], 0C0000001h
0x1800069c6  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800069ca  mov     [rbx], rax
0x1800069cd  cmp     [rcx+28h], dil
0x1800069d1  jz      short loc_1800069DD
0x1800069d3  mov     [rcx+28h], dil
0x1800069d7  call    cs:__imp_DeleteCriticalSection
0x1800069dd  mov     edx, 48h ; 'H'
0x1800069e2  mov     rcx, rbx; Block
0x1800069e5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800069ea  jmp     short loc_180006A04
0x1800069ec  cmp     edi, 1
0x1800069ef  jnz     short loc_180006A04
0x1800069f1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800069f8  mov     rdx, [rcx]
0x1800069fb  mov     rax, [rdx+10h]
0x1800069ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a04  mov     rbx, [rsp+28h+arg_0]
0x180006a09  mov     eax, edi
0x180006a0b  add     rsp, 20h
0x180006a0f  pop     rdi
0x180006a10  retn
```
