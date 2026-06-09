# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x1800080a0`
- end: `0x18000812d`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800080a0`
- `0x180012010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008100`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008100`
- `KERNEL32!DeleteCriticalSection` at `0x1800080f7`
- `KERNEL32!DeleteCriticalSection` at `0x1800080f7`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(char *a1)
{
  signed __int32 i; // ecx
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)a1 + 2, i - 1, i);
        i = *((_DWORD *)a1 + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    if ( a1 )
    {
      *((_DWORD *)a1 + 2) = -1073741823;
      *(_QWORD *)a1 = &ATL::CComClassFactory::`vftable';
      if ( a1[56] != (_BYTE)v3 )
      {
        a1[56] = v3;
        DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
      }
      operator delete(a1);
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
0x1800080a0  mov     [rsp+arg_0], rbx
0x1800080a5  push    rdi
0x1800080a6  sub     rsp, 20h
0x1800080aa  mov     rbx, rcx
0x1800080ad  mov     r8d, 7FFFFFFFh
0x1800080b3  mov     ecx, [rcx+8]
0x1800080b6  jmp     short loc_1800080C7
0x1800080b8  lea     edx, [rcx-1]
0x1800080bb  mov     eax, ecx
0x1800080bd  lock cmpxchg [rbx+8], edx
0x1800080c2  jz      short loc_1800080CC
0x1800080c4  mov     ecx, [rbx+8]
0x1800080c7  cmp     ecx, r8d
0x1800080ca  jnz     short loc_1800080B8
0x1800080cc  lea     edi, [rcx-1]
0x1800080cf  test    edi, edi
0x1800080d1  jnz     short loc_180008108
0x1800080d3  test    rbx, rbx
0x1800080d6  jz      short loc_180008120
0x1800080d8  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1800080df  mov     dword ptr [rbx+8], 0C0000001h
0x1800080e6  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800080ea  mov     [rbx], rax
0x1800080ed  cmp     [rcx+28h], dil
0x1800080f1  jz      short loc_1800080FD
0x1800080f3  mov     [rcx+28h], dil
0x1800080f7  call    cs:__imp_DeleteCriticalSection
0x1800080fd  mov     rcx, rbx
0x180008100  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008106  jmp     short loc_180008120
0x180008108  cmp     edi, 1
0x18000810b  jnz     short loc_180008120
0x18000810d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008114  mov     rdx, [rcx]
0x180008117  mov     rax, [rdx+10h]
0x18000811b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008120  mov     rbx, [rsp+28h+arg_0]
0x180008125  mov     eax, edi
0x180008127  add     rsp, 20h
0x18000812b  pop     rdi
0x18000812c  retn
```
